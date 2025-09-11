# Flutter Hello World 👋

[![Open in Codespaces](https://img.shields.io/badge/Open%20in-Codespaces-24292e?logo=github)](https://codespaces.new/ahsenelmas/flutter-hello-world)

A minimal **Flutter** “Hello, world 👋” app that runs in **GitHub Codespaces** (via Flutter Web) or locally.
Includes a sample **widget test**, default **linting**, and **GitHub Actions CI**.

---

## ✨ Features

- Runs in **GitHub Codespaces** (no local setup) — previews via Flutter Web
- **Widget test** (`flutter_test`)
- **Static analysis** (`flutter analyze`) and **format check**
- **CI** on push/PR: format → analyze → test → build web

---

## 🚀 Quick Start (GitHub Codespaces)

> If you ever see `bash: flutter: command not found`, open in **Codespaces** and **Rebuild Container** to load Flutter.

1. Open this repo in **Codespaces** (or click the badge above).
2. When the container finishes, verify Flutter:
   ```bash
   flutter --version
   flutter doctor
   ```

Run the app (Web preview):

```bash
flutter config --enable-web
flutter run -d web-server --web-hostname 0.0.0.0 --web-port 3000
```

Open the forwarded Port 3000 to see “Hello, world 👋”.

Android/iOS emulators don’t run inside Codespaces. Use Flutter Web here.
On your own machine, you can run on Android/iOS normally.

🖥️ Local Development (optional)
Install Flutter (stable): https://docs.flutter.dev/get-started/install

Fetch deps:

```bash
flutter pub get
```

Run on Chrome (or a connected device/emulator):

```bash
flutter config --enable-web
flutter run -d chrome
```

or simply:

```bash
flutter run
```

### 🧪 Tests
Run all tests:

```
flutter test
```

Sample widget test (in test/hello_widget_test.dart):

```
import 'package:flutter_test/flutter_test.dart';
import 'package:flutter_hello_world/main.dart';

void main() {
  testWidgets('shows Hello, world', (tester) async {
    await tester.pumpWidget(const MyApp());
    expect(find.text('Hello, world 👋'), findsOneWidget);
  });
}

```


### 🧹 Linting & Formatting
```bash
# Static analysis
flutter analyze
```

# Format check (same as CI)
```
flutter format --set-exit-if-changed .
```
This project uses the default flutter_lints. You can customize rules in analysis_options.yaml.

### 🤖 Continuous Integration
GitHub Actions workflow: .github/workflows/flutter.yml

On every push/PR:

Setup Flutter (stable)
```
flutter pub get
```
Format check

```
flutter analyze
```

```
flutter test
```

```
flutter build web (release)

```
Badge (add if you fork/rename):

markdown
📁 Project Structure
```bash
lib/
  main.dart                 # App entrypoint (Hello, world 👋)
test/
1  hello_widget_test.dart    # Sample widget test
.github/
  workflows/
    flutter.yml             # CI: format, analyze, test, build web
.devcontainer/
  devcontainer.json         # Codespaces image with Flutter preinstalled
```

Note: Flutter/Dart package names use underscores.
If your repo has hyphens (flutter-hello-world), the package is named with underscores (flutter_hello_world).

### 🛠️ Troubleshooting
flutter: command not found in Codespaces

Rebuild container: F1 → “Codespaces: Rebuild Container”.

Web preview not opening

Make sure you ran:

```bash
flutter run -d web-server --web-hostname 0.0.0.0 --web-port 3000
Then open Port 3000 in Codespaces.

Git LFS pre-push hook blocks pushing

Install LFS inside the container:

```bash
sudo apt-get update && sudo apt-get install -y git-lfs
git lfs install
```

Or remove the hook if LFS isn’t needed:

```bash
rm -f .git/hooks/pre-push
```

### 📜 License
MIT

Want me to tweak anything (screenshots, a “Deploy to Pages” section, stricter lints, or an Issue template)?

