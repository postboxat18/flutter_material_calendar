Here’s the **README** for the **Flutter Material Calendar** package with the additional code for handling events:

---

# Flutter Material Calendar

**Flutter Material Calendar** is a Flutter package that provides a simple and customizable monthly calendar interface with event management, perfect for adding, viewing, and managing tasks or events.

---

## Features

- **Monthly Calendar View**: Displays a clean and simple month-based calendar for easy navigation.
- **Event Management**: Allows users to add, view, and manage events within the calendar.
- **Customizable UI**: Flexibility to customize the calendar to fit your app’s design.
- **Lightweight & Easy to Use**: Simple integration for any Flutter project.

---

## Video Demo
![FlutterDemo-GoogleChrome2025-03-0120-55-20-ezgif com-video-to-gif-converter](https://github.com/user-attachments/assets/4cc6d988-b12b-4a5f-bb86-1bc9c3778f33)


---

## Installation

Add the package to your `pubspec.yaml` file:

```yaml
dependencies:
  flutter:
    sdk: flutter
  flutter_material_calendar: ^0.0.7
```

Then run `flutter pub get` to install it.

---

## Usage

### 1. Event List Setup

Before using the calendar, you need to set up an event list:

```dart
late List<EventList> eventList = [
  EventList(
    "2024-03-01",
    {
      "2024-03-01": [
        EventName(Color(0xff008A5E), "10:20", "Event Title 1"),
      ]
    },
  ),
];
```

### 2. Adding the **Material Calendar** to Your App

```dart
import 'package:flutter/material.dart';
import 'package:flutter_material_calendar/flutter_material_calendar.dart';
import 'package:intl/intl.dart';

void main() => runApp(MyApp());

class MyApp extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    // Sample event list
    late List<EventList> eventList = [
      EventList(
        "2024-03-01",
        {
          "2024-03-01": [
            EventName(Color(0xff008A5E), "10:20", "Event Title 1"),
          ]
        },
      ),
    ];

    return MaterialApp(
      home: Scaffold(
        appBar: AppBar(
          title: Text('Flutter Material Calendar with Events'),
        ),
        body: Center(
          child: MaterialCalendarEvent(
            Colors.grey,
            Colors.blueAccent,
            DateFormat("MMMM-yyyy").format(DateTime.now()), // Display format
            eventList, // List of events
          ),
        ),
      ),
    );
  }
}
```

### Explanation:
- **EventList**: A model representing the events for a specific date. Each `EventList` contains the date and a map with the events associated with that date.
- **MaterialCalendarEvent**: The main calendar widget that displays events based on the provided event list, date format, and color customization.

---

## Example

Here’s a complete example:

```dart
import 'package:flutter/material.dart';
import 'package:flutter_material_calendar/flutter_material_calendar.dart';
import 'package:intl/intl.dart';

void main() {
  runApp(const MyApp());
}

class MyApp extends StatelessWidget {
  const MyApp({super.key});

  // This widget is the root of your application.
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      title: 'Flutter Demo',
      theme: ThemeData(
        colorScheme: ColorScheme.fromSeed(seedColor: Colors.deepPurple),
        useMaterial3: true,
      ),
      home: const MyHomePage(title: 'Flutter Demo Home Page'),
    );
  }
}

class MyHomePage extends StatefulWidget {
  const MyHomePage({super.key, required this.title});

  final String title;

  @override
  State<MyHomePage> createState() => _MyHomePageState();
}

class _MyHomePageState extends State<MyHomePage> {
  late List<EventList> eventList = [
    EventList("2024-03-01",
        {"2024-03-01": [EventName(Color(0xff008A5E), "10:20", "10:20")]}),
    EventList("2024-03-03",
        {"2024-03-03": [EventName(Color(0xffF1BE41), "PH", "Public Holiday")]}),
    EventList("2024-03-05",
        {"2024-03-05": [EventName(Color(0xff008A5E), "10:20", "10:20"), EventName(Color(0xffB73434), "SL", "Sick Leave")]}),
    EventList("2024-03-06",
        {"2024-03-06": [EventName(Color(0xff008A5E), "10:20", "10:20")]}),
    EventList("2024-03-07",
        {"2024-03-07": [EventName(Color(0xffB73434), "CL", "Casual Leave")]}),
    EventList("2024-03-10",
        {"2024-03-10": [EventName(Color(0xffF1BE41), "PH", "Public Holiday")]}),
    EventList("2024-03-11",
        {"2024-03-11": [EventName(Color(0xff008A5E), "10:20", "10:20"),EventName(Color(0xffB73434), "CL", "Casual Leave")]}),
    EventList("2024-03-14",
        {"2024-03-14": [EventName(Color(0xffF1BE41), "CL", "Casual Leave")]}),
    EventList("2024-03-15",
        {"2024-03-15": [EventName(Color(0xffF1BE41), "PH", "Public Holiday")]}),
    EventList("2024-03-16",
        {"2024-03-16":[ EventName(Color(0xff008A5E), "10:20", "10:20")]}),
    EventList("2024-03-18",
        {"2024-03-18":[ EventName(Color(0xff008A5E), "10:20", "10:20"),EventName(Color(0xffB73434), "SL", "Sick Leave")]}),
    EventList("2024-03-20",
        {"2024-03-20": [EventName(Color(0xff008A5E), "10:20", "10:20")]}),
    EventList("2024-03-22",
        {"2024-03-22": [EventName(Color(0xffB73434), "SL", "Sick Leave")]}),
    EventList("2024-03-24",
        {"2024-03-24": [EventName(Color(0xff008A5E), "10:20", "10:20")]}),
    EventList("2024-03-26",
        {"2024-03-26":[ EventName(Color(0xffB73434), "CL", "Casual Leave")]}),
    EventList("2024-03-29",
        {"2024-03-29": [EventName(Color(0xff008A5E), "10:20", "10:20")]}),
    EventList("2024-03-30",
        {"2024-03-30": [EventName(Color(0xffF1BE41), "SL", "Sick Leave")]}),
  ];


  @override
  void initState() {
    super.initState();
  }

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        backgroundColor: Theme.of(context).colorScheme.inversePrimary,
        title: Text(widget.title),
      ),
      body:  SingleChildScrollView(child: MaterialCalendarEvent(Colors.grey, Colors.blueAccent, DateFormat("MMMM-yyyy")
          .format(DateTime.now()), eventList),),
    );
  }
}

```

---

## License

This package is open-source and available under the [MIT License](LICENSE).

---

For more details, check out the [Flutter Material Calendar on Pub.dev](https://pub.dev/packages/flutter_material_calendar).

---

This README now includes the event management setup, showing how to initialize the event list and integrate it with the calendar for a fully functional event calendar system.
