

# Flutter Material Calendar

**Flutter Material Calendar** is a Flutter package that provides a simple and customizable monthly calendar interface, perfect for adding, managing, and viewing to-do items or events.

---

## Features

- **Monthly View**: Displays a clean and simple month-based calendar for easy navigation.
- **To-do List Management**: Allows users to add, view, and manage tasks or events within the calendar.
- **Customizable UI**: Easily integrates with any Flutter project with flexibility for custom styling and design.
- **Lightweight & Easy to Use**: Built with simplicity in mind, making it quick to integrate into any app.

---

![Flutter Material Calendar](https://github.com/postboxat18/flutter_material_calendar/assets/77087523/6469eaad-862c-4805-af0d-0f038f19cd37)

---

## Video Demo

Check out this **[video demonstration](https://github.com/postboxat18/flutter_material_calendar/assets/77087523/6469eaad-862c-4805-af0d-0f038f19cd37)** to see how the **Flutter Material Calendar** works in action.

---

## Installation

Add the package to your `pubspec.yaml` file:

```yaml
dependencies:
  flutter:
    sdk: flutter
  flutter_material_calendar: ^1.0.0
```

Then run `flutter pub get` to install it.

---

## Usage

Import the package:

```dart
import 'package:flutter_material_calendar/flutter_material_calendar.dart';
```

Add the **Flutter Material Calendar** to your app:

```dart
MaterialCalendar(
  onDaySelected: (DateTime date) {
    print('Selected date: $date');
  },
  onTodoAdded: (String task) {
    print('Added task: $task');
  },
);
```

---

## Example

```dart
import 'package:flutter/material.dart';
import 'package:flutter_material_calendar/flutter_material_calendar.dart';

void main() => runApp(MyApp());

class MyApp extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      home: Scaffold(
        appBar: AppBar(title: Text('Flutter Material Calendar')),
        body: MaterialCalendar(
          onDaySelected: (DateTime date) {
            print('Selected date: $date');
          },
          onTodoAdded: (String task) {
            print('Added task: $task');
          },
        ),
      ),
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

This README outlines the key features, installation, and usage of the **Flutter Material Calendar** package, providing potential users with a straightforward guide for implementation.