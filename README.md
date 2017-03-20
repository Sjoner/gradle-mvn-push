gradle-mvn-push
## Usage

### 1. Have a working Gradle build
This is upto you.

### 2. Create gradle.properties in sub-project
```properties
NEXUS_USERNAME=username
NEXUS_PASSWORD=password
VERSION_NAME=0.0.1-SNAPSHOT
GROUP=com.github.mvn-push
POM_NAME=Sample
POM_ARTIFACT_ID=library
POM_PACKAGING=aar
RELEASE_REPOSITORY_URL (defaults to Maven Central's staging server)
SNAPSHOT_REPOSITORY_URL (defaults to Maven Central's snapshot server)
```
### 5. Call the script from each sub-modules build.gradle

Add the following at the end of each `build.gradle` that you wish to upload:

```groovy
apply from: 'https://raw.github.com/jd-lmq/gradle-mvn-push/master/aar-mvn-push.gradle'
```

```groovy
apply from: 'https://raw.github.com/jd-lmq/gradle-mvn-push/master/jar-mvn-push.gradle'
```

### 6. Build and Push

You can now build and push:

```bash
$ gradle -p {moduleName} clean build uploadArchives --info
```
