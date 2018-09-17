
Learning Flutter
====

<em>NOTE: All the following content are working on Windows 10 only</em>

I. Getting Start
---

### Flutter SDK Installation

- https://flutter.io/get-started/install/
- https://flutter.io/setup-windows/
- [flutter_windows_v0.7.3-beta.zip][flutter-windows-sdk]

1. Install PowerShell, Git, VS Code and Android Studio
2. Download the Flutter SDK and update path environment
3. `flutter doctor` to check environment. You need Flutter, Android toolchain and one IDE and a device(or emulator).
4. I use VS Code, easy to find the Flutter extension.
5. <kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd>, `flutter new project` to create a project. And `flutter run` to build and run the app on your connected device.

### Project Structure

- `lib/main.dart` ⇒ entry of the project
- `pubspec.yml` and `pubspec.lock` ⇒ dependencies and configuration
- ...✍

II. Concepts
----

### Widget



### StatelessWidget and StatefullWidget

> State<em>less</em> widgets are immutable, meaning that their properties can’t change—all values are final.
>
> State<em>ful</em> widgets maintain state that might change during the lifetime of the widget. Implementing a stateful widget requires at least two classes: 1) a StatefulWidget class that creates an instance of 2) a State class. **The StatefulWidget class is, itself, immutable, but the State class persists over the lifetime of the widget**.
>
> [Step 3: Add a Stateful widget](https://flutter.io/get-started/codelab/)

Difference between stateless widget and stateful widget is their lifetime, or actually, the state class, its lifetime is different.


[flutter-windows-sdk]: https://storage.googleapis.com/flutter_infra/releases/beta/windows/flutter_windows_v0.7.3-beta.zip
[emulator-or-simulator]: https://stackoverflow.com/questions/1584617/simulator-or-emulator-what-is-the-difference
<!--stackedit_data:
eyJwcm9wZXJ0aWVzIjoidGl0bGU6IE15IEZsdXR0ZXIgTm90ZV
xuYXV0aG9yOiBaZXJvb2tcbnRhZ3M6ICdGbHV0dGVyLCBBbmRy
b2lkJ1xuY2F0ZWdvcmllczogRmx1dHRlclxuc3RhdHVzOiBkcm
FmdFxuZGF0ZTogJzIwMTgtMDktMTcnXG4iLCJoaXN0b3J5Ijpb
MTM5NTI4NjAzMiwtNjA0NDM5NzA3LC0zMTM3NzEzNzUsMjAyND
cxODQxNywtMTM0OTIxOTU2MSwtMTU2MjgyNDQwNF19
-->