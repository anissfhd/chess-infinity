# Chess Infinity

> Flutter application for managing chess tournaments. **Early prototype** — what exists today is the branded launch screen with an animated logo and the full cross-platform scaffold behind it.

[![Flutter](https://img.shields.io/badge/Flutter-02569B?logo=flutter&logoColor=white)](https://flutter.dev/)
[![Dart](https://img.shields.io/badge/Dart-0175C2?logo=dart&logoColor=white)](https://dart.dev/)
[![Platforms](https://img.shields.io/badge/platforms-Android%20·%20iOS%20·%20Web%20·%20Desktop-lightgrey)](#platforms)
[![Status](https://img.shields.io/badge/status-prototype-orange)](#project-status)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

🇫🇷 [Lire ce document en français](README.fr.md)

<p align="center">
  <img src="docs/assets/logo.png" alt="Chess Infinity logo" width="160">
</p>

---

## Project status

Read this before anything else, so the repository is not mistaken for more than it is.

**What is built:**
- Branded launch screen — animated logo paired with the *Chess Infinity* wordmark
- `AnimatedLogo`, a custom `StatefulWidget` running a combined scale and rotation animation over 800 ms with an `easeOut` curve, driven by a single `AnimationController`
- Kanit typography wired through `pubspec.yaml`, brand colour `#511465`
- Complete Flutter scaffold for six target platforms, with a widget test in place

**What is not built yet:** tournament creation, player registration, pairing (Swiss or round-robin), result entry, standings, and any form of persistence.

The application code is **140 lines of Dart across two files**. Everything else in this repository is Flutter's generated platform scaffolding.

---

## What it is meant to become

A tournament management application for the Chess Infinity club: creating tournaments, registering players, generating pairings, recording results and publishing standings.

---

## Code

```
lib/
├── main.dart           82 lines — MaterialApp, theme, launch screen
└── animated_logo.dart  58 lines — animated logo widget
```

`AnimatedLogo` takes a `size` parameter (default 40) and combines two tweens off one controller:

```dart
_scale    = Tween<double>(begin: 0.0, end: 1.0).animate(curved);
_rotation = Tween<double>(begin: -0.5, end: 0.0).animate(curved);
```

The logo scales up from nothing while rotating into place — a single 800 ms `easeOut` gesture rather than two separate animations.

## Platforms

The scaffold targets Android, iOS, Web, Windows, macOS and Linux. Only the launch screen has been exercised on them.

## Running it

```bash
flutter pub get
flutter run
```

Requires the Flutter SDK. `android/local.properties` is machine-specific and is not committed — it is regenerated on first build.

## Assets and fonts

- **Kanit** (`assets/fonts/kanit/`) — SIL Open Font License, see `OFL.txt`
- `assets/logo.png` — project logo

> An unused copy of the Inter font family (20 MB, never declared in `pubspec.yaml`) was removed from this repository.

## License

[MIT](LICENSE) for the code. Bundled fonts keep their own licenses.
