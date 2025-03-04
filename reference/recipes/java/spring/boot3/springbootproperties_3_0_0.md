# Migrate Spring Boot properties to 3.0

**org.openrewrite.java.spring.boot3.SpringBootProperties\_3\_0\_0**
_Migrate properties found in `application.properties` and `application.yml`._

### Tags

* spring
* spring-boot
* spring-boot-3-0

## Source

[Github](https://github.com/openrewrite/rewrite-spring), [Issue Tracker](https://github.com/openrewrite/rewrite-spring/issues), [Maven Central](https://search.maven.org/artifact/org.openrewrite.recipe/rewrite-spring/4.31.0/jar)

* groupId: org.openrewrite.recipe
* artifactId: rewrite-spring
* version: 4.31.0


## Usage

This recipe has no required configuration options and can be activated directly after taking a dependency on org.openrewrite.recipe:rewrite-spring:4.31.0 in your build file:

{% tabs %}
{% tab title="Gradle" %}
{% code title="build.gradle" %}
```groovy
plugins {
    id("org.openrewrite.rewrite") version("5.33.0")
}

rewrite {
    activeRecipe("org.openrewrite.java.spring.boot3.SpringBootProperties_3_0_0")
}

repositories {
    mavenCentral()
}

dependencies {
    rewrite("org.openrewrite.recipe:rewrite-spring:4.31.0")
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
            <recipe>org.openrewrite.java.spring.boot3.SpringBootProperties_3_0_0</recipe>
          </activeRecipes>
        </configuration>
        <dependencies>
          <dependency>
            <groupId>org.openrewrite.recipe</groupId>
            <artifactId>rewrite-spring</artifactId>
            <version>4.31.0</version>
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
  -Drewrite.recipeArtifactCoordinates=org.openrewrite.recipe:rewrite-spring:4.31.0 \
  -DactiveRecipes=org.openrewrite.java.spring.boot3.SpringBootProperties_3_0_0
```
{% endcode %}
{% endtab %}
{% endtabs %}

Recipes can also be activated directly from the command line by adding the argument `-Drewrite.activeRecipes=org.openrewrite.java.spring.boot3.SpringBootProperties_3_0_0`

## Definition

{% tabs %}
{% tab title="Recipe List" %}
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `spring.data.cassandra.compression`
  * newPropertyKey: `spring.cassandra.compression`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `spring.data.cassandra.config`
  * newPropertyKey: `spring.cassandra.config`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `spring.data.cassandra.connection.connect-timeout`
  * newPropertyKey: `spring.cassandra.connection.connect-timeout`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `spring.data.cassandra.connection.init-query-timeout`
  * newPropertyKey: `spring.cassandra.connection.init-query-timeout`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `spring.data.cassandra.contact-points`
  * newPropertyKey: `spring.cassandra.contact-points`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `spring.data.cassandra.controlconnection.timeout`
  * newPropertyKey: `spring.cassandra.controlconnection.timeout`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `spring.data.cassandra.keyspace-name`
  * newPropertyKey: `spring.cassandra.keyspace-name`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `spring.data.cassandra.local-datacenter`
  * newPropertyKey: `spring.cassandra.local-datacenter`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `spring.data.cassandra.password`
  * newPropertyKey: `spring.cassandra.password`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `spring.data.cassandra.pool.heartbeat-interval`
  * newPropertyKey: `spring.cassandra.pool.heartbeat-interval`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `spring.data.cassandra.pool.idle-timeout`
  * newPropertyKey: `spring.cassandra.pool.idle-timeout`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `spring.data.cassandra.port`
  * newPropertyKey: `spring.cassandra.port`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `spring.data.cassandra.request.consistency`
  * newPropertyKey: `spring.cassandra.request.consistency`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `spring.data.cassandra.request.page-size`
  * newPropertyKey: `spring.cassandra.request.page-size`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `spring.data.cassandra.request.serial-consistency`
  * newPropertyKey: `spring.cassandra.request.serial-consistency`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `spring.data.cassandra.request.throttler.drain-interval`
  * newPropertyKey: `spring.cassandra.request.throttler.drain-interval`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `spring.data.cassandra.request.throttler.max-concurrent-requests`
  * newPropertyKey: `spring.cassandra.request.throttler.max-concurrent-requests`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `spring.data.cassandra.request.throttler.max-queue-size`
  * newPropertyKey: `spring.cassandra.request.throttler.max-queue-size`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `spring.data.cassandra.request.throttler.max-requests-per-second`
  * newPropertyKey: `spring.cassandra.request.throttler.max-requests-per-second`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `spring.data.cassandra.request.throttler.type`
  * newPropertyKey: `spring.cassandra.request.throttler.type`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `spring.data.cassandra.request.timeout`
  * newPropertyKey: `spring.cassandra.request.timeout`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `spring.data.cassandra.schema-action`
  * newPropertyKey: `spring.cassandra.schema-action`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `spring.data.cassandra.session-name`
  * newPropertyKey: `spring.cassandra.session-name`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `spring.data.cassandra.ssl`
  * newPropertyKey: `spring.cassandra.ssl`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `spring.data.cassandra.username`
  * newPropertyKey: `spring.cassandra.username`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `spring.flyway.ignore-future-migrations`
  * newPropertyKey: `spring.flyway.ignore-migration-patterns`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `spring.flyway.ignore-ignored-migrations`
  * newPropertyKey: `spring.flyway.ignore-migration-patterns`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `spring.flyway.ignore-missing-migrations`
  * newPropertyKey: `spring.flyway.ignore-migration-patterns`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `spring.flyway.ignore-pending-migrations`
  * newPropertyKey: `spring.flyway.ignore-migration-patterns`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `spring.flyway.oracle-kerberos-config-file`
  * newPropertyKey: `spring.flyway.kerberos-config-file`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `spring.redis.client-name`
  * newPropertyKey: `spring.data.redis.client-name`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `spring.redis.client-type`
  * newPropertyKey: `spring.data.redis.client-type`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `spring.redis.cluster.max-redirects`
  * newPropertyKey: `spring.data.redis.cluster.max-redirects`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `spring.redis.cluster.nodes`
  * newPropertyKey: `spring.data.redis.cluster.nodes`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `spring.redis.connect-timeout`
  * newPropertyKey: `spring.data.redis.connect-timeout`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `spring.redis.database`
  * newPropertyKey: `spring.data.redis.database`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `spring.redis.host`
  * newPropertyKey: `spring.data.redis.host`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `spring.redis.lettuce.cluster.refresh.adaptive`
  * newPropertyKey: `spring.data.redis.lettuce.cluster.refresh.adaptive`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `spring.redis.lettuce.cluster.refresh.dynamic-refresh-sources`
  * newPropertyKey: `spring.data.redis.lettuce.cluster.refresh.dynamic-refresh-sources`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `spring.redis.lettuce.cluster.refresh.period`
  * newPropertyKey: `spring.data.redis.lettuce.cluster.refresh.period`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `spring.redis.lettuce.shutdown-timeout`
  * newPropertyKey: `spring.data.redis.lettuce.shutdown-timeout`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `spring.redis.password`
  * newPropertyKey: `spring.data.redis.password`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `spring.redis.port`
  * newPropertyKey: `spring.data.redis.port`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `spring.redis.sentinel.master`
  * newPropertyKey: `spring.data.redis.sentinel.master`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `spring.redis.sentinel.nodes`
  * newPropertyKey: `spring.data.redis.sentinel.nodes`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `spring.redis.sentinel.password`
  * newPropertyKey: `spring.data.redis.sentinel.password`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `spring.redis.sentinel.username`
  * newPropertyKey: `spring.data.redis.sentinel.username`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `spring.redis.ssl`
  * newPropertyKey: `spring.data.redis.ssl`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `spring.redis.timeout`
  * newPropertyKey: `spring.data.redis.timeout`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `spring.redis.url`
  * newPropertyKey: `spring.data.redis.url`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `spring.redis.username`
  * newPropertyKey: `spring.data.redis.username`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `spring.security.oauth2.resourceserver.jwt.jws-algorithm`
  * newPropertyKey: `spring.security.oauth2.resourceserver.jwt.jws-algorithms`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `management.metrics.export.appoptics.api-token`
  * newPropertyKey: `management.appoptics.metrics.export.api-token`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `management.metrics.export.appoptics.batch-size`
  * newPropertyKey: `management.appoptics.metrics.export.batch-size`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `management.metrics.export.appoptics.connect-timeout`
  * newPropertyKey: `management.appoptics.metrics.export.connect-timeout`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `management.metrics.export.appoptics.enabled`
  * newPropertyKey: `management.appoptics.metrics.export.enabled`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `management.metrics.export.appoptics.floor-times`
  * newPropertyKey: `management.appoptics.metrics.export.floor-times`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `management.metrics.export.appoptics.host-tag`
  * newPropertyKey: `management.appoptics.metrics.export.host-tag`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `management.metrics.export.appoptics.read-timeout`
  * newPropertyKey: `management.appoptics.metrics.export.read-timeout`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `management.metrics.export.appoptics.step`
  * newPropertyKey: `management.appoptics.metrics.export.step`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `management.metrics.export.appoptics.uri`
  * newPropertyKey: `management.appoptics.metrics.export.uri`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `management.metrics.export.atlas.batch-size`
  * newPropertyKey: `management.atlas.metrics.export.batch-size`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `management.metrics.export.atlas.config-refresh-frequency`
  * newPropertyKey: `management.atlas.metrics.export.config-refresh-frequency`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `management.metrics.export.atlas.config-time-to-live`
  * newPropertyKey: `management.atlas.metrics.export.config-time-to-live`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `management.metrics.export.atlas.config-uri`
  * newPropertyKey: `management.atlas.metrics.export.config-uri`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `management.metrics.export.atlas.connect-timeout`
  * newPropertyKey: `management.atlas.metrics.export.connect-timeout`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `management.metrics.export.atlas.enabled`
  * newPropertyKey: `management.atlas.metrics.export.enabled`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `management.metrics.export.atlas.eval-uri`
  * newPropertyKey: `management.atlas.metrics.export.eval-uri`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `management.metrics.export.atlas.lwc-enabled`
  * newPropertyKey: `management.atlas.metrics.export.lwc-enabled`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `management.metrics.export.atlas.meter-time-to-live`
  * newPropertyKey: `management.atlas.metrics.export.meter-time-to-live`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `management.metrics.export.atlas.read-timeout`
  * newPropertyKey: `management.atlas.metrics.export.read-timeout`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `management.metrics.export.atlas.step`
  * newPropertyKey: `management.atlas.metrics.export.step`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `management.metrics.export.atlas.uri`
  * newPropertyKey: `management.atlas.metrics.export.uri`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `management.metrics.export.datadog.api-key`
  * newPropertyKey: `management.datadog.metrics.export.api-key`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `management.metrics.export.datadog.application-key`
  * newPropertyKey: `management.datadog.metrics.export.application-key`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `management.metrics.export.datadog.batch-size`
  * newPropertyKey: `management.datadog.metrics.export.batch-size`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `management.metrics.export.datadog.connect-timeout`
  * newPropertyKey: `management.datadog.metrics.export.connect-timeout`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `management.metrics.export.datadog.descriptions`
  * newPropertyKey: `management.datadog.metrics.export.descriptions`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `management.metrics.export.datadog.enabled`
  * newPropertyKey: `management.datadog.metrics.export.enabled`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `management.metrics.export.datadog.host-tag`
  * newPropertyKey: `management.datadog.metrics.export.host-tag`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `management.metrics.export.datadog.read-timeout`
  * newPropertyKey: `management.datadog.metrics.export.read-timeout`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `management.metrics.export.datadog.step`
  * newPropertyKey: `management.datadog.metrics.export.step`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `management.metrics.export.datadog.uri`
  * newPropertyKey: `management.datadog.metrics.export.uri`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `management.metrics.export.defaults.enabled`
  * newPropertyKey: `management.defaults.metrics.export.enabled`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `management.metrics.export.dynatrace.api-token`
  * newPropertyKey: `management.dynatrace.metrics.export.api-token`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `management.metrics.export.dynatrace.batch-size`
  * newPropertyKey: `management.dynatrace.metrics.export.batch-size`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `management.metrics.export.dynatrace.connect-timeout`
  * newPropertyKey: `management.dynatrace.metrics.export.connect-timeout`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `management.metrics.export.dynatrace.device-id`
  * newPropertyKey: `management.dynatrace.metrics.export.device-id`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `management.metrics.export.dynatrace.enabled`
  * newPropertyKey: `management.dynatrace.metrics.export.enabled`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `management.metrics.export.dynatrace.group`
  * newPropertyKey: `management.dynatrace.metrics.export.group`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `management.metrics.export.dynatrace.read-timeout`
  * newPropertyKey: `management.dynatrace.metrics.export.read-timeout`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `management.metrics.export.dynatrace.step`
  * newPropertyKey: `management.dynatrace.metrics.export.step`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `management.metrics.export.dynatrace.technology-type`
  * newPropertyKey: `management.dynatrace.metrics.export.technology-type`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `management.metrics.export.dynatrace.uri`
  * newPropertyKey: `management.dynatrace.metrics.export.uri`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `management.metrics.export.dynatrace.v1.device-id`
  * newPropertyKey: `management.dynatrace.metrics.export.v1.device-id`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `management.metrics.export.dynatrace.v1.group`
  * newPropertyKey: `management.dynatrace.metrics.export.v1.group`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `management.metrics.export.dynatrace.v1.technology-type`
  * newPropertyKey: `management.dynatrace.metrics.export.v1.technology-type`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `management.metrics.export.dynatrace.v2.default-dimensions`
  * newPropertyKey: `management.dynatrace.metrics.export.v2.default-dimensions`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `management.metrics.export.dynatrace.v2.enrich-with-dynatrace-metadata`
  * newPropertyKey: `management.dynatrace.metrics.export.v2.enrich-with-dynatrace-metadata`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `management.metrics.export.dynatrace.v2.metric-key-prefix`
  * newPropertyKey: `management.dynatrace.metrics.export.v2.metric-key-prefix`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `management.metrics.export.elastic.api-key-credentials`
  * newPropertyKey: `management.elastic.metrics.export.api-key-credentials`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `management.metrics.export.elastic.auto-create-index`
  * newPropertyKey: `management.elastic.metrics.export.auto-create-index`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `management.metrics.export.elastic.batch-size`
  * newPropertyKey: `management.elastic.metrics.export.batch-size`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `management.metrics.export.elastic.connect-timeout`
  * newPropertyKey: `management.elastic.metrics.export.connect-timeout`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `management.metrics.export.elastic.enabled`
  * newPropertyKey: `management.elastic.metrics.export.enabled`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `management.metrics.export.elastic.host`
  * newPropertyKey: `management.elastic.metrics.export.host`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `management.metrics.export.elastic.index`
  * newPropertyKey: `management.elastic.metrics.export.index`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `management.metrics.export.elastic.index-date-format`
  * newPropertyKey: `management.elastic.metrics.export.index-date-format`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `management.metrics.export.elastic.index-date-separator`
  * newPropertyKey: `management.elastic.metrics.export.index-date-separator`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `management.metrics.export.elastic.password`
  * newPropertyKey: `management.elastic.metrics.export.password`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `management.metrics.export.elastic.pipeline`
  * newPropertyKey: `management.elastic.metrics.export.pipeline`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `management.metrics.export.elastic.read-timeout`
  * newPropertyKey: `management.elastic.metrics.export.read-timeout`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `management.metrics.export.elastic.step`
  * newPropertyKey: `management.elastic.metrics.export.step`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `management.metrics.export.elastic.timestamp-field-name`
  * newPropertyKey: `management.elastic.metrics.export.timestamp-field-name`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `management.metrics.export.elastic.user-name`
  * newPropertyKey: `management.elastic.metrics.export.user-name`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `management.metrics.export.ganglia.addressing-mode`
  * newPropertyKey: `management.ganglia.metrics.export.addressing-mode`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `management.metrics.export.ganglia.duration-units`
  * newPropertyKey: `management.ganglia.metrics.export.duration-units`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `management.metrics.export.ganglia.enabled`
  * newPropertyKey: `management.ganglia.metrics.export.enabled`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `management.metrics.export.ganglia.host`
  * newPropertyKey: `management.ganglia.metrics.export.host`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `management.metrics.export.ganglia.port`
  * newPropertyKey: `management.ganglia.metrics.export.port`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `management.metrics.export.ganglia.step`
  * newPropertyKey: `management.ganglia.metrics.export.step`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `management.metrics.export.ganglia.time-to-live`
  * newPropertyKey: `management.ganglia.metrics.export.time-to-live`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `management.metrics.export.graphite.duration-units`
  * newPropertyKey: `management.graphite.metrics.export.duration-units`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `management.metrics.export.graphite.enabled`
  * newPropertyKey: `management.graphite.metrics.export.enabled`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `management.metrics.export.graphite.graphite-tags-enabled`
  * newPropertyKey: `management.graphite.metrics.export.graphite-tags-enabled`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `management.metrics.export.graphite.host`
  * newPropertyKey: `management.graphite.metrics.export.host`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `management.metrics.export.graphite.port`
  * newPropertyKey: `management.graphite.metrics.export.port`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `management.metrics.export.graphite.protocol`
  * newPropertyKey: `management.graphite.metrics.export.protocol`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `management.metrics.export.graphite.rate-units`
  * newPropertyKey: `management.graphite.metrics.export.rate-units`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `management.metrics.export.graphite.step`
  * newPropertyKey: `management.graphite.metrics.export.step`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `management.metrics.export.graphite.tags-as-prefix`
  * newPropertyKey: `management.graphite.metrics.export.tags-as-prefix`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `management.metrics.export.humio.api-token`
  * newPropertyKey: `management.humio.metrics.export.api-token`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `management.metrics.export.humio.batch-size`
  * newPropertyKey: `management.humio.metrics.export.batch-size`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `management.metrics.export.humio.connect-timeout`
  * newPropertyKey: `management.humio.metrics.export.connect-timeout`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `management.metrics.export.humio.enabled`
  * newPropertyKey: `management.humio.metrics.export.enabled`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `management.metrics.export.humio.read-timeout`
  * newPropertyKey: `management.humio.metrics.export.read-timeout`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `management.metrics.export.humio.step`
  * newPropertyKey: `management.humio.metrics.export.step`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `management.metrics.export.humio.tags`
  * newPropertyKey: `management.humio.metrics.export.tags`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `management.metrics.export.humio.uri`
  * newPropertyKey: `management.humio.metrics.export.uri`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `management.metrics.export.influx.api-version`
  * newPropertyKey: `management.influx.metrics.export.api-version`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `management.metrics.export.influx.auto-create-db`
  * newPropertyKey: `management.influx.metrics.export.auto-create-db`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `management.metrics.export.influx.batch-size`
  * newPropertyKey: `management.influx.metrics.export.batch-size`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `management.metrics.export.influx.bucket`
  * newPropertyKey: `management.influx.metrics.export.bucket`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `management.metrics.export.influx.compressed`
  * newPropertyKey: `management.influx.metrics.export.compressed`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `management.metrics.export.influx.connect-timeout`
  * newPropertyKey: `management.influx.metrics.export.connect-timeout`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `management.metrics.export.influx.consistency`
  * newPropertyKey: `management.influx.metrics.export.consistency`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `management.metrics.export.influx.db`
  * newPropertyKey: `management.influx.metrics.export.db`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `management.metrics.export.influx.enabled`
  * newPropertyKey: `management.influx.metrics.export.enabled`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `management.metrics.export.influx.org`
  * newPropertyKey: `management.influx.metrics.export.org`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `management.metrics.export.influx.password`
  * newPropertyKey: `management.influx.metrics.export.password`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `management.metrics.export.influx.read-timeout`
  * newPropertyKey: `management.influx.metrics.export.read-timeout`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `management.metrics.export.influx.retention-duration`
  * newPropertyKey: `management.influx.metrics.export.retention-duration`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `management.metrics.export.influx.retention-policy`
  * newPropertyKey: `management.influx.metrics.export.retention-policy`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `management.metrics.export.influx.retention-replication-factor`
  * newPropertyKey: `management.influx.metrics.export.retention-replication-factor`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `management.metrics.export.influx.retention-shard-duration`
  * newPropertyKey: `management.influx.metrics.export.retention-shard-duration`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `management.metrics.export.influx.step`
  * newPropertyKey: `management.influx.metrics.export.step`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `management.metrics.export.influx.token`
  * newPropertyKey: `management.influx.metrics.export.token`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `management.metrics.export.influx.uri`
  * newPropertyKey: `management.influx.metrics.export.uri`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `management.metrics.export.influx.user-name`
  * newPropertyKey: `management.influx.metrics.export.user-name`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `management.metrics.export.jmx.domain`
  * newPropertyKey: `management.jmx.metrics.export.domain`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `management.metrics.export.jmx.enabled`
  * newPropertyKey: `management.jmx.metrics.export.enabled`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `management.metrics.export.jmx.step`
  * newPropertyKey: `management.jmx.metrics.export.step`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `management.metrics.export.kairos.batch-size`
  * newPropertyKey: `management.kairos.metrics.export.batch-size`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `management.metrics.export.kairos.connect-timeout`
  * newPropertyKey: `management.kairos.metrics.export.connect-timeout`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `management.metrics.export.kairos.enabled`
  * newPropertyKey: `management.kairos.metrics.export.enabled`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `management.metrics.export.kairos.password`
  * newPropertyKey: `management.kairos.metrics.export.password`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `management.metrics.export.kairos.read-timeout`
  * newPropertyKey: `management.kairos.metrics.export.read-timeout`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `management.metrics.export.kairos.step`
  * newPropertyKey: `management.kairos.metrics.export.step`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `management.metrics.export.kairos.uri`
  * newPropertyKey: `management.kairos.metrics.export.uri`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `management.metrics.export.kairos.user-name`
  * newPropertyKey: `management.kairos.metrics.export.user-name`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `management.metrics.export.newrelic.account-id`
  * newPropertyKey: `management.newrelic.metrics.export.account-id`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `management.metrics.export.newrelic.api-key`
  * newPropertyKey: `management.newrelic.metrics.export.api-key`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `management.metrics.export.newrelic.batch-size`
  * newPropertyKey: `management.newrelic.metrics.export.batch-size`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `management.metrics.export.newrelic.client-provider-type`
  * newPropertyKey: `management.newrelic.metrics.export.client-provider-type`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `management.metrics.export.newrelic.connect-timeout`
  * newPropertyKey: `management.newrelic.metrics.export.connect-timeout`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `management.metrics.export.newrelic.enabled`
  * newPropertyKey: `management.newrelic.metrics.export.enabled`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `management.metrics.export.newrelic.event-type`
  * newPropertyKey: `management.newrelic.metrics.export.event-type`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `management.metrics.export.newrelic.meter-name-event-type-enabled`
  * newPropertyKey: `management.newrelic.metrics.export.meter-name-event-type-enabled`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `management.metrics.export.newrelic.read-timeout`
  * newPropertyKey: `management.newrelic.metrics.export.read-timeout`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `management.metrics.export.newrelic.step`
  * newPropertyKey: `management.newrelic.metrics.export.step`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `management.metrics.export.newrelic.uri`
  * newPropertyKey: `management.newrelic.metrics.export.uri`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `management.metrics.export.prometheus.descriptions`
  * newPropertyKey: `management.prometheus.metrics.export.descriptions`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `management.metrics.export.prometheus.enabled`
  * newPropertyKey: `management.prometheus.metrics.export.enabled`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `management.metrics.export.prometheus.histogram-flavor`
  * newPropertyKey: `management.prometheus.metrics.export.histogram-flavor`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `management.metrics.export.prometheus.pushgateway.base-url`
  * newPropertyKey: `management.prometheus.metrics.export.pushgateway.base-url`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `management.metrics.export.prometheus.pushgateway.enabled`
  * newPropertyKey: `management.prometheus.metrics.export.pushgateway.enabled`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `management.metrics.export.prometheus.pushgateway.grouping-key`
  * newPropertyKey: `management.prometheus.metrics.export.pushgateway.grouping-key`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `management.metrics.export.prometheus.pushgateway.job`
  * newPropertyKey: `management.prometheus.metrics.export.pushgateway.job`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `management.metrics.export.prometheus.pushgateway.password`
  * newPropertyKey: `management.prometheus.metrics.export.pushgateway.password`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `management.metrics.export.prometheus.pushgateway.push-rate`
  * newPropertyKey: `management.prometheus.metrics.export.pushgateway.push-rate`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `management.metrics.export.prometheus.pushgateway.shutdown-operation`
  * newPropertyKey: `management.prometheus.metrics.export.pushgateway.shutdown-operation`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `management.metrics.export.prometheus.pushgateway.username`
  * newPropertyKey: `management.prometheus.metrics.export.pushgateway.username`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `management.metrics.export.prometheus.step`
  * newPropertyKey: `management.prometheus.metrics.export.step`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `management.metrics.export.signalfx.access-token`
  * newPropertyKey: `management.signalfx.metrics.export.access-token`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `management.metrics.export.signalfx.batch-size`
  * newPropertyKey: `management.signalfx.metrics.export.batch-size`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `management.metrics.export.signalfx.connect-timeout`
  * newPropertyKey: `management.signalfx.metrics.export.connect-timeout`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `management.metrics.export.signalfx.enabled`
  * newPropertyKey: `management.signalfx.metrics.export.enabled`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `management.metrics.export.signalfx.read-timeout`
  * newPropertyKey: `management.signalfx.metrics.export.read-timeout`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `management.metrics.export.signalfx.source`
  * newPropertyKey: `management.signalfx.metrics.export.source`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `management.metrics.export.signalfx.step`
  * newPropertyKey: `management.signalfx.metrics.export.step`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `management.metrics.export.signalfx.uri`
  * newPropertyKey: `management.signalfx.metrics.export.uri`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `management.metrics.export.simple.enabled`
  * newPropertyKey: `management.simple.metrics.export.enabled`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `management.metrics.export.simple.mode`
  * newPropertyKey: `management.simple.metrics.export.mode`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `management.metrics.export.simple.step`
  * newPropertyKey: `management.simple.metrics.export.step`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `management.metrics.export.stackdriver.batch-size`
  * newPropertyKey: `management.stackdriver.metrics.export.batch-size`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `management.metrics.export.stackdriver.connect-timeout`
  * newPropertyKey: `management.stackdriver.metrics.export.connect-timeout`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `management.metrics.export.stackdriver.enabled`
  * newPropertyKey: `management.stackdriver.metrics.export.enabled`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `management.metrics.export.stackdriver.project-id`
  * newPropertyKey: `management.stackdriver.metrics.export.project-id`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `management.metrics.export.stackdriver.read-timeout`
  * newPropertyKey: `management.stackdriver.metrics.export.read-timeout`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `management.metrics.export.stackdriver.resource-labels`
  * newPropertyKey: `management.stackdriver.metrics.export.resource-labels`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `management.metrics.export.stackdriver.resource-type`
  * newPropertyKey: `management.stackdriver.metrics.export.resource-type`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `management.metrics.export.stackdriver.step`
  * newPropertyKey: `management.stackdriver.metrics.export.step`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `management.metrics.export.stackdriver.use-semantic-metric-types`
  * newPropertyKey: `management.stackdriver.metrics.export.use-semantic-metric-types`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `management.metrics.export.statsd.enabled`
  * newPropertyKey: `management.statsd.metrics.export.enabled`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `management.metrics.export.statsd.flavor`
  * newPropertyKey: `management.statsd.metrics.export.flavor`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `management.metrics.export.statsd.host`
  * newPropertyKey: `management.statsd.metrics.export.host`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `management.metrics.export.statsd.max-packet-length`
  * newPropertyKey: `management.statsd.metrics.export.max-packet-length`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `management.metrics.export.statsd.polling-frequency`
  * newPropertyKey: `management.statsd.metrics.export.polling-frequency`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `management.metrics.export.statsd.port`
  * newPropertyKey: `management.statsd.metrics.export.port`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `management.metrics.export.statsd.protocol`
  * newPropertyKey: `management.statsd.metrics.export.protocol`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `management.metrics.export.statsd.publish-unchanged-meters`
  * newPropertyKey: `management.statsd.metrics.export.publish-unchanged-meters`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `management.metrics.export.wavefront.api-token`
  * newPropertyKey: `management.wavefront.api-token`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `management.metrics.export.wavefront.batch-size`
  * newPropertyKey: `management.wavefront.sender.batch-size`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `management.metrics.export.wavefront.enabled`
  * newPropertyKey: `management.wavefront.metrics.export.enabled`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `management.metrics.export.wavefront.global-prefix`
  * newPropertyKey: `management.wavefront.metrics.export.global-prefix`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `management.metrics.export.wavefront.sender.flush-interval`
  * newPropertyKey: `management.wavefront.sender.flush-interval`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `management.metrics.export.wavefront.sender.max-queue-size`
  * newPropertyKey: `management.wavefront.sender.max-queue-size`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `management.metrics.export.wavefront.sender.message-size`
  * newPropertyKey: `management.wavefront.sender.message-size`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `management.metrics.export.wavefront.source`
  * newPropertyKey: `management.wavefront.source`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `management.metrics.export.wavefront.step`
  * newPropertyKey: `management.wavefront.metrics.export.step`
* [Change the key of a spring application property](../../../java/spring/changespringpropertykey.md)
  * oldPropertyKey: `management.metrics.export.wavefront.uri`
  * newPropertyKey: `management.wavefront.uri`

{% endtab %}

{% tab title="Yaml Recipe List" %}
```yaml
---
type: specs.openrewrite.org/v1beta/recipe
name: org.openrewrite.java.spring.boot3.SpringBootProperties_3_0_0
displayName: Migrate Spring Boot properties to 3.0
description: Migrate properties found in `application.properties` and `application.yml`.
tags:
  - spring
  - spring-boot
  - spring-boot-3-0
recipeList:
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: spring.data.cassandra.compression
      newPropertyKey: spring.cassandra.compression
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: spring.data.cassandra.config
      newPropertyKey: spring.cassandra.config
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: spring.data.cassandra.connection.connect-timeout
      newPropertyKey: spring.cassandra.connection.connect-timeout
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: spring.data.cassandra.connection.init-query-timeout
      newPropertyKey: spring.cassandra.connection.init-query-timeout
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: spring.data.cassandra.contact-points
      newPropertyKey: spring.cassandra.contact-points
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: spring.data.cassandra.controlconnection.timeout
      newPropertyKey: spring.cassandra.controlconnection.timeout
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: spring.data.cassandra.keyspace-name
      newPropertyKey: spring.cassandra.keyspace-name
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: spring.data.cassandra.local-datacenter
      newPropertyKey: spring.cassandra.local-datacenter
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: spring.data.cassandra.password
      newPropertyKey: spring.cassandra.password
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: spring.data.cassandra.pool.heartbeat-interval
      newPropertyKey: spring.cassandra.pool.heartbeat-interval
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: spring.data.cassandra.pool.idle-timeout
      newPropertyKey: spring.cassandra.pool.idle-timeout
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: spring.data.cassandra.port
      newPropertyKey: spring.cassandra.port
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: spring.data.cassandra.request.consistency
      newPropertyKey: spring.cassandra.request.consistency
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: spring.data.cassandra.request.page-size
      newPropertyKey: spring.cassandra.request.page-size
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: spring.data.cassandra.request.serial-consistency
      newPropertyKey: spring.cassandra.request.serial-consistency
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: spring.data.cassandra.request.throttler.drain-interval
      newPropertyKey: spring.cassandra.request.throttler.drain-interval
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: spring.data.cassandra.request.throttler.max-concurrent-requests
      newPropertyKey: spring.cassandra.request.throttler.max-concurrent-requests
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: spring.data.cassandra.request.throttler.max-queue-size
      newPropertyKey: spring.cassandra.request.throttler.max-queue-size
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: spring.data.cassandra.request.throttler.max-requests-per-second
      newPropertyKey: spring.cassandra.request.throttler.max-requests-per-second
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: spring.data.cassandra.request.throttler.type
      newPropertyKey: spring.cassandra.request.throttler.type
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: spring.data.cassandra.request.timeout
      newPropertyKey: spring.cassandra.request.timeout
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: spring.data.cassandra.schema-action
      newPropertyKey: spring.cassandra.schema-action
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: spring.data.cassandra.session-name
      newPropertyKey: spring.cassandra.session-name
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: spring.data.cassandra.ssl
      newPropertyKey: spring.cassandra.ssl
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: spring.data.cassandra.username
      newPropertyKey: spring.cassandra.username
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: spring.flyway.ignore-future-migrations
      newPropertyKey: spring.flyway.ignore-migration-patterns
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: spring.flyway.ignore-ignored-migrations
      newPropertyKey: spring.flyway.ignore-migration-patterns
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: spring.flyway.ignore-missing-migrations
      newPropertyKey: spring.flyway.ignore-migration-patterns
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: spring.flyway.ignore-pending-migrations
      newPropertyKey: spring.flyway.ignore-migration-patterns
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: spring.flyway.oracle-kerberos-config-file
      newPropertyKey: spring.flyway.kerberos-config-file
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: spring.redis.client-name
      newPropertyKey: spring.data.redis.client-name
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: spring.redis.client-type
      newPropertyKey: spring.data.redis.client-type
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: spring.redis.cluster.max-redirects
      newPropertyKey: spring.data.redis.cluster.max-redirects
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: spring.redis.cluster.nodes
      newPropertyKey: spring.data.redis.cluster.nodes
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: spring.redis.connect-timeout
      newPropertyKey: spring.data.redis.connect-timeout
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: spring.redis.database
      newPropertyKey: spring.data.redis.database
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: spring.redis.host
      newPropertyKey: spring.data.redis.host
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: spring.redis.lettuce.cluster.refresh.adaptive
      newPropertyKey: spring.data.redis.lettuce.cluster.refresh.adaptive
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: spring.redis.lettuce.cluster.refresh.dynamic-refresh-sources
      newPropertyKey: spring.data.redis.lettuce.cluster.refresh.dynamic-refresh-sources
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: spring.redis.lettuce.cluster.refresh.period
      newPropertyKey: spring.data.redis.lettuce.cluster.refresh.period
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: spring.redis.lettuce.shutdown-timeout
      newPropertyKey: spring.data.redis.lettuce.shutdown-timeout
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: spring.redis.password
      newPropertyKey: spring.data.redis.password
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: spring.redis.port
      newPropertyKey: spring.data.redis.port
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: spring.redis.sentinel.master
      newPropertyKey: spring.data.redis.sentinel.master
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: spring.redis.sentinel.nodes
      newPropertyKey: spring.data.redis.sentinel.nodes
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: spring.redis.sentinel.password
      newPropertyKey: spring.data.redis.sentinel.password
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: spring.redis.sentinel.username
      newPropertyKey: spring.data.redis.sentinel.username
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: spring.redis.ssl
      newPropertyKey: spring.data.redis.ssl
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: spring.redis.timeout
      newPropertyKey: spring.data.redis.timeout
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: spring.redis.url
      newPropertyKey: spring.data.redis.url
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: spring.redis.username
      newPropertyKey: spring.data.redis.username
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: spring.security.oauth2.resourceserver.jwt.jws-algorithm
      newPropertyKey: spring.security.oauth2.resourceserver.jwt.jws-algorithms
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: management.metrics.export.appoptics.api-token
      newPropertyKey: management.appoptics.metrics.export.api-token
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: management.metrics.export.appoptics.batch-size
      newPropertyKey: management.appoptics.metrics.export.batch-size
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: management.metrics.export.appoptics.connect-timeout
      newPropertyKey: management.appoptics.metrics.export.connect-timeout
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: management.metrics.export.appoptics.enabled
      newPropertyKey: management.appoptics.metrics.export.enabled
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: management.metrics.export.appoptics.floor-times
      newPropertyKey: management.appoptics.metrics.export.floor-times
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: management.metrics.export.appoptics.host-tag
      newPropertyKey: management.appoptics.metrics.export.host-tag
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: management.metrics.export.appoptics.read-timeout
      newPropertyKey: management.appoptics.metrics.export.read-timeout
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: management.metrics.export.appoptics.step
      newPropertyKey: management.appoptics.metrics.export.step
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: management.metrics.export.appoptics.uri
      newPropertyKey: management.appoptics.metrics.export.uri
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: management.metrics.export.atlas.batch-size
      newPropertyKey: management.atlas.metrics.export.batch-size
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: management.metrics.export.atlas.config-refresh-frequency
      newPropertyKey: management.atlas.metrics.export.config-refresh-frequency
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: management.metrics.export.atlas.config-time-to-live
      newPropertyKey: management.atlas.metrics.export.config-time-to-live
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: management.metrics.export.atlas.config-uri
      newPropertyKey: management.atlas.metrics.export.config-uri
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: management.metrics.export.atlas.connect-timeout
      newPropertyKey: management.atlas.metrics.export.connect-timeout
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: management.metrics.export.atlas.enabled
      newPropertyKey: management.atlas.metrics.export.enabled
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: management.metrics.export.atlas.eval-uri
      newPropertyKey: management.atlas.metrics.export.eval-uri
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: management.metrics.export.atlas.lwc-enabled
      newPropertyKey: management.atlas.metrics.export.lwc-enabled
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: management.metrics.export.atlas.meter-time-to-live
      newPropertyKey: management.atlas.metrics.export.meter-time-to-live
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: management.metrics.export.atlas.read-timeout
      newPropertyKey: management.atlas.metrics.export.read-timeout
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: management.metrics.export.atlas.step
      newPropertyKey: management.atlas.metrics.export.step
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: management.metrics.export.atlas.uri
      newPropertyKey: management.atlas.metrics.export.uri
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: management.metrics.export.datadog.api-key
      newPropertyKey: management.datadog.metrics.export.api-key
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: management.metrics.export.datadog.application-key
      newPropertyKey: management.datadog.metrics.export.application-key
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: management.metrics.export.datadog.batch-size
      newPropertyKey: management.datadog.metrics.export.batch-size
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: management.metrics.export.datadog.connect-timeout
      newPropertyKey: management.datadog.metrics.export.connect-timeout
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: management.metrics.export.datadog.descriptions
      newPropertyKey: management.datadog.metrics.export.descriptions
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: management.metrics.export.datadog.enabled
      newPropertyKey: management.datadog.metrics.export.enabled
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: management.metrics.export.datadog.host-tag
      newPropertyKey: management.datadog.metrics.export.host-tag
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: management.metrics.export.datadog.read-timeout
      newPropertyKey: management.datadog.metrics.export.read-timeout
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: management.metrics.export.datadog.step
      newPropertyKey: management.datadog.metrics.export.step
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: management.metrics.export.datadog.uri
      newPropertyKey: management.datadog.metrics.export.uri
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: management.metrics.export.defaults.enabled
      newPropertyKey: management.defaults.metrics.export.enabled
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: management.metrics.export.dynatrace.api-token
      newPropertyKey: management.dynatrace.metrics.export.api-token
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: management.metrics.export.dynatrace.batch-size
      newPropertyKey: management.dynatrace.metrics.export.batch-size
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: management.metrics.export.dynatrace.connect-timeout
      newPropertyKey: management.dynatrace.metrics.export.connect-timeout
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: management.metrics.export.dynatrace.device-id
      newPropertyKey: management.dynatrace.metrics.export.device-id
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: management.metrics.export.dynatrace.enabled
      newPropertyKey: management.dynatrace.metrics.export.enabled
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: management.metrics.export.dynatrace.group
      newPropertyKey: management.dynatrace.metrics.export.group
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: management.metrics.export.dynatrace.read-timeout
      newPropertyKey: management.dynatrace.metrics.export.read-timeout
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: management.metrics.export.dynatrace.step
      newPropertyKey: management.dynatrace.metrics.export.step
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: management.metrics.export.dynatrace.technology-type
      newPropertyKey: management.dynatrace.metrics.export.technology-type
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: management.metrics.export.dynatrace.uri
      newPropertyKey: management.dynatrace.metrics.export.uri
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: management.metrics.export.dynatrace.v1.device-id
      newPropertyKey: management.dynatrace.metrics.export.v1.device-id
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: management.metrics.export.dynatrace.v1.group
      newPropertyKey: management.dynatrace.metrics.export.v1.group
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: management.metrics.export.dynatrace.v1.technology-type
      newPropertyKey: management.dynatrace.metrics.export.v1.technology-type
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: management.metrics.export.dynatrace.v2.default-dimensions
      newPropertyKey: management.dynatrace.metrics.export.v2.default-dimensions
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: management.metrics.export.dynatrace.v2.enrich-with-dynatrace-metadata
      newPropertyKey: management.dynatrace.metrics.export.v2.enrich-with-dynatrace-metadata
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: management.metrics.export.dynatrace.v2.metric-key-prefix
      newPropertyKey: management.dynatrace.metrics.export.v2.metric-key-prefix
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: management.metrics.export.elastic.api-key-credentials
      newPropertyKey: management.elastic.metrics.export.api-key-credentials
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: management.metrics.export.elastic.auto-create-index
      newPropertyKey: management.elastic.metrics.export.auto-create-index
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: management.metrics.export.elastic.batch-size
      newPropertyKey: management.elastic.metrics.export.batch-size
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: management.metrics.export.elastic.connect-timeout
      newPropertyKey: management.elastic.metrics.export.connect-timeout
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: management.metrics.export.elastic.enabled
      newPropertyKey: management.elastic.metrics.export.enabled
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: management.metrics.export.elastic.host
      newPropertyKey: management.elastic.metrics.export.host
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: management.metrics.export.elastic.index
      newPropertyKey: management.elastic.metrics.export.index
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: management.metrics.export.elastic.index-date-format
      newPropertyKey: management.elastic.metrics.export.index-date-format
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: management.metrics.export.elastic.index-date-separator
      newPropertyKey: management.elastic.metrics.export.index-date-separator
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: management.metrics.export.elastic.password
      newPropertyKey: management.elastic.metrics.export.password
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: management.metrics.export.elastic.pipeline
      newPropertyKey: management.elastic.metrics.export.pipeline
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: management.metrics.export.elastic.read-timeout
      newPropertyKey: management.elastic.metrics.export.read-timeout
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: management.metrics.export.elastic.step
      newPropertyKey: management.elastic.metrics.export.step
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: management.metrics.export.elastic.timestamp-field-name
      newPropertyKey: management.elastic.metrics.export.timestamp-field-name
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: management.metrics.export.elastic.user-name
      newPropertyKey: management.elastic.metrics.export.user-name
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: management.metrics.export.ganglia.addressing-mode
      newPropertyKey: management.ganglia.metrics.export.addressing-mode
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: management.metrics.export.ganglia.duration-units
      newPropertyKey: management.ganglia.metrics.export.duration-units
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: management.metrics.export.ganglia.enabled
      newPropertyKey: management.ganglia.metrics.export.enabled
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: management.metrics.export.ganglia.host
      newPropertyKey: management.ganglia.metrics.export.host
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: management.metrics.export.ganglia.port
      newPropertyKey: management.ganglia.metrics.export.port
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: management.metrics.export.ganglia.step
      newPropertyKey: management.ganglia.metrics.export.step
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: management.metrics.export.ganglia.time-to-live
      newPropertyKey: management.ganglia.metrics.export.time-to-live
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: management.metrics.export.graphite.duration-units
      newPropertyKey: management.graphite.metrics.export.duration-units
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: management.metrics.export.graphite.enabled
      newPropertyKey: management.graphite.metrics.export.enabled
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: management.metrics.export.graphite.graphite-tags-enabled
      newPropertyKey: management.graphite.metrics.export.graphite-tags-enabled
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: management.metrics.export.graphite.host
      newPropertyKey: management.graphite.metrics.export.host
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: management.metrics.export.graphite.port
      newPropertyKey: management.graphite.metrics.export.port
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: management.metrics.export.graphite.protocol
      newPropertyKey: management.graphite.metrics.export.protocol
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: management.metrics.export.graphite.rate-units
      newPropertyKey: management.graphite.metrics.export.rate-units
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: management.metrics.export.graphite.step
      newPropertyKey: management.graphite.metrics.export.step
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: management.metrics.export.graphite.tags-as-prefix
      newPropertyKey: management.graphite.metrics.export.tags-as-prefix
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: management.metrics.export.humio.api-token
      newPropertyKey: management.humio.metrics.export.api-token
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: management.metrics.export.humio.batch-size
      newPropertyKey: management.humio.metrics.export.batch-size
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: management.metrics.export.humio.connect-timeout
      newPropertyKey: management.humio.metrics.export.connect-timeout
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: management.metrics.export.humio.enabled
      newPropertyKey: management.humio.metrics.export.enabled
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: management.metrics.export.humio.read-timeout
      newPropertyKey: management.humio.metrics.export.read-timeout
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: management.metrics.export.humio.step
      newPropertyKey: management.humio.metrics.export.step
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: management.metrics.export.humio.tags
      newPropertyKey: management.humio.metrics.export.tags
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: management.metrics.export.humio.uri
      newPropertyKey: management.humio.metrics.export.uri
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: management.metrics.export.influx.api-version
      newPropertyKey: management.influx.metrics.export.api-version
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: management.metrics.export.influx.auto-create-db
      newPropertyKey: management.influx.metrics.export.auto-create-db
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: management.metrics.export.influx.batch-size
      newPropertyKey: management.influx.metrics.export.batch-size
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: management.metrics.export.influx.bucket
      newPropertyKey: management.influx.metrics.export.bucket
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: management.metrics.export.influx.compressed
      newPropertyKey: management.influx.metrics.export.compressed
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: management.metrics.export.influx.connect-timeout
      newPropertyKey: management.influx.metrics.export.connect-timeout
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: management.metrics.export.influx.consistency
      newPropertyKey: management.influx.metrics.export.consistency
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: management.metrics.export.influx.db
      newPropertyKey: management.influx.metrics.export.db
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: management.metrics.export.influx.enabled
      newPropertyKey: management.influx.metrics.export.enabled
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: management.metrics.export.influx.org
      newPropertyKey: management.influx.metrics.export.org
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: management.metrics.export.influx.password
      newPropertyKey: management.influx.metrics.export.password
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: management.metrics.export.influx.read-timeout
      newPropertyKey: management.influx.metrics.export.read-timeout
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: management.metrics.export.influx.retention-duration
      newPropertyKey: management.influx.metrics.export.retention-duration
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: management.metrics.export.influx.retention-policy
      newPropertyKey: management.influx.metrics.export.retention-policy
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: management.metrics.export.influx.retention-replication-factor
      newPropertyKey: management.influx.metrics.export.retention-replication-factor
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: management.metrics.export.influx.retention-shard-duration
      newPropertyKey: management.influx.metrics.export.retention-shard-duration
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: management.metrics.export.influx.step
      newPropertyKey: management.influx.metrics.export.step
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: management.metrics.export.influx.token
      newPropertyKey: management.influx.metrics.export.token
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: management.metrics.export.influx.uri
      newPropertyKey: management.influx.metrics.export.uri
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: management.metrics.export.influx.user-name
      newPropertyKey: management.influx.metrics.export.user-name
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: management.metrics.export.jmx.domain
      newPropertyKey: management.jmx.metrics.export.domain
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: management.metrics.export.jmx.enabled
      newPropertyKey: management.jmx.metrics.export.enabled
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: management.metrics.export.jmx.step
      newPropertyKey: management.jmx.metrics.export.step
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: management.metrics.export.kairos.batch-size
      newPropertyKey: management.kairos.metrics.export.batch-size
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: management.metrics.export.kairos.connect-timeout
      newPropertyKey: management.kairos.metrics.export.connect-timeout
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: management.metrics.export.kairos.enabled
      newPropertyKey: management.kairos.metrics.export.enabled
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: management.metrics.export.kairos.password
      newPropertyKey: management.kairos.metrics.export.password
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: management.metrics.export.kairos.read-timeout
      newPropertyKey: management.kairos.metrics.export.read-timeout
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: management.metrics.export.kairos.step
      newPropertyKey: management.kairos.metrics.export.step
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: management.metrics.export.kairos.uri
      newPropertyKey: management.kairos.metrics.export.uri
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: management.metrics.export.kairos.user-name
      newPropertyKey: management.kairos.metrics.export.user-name
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: management.metrics.export.newrelic.account-id
      newPropertyKey: management.newrelic.metrics.export.account-id
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: management.metrics.export.newrelic.api-key
      newPropertyKey: management.newrelic.metrics.export.api-key
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: management.metrics.export.newrelic.batch-size
      newPropertyKey: management.newrelic.metrics.export.batch-size
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: management.metrics.export.newrelic.client-provider-type
      newPropertyKey: management.newrelic.metrics.export.client-provider-type
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: management.metrics.export.newrelic.connect-timeout
      newPropertyKey: management.newrelic.metrics.export.connect-timeout
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: management.metrics.export.newrelic.enabled
      newPropertyKey: management.newrelic.metrics.export.enabled
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: management.metrics.export.newrelic.event-type
      newPropertyKey: management.newrelic.metrics.export.event-type
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: management.metrics.export.newrelic.meter-name-event-type-enabled
      newPropertyKey: management.newrelic.metrics.export.meter-name-event-type-enabled
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: management.metrics.export.newrelic.read-timeout
      newPropertyKey: management.newrelic.metrics.export.read-timeout
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: management.metrics.export.newrelic.step
      newPropertyKey: management.newrelic.metrics.export.step
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: management.metrics.export.newrelic.uri
      newPropertyKey: management.newrelic.metrics.export.uri
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: management.metrics.export.prometheus.descriptions
      newPropertyKey: management.prometheus.metrics.export.descriptions
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: management.metrics.export.prometheus.enabled
      newPropertyKey: management.prometheus.metrics.export.enabled
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: management.metrics.export.prometheus.histogram-flavor
      newPropertyKey: management.prometheus.metrics.export.histogram-flavor
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: management.metrics.export.prometheus.pushgateway.base-url
      newPropertyKey: management.prometheus.metrics.export.pushgateway.base-url
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: management.metrics.export.prometheus.pushgateway.enabled
      newPropertyKey: management.prometheus.metrics.export.pushgateway.enabled
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: management.metrics.export.prometheus.pushgateway.grouping-key
      newPropertyKey: management.prometheus.metrics.export.pushgateway.grouping-key
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: management.metrics.export.prometheus.pushgateway.job
      newPropertyKey: management.prometheus.metrics.export.pushgateway.job
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: management.metrics.export.prometheus.pushgateway.password
      newPropertyKey: management.prometheus.metrics.export.pushgateway.password
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: management.metrics.export.prometheus.pushgateway.push-rate
      newPropertyKey: management.prometheus.metrics.export.pushgateway.push-rate
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: management.metrics.export.prometheus.pushgateway.shutdown-operation
      newPropertyKey: management.prometheus.metrics.export.pushgateway.shutdown-operation
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: management.metrics.export.prometheus.pushgateway.username
      newPropertyKey: management.prometheus.metrics.export.pushgateway.username
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: management.metrics.export.prometheus.step
      newPropertyKey: management.prometheus.metrics.export.step
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: management.metrics.export.signalfx.access-token
      newPropertyKey: management.signalfx.metrics.export.access-token
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: management.metrics.export.signalfx.batch-size
      newPropertyKey: management.signalfx.metrics.export.batch-size
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: management.metrics.export.signalfx.connect-timeout
      newPropertyKey: management.signalfx.metrics.export.connect-timeout
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: management.metrics.export.signalfx.enabled
      newPropertyKey: management.signalfx.metrics.export.enabled
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: management.metrics.export.signalfx.read-timeout
      newPropertyKey: management.signalfx.metrics.export.read-timeout
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: management.metrics.export.signalfx.source
      newPropertyKey: management.signalfx.metrics.export.source
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: management.metrics.export.signalfx.step
      newPropertyKey: management.signalfx.metrics.export.step
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: management.metrics.export.signalfx.uri
      newPropertyKey: management.signalfx.metrics.export.uri
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: management.metrics.export.simple.enabled
      newPropertyKey: management.simple.metrics.export.enabled
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: management.metrics.export.simple.mode
      newPropertyKey: management.simple.metrics.export.mode
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: management.metrics.export.simple.step
      newPropertyKey: management.simple.metrics.export.step
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: management.metrics.export.stackdriver.batch-size
      newPropertyKey: management.stackdriver.metrics.export.batch-size
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: management.metrics.export.stackdriver.connect-timeout
      newPropertyKey: management.stackdriver.metrics.export.connect-timeout
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: management.metrics.export.stackdriver.enabled
      newPropertyKey: management.stackdriver.metrics.export.enabled
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: management.metrics.export.stackdriver.project-id
      newPropertyKey: management.stackdriver.metrics.export.project-id
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: management.metrics.export.stackdriver.read-timeout
      newPropertyKey: management.stackdriver.metrics.export.read-timeout
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: management.metrics.export.stackdriver.resource-labels
      newPropertyKey: management.stackdriver.metrics.export.resource-labels
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: management.metrics.export.stackdriver.resource-type
      newPropertyKey: management.stackdriver.metrics.export.resource-type
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: management.metrics.export.stackdriver.step
      newPropertyKey: management.stackdriver.metrics.export.step
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: management.metrics.export.stackdriver.use-semantic-metric-types
      newPropertyKey: management.stackdriver.metrics.export.use-semantic-metric-types
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: management.metrics.export.statsd.enabled
      newPropertyKey: management.statsd.metrics.export.enabled
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: management.metrics.export.statsd.flavor
      newPropertyKey: management.statsd.metrics.export.flavor
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: management.metrics.export.statsd.host
      newPropertyKey: management.statsd.metrics.export.host
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: management.metrics.export.statsd.max-packet-length
      newPropertyKey: management.statsd.metrics.export.max-packet-length
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: management.metrics.export.statsd.polling-frequency
      newPropertyKey: management.statsd.metrics.export.polling-frequency
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: management.metrics.export.statsd.port
      newPropertyKey: management.statsd.metrics.export.port
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: management.metrics.export.statsd.protocol
      newPropertyKey: management.statsd.metrics.export.protocol
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: management.metrics.export.statsd.publish-unchanged-meters
      newPropertyKey: management.statsd.metrics.export.publish-unchanged-meters
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: management.metrics.export.wavefront.api-token
      newPropertyKey: management.wavefront.api-token
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: management.metrics.export.wavefront.batch-size
      newPropertyKey: management.wavefront.sender.batch-size
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: management.metrics.export.wavefront.enabled
      newPropertyKey: management.wavefront.metrics.export.enabled
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: management.metrics.export.wavefront.global-prefix
      newPropertyKey: management.wavefront.metrics.export.global-prefix
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: management.metrics.export.wavefront.sender.flush-interval
      newPropertyKey: management.wavefront.sender.flush-interval
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: management.metrics.export.wavefront.sender.max-queue-size
      newPropertyKey: management.wavefront.sender.max-queue-size
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: management.metrics.export.wavefront.sender.message-size
      newPropertyKey: management.wavefront.sender.message-size
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: management.metrics.export.wavefront.source
      newPropertyKey: management.wavefront.source
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: management.metrics.export.wavefront.step
      newPropertyKey: management.wavefront.metrics.export.step
  - org.openrewrite.java.spring.ChangeSpringPropertyKey:
      oldPropertyKey: management.metrics.export.wavefront.uri
      newPropertyKey: management.wavefront.uri

```
{% endtab %}
{% endtabs %}
