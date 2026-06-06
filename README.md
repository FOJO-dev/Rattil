# القرآن الكريم - Quran Recitation App

A lightweight, elegant Quran reading and recitation assistant app built with Flutter. Features Arabic text display, ayah-by-ayah audio playback, voice recording with basic recitation analysis, progress tracking, and dark/light mode support with a beautiful Islamic green + gold theme.

## ✨ Features

- **Full Quran Text** - All 114 surahs with complete Arabic text
- **Audio Playback** - Ayah-by-ayah recitation streaming (Mishary Al-Afasy)
- **Voice Recording** - Record your recitation and get basic feedback
- **Verse Highlighting** - Current verse highlighted during playback/reading
- **Progress Tracking** - Saves last read verse automatically
- **RTL Support** - Full right-to-left layout for Arabic
- **Dark/Light Mode** - Elegant green + gold Islamic theme
- **Minimal UI** - Clean, distraction-free reading experience

## 📱 Screenshots

(Add screenshots here once built)

## 🛠️ Prerequisites

Before you begin, ensure you have the following installed:

1. **Flutter SDK** (>=3.0.0)
   - Download from: https://flutter.dev/docs/get-started/install
   - Verify installation: `flutter --version`

2. **Android Studio** (for Android development)
   - Download from: https://developer.android.com/studio
   - Install Android SDK (API 21+)

3. **Git** (optional, for version control)
   - Download from: https://git-scm.com/

## 🚀 Setup Instructions

### Step 1: Install Flutter

```bash
# Windows - Download and extract Flutter SDK, then add to PATH:
# Download from https://docs.flutter.dev/get-started/install/windows
# Extract to C:\src\flutter
# Add to User PATH: C:\src\flutter\bin

# Verify installation:
flutter doctor
```

### Step 2: Get the Code

```bash
# Navigate to the project directory
cd quran_app

# Install dependencies
flutter pub get
```

### Step 3: Run the App

```bash
# For Android (connect a device or start emulator)
flutter run

# Or build APK directly:
flutter build apk --debug
# The APK will be at: build/app/outputs/flutter-apk/app-debug.apk

# For release build:
flutter build apk --release
```

### Step 4: Install on Device

1. Locate the built APK: `build/app/outputs/flutter-apk/app-debug.apk`
2. Transfer to your Android device
3. Enable "Install from Unknown Sources" in Settings
4. Tap the APK to install

## 📁 Project Structure

```
quran_app/
├── lib/
│   ├── main.dart                 # App entry point
│   ├── app.dart                  # App shell with navigation
│   ├── models/
│   │   ├── surah.dart            # Surah data model
│   │   ├── verse.dart            # Verse data model
│   │   └── reading_progress.dart # Progress tracking model
│   ├── data/
│   │   ├── quran_repository.dart  # Data loading & search
│   │   └── quran_data.dart       # Complete Quran text (114 surahs)
│   ├── services/
│   │   ├── storage_service.dart   # Local storage (SharedPreferences)
│   │   ├── audio_service.dart     # Audio playback (just_audio)
│   │   ├── recording_service.dart # Voice recording (record)
│   │   └── recitation_analyzer.dart # Basic recitation comparison
│   ├── screens/
│   │   ├── home_screen.dart       # Home with last read & quick access
│   │   ├── surah_list_screen.dart # Searchable surah index
│   │   ├── reading_screen.dart    # Main reading & recitation screen
│   │   └── settings_screen.dart   # Theme, language, data settings
│   ├── widgets/
│   │   ├── verse_tile.dart        # Individual verse display widget
│   │   ├── surah_card.dart        # Surah list card widget
│   │   └── recitation_feedback.dart # Recitation result display
│   └── theme/
│       ├── app_colors.dart        # Green + gold color palette
│       └── app_theme.dart         # Light & dark theme definitions
├── assets/
│   ├── images/                    # App images
│   └── data/                      # Optional external data files
├── test/                          # Tests
└── pubspec.yaml                   # Dependencies & configuration
```

## 🏗️ Architecture

The app uses **Provider** for state management with a clean layered architecture:

- **Models** - Data classes for Surah, Verse, and ReadingProgress
- **Data** - Repository pattern for loading Quran text (from asset JSON or embedded data)
- **Services** - Audio playback, voice recording, storage, and recitation analysis
- **Screens** - UI screens that consume services via Provider
- **Widgets** - Reusable UI components
- **Theme** - Centralized color palette and theme configurations

## ⚙️ Key Dependencies

| Package | Version | Purpose |
|---------|---------|---------|
| provider | ^6.1.1 | State management |
| shared_preferences | ^2.2.2 | Local progress storage |
| just_audio | ^0.9.36 | Audio playback |
| record | ^5.0.4 | Voice recording |
| path_provider | ^2.1.1 | File paths for recordings |
| flutter_localizations | - | Arabic/English localization |

## 🎨 Customization

### Changing the Reciter

Edit the audio URL in `lib/services/audio_service.dart`:

```dart
String _getAyahUrl(String surahNumber, int verseNumber) {
  // Currently using Mishary Al-Afasy
  return 'https://cdn.islamic.audio/ayah/ar.alafasy/$surahNumber$verseNumber.mp3';
  // For other reciters, change the path segment:
  // ar.abdulbasit - Abdul Basit
  // ar.saoodshuraym - Saud Al-Shuraym
}
```

### Adding English Translation

1. Add translation text to the verse data in `quran_data.dart`
2. The app will display translations when toggled

### Adding More Quran Data

The app comes with all 114 surahs and complete Arabic text. To add translations or additional data formats:

1. Download a complete Quran JSON (e.g., from https://api.alquran.cloud or https://quran.com)
2. Save as `assets/data/quran.json`
3. The repository will automatically load from this file instead of the embedded data

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## 📄 License

This project is open source. The Quran text is in the public domain.

## 🙏 Acknowledgments

- Quran audio API: Islamic Network (cdn.islamic.audio)
- Flutter framework: Google
- Quran text: Open Source Quran Data

---

**تم بحمد الله**
