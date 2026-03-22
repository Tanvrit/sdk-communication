# tanvrit/communication

Chat, feed, events, contacts, tasks, and jobs — full communication and social layer.

## Install

Add the GitHub Packages repository to your `settings.gradle.kts` or `build.gradle.kts`:

```kotlin
maven {
    url = uri("https://maven.pkg.github.com/tanvrit/communication")
    credentials {
        username = (project.findProperty("gpr.user") as String?) ?: System.getenv("GITHUB_ACTOR") ?: ""
        password = (project.findProperty("gpr.key") as String?) ?: System.getenv("GITHUB_TOKEN") ?: ""
    }
}
```

Add the dependency:

```kotlin
// JVM / Ktor server
implementation("com.tanvrit:communication-jvm:0.0.1")

// Android
implementation("com.tanvrit:communication-android:0.0.1")

// KMP commonMain
implementation("com.tanvrit:communication:0.0.1")
```

## Authentication

Packages are public but GitHub Packages requires a token to download.

1. Create a [GitHub Personal Access Token](https://github.com/settings/tokens) with `read:packages` scope
2. Add to `~/.gradle/gradle.properties`:

```properties
gpr.user=YOUR_GITHUB_USERNAME
gpr.key=YOUR_GITHUB_TOKEN
```

## Part of the Tanvrit SDK

This module is part of the [Tanvrit Platform](https://tanvrit.com). All SDK modules: `core` · `storage` · `auth` · `business` · `commerce` · `communication` · `social` · `ui` · `commerceui` · `commerceapp`

