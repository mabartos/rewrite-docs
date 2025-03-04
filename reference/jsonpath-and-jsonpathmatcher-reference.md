---
description: A tool and syntax for selecting elements within JSON-like structures
---

# JsonPath and JsonPathMatcher Reference

{% hint style="info" %}
Despite the name, `JsonPathMatcher` and `JsonPath` expressions may be used in other markup languages besides JSON which support it, such as YAML. When we refer to "JSON" keep in mind JsonPathMatcher and JsonPath expressions apply to markup languages which have a JsonPathMatcher implementation, such as YAML.
{% endhint %}

`JsonPathMatcher` provides methods for matching the given cursor location using a provided `JsonPath` expression. "JsonPath" (sometimes stylized as JSONPath) is a query language for JSON, similar to how XPath is a query language for XML. Despite the name, JsonPathMatcher can be used on other languages besides JSON, such as YAML.

JsonPathMatcher and JsonPath expressions go hand-in-hand. A JsonPath expression specifies a path to an element in the JSON or YAML structure. A JsonPathMatcher provides methods which visitors can use to make decisions about whether an LST element is a desired target.

## JsonPath Expression Notation

A JsonPath expression specifies a path to an element, or set of elements, in a JSON-like structure.

{% hint style="warning" %}
The JsonPath expression syntax OpenRewrite provides is a subset implementation of the JsonPath syntax.
{% endhint %}

### Syntax Components

Paths can use dot notation, or bracket notation. For example, these two JsonPath expressions are equivalent:

```text
$.spec.containers[0].image
$['spec']['containers'][0]['image']
```

Additional syntax subcomponents of a JsonPath expression are shown below:

| Expression | Description |
| :--- | :--- |
| `$` | The root object of the document. |
| `.property` | Selects a specific property name. |
| `['property']` | Selects a specific property name. Use this notation if the property name contains special characters such as spaces, or begins with a character other than `A..Za..z_`. |
| `[n]` | Selects the n-th element from an array. Indexes are 0-based. |
| `[:n]` | Selects the first n elements of the array. Returns a list. |
| `..property` | Recursive descent. This searches for the specified property name recursively and returns an array of all values with this property name. Always returns a list, even if just one property is found. |
| `*` | Wildcard selects all elements in an object or an array, regardless of their names or indexes. For example, `address.*` means all properties of the `address` object, and `book[*]` means all items of the `book` array. |
| `[(expression)]` | Script expressions can be used instead of explicit property names or indexes. |
| `@` | Used in filter expressions to refer to the current node being processed. |

### Filter Expressions

Filters are logical expressions used to filter arrays. An example of a JsonPath expression with a filter is:

```text
$.subjects[?(@.kind == 'ServiceAccount')].kind
```

where `[?(@.kind == 'ServiceAccount')]` is the actual filter expression, and `@` represents the current item being processed.

The supported operators of a filter expression are shown below:

| Operator | Description |
| :--- | :--- |
| `==` | Equals to. String values should be enclosed in single quotes. For example, `[?(@.kind == 'Deployment')]`. |
| `=~` | Matches a [JavaScript regular expression](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Regular_Expressions). For example, `[?(@.uses =~ 'actions/setup-java@v2.*')]` matches items which `uses` starts with `actions/setup-java@v2`, and so would include `actions/setup-java@v2.1.0`. |

## Configuring Recipes using JsonPath Expressions

Recipes which take JsonPath expressions as arguments take them as strings. In yaml that looks like this:

```yaml
---
type: specs.openrewrite.org/v1beta/recipe
name: com.yourorg.ChangeValueExample
displayName: ChangeValueExample
recipeList:
  - org.openrewrite.yaml.ChangeValue:
      oldKeyPath: $.subjects[?(@.kind == 'ServiceAccount')].kind
      value: Deployment
```

Constructing a similarly configured instance of the same recipe in Java:

```java
ChangeValue v = new ChangeValue("$.subjects[?(@.kind == 'ServiceAccount')].kind", "Deployment", null);
```

Which, for example, would change the following YAML document:

{% tabs %}
{% tab title="Before" %}
{% code title="example.yml" %}
```yml
---
subjects:
  - kind: User
    name: some-user
  - kind: ServiceAccount
    name: monitoring-tools
```
{% endcode %}
{% endtab %}

{% tab title="After" %}
{% code title="example.yml" %}
```yml
---
subjects:
  - kind: User
    name: some-user
  - kind: Deployment
    name: monitoring-tools
```
{% endcode %}
{% endtab %}
{% endtabs %}

## Authoring Recipes with JsonPathMatcher

`org.openrewrite.json.JsonPathMatcher` (or `org.openrewrite.yaml.JsonPathMatcher`) are the classes that most recipes will use JsonPath expression patterns with. Instances are created by providing the JsonPath expression pattern to the JsonPathMatcher constructor:

```java
JsonPathMatcher matcher = new JsonPathMatcher("$.spec.containers[?(@.name == 'app')].image");
```

Once you have constructed your JsonPathMatcher with a JsonPath expression as the "evaluation target", you can use the JsonPathMatcher to determine whether a given `Cursor` at a point within the tree matches what you're looking for.

`JsonPathMatcher.matches(Cursor c)` returns `true` if the provided `Cursor` is a location within the document tree which _exactly_ matches the provided JsonPath expression. `JsonPathMatcher.encloses(Cursor c)` returns `true` if the provided `Cursor` is a location within the document tree which is _within the path_ of the provided JsonPath expression.

```java
class ActionsSetupJavaAdoptOpenJDKToTemurinVisitor extends YamlIsoVisitor<ExecutionContext> {
    private static final JsonPathMatcher distribution = new JsonPathMatcher("..steps[?(@.uses =~ 'actions/setup-java@v2.*')].with.distribution");

    @Override
    public Yaml.Mapping.Entry visitMappingEntry(Yaml.Mapping.Entry entry, ExecutionContext ctx) {
        if (distribution.encloses(getCursor()) && ((Yaml.Scalar) entry.getValue()).getValue().contains("adopt")) {
            return super.visitMappingEntry(entry.withValue(((Yaml.Scalar) entry.getValue()).withValue("temurin")), ctx);
        }
        return super.visitMappingEntry(entry, ctx);
    }
}
```
