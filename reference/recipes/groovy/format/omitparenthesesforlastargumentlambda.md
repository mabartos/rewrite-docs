# Move a closure which is the last argument of a method invocation out of parentheses

**org.openrewrite.groovy.format.OmitParenthesesForLastArgumentLambda**
_Groovy allows a shorthand syntax that allows a closure to be placed outside of parentheses._

## Source

[Github](https://github.com/openrewrite/rewrite-groovy), [Issue Tracker](https://github.com/openrewrite/rewrite-groovy/issues), [Maven Central](https://search.maven.org/artifact/org.openrewrite/rewrite-groovy/7.34.0/jar)

* groupId: org.openrewrite
* artifactId: rewrite-groovy
* version: 7.34.0


## Usage

This recipe has no required configuration options and can be activated directly after taking a dependency on org.openrewrite:rewrite-groovy:7.34.0 in your build file:

{% tabs %}
{% tab title="Gradle" %}
{% code title="build.gradle" %}
```groovy
plugins {
    id("org.openrewrite.rewrite") version("5.33.0")
}

rewrite {
    activeRecipe("org.openrewrite.groovy.format.OmitParenthesesForLastArgumentLambda")
}

repositories {
    mavenCentral()
}

dependencies {
    rewrite("org.openrewrite:rewrite-groovy:7.34.0")
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
            <recipe>org.openrewrite.groovy.format.OmitParenthesesForLastArgumentLambda</recipe>
          </activeRecipes>
        </configuration>
        <dependencies>
          <dependency>
            <groupId>org.openrewrite</groupId>
            <artifactId>rewrite-groovy</artifactId>
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
  -Drewrite.recipeArtifactCoordinates=org.openrewrite:rewrite-groovy:7.34.0 \
  -DactiveRecipes=org.openrewrite.groovy.format.OmitParenthesesForLastArgumentLambda
```
{% endcode %}
{% endtab %}
{% endtabs %}

Recipes can also be activated directly from the command line by adding the argument `-Drewrite.activeRecipes=org.openrewrite.groovy.format.OmitParenthesesForLastArgumentLambda`
