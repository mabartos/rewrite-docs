# Migrate deprecated `javax.security.enterprise` packages to `jakarta.security.enterprise`

**org.openrewrite.java.migrate.jakarta.JavaxSecurityToJakartaSecurity**
_Java EE has been rebranded to Jakarta EE, necessitating a package relocation._

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
    activeRecipe("org.openrewrite.java.migrate.jakarta.JavaxSecurityToJakartaSecurity")
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
            <recipe>org.openrewrite.java.migrate.jakarta.JavaxSecurityToJakartaSecurity</recipe>
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
  -DactiveRecipes=org.openrewrite.java.migrate.jakarta.JavaxSecurityToJakartaSecurity
```
{% endcode %}
{% endtab %}
{% endtabs %}

Recipes can also be activated directly from the command line by adding the argument `-Drewrite.activeRecipes=org.openrewrite.java.migrate.jakarta.JavaxSecurityToJakartaSecurity`

## Definition

{% tabs %}
{% tab title="Recipe List" %}
* [Add Maven dependency](../../../maven/adddependency.md)
  * groupId: `jakarta.security.enterprise`
  * artifactId: `jakarta.security.enterprise-api`
  * version: `2.x`
  * onlyIfUsing: `javax.security.enterprise.+`
* [Upgrade Maven dependency version](../../../maven/upgradedependencyversion.md)
  * groupId: `jakarta.security.enterprise`
  * artifactId: `jakarta.security.enterprise-api`
  * newVersion: `2.x`
  * retainVersions: `[]`
* [Rename package name](../../../java/changepackage.md)
  * oldPackageName: `javax.security.enterprise`
  * newPackageName: `jakarta.security.enterprise`
  * recursive: `true`
* [Remove Maven dependency](../../../maven/removedependency.md)
  * groupId: `javax.security.enterprise`
  * artifactId: `javax.security.enterprise-api`

{% endtab %}

{% tab title="Yaml Recipe List" %}
```yaml
---
type: specs.openrewrite.org/v1beta/recipe
name: org.openrewrite.java.migrate.jakarta.JavaxSecurityToJakartaSecurity
displayName: Migrate deprecated `javax.security` packages to `jakarta.security`
description: Java EE has been rebranded to Jakarta EE, necessitating a package relocation.
recipeList:
  - org.openrewrite.maven.AddDependency:
      groupId: jakarta.security.enterprise
      artifactId: jakarta.security.enterprise-api
      version: 2.x
      onlyIfUsing: javax.security.enterprise.+
  - org.openrewrite.maven.UpgradeDependencyVersion:
      groupId: jakarta.security.enterprise
      artifactId: jakarta.security.enterprise-api
      newVersion: 2.x
      retainVersions: []
  - org.openrewrite.java.ChangePackage:
      oldPackageName: javax.security.enterprise
      newPackageName: jakarta.security.enterprise
      recursive: true
  - org.openrewrite.maven.RemoveDependency:
      groupId: javax.security.enterprise
      artifactId: javax.security.enterprise-api

```
{% endtab %}
{% endtabs %}
