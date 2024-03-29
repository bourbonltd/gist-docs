---
description: Our Flutter library wraps around the native iOS & Android libraries
---

# Flutter

### Installation

```yaml
dependencies:
  flutter:
    sdk: flutter

  gist_flutter: ^1.1.1
```

#### Android

Open the **Project** build.gradle file and update your kotlin version

```
ext.kotlin_version = '1.5.30'
```

Open the **App** build.gradle file and update the minimum SDK version

```
minSdkVersion 19
```

**Note:** If a version is higher then the one specified here, you can leave it as is.

#### iOS

Open the project's **.xcworkspace** file, select the project and make sure the **deployment target** is 10 or higher.

### Setup

```dart
import 'package:gist_flutter/gist.dart';
```

Gist can be initialized anywhere within your app, the `organizationId` property can be retrieved from the Gist dashboard.

```dart
Gist.setup("your-organization-id");
```

#### User Token

If your app is relying on Gist’s webhook service to trigger in-app messages, a user token must be set. This user token should be generated by your services and set at any point during runtime, for example, login or registration.

```dart
Gist.setUserToken("unique-user-token");
```

To clear the user token:

```dart
Gist.clearUserToken();
```

#### Current Route

Gist is able to show messages when a user reaches a particular route within your product. This is completely optional but messages containing route rules will not be displayed unless the route matches.

In your route handler add:

```dart
Gist.setCurrentRoute("users/home");
```

### Broadcasts

Broadcasts enable you to receive messages based on topics the client is subscribed to.

#### Subscribing

```dart
Gist.subscribeToTopic("announcements");
```

#### Unsubscribing

```dart
Gist.unsubscribeFromTopic("announcements");
```

#### Clear All Topics

```dart
Gist.clearTopics();
```

### Event Handling

Implement the `GistDelegate` into your class and add your class as an event listener.

```dart
Gist.eventListeners.add(this);
```

```dart
  @override
  onAction(message, action) {
    debugPrint("Action: Message instance: ${message.instanceId}, with id: ${message.messageId} and queue id: ${message.queueId}");
    debugPrint("Action: Message action: ${action.action} on route ${action.currentRoute}");
  }

  @override
  onError(message) {
    debugPrint("Error: Message instance: ${message.instanceId}, with id: ${message.messageId} and queue id: ${message.queueId}");
  }

  @override
  onMessageDismissed(message) {
    debugPrint("Dismissed: Message instance: ${message.instanceId}, with id: ${message.messageId} and queue id: ${message.queueId}");
  }

  @override
  onMessageShown(message) {
    debugPrint("Shown: Message instance: ${message.instanceId}, with id: ${message.messageId} and queue id: ${message.queueId}");
  }
```

### Messages

To programmatically dismiss messages `Gist.dismissMessage()` can be used to dismiss any active modal message being displayed.

### Important

The current Flutter implementation doesn't support message embedding or manual triggering of Gist messages, these features will be available at a later date.
