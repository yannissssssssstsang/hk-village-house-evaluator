# Development Guide

## Setting Up the Project

### Prerequisites
- Android Studio Flamingo or later
- Java 17 JDK
- Kotlin 1.9+
- Google Play Services SDK

### Initial Setup

1. Clone the repository
2. Create `local.properties` with API keys
3. Build: `./gradlew build`

## Architecture

MVVM pattern with Repository layer for data access:
- **UI Layer**: Jetpack Compose screens
- **ViewModel Layer**: Business logic and state
- **Repository Layer**: Data access
- **Network Layer**: Retrofit API calls

## Using HK Government Data

### Available Data Sources

1. **Land Registry** - Property registration and transaction records
2. **Rating & Valuation Department** - Property assessments and valuations
3. **Buildings Department** - Building records and information
4. **Open Data Portal** - Government open datasets

### Data Integration

API calls are managed through `HKDataApi` interface in `network/` package.

## Building & Testing

```bash
./gradlew build       # Build project
./gradlew test        # Run unit tests
./gradlew installDebug # Install debug APK
```

## Code Style

- Language: Kotlin
- Naming: camelCase (variables), PascalCase (classes)
- Max line length: 120 characters
