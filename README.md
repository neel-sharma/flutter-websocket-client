# Dart WebSocket Client

PieSocket Channels SDK for Flutter written in Dart.

This SDK can be used to communicate with any third-party WebSocket server,
and implements auto-reconnection among other best WebSocket practices.


## Installation
Add PieSocket Channels into your project.
```
flutter pub add piesocket_channels
```

## Usage

Import the library
```dart
import 'package:piesocket_channels/channels.dart';
```

### Stand-alone Usage
Create a Channel instance as shown below.
```dart
Chanel channel = Channel.connect("wss://example.com", true)

channel.listen("system:message", (PieSocketEvent event) {
    log("WebSocket message arrived!");
    print(event.toString());
});
```

### PieSocket's managed WebSocket server
Use following code to create a Channel with PieSocket's managed WebSocket servers.

Get your API key and Cluster ID here: [Get API Key](https://www.piesocket.com/app/v4/register)

```dart
var options = PieSocketOptions();
options.setClusterId("demo");
options.setApiKey("VCXCEuvhGcBDP7XhiJJUDvR1e1D3eiVjgZ9VRiaV");

PieSocket piesocket = PieSocket(options);
Channel channel = piesocket.join("chat-room");
```


[PieSocket Channels](https://piesocket.com/channels) is scalable WebSocket API service with following features:
  - Authentication
  - Private Channels
  - Presence Channels
  - Publish messages with REST API
  - Auto-scalability
  - Webhooks
  - Analytics
  - Authentication
  - Upto 60% cost savings

We highly recommend using PieSocket Channels over self hosted WebSocket servers for production applications.

## Events
`system:connected` is the event fired when WebSocket connection is ready, get a full list system messages here: [PieSocket System Messages](https://www.piesocket.com/docs/3.0/events#system-events)


## Documentation
For usage examples and more information, refer to: [Official SDK docs](https://www.piesocket.com/docs/3.0/flutter-websockets)