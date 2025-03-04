# Find files in a source set

**org.openrewrite.java.search.HasSourceSet**
_Source sets are a way to organize your source code into logical groups. For example, Java projects commonly have a `main` source set for application code and a `test` source set for test code. This recipe will find all files in a given source set._

## Source

[Github](https://github.com/openrewrite/rewrite), [Issue Tracker](https://github.com/openrewrite/rewrite/issues), [Maven Central](https://search.maven.org/artifact/org.openrewrite/rewrite-java/7.35.0-SNAPSHOT/jar)

* groupId: org.openrewrite
* artifactId: rewrite-java
* version: 7.35.0-SNAPSHOT

## Options

| Type | Name | Description |
| -- | -- | -- |
| `String` | sourceSet | The source set to search for. |


## Usage

This recipe has required configuration parameters. Recipes with required configuration parameters cannot be activated directly. To activate this recipe you must create a new recipe which fills in the required parameters. In your rewrite.yml create a new recipe with a unique name. For example: `com.yourorg.HasSourceSetExample`.
Here's how you can define and customize such a recipe within your rewrite.yml:

{% code title="rewrite.yml" %}
```yaml
---
type: specs.openrewrite.org/v1beta/recipe
name: com.yourorg.HasSourceSetExample
displayName: Find files in a source set example
recipeList:
  - org.openrewrite.java.search.HasSourceSet:
      sourceSet: main
```
{% endcode %}


Now that `com.yourorg.HasSourceSetExample` has been defined activate it in your build file:

{% tabs %}
{% tab title="Gradle" %}
{% code title="build.gradle" %}
```groovy
plugins {
    id("org.openrewrite.rewrite") version("5.33.2")
}

rewrite {
    activeRecipe("com.yourorg.HasSourceSetExample")
}

repositories {
    mavenCentral()
}

```
{% endcode %}
{% endtab %}

{% tab title="Maven" %}
{% code title="pom.xml" %}
```markup
<project>
  <build>
    <plugins>
      <plugin>
        <groupId>org.openrewrite.maven</groupId>
        <artifactId>rewrite-maven-plugin</artifactId>
        <version>4.38.2</version>
        <configuration>
          <activeRecipes>
            <recipe>com.yourorg.HasSourceSetExample</recipe>
          </activeRecipes>
        </configuration>
      </plugin>
    </plugins>
  </build>
</project>
```
{% endcode %}
{% endtab %}
{% endtabs %}

Recipes can also be activated directly from the commandline by adding the argument `-Drewrite.activeRecipes=com.yourorg.HasSourceSetExample`
