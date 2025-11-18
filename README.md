# Money Assistant – Expense & Budget Tracker

> A Flutter-based personal finance app for tracking daily expenses and income, analyzing spending, and staying on top of your budget.

![MMAS (820 x 360 px)](https://user-images.githubusercontent.com/72301141/206877824-90492e92-2e2d-4de6-b23c-312f283bdfd6.png)

Money Assistant is a mobile app built with Flutter and Dart.
It helps you record transactions quickly, categorize your spending, view calendar and chart-based analysis, and manage your money more intelligently.

---

## Features

- **Transaction tracking**
  - Add **income** and **expense** entries with amount, category, description, date, and time.
  - Edit and delete existing records.
  - Local SQLite (`sqflite`) storage, fully offline.

- **Rich categories**
  - Predefined categories such as:
    - Food & Beverages, Transport, Personal Development, Shopping, Entertainment, Home, Utility Bills, Health, Gifts & Donations, Kids, Other.
  - Subcategories (e.g. Fuel, Tuition, Games, Travel, etc.).
  - Stored and customizable via `shared_preferences`.

- **Analysis & reports**
  - Overview and analysis screens for your spending and income.
  - Calendar view of transactions.
  - Chart-based insights using **Syncfusion Flutter Charts**.

- **Multilingual UI**
  - Custom localization system with JSON language files.
  - Supported languages include:
    - English, German, Spanish, French, Hindi, Japanese, Korean, Portuguese, Russian, Turkish, Vietnamese, Chinese, Nepali.

- **Security & app experience**
  - Optional passcode lock (via screen lock packages).
  - “Rate this app” dialog integration.
  - Responsive UI using **flutter_screenutil**.

- **Authentication (extensible)**
  - Basic login/sign-up flow built with `flutter_login`.
  - Google sign-in wiring prepared via `google_sign_in` and `firebase_auth` (can be extended for full auth flows).

---

## Tech stack

- **Framework:** Flutter
- **Language:** Dart (>= 2.12, null safety)
- **State management:** `provider`
- **Local storage:**
  - `sqflite` for the main transaction database.
  - `shared_preferences` for settings, categories, and configuration.
- **UI / UX libraries:**
  - `flutter_screenutil`
  - `table_calendar`
  - `sliding_up_panel`
  - `flutter_swipe_action_cell`
  - `fluttertoast`
  - `day_night_time_picker`
- **Charts & visualization:** `syncfusion_flutter_charts`
- **Auth & services:**
  - `google_sign_in`
  - `firebase_auth`
  - `firebase_core`
- **Misc:**
  - `rate_my_app`
  - `in_app_review`
  - `share_plus`
  - Icon packs: `material_design_icons_flutter`, `font_awesome_flutter`, `outline_material_icons`, `flutter_boxicons`, `icofont_flutter`

For all dependencies and versions, see [`pubspec.yaml`](./pubspec.yaml).

---

## Getting started

### Prerequisites

- Flutter SDK installed and configured  
  (see the official docs: https://docs.flutter.dev/get-started/install)
- A working emulator or device (Android or iOS).

### Clone and install dependencies

```bash
git clone https://github.com/floranguyen0/mmas-money-tracker
cd mmas-money-tracker
flutter pub get
```

### Run the app

From the project root:

```bash
flutter run
```

Flutter will ask you to select a device/emulator if multiple are available.

---

## Project structure

High-level structure of the main app code:

```text
lib/
  main.dart                    # Entrypoint; delegates to real_main.dart
  project/
    real_main.dart             # App initialization, localization, root MaterialApp
    home.dart                  # Bottom navigation and main tab pages

    auth_pages/
      sign_in.dart             # Login/signup screen (FlutterLogin-based)

    app_pages/
      input.dart               # Add income/expense transactions
      analysis.dart            # Analysis and reports
      calendar.dart            # Calendar-based view
      others.dart              # Other settings and options

    database_management/
      sqflite_services.dart    # SQLite DB (CRUD for transactions)
      shared_preferences_services.dart  # Categories, settings, flags, etc.

    localization/
      app_localization.dart    # Custom localization loader
      methods.dart             # Helpers (e.g. getTranslated)
      lang/                    # JSON language files

    classes/
      input_model.dart         # Model for a single transaction
      category_item.dart       # Model for categories
      constants.dart           # UI constants (colors, etc.)

    provider.dart              # ChangeNotifier classes for app state
```

---

## Localization

To add or adjust translations:

- Edit the JSON files in `lib/project/localization/lang/`.
- Each file corresponds to a language (e.g. `en.json`, `de.json`, `es.json`, etc.).
- Keys are loaded by `AppLocalization` and used via `getTranslated(context, key)`.

---

## Contributing

Pull requests and issues are welcome.

- Fork the repository.
- Create a feature branch.
- Make your changes and add appropriate tests (if applicable).
- Open a pull request with a clear description of the changes.

---

## License

Money Assistant is [MIT-licensed](https://github.com/floranguyen0/mmas-money-tracker/blob/main/LICENSE).
