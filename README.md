# Favorite Places

A cross-platform mobile application built with Flutter that allows users to capture, save, and manage their favorite locations with images and precise geographic coordinates. The app provides a seamless experience for documenting memorable places with camera integration, location services, and persistent local storage.

## Features

- **Add New Places**: Capture locations with custom titles and photos
- **Camera Integration**: Take photos directly from the app or select from gallery
- **Location Services**: Automatically capture GPS coordinates for precise location mapping
- **Interactive Maps**: View saved places on embedded maps with accurate positioning
- **Persistent Storage**: Local SQLite database ensures data persistence across app sessions
- **Modern UI**: Material Design 3 with dark theme and responsive layout
- **Cross-Platform**: Works seamlessly on both Android and iOS devices
- **State Management**: Efficient state handling using Flutter Riverpod

## How It Works

### Adding a Favorite Place
1. Tap the "+" button on the main screen
2. Enter a descriptive title for your location
3. Take a photo using the camera or select from gallery
4. Allow location access to automatically capture GPS coordinates
5. Save the place to your collection

### Viewing Places
- Browse your saved places in an organized list view
- Each place displays a thumbnail image and title
- Tap any place to view full details and location on map

### Place Details
- View full-size images of your saved locations
- See precise coordinates and location information
- Interactive map integration for geographic context

## Installation & Setup

### Prerequisites
- Flutter SDK (3.0.0 or higher)
- Dart SDK (2.17.0 or higher)
- Android Studio / VS Code with Flutter extensions
- Android device/emulator or iOS device/simulator

### Getting Started

1. **Clone the repository**
   ```bash
   git clone https://github.com/yourusername/favorite-places.git
   cd favorite-places
   ```

2. **Install dependencies**
   ```bash
   flutter pub get
   ```

3. **Configure platform-specific settings**
   
   **Android** - Add to `android/app/src/main/AndroidManifest.xml`:
   ```xml
   <uses-permission android:name="android.permission.CAMERA" />
   <uses-permission android:name="android.permission.ACCESS_FINE_LOCATION" />
   <uses-permission android:name="android.permission.ACCESS_COARSE_LOCATION" />
   ```

   **iOS** - Add to `ios/Runner/Info.plist`:
   ```xml
   <key>NSCameraUsageDescription</key>
   <string>This app needs camera access to take photos of places</string>
   <key>NSLocationWhenInUseUsageDescription</key>
   <string>This app needs location access to save place coordinates</string>
   ```

4. **Run the application**
   ```bash
   flutter run
   ```

## Project Structure

```
lib/
├── main.dart                 # App entry point and theme configuration
├── models/
│   └── place.dart           # Place data model with UUID generation
├── providers/
│   └── user_places.dart     # State management and SQLite operations
├── screens/
│   ├── places.dart          # Main screen displaying saved places
│   ├── add_place.dart       # Add new place form screen
│   └── place_detail.dart    # Individual place detail view
└── widgets/
    ├── places_list.dart     # List widget for displaying places
    ├── image_input.dart     # Camera/gallery image picker widget
    └── location_input.dart  # Location services integration widget
```

## Architecture

The app follows a clean architecture pattern with clear separation of concerns:

- **Models**: Data structures and business logic (`Place` class)
- **Providers**: State management using Riverpod with `StateNotifier`
- **Screens**: Full-page UI components for navigation
- **Widgets**: Reusable UI components for specific functionality
- **Database**: SQLite integration for persistent local storage

### Key Components

- **UserPlacesNotifier**: Manages app state and database operations
- **Place Model**: Represents location data with UUID, title, and image
- **Database Layer**: SQLite setup with async operations for CRUD functionality

## Dependencies

- `flutter_riverpod`: State management solution
- `sqflite`: SQLite database for local storage
- `image_picker`: Camera and gallery integration
- `location`: GPS and location services
- `path_provider`: File system path access
- `google_fonts`: Custom typography (Ubuntu Condensed)
- `uuid`: Unique identifier generation

## Development

### Database Schema
```sql
CREATE TABLE user_places(
  id TEXT PRIMARY KEY,
  title TEXT,
  image TEXT
);
```

### Adding New Features
1. Create feature branch from `main`
2. Implement changes following existing architecture patterns
3. Add appropriate tests
4. Submit pull request with detailed description

## Contributing

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add some amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

Built with ❤️ using Flutter
