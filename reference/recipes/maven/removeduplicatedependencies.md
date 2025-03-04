# Remove duplicate Maven dependencies

**org.openrewrite.maven.RemoveDuplicateDependencies**
_Removes duplicated dependencies in the `<dependencies>` and `<dependencyManagement>` sections of the `pom.xml`._

## Source

[Github](https://github.com/openrewrite/rewrite), [Issue Tracker](https://github.com/openrewrite/rewrite/issues), [Maven Central](https://search.maven.org/artifact/org.openrewrite/rewrite-maven/7.34.2/jar)

* groupId: org.openrewrite
* artifactId: rewrite-maven
* version: 7.34.2


## Usage

This recipe has no required configuration parameters and comes from a rewrite core library. It can be activated directly without adding any dependencies.

{% tabs %}
{% tab title="Gradle" %}
{% code title="build.gradle" %}
```groovy
plugins {
    id("org.openrewrite.rewrite") version("5.33.1")
}

rewrite {
    activeRecipe("org.openrewrite.maven.RemoveDuplicateDependencies")
}

repositories {
    mavenCentral()
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
        <version>4.38.1</version>
        <configuration>
          <activeRecipes>
            <recipe>org.openrewrite.maven.RemoveDuplicateDependencies</recipe>
          </activeRecipes>
        </configuration>
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
mvn org.openrewrite.maven:rewrite-maven-plugin:4.38.1:run \
  -DactiveRecipes=org.openrewrite.maven.RemoveDuplicateDependencies
```
{% endcode %}
{% endtab %}
{% endtabs %}

Recipes can also be activated directly from the command line by adding the argument `-Drewrite.activeRecipes=org.openrewrite.maven.RemoveDuplicateDependencies`
