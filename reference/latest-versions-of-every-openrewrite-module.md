# Latest versions of every OpenRewrite module

OpenRewrite's modules are published to [Maven Central](https://search.maven.org/search?q=org.openrewrite). Each time a release is made, a bill of materials artifact is also published to correctly align and manage the versions of all published artifacts. The Gradle plugin is published to the [Gradle Plugin Portal](https://plugins.gradle.org/plugin/org.openrewrite.rewrite).

It is highly recommended that developers use the rewrite-recipe-bom to align the versions of Rewrite's modules to ensure compatibility. The use of the "bill of materials" means that a developer will only need to specify explicit versions of the BOM and the build plugins:\\

| Module                                            | Version    |
| ------------------------------------------------- |------------|
| **org.openrewrite:rewrite-recipe-bom**            | **1.12.3** |
| **org.openrewrite:rewrite-maven-plugin**          | **4.38.0** |
| **org.openrewrite:rewrite-gradle-plugin**         | **5.33.0** |
| org.openrewrite:rewrite-core                      | 7.33.0     |
| org.openrewrite:rewrite-groovy                    | 7.33.0     |
| org.openrewrite:rewrite-gradle                    | 7.33.0     |
| org.openrewrite:rewrite-hcl                       | 7.33.0     |
| org.openrewrite:rewrite-java                      | 7.33.0     |
| org.openrewrite:rewrite-java-8                    | 7.33.0     |
| org.openrewrite:rewrite-java-11                   | 7.33.0     |
| org.openrewrite:rewrite-java-17                   | 7.33.0     |
| org.openrewrite:rewrite-json                      | 7.33.0     |
| org.openrewrite:rewrite-maven                     | 7.33.0     |
| org.openrewrite:rewrite-properties                | 7.33.0     |
| org.openrewrite:rewrite-protobuf                  | 7.33.0     |
| org.openrewrite:rewrite-xml                       | 7.33.0     |
| org.openrewrite:rewrite-yaml                      | 7.33.0     |
| org.openrewrite:rewrite-test                      | 7.33.0     |
| org.openrewrite.recipe:rewrite-circleci           | 1.15.0     |
| org.openrewrite.recipe:rewrite-concourse          | 1.14.0     |
| org.openrewrite.recipe:rewrite-github-actions     | 1.14.0     |
| org.openrewrite.recipe:rewrite-java-security      | 1.19.0     |
| org.openrewrite.recipe:rewrite-jhipster           | 1.14.0     |
| org.openrewrite.recipe:rewrite-kubernetes         | 1.25.0     |
| org.openrewrite.recipe:rewrite-logging-frameworks | 1.15.0     |
| org.openrewrite.recipe:rewrite-micronaut          | 1.19.0     |
| org.openrewrite.recipe.rewrite-migrate-java       | 1.14.1     |
| org.openrewrite.recipe:rewrite-quarkus            | 1.14.0     |
| org.openrewrite.recipe:rewrite-spring             | 4.30.0     |
| org.openrewrite.recipe:rewrite-terraform          | 1.14.0     |
| org.openrewrite.recipe:rewrite-testing-frameworks | 1.31.0     |

