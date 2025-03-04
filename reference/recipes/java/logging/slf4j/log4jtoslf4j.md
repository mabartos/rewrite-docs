# Migrate Log4j to SLF4J

**org.openrewrite.java.logging.slf4j.Log4jToSlf4j**
_Migrates usage of Apache Log4j to using SLF4J directly. Use of the traditional Log4j to SLF4J bridge can result in loss of performance, as the Log4j messages must be formatted before they can be passed to SLF4J. Note, this currently does not modify `log4j.properties` files._

### Tags

* slf4j
* logging
* log4j

## Source

[Github](https://github.com/openrewrite/rewrite-logging-frameworks), [Issue Tracker](https://github.com/openrewrite/rewrite-logging-frameworks/issues), [Maven Central](https://search.maven.org/artifact/org.openrewrite.recipe/rewrite-logging-frameworks/1.16.0/jar)

* groupId: org.openrewrite.recipe
* artifactId: rewrite-logging-frameworks
* version: 1.16.0


## Usage

This recipe has no required configuration options and can be activated directly after taking a dependency on org.openrewrite.recipe:rewrite-logging-frameworks:1.16.0 in your build file:

{% tabs %}
{% tab title="Gradle" %}
{% code title="build.gradle" %}
```groovy
plugins {
    id("org.openrewrite.rewrite") version("5.33.0")
}

rewrite {
    activeRecipe("org.openrewrite.java.logging.slf4j.Log4jToSlf4j")
}

repositories {
    mavenCentral()
}

dependencies {
    rewrite("org.openrewrite.recipe:rewrite-logging-frameworks:1.16.0")
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
            <recipe>org.openrewrite.java.logging.slf4j.Log4jToSlf4j</recipe>
          </activeRecipes>
        </configuration>
        <dependencies>
          <dependency>
            <groupId>org.openrewrite.recipe</groupId>
            <artifactId>rewrite-logging-frameworks</artifactId>
            <version>1.16.0</version>
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
  -Drewrite.recipeArtifactCoordinates=org.openrewrite.recipe:rewrite-logging-frameworks:1.16.0 \
  -DactiveRecipes=org.openrewrite.java.logging.slf4j.Log4jToSlf4j
```
{% endcode %}
{% endtab %}
{% endtabs %}

Recipes can also be activated directly from the command line by adding the argument `-Drewrite.activeRecipes=org.openrewrite.java.logging.slf4j.Log4jToSlf4j`

## Definition

{% tabs %}
{% tab title="Recipe List" %}
* [Migrate Log4j 1.x to SLF4J 1.x](../../../java/logging/slf4j/log4j1toslf4j1.md)
* [Loggers should be named for their enclosing classes](../../../java/logging/slf4j/loggersnamedforenclosingclass.md)
* [Remove Maven dependency](../../../maven/removedependency.md)
  * groupId: `org.apache.logging.log4j`
  * artifactId: `log4j-to-slf4j`
* [Upgrade Maven dependency version](../../../maven/upgradedependencyversion.md)
  * groupId: `org.apache.logging.log4j`
  * artifactId: `log4j-api`
  * newVersion: `latest.release`
  * overrideManagedVersion: `true`
  * retainVersions: `[]`
* [Upgrade Maven dependency version](../../../maven/upgradedependencyversion.md)
  * groupId: `org.apache.logging.log4j`
  * artifactId: `log4j-core`
  * newVersion: `latest.release`
  * overrideManagedVersion: `true`
  * retainVersions: `[]`
* [Add Maven dependency](../../../maven/adddependency.md)
  * groupId: `org.slf4j`
  * artifactId: `slf4j-api`
  * version: `latest.release`
  * onlyIfUsing: `org.apache.logging.log4j.*`
* [Add Maven dependency](../../../maven/adddependency.md)
  * groupId: `org.apache.logging.log4j`
  * artifactId: `log4j-slf4j-impl`
  * version: `latest.release`
  * onlyIfUsing: `org.apache.logging.log4j.*`
* [Add Maven dependency](../../../maven/adddependency.md)
  * groupId: `org.slf4j`
  * artifactId: `slf4j-api`
  * version: `latest.release`
  * onlyIfUsing: `org.apache.log4j.*`
* [Add Maven dependency](../../../maven/adddependency.md)
  * groupId: `org.apache.logging.log4j`
  * artifactId: `log4j-slf4j-impl`
  * version: `latest.release`
  * onlyIfUsing: `org.apache.log4j.*`

{% endtab %}

{% tab title="Yaml Recipe List" %}
```yaml
---
type: specs.openrewrite.org/v1beta/recipe
name: org.openrewrite.java.logging.slf4j.Log4jToSlf4j
displayName: Migrate Log4j to SLF4J
description: Migrates usage of Apache Log4j to using SLF4J directly. Use of the traditional Log4j to SLF4J bridge can result in loss of performance, as the Log4j messages must be formatted before they can be passed to SLF4J. Note, this currently does not modify `log4j.properties` files.
tags:
  - slf4j
  - logging
  - log4j
recipeList:
  - org.openrewrite.java.logging.slf4j.Log4j1ToSlf4j1
  - org.openrewrite.java.logging.slf4j.LoggersNamedForEnclosingClass
  - org.openrewrite.maven.RemoveDependency:
      groupId: org.apache.logging.log4j
      artifactId: log4j-to-slf4j
  - org.openrewrite.maven.UpgradeDependencyVersion:
      groupId: org.apache.logging.log4j
      artifactId: log4j-api
      newVersion: latest.release
      overrideManagedVersion: true
      retainVersions: []
  - org.openrewrite.maven.UpgradeDependencyVersion:
      groupId: org.apache.logging.log4j
      artifactId: log4j-core
      newVersion: latest.release
      overrideManagedVersion: true
      retainVersions: []
  - org.openrewrite.maven.AddDependency:
      groupId: org.slf4j
      artifactId: slf4j-api
      version: latest.release
      onlyIfUsing: org.apache.logging.log4j.*
  - org.openrewrite.maven.AddDependency:
      groupId: org.apache.logging.log4j
      artifactId: log4j-slf4j-impl
      version: latest.release
      onlyIfUsing: org.apache.logging.log4j.*
  - org.openrewrite.maven.AddDependency:
      groupId: org.slf4j
      artifactId: slf4j-api
      version: latest.release
      onlyIfUsing: org.apache.log4j.*
  - org.openrewrite.maven.AddDependency:
      groupId: org.apache.logging.log4j
      artifactId: log4j-slf4j-impl
      version: latest.release
      onlyIfUsing: org.apache.log4j.*

```
{% endtab %}
{% endtabs %}
