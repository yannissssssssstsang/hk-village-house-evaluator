# HK Village House Evaluator - Android Native App

## Project Overview

A comprehensive native Android application built with **Kotlin** and **Jetpack Compose** to evaluate Hong Kong Village Houses (村屋) for potential renters and buyers.

### Core Capabilities

**Core 1: Address Search & Property Metadata Retrieval**
- Text-based address search with autocomplete
- Map pin-drop property selection
- Property specifications: transaction prices, building age, renovation history
- Lot boundary analysis (private vs. government land) from CSDI

**Core 2: Risk Incident Checking (凶宅 Detection)**
- Historical incident database: unnatural deaths, accidents
- Risk level assessment and alerts
- Incident source attribution and verification status
- Timeline tracking

**Core 3: Environmental & Spatial Analysis**
- Solar exposure calculation (seasonal sunlight hours)
- Afternoon heat analysis (西斜 - west-facing detection)
- Viewshed and ventilation scoring
- 3D spatial modeling

**Core 4: 3D Map Visualization**
- Interactive 3D building rendering
- Terrain integration
- Native map controls

## Architecture

**Pattern**: MVVM + Clean Architecture
- **Presentation Layer**: Jetpack Compose UI
- **Domain Layer**: Use cases and business logic
- **Data Layer**: Repository pattern with multiple API clients

## API Integration Scaffolding

### 1. **CSDI Portal API**
- 3D building visualization data
- Lot boundaries and property metadata
- Building age and transaction history
- Source: Hong Kong Lands Department CSDI

### 2. **HKeMobility API**
- Transit accessibility (MTR, bus, minibus stations)
- Walking distance calculations
- Route optimization

### 3. **Census & Statistics API**
- Population density analysis
- Demographic data by village/district
- Education and income statistics

### 4. **Incidents API**
- Unnatural death tracking (凶宅)
- Accident history
- Risk assessment scoring
- Data source attribution

## Dependencies

### Android Core
- AndroidX Core KTX
- Jetpack Compose UI Suite
- Navigation Compose

### Networking
- Retrofit 2.10.0
- OkHttp 4.11.0
- Gson 2.10.1

### Database
- Room 2.6.1

### DI & Async
- Hilt 2.50
- Kotlin Coroutines 1.7.3

### Maps & Graphics
- Google Play Services Maps 18.2.0
- Filament 3D Graphics 1.50.5

## Project Structure

```
hk-village-house-evaluator/
├── app/
│   └── src/main/
│       ├── kotlin/com/hk/villagehaus/
│       │   ├── ui/
│       │   │   ├── screens/
│       │   │   ├── components/
│       │   │   └── theme/
│       │   ├── data/
│       │   │   ├── api/
│       │   │   │   ├── csdi/
│       │   │   │   ├── hkemobility/
│       │   │   │   ├── census/
│       │   │   │   └── incidents/
│       │   │   ├── repository/
│       │   │   ├── local/
│       │   │   └── model/
│       │   ├── domain/
│       │   │   ├── usecase/
│       │   │   └── model/
│       │   ├── utils/
│       │   │   ├── spatial/
│       │   │   ├── location/
│       │   │   └── analytics/
│       │   └── MainActivity.kt
│       └── res/
├── build.gradle.kts
├── settings.gradle.kts
└── .gitignore
```

## Quick Start

```bash
git clone https://github.com/yannissssssssstsang/hk-village-house-evaluator.git
cd hk-village-house-evaluator
./gradlew build
./gradlew installDebug
```

## Development Workflow

### Branch Strategy
- `main` - Production releases
- `develop` - Integration branch
- `feature/core1-*` - Address search
- `feature/core2-*` - Incident checking
- `feature/core3-*` - Environmental analysis
- `feature/core4-*` - 3D visualization

## API Keys

Add to `local.properties`:
```properties
google.maps.api.key=YOUR_KEY
csdi.api.key=YOUR_KEY
hkemobility.api.key=YOUR_KEY
```

## Contributing

See CONTRIBUTING.md for guidelines.

## License

MIT License
