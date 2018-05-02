# artifactory and android-maven-publish plugin compatibility check

This repository contains a non working sample, when use `artifactory` plugin with the `android-maven-publish` plugin.

The `android-maven-publish` does not find the `releaseApiElements` and `releaseRuntimeElements` configuration when the `artifactory` plugin tries to collect maven publications in configuration phase.

## Sample configuration
```groovy
apply plugin: 'com.android.library'
apply plugin: 'digital.wup.android-maven-publish'
apply plugin: 'com.jfrog.artifactory'

android {
    // Android library plugin configuration
    // ...
}

dependencies {
    // List of dependencies
    // ...
}


publishing {
    publications {
        testArtifact(MavenPublication) {
            from components.android
        }
    }
}

```
