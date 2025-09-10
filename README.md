# Flutter Hello World 👋

A minimal **Flutter** “Hello, world” mobile app that runs in **GitHub Codespaces** (via Flutter Web) or locally.  
Includes a widget test, linting, and GitHub Actions CI.

---

## Quick Start (GitHub Codespaces)

> If you see `bash: flutter: command not found`, this repo uses a devcontainer. Open in **Codespaces** and, if prompted, **Rebuild Container**.

1. Open this repo in **Codespaces** (Code ▸ Create codespace on main).
2. When the container finishes, verify Flutter:
   ```bash
   flutter --version
   flutter doctor
Run the app (Web preview):

bash
Copy code
flutter config --enable-web
flutter run -d web-server --web-hostname 0.0.0.0 --web-port 3000
Open the forwarded Port 3000 to see the app.

Android/iOS emulators don’t run inside Codespaces. Use Flutter Web here.
On your machine you can run with Android/iOS normally.

Local Development (optional)
Install Flutter (stable channel): https://docs.flutter.dev/get-started/install

Fetch deps:

bash
Copy code
flutter pub get
Run on Chrome (or a device/emulator):

bash
Copy code
flutter config --enable-web
flutter run -d chrome
or

bash
Copy code
flutter run
Project Structure
bash
Copy code
lib/
  main.dart           # App entrypoint (Hello, world 👋)
test/
  hello_widget_test.dart
.github/
  workflows/
    flutter.yml       # CI: format check, analyze, test, build web
.devcontainer/
  devcontainer.json   # Codespaces image with Flutter preinstalled
Note: Flutter/Dart package names use underscores.
If your repo name has hyphens (e.g., flutter-hello-world), the generated package name uses underscores (e.g., flutter_hello_world).

Run Tests
bash
Copy code
flutter test
Sample test (already included as test/hello_widget_test.dart):

dart
Copy code
import 'package:flutter_test/flutter_test.dart';
import 'package:flutter_hello_world/main.dart';

void main() {
  testWidgets('shows Hello, world', (tester) async {
    await tester.pumpWidget(const MyApp());
    expect(find.text('Hello, world 👋'), findsOneWidget);
  });
}
Linting / Formatting
This project uses the default flutter_lints.

bash
Copy code
# Static analysis
flutter analyze

# Format check (used in CI)
flutter format --set-exit-if-changed .
Continuous Integration (GitHub Actions)
The workflow at .github/workflows/flutter.yml runs on every push/PR:

Setup Flutter (stable)

flutter pub get

Format check

flutter analyze

flutter test

Build Web (flutter build web)

Add a badge after your first successful run:

markdown
Copy code
![CI](https://github.com/<YOUR_GH_USERNAME>/<REPO_NAME>/actions/workflows/flutter.yml/badge.svg)
Troubleshooting
flutter: command not found in Codespaces
Rebuild the container: F1 → Codespaces: Rebuild Container.
The devcontainer uses ghcr.io/cirruslabs/flutter:stable and installs Flutter automatically.

Web preview not opening
Make sure you ran with the web server flag:

bash
Copy code
flutter run -d web-server --web-hostname 0.0.0.0 --web-port 3000
Then open Port 3000 in Codespaces.

License
MIT

css
Copy code

If you want me to add this file to your repo or tweak any section (e.g., screenshots, more tests), tel