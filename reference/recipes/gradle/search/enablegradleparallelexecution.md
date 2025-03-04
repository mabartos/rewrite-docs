# Enable Gradle parallel execution

**org.openrewrite.gradle.search.EnableGradleParallelExecution**
_Most builds consist of more than one project and some of those projects are usually independent of one another. Yet Gradle will only run one task at a time by default, regardless of the project structure. By using the `--parallel` switch, you can force Gradle to execute tasks in parallel as long as those tasks are in different projects. See the [Gradle performance documentation](https://docs.gradle.org/current/userguide/performance.html#parallel_execution) for more._

## Source

[Github](https://github.com/openrewrite/rewrite-gradle), [Issue Tracker](https://github.com/openrewrite/rewrite-gradle/issues), [Maven Central](https://search.maven.org/artifact/org.openrewrite/rewrite-gradle/7.34.0/jar)

* groupId: org.openrewrite
* artifactId: rewrite-gradle
* version: 7.34.0


## Usage

This recipe has no required configuration options and can be activated directly after taking a dependency on org.openrewrite:rewrite-gradle:7.34.0 in your build file:

{% tabs %}
{% tab title="Gradle" %}
{% code title="build.gradle" %}
```groovy
plugins {
    id("org.openrewrite.rewrite") version("5.33.0")
}

rewrite {
    activeRecipe("org.openrewrite.gradle.search.EnableGradleParallelExecution")
}

repositories {
    mavenCentral()
}

dependencies {
    rewrite("org.openrewrite:rewrite-gradle:7.34.0")
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
            <recipe>org.openrewrite.gradle.search.EnableGradleParallelExecution</recipe>
          </activeRecipes>
        </configuration>
        <dependencies>
          <dependency>
            <groupId>org.openrewrite</groupId>
            <artifactId>rewrite-gradle</artifactId>
            <version>7.34.0</version>
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
  -Drewrite.recipeArtifactCoordinates=org.openrewrite:rewrite-gradle:7.34.0 \
  -DactiveRecipes=org.openrewrite.gradle.search.EnableGradleParallelExecution
```
{% endcode %}
{% endtab %}
{% endtabs %}

Recipes can also be activated directly from the command line by adding the argument `-Drewrite.activeRecipes=org.openrewrite.gradle.search.EnableGradleParallelExecution`

## Definition

{% tabs %}
{% tab title="Recipe List" %}
* [Add Gradle property](../../gradle/addproperty.md)
  * key: `org.gradle.parallel`
  * value: `true`

{% endtab %}

{% tab title="Yaml Recipe List" %}
```yaml
---
type: specs.openrewrite.org/v1beta/recipe
name: org.openrewrite.gradle.search.EnableGradleParallelExecution
displayName: Enable Gradle parallel execution
description: Most builds consist of more than one project and some of those projects are usually independent of one another. Yet Gradle will only run one task at a time by default, regardless of the project structure. By using the `--parallel` switch, you can force Gradle to execute tasks in parallel as long as those tasks are in different projects. See the [Gradle performance documentation](https://docs.gradle.org/current/userguide/performance.html#parallel_execution) for more.
recipeList:
  - org.openrewrite.gradle.AddProperty:
      key: org.gradle.parallel
      value: true

```
{% endtab %}
{% endtabs %}
