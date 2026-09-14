# Chess Infinity

> Application Flutter de gestion de tournois d'échecs. **Prototype à un stade précoce** — ce qui existe aujourd'hui est l'écran de lancement de la marque, avec son logo animé, et l'ossature multiplateforme derrière.

[![Flutter](https://img.shields.io/badge/Flutter-02569B?logo=flutter&logoColor=white)](https://flutter.dev/)
[![Dart](https://img.shields.io/badge/Dart-0175C2?logo=dart&logoColor=white)](https://dart.dev/)
[![Plateformes](https://img.shields.io/badge/plateformes-Android%20·%20iOS%20·%20Web%20·%20Desktop-lightgrey)](#plateformes)
[![Statut](https://img.shields.io/badge/statut-prototype-orange)](#état-du-projet)
[![Licence : MIT](https://img.shields.io/badge/Licence-MIT-yellow.svg)](LICENSE)

🇬🇧 [Read this document in English](README.md)

<p align="center">
  <img src="docs/assets/logo.png" alt="Logo Chess Infinity" width="160">
</p>

---

## État du projet

À lire avant tout le reste, pour que ce dépôt ne soit pas pris pour plus qu'il n'est.

**Ce qui est construit :**
- Écran de lancement de la marque — logo animé accompagné du mot-symbole *Chess Infinity*
- `AnimatedLogo`, un `StatefulWidget` personnalisé combinant une animation d'échelle et de rotation sur 800 ms avec une courbe `easeOut`, piloté par un seul `AnimationController`
- Typographie Kanit câblée dans `pubspec.yaml`, couleur de marque `#511465`
- Ossature Flutter complète pour six plateformes cibles, avec un widget test en place

**Ce qui n'est pas encore construit :** création de tournois, inscription des joueurs, appariements (système suisse ou toutes rondes), saisie des résultats, classements, et toute forme de persistance.

Le code applicatif représente **140 lignes de Dart réparties sur deux fichiers**. Tout le reste du dépôt est l'ossature de plateforme générée par Flutter.

---

## Ce que le projet doit devenir

Une application de gestion de tournois pour le club Chess Infinity : création de tournois, inscription des joueurs, génération des appariements, saisie des résultats et publication des classements.

---

## Code

```
lib/
├── main.dart           82 lignes — MaterialApp, thème, écran de lancement
└── animated_logo.dart  58 lignes — widget du logo animé
```

`AnimatedLogo` prend un paramètre `size` (40 par défaut) et combine deux tweens sur un seul contrôleur :

```dart
_scale    = Tween<double>(begin: 0.0, end: 1.0).animate(curved);
_rotation = Tween<double>(begin: -0.5, end: 0.0).animate(curved);
```

Le logo grandit depuis rien tout en pivotant jusqu'à sa position — un seul geste `easeOut` de 800 ms plutôt que deux animations distinctes.

## Plateformes

L'ossature cible Android, iOS, Web, Windows, macOS et Linux. Seul l'écran de lancement y a été éprouvé.

## Exécution

```bash
flutter pub get
flutter run
```

Nécessite le SDK Flutter. `android/local.properties` dépend de la machine et n'est pas versionné — il est régénéré au premier build.

## Assets et polices

- **Kanit** (`assets/fonts/kanit/`) — SIL Open Font License, voir `OFL.txt`
- `assets/logo.png` — logo du projet

> Une copie inutilisée de la famille de polices Inter (20 Mo, jamais déclarée dans `pubspec.yaml`) a été retirée de ce dépôt.

## Licence

[MIT](LICENSE) pour le code. Les polices embarquées conservent leurs licences propres.
