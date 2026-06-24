# HK Village House Evaluator - Setup Instructions

## Quick Start

### 1. Prerequisites
```bash
# Android Studio 2023.2+
# Kotlin 1.9+
# Java 17+
# Android SDK 34+
```

### 2. Clone & Setup
```bash
git clone https://github.com/yannissssssssstsang/hk-village-house-evaluator.git
cd hk-village-house-evaluator
```

### 3. Configure API Keys
Create `local.properties`:
```properties
sdk.dir=/path/to/android/sdk
google.maps.api.key=YOUR_GOOGLE_MAPS_KEY
hk.data.api.key=YOUR_HK_DATA_API_KEY
```

### 4. Build & Run

**Option A: Android Studio**
1. Open project in Android Studio
2. Click Run (Shift + F10)

**Option B: Command Line**
```bash
# Make scripts executable
chmod +x build.sh install.sh

# Build
./build.sh

# Install on device
./install.sh
```

### 5. API Keys Setup

#### Google Maps API
1. Visit [Google Cloud Console](https://console.cloud.google.com)
2. Create new project
3. Enable Maps SDK for Android
4. Create API key
5. Add to AndroidManifest.xml

#### HK Government Data APIs
- Land Registry: https://www.landreg.gov.hk/
- Rating & Valuation: https://www.rvd.gov.hk/
- Buildings Department: https://www.bd.gov.hk/
- Open Data Portal: https://data.gov.hk/

## Project Structure

```
hk-village-house-evaluator/
├── app/
│   ├── src/main/
│   │   ├── kotlin/com/hkvillage/evaluator/
│   │   │   ├── ui/              # Compose screens & navigation
│   │   │   ├── network/         # API interfaces
│   │   │   ├── repository/      # Data access layer
│   │   │   ├── model/           # Data models
│   │   │   ├── util/            # Utilities
│   │   │   ├── di/              # Dependency injection
│   │   │   └── component/       # Reusable UI components
│   │   ├── res/                 # Resources (strings, themes, XML)
│   │   └── AndroidManifest.xml
│   ├── build.gradle.kts
│   └── proguard-rules.pro
├── build.gradle.kts
├── settings.gradle.kts
├── build.sh                     # Build script
├── install.sh                   # Install script
├── README.md
├── DEVELOPMENT.md
├── CONTRIBUTING.md
└── LICENSE
```

## Features

✅ Property search with government data
✅ Map-based browsing
✅ Price estimation
✅ Market statistics
✅ Material Design 3 UI
✅ Offline caching
✅ Location-based search

## Troubleshooting

### Build Issues
```bash
# Clean cache
./gradlew clean

# Update gradle
./gradlew wrapper --gradle-version latest
```

### API Connection
- Check network connectivity
- Verify API keys in local.properties
- Check firewall/proxy settings

### Device Issues
```bash
# List connected devices
adb devices

# Clear app data
adb shell pm clear com.hkvillage.evaluator

# Restart adb
adb kill-server
adb start-server
```

## Development Workflow

1. Create feature branch: `git checkout -b feature/your-feature`
2. Make changes
3. Run tests: `./gradlew test`
4. Commit: `git commit -am 'Add feature description'`
5. Push: `git push origin feature/your-feature`
6. Create Pull Request

## Next Steps

1. ✅ Add property database entities
2. ✅ Implement API data fetching
3. ✅ Add offline caching
4. ✅ Implement Google Maps integration
5. ✅ Add property filtering options
6. ✅ Implement favorites/bookmarks
7. ✅ Add user ratings and reviews
8. ✅ Release to Play Store

## Support

For issues and questions:
- Open a GitHub Issue
- Check existing discussions
- Review CONTRIBUTING.md

Happy coding! 🎉
