# Serverless bug example

How to reproduce bug:

1. Run `./gradlew buildZip`
2. Run `serverless invoke local -f hello`
3. Everything works
4. Change the serverless configuration to individual packaging:
```yaml
package:
  individually: true

functions:
  hello:
    handler: com.serverless.Handler
    package:
      artifact: build/distributions/hello.zip
```
5. You're going to get error:
```
 Artifact undefined doesn't exists, please compile it first.
```

