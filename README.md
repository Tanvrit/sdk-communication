# tanvrit-sdk · communication

> Real-time chat, messaging threads, presence, and WebRTC video / audio calls.

[![Maven](https://img.shields.io/badge/maven.tanvrit.com-1.0.12-blue)](https://maven.tanvrit.com)
![KMP](https://img.shields.io/badge/Kotlin_Multiplatform-7_targets-blueviolet)

## Install

### Option A — Tanvrit Gradle plugin _(recommended)_

```kotlin
// settings.gradle.kts
pluginManagement {
    repositories { maven { url = uri("https://maven.tanvrit.com") } }
}
```

```kotlin
// build.gradle.kts
plugins { id("com.tanvrit.sdk") version "1.0.12" }

tanvrit {
    version = "1.0.12"
    modules = listOf("communication")
}
```

### Option B — Direct dependency

```kotlin
// settings.gradle.kts
dependencyResolutionManagement {
    repositories { maven { url = uri("https://maven.tanvrit.com") } }
}
```

```kotlin
// build.gradle.kts  (KMP)
kotlin {
    sourceSets {
        commonMain.dependencies {
            implementation("com.tanvrit:communication:1.0.12")
        }
    }
}
```

## Targets

| Platform | Artifact |
|----------|----------|
| Android | `communication-android` |
| Iosarm64 | `communication-iosarm64` |
| Iossimulatorarm64 | `communication-iossimulatorarm64` |
| Iosx64 | `communication-iosx64` |
| Jvm | `communication-jvm` |
| Js | `communication-js` |
| Wasm Js | `communication-wasm-js` |

## Quick start

```kotlin
val chat = ChatHandler.shared()

// Send a message
chat.sendMessage(
    threadId  = "thread-001",
    content   = "Hello!",
    senderId  = "user-001",
) { message -> println("Sent: \${message?.id}") }

// Observe messages in a thread
chat.messageRepository.messages.collect { messages ->
    renderMessages(messages)
}

// Start a call
val call = CallHandler.shared()
call.startCall(participantId = "user-002", type = "video")
```

## Resources

- **Full SDK source:** [tanvrit/sdk](https://github.com/tanvrit/sdk)
- **All modules:** [maven.tanvrit.com](https://maven.tanvrit.com)
- **Issues:** [tanvrit/sdk/issues](https://github.com/tanvrit/sdk/issues)
