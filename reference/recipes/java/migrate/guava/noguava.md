# Prefer the Java standard library instead of Guava

**org.openrewrite.java.migrate.guava.NoGuava**
_Guava filled in important gaps in the Java standard library and still does. But at least some of Guava's API surface area is covered by the Java standard library now, and some projects may be able to remove Guava altogether if they migrate to standard library for these functions.
_

### Tags

* guava

## Source

[Github](https://github.com/openrewrite/rewrite-migrate-java), [Issue Tracker](https://github.com/openrewrite/rewrite-migrate-java/issues), [Maven Central](https://search.maven.org/artifact/org.openrewrite.recipe/rewrite-migrate-java/1.15.0/jar)

* groupId: org.openrewrite.recipe
* artifactId: rewrite-migrate-java
* version: 1.15.0


## Usage

This recipe has no required configuration options and can be activated directly after taking a dependency on org.openrewrite.recipe:rewrite-migrate-java:1.15.0 in your build file:

{% tabs %}
{% tab title="Gradle" %}
{% code title="build.gradle" %}
```groovy
plugins {
    id("org.openrewrite.rewrite") version("5.33.0")
}

rewrite {
    activeRecipe("org.openrewrite.java.migrate.guava.NoGuava")
}

repositories {
    mavenCentral()
}

dependencies {
    rewrite("org.openrewrite.recipe:rewrite-migrate-java:1.15.0")
}
```
{% endcode %}
{% endtab %}

{% tab title="Maven POM" %}
{% code title="pom.xml" %}
```markup
<project>
  <build>
    <plugins>
      <plugin>
        <groupId>org.openrewrite.maven</groupId>
        <artifactId>rewrite-maven-plugin</artifactId>
        <version>4.38.0</version>
        <configuration>
          <activeRecipes>
            <recipe>org.openrewrite.java.migrate.guava.NoGuava</recipe>
          </activeRecipes>
        </configuration>
        <dependencies>
          <dependency>
            <groupId>org.openrewrite.recipe</groupId>
            <artifactId>rewrite-migrate-java</artifactId>
            <version>1.15.0</version>
          </dependency>
        </dependencies>
      </plugin>
    </plugins>
  </build>
</project>
```
{% endcode %}
{% endtab %}

{% tab title="Maven Command Line" %}
{% code title="shell" %}
```shell
mvn org.openrewrite.maven:rewrite-maven-plugin:4.38.0:run \
  -Drewrite.recipeArtifactCoordinates=org.openrewrite.recipe:rewrite-migrate-java:1.15.0 \
  -DactiveRecipes=org.openrewrite.java.migrate.guava.NoGuava
```
{% endcode %}
{% endtab %}
{% endtabs %}

Recipes can also be activated directly from the command line by adding the argument `-Drewrite.activeRecipes=org.openrewrite.java.migrate.guava.NoGuava`

## Definition

{% tabs %}
{% tab title="Recipe List" %}
* [Prefer `Files#createTempDirectory()`](../../../java/migrate/guava/noguavacreatetempdir.md)
* [Prefer `Runnable::run`](../../../java/migrate/guava/noguavadirectexecutor.md)
* [Prefer `new ArrayList<>()`](../../../java/migrate/guava/noguavalistsnewarraylist.md)
* [Prefer `new CopyOnWriteArrayList<>()`](../../../java/migrate/guava/noguavalistsnewcopyonwritearraylist.md)
* [Prefer `new LinkedList<>()`](../../../java/migrate/guava/noguavalistsnewlinkedlist.md)
* [Prefer `new HashSet<>()`](../../../java/migrate/guava/noguavasetsnewhashset.md)
* [Prefer `new ConcurrentHashMap<>()`](../../../java/migrate/guava/noguavasetsnewconcurrenthashset.md)
* [Prefer `new LinkedHashSet<>()`](../../../java/migrate/guava/noguavasetsnewlinkedhashset.md)
* [Prefer `java.util.function.Function`](../../../java/migrate/guava/preferjavautilfunction.md)
* [Prefer `java.util.function.Predicate`](../../../java/migrate/guava/preferjavautilpredicate.md)
* [Prefer `java.util.function.Supplier`](../../../java/migrate/guava/preferjavautilsupplier.md)
* [Prefer `java.util.Objects#equals`](../../../java/migrate/guava/preferjavautilobjectsequals.md)
* [Prefer `java.util.Objects#hash`](../../../java/migrate/guava/preferjavautilobjectshashcode.md)
* [Prefer `java.util.Collections#unmodifiableNavigableMap`](../../../java/migrate/guava/preferjavautilcollectionsunmodifiablenavigablemap.md)
* [Prefer `java.util.Collections#synchronizedNavigableMap`](../../../java/migrate/guava/preferjavautilcollectionssynchronizednavigablemap.md)
* [Prefer `java.lang.Char#compare`](../../../java/migrate/guava/prefercharcompare.md)
* [Prefer `Integer#compare`](../../../java/migrate/guava/preferintegercompare.md)
* [Prefer `Long#compare`](../../../java/migrate/guava/preferlongcompare.md)
* [Prefer `Short#compare`](../../../java/migrate/guava/prefershortcompare.md)
* [Prefer `Integer#compareUnsigned`](../../../java/migrate/guava/preferintegercompareunsigned.md)
* [Prefer `Integer#divideUnsigned`](../../../java/migrate/guava/preferintegerdivideunsigned.md)
* [Prefer `Integer#parseUnsignedInt`](../../../java/migrate/guava/preferintegerparseunsignedint.md)
* [Prefer `Long#compareUnsigned`](../../../java/migrate/guava/preferlongcompareunsigned.md)
* [Prefer `Long#divideUnsigned`](../../../java/migrate/guava/preferlongdivideunsigned.md)
* [Prefer `Long#parseUnsignedInt`](../../../java/migrate/guava/preferlongparseunsignedlong.md)
* [Prefer `Long#remainderUnsigned`](../../../java/migrate/guava/preferlongremainderunsigned.md)
* [Prefer `Math#addExact`](../../../java/migrate/guava/prefermathaddexact.md)
* [Prefer `Math#subtractExact`](../../../java/migrate/guava/prefermathsubtractexact.md)
* [Prefer `Math#multiplyExact`](../../../java/migrate/guava/prefermathmultiplyexact.md)
* [Prefer `new AtomicReference<>()`](../../../java/migrate/guava/noguavaatomicsnewreference.md)
* [Prefer `List.of(..)` in Java 9 or higher](../../../java/migrate/guava/noguavaimmutablelistof.md)
* [Prefer `Map.of(..)` in Java 9 or higher](../../../java/migrate/guava/noguavaimmutablemapof.md)
* [Prefer `Set.of(..)` in Java 9 or higher](../../../java/migrate/guava/noguavaimmutablesetof.md)

{% endtab %}

{% tab title="Yaml Recipe List" %}
```yaml
---
type: specs.openrewrite.org/v1beta/recipe
name: org.openrewrite.java.migrate.guava.NoGuava
displayName: Prefer the Java standard library instead of Guava
description: Guava filled in important gaps in the Java standard library and still does. But at least some of Guava's API surface area is covered by the Java standard library now, and some projects may be able to remove Guava altogether if they migrate to standard library for these functions.

tags:
  - guava
recipeList:
  - org.openrewrite.java.migrate.guava.NoGuavaCreateTempDir
  - org.openrewrite.java.migrate.guava.NoGuavaDirectExecutor
  - org.openrewrite.java.migrate.guava.NoGuavaListsNewArrayList
  - org.openrewrite.java.migrate.guava.NoGuavaListsNewCopyOnWriteArrayList
  - org.openrewrite.java.migrate.guava.NoGuavaListsNewLinkedList
  - org.openrewrite.java.migrate.guava.NoGuavaSetsNewHashSet
  - org.openrewrite.java.migrate.guava.NoGuavaSetsNewConcurrentHashSet
  - org.openrewrite.java.migrate.guava.NoGuavaSetsNewLinkedHashSet
  - org.openrewrite.java.migrate.guava.PreferJavaUtilFunction
  - org.openrewrite.java.migrate.guava.PreferJavaUtilPredicate
  - org.openrewrite.java.migrate.guava.PreferJavaUtilSupplier
  - org.openrewrite.java.migrate.guava.PreferJavaUtilObjectsEquals
  - org.openrewrite.java.migrate.guava.PreferJavaUtilObjectsHashCode
  - org.openrewrite.java.migrate.guava.PreferJavaUtilCollectionsUnmodifiableNavigableMap
  - org.openrewrite.java.migrate.guava.PreferJavaUtilCollectionsSynchronizedNavigableMap
  - org.openrewrite.java.migrate.guava.PreferCharCompare
  - org.openrewrite.java.migrate.guava.PreferIntegerCompare
  - org.openrewrite.java.migrate.guava.PreferLongCompare
  - org.openrewrite.java.migrate.guava.PreferShortCompare
  - org.openrewrite.java.migrate.guava.PreferIntegerCompareUnsigned
  - org.openrewrite.java.migrate.guava.PreferIntegerDivideUnsigned
  - org.openrewrite.java.migrate.guava.PreferIntegerParseUnsignedInt
  - org.openrewrite.java.migrate.guava.PreferLongCompareUnsigned
  - org.openrewrite.java.migrate.guava.PreferLongDivideUnsigned
  - org.openrewrite.java.migrate.guava.PreferLongParseUnsignedLong
  - org.openrewrite.java.migrate.guava.PreferLongRemainderUnsigned
  - org.openrewrite.java.migrate.guava.PreferMathAddExact
  - org.openrewrite.java.migrate.guava.PreferMathSubtractExact
  - org.openrewrite.java.migrate.guava.PreferMathMultiplyExact
  - org.openrewrite.java.migrate.guava.NoGuavaAtomicsNewReference
  - org.openrewrite.java.migrate.guava.NoGuavaImmutableListOf
  - org.openrewrite.java.migrate.guava.NoGuavaImmutableMapOf
  - org.openrewrite.java.migrate.guava.NoGuavaImmutableSetOf

```
{% endtab %}
{% endtabs %}
