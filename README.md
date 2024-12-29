## Development Environment

This project is built and tested using the following tools:

- **JDK**: [Amazon Corretto 21](https://aws.amazon.com/corretto/)
- **Build Tool**: [Gradle 8.11](https://gradle.org/releases/)

## Demo
### setup - JAVA_HOME
- macos
```shell
brew install --cask corretto@21
export JAVA_HOME=$(/usr/libexec/java_home -v 21)
export PATH=$JAVA_HOME/bin:$PATH
wget https://services.gradle.org/distributions/gradle-8.11.1-bin.zip -O gradle/wrapper/gradle-8.11.1-bin.zip
```

### online build
```shell
./gradlew clean build --project-cache-dir libs --gradle-user-home libs
```

### offline build
- copy dependencies to /libs
```shell
./gradlew clean build --project-cache-dir libs --gradle-user-home libs --offline
```

### execute jar
- [http://localhost:8080/swagger-ui/index.html](http://localhost:8080/swagger-ui/index.html)
```shell
java -jar build/libs/gradle-offline-demo-0.0.1-SNAPSHOT.jar
```

### docker test(internet off)
- you must change distributionUrl in [gradle/wrapper/gradle-wrapper.properties](gradle/wrapper/gradle-wrapper.properties)
```shell
docker compose up -d
```