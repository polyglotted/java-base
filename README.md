# Minimalistic Alpine based Java docker

Based on [develar/docker-java](https://github.com/develar/docker-java). Changes from the original image include
  * remove entry point and make it extensible
  * support for tag based releases in dockerhub


### Example usage

```yaml
image: polyglotted/java-base:8u74
environment:
  _JAVA_OPTIONS: "-agentlib:jdwp=transport=dt_socket,server=y,suspend=n,address=5050 -Xms48m -Xmx64M"
  CLASSPATH: /app/lib/*:/app/classes
volumes:
  - out/production/moduleName:/app/classes:ro
  - lib:/app/lib:ro
command: com.example.ClassName
expose:
  - "80"
ports:
  - "5050:5050"
```
