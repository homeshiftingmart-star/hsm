# Home Shifting Mart (HSM) - Flutter Mobile App

A complete Flutter-based mobile application for Home Shifting Mart customer booking system. This production-ready demo app includes all features from the SRS document.

## ✅ Project Status: COMPLETE & READY TO BUILD APK

### 🎯 Features Implemented

#### 1. **Home Screen** ✓
- Company branding (HSM Logo)
- Service cards (Home Shifting, Office, Packing, Vehicle)
- Call & WhatsApp contact buttons
- Responsive design

#### 2. **Services Screen** ✓
- 4 services with descriptions
- Service features and icons
- Clickable "Book This Service" buttons

#### 3. **Booking Form** ✓
- Customer name, phone, addresses
- Form validation
- Notes/special instructions

#### 4. **Goods Selection** ✓
- 8 predefined items (Sofa, Bed, Table, Chair, etc.)
- Quantity selector
- Custom items input

#### 5. **Date & Time Selection** ✓
- Calendar date picker
- 8 time slots (08:00 AM - 06:00 PM)
- Separate survey date/time

#### 6. **Booking Review** ✓
- Complete booking summary
- All details organized by category

#### 7. **Booking Confirmation** ✓
- Auto-generated Booking ID
- Success animation
- Next steps information

## Project Structure

```
lib/
├── main.dart                          # App entry point
└── screens/
    ├── home_screen.dart               # Home screen with services
    ├── services_screen.dart           # Service selection screen
    ├── booking_form_screen.dart       # Customer details form
    ├── goods_selection_screen.dart    # Goods selection with quantity
    ├── date_time_selection_screen.dart # Date & time pickers
    ├── confirmation_screen.dart       # Booking review screen
    └── booking_success_screen.dart    # Success confirmation
```

## Requirements

- Flutter 3.0 or higher
- Dart 3.0 or higher
- Android SDK (for Android app)
- iOS SDK (for iOS app - optional)

## Dependencies

- `google_fonts`: For custom fonts
- `intl`: For date formatting
- `url_launcher`: For phone calls and WhatsApp integration

## Installation & Setup

1. Clone or navigate to the project directory
2. Run `flutter pub get` to install dependencies
3. Run `flutter run` to launch the app on connected device or emulator

## Building APK

```bash
flutter build apk --release
```

For split APKs:
```bash
flutter build apk --split-per-abi --release
```

## App Flow

1. **Home Screen** → Browse services and company info
2. **Service Selection** → Choose desired shifting service
3. **Booking Form** → Enter customer details and addresses
4. **Goods Selection** → Select items and quantities
5. **Date & Time Selection** → Choose shifting and survey dates
6. **Booking Review** → Review all booking details
7. **Confirmation** → Get booking ID and next steps

## Features Included

✓ Service selection with descriptions
✓ Multi-step booking form with validation
✓ Goods selection with quantity management
✓ Date picker for shifting and survey dates
✓ Time slot selection
✓ Complete booking review
✓ Booking confirmation with ID
✓ Call and WhatsApp integration (links)
✓ Responsive UI for all screen sizes
✓ Professional Material Design UI

## Future Enhancements

- OTP-based login
- Booking history
- Live tracking
- Price estimation
- Online payment integration
- Push notifications
- Real database backend

## Platform Support

- ✓ Android 8.0 and above
- iOS (optional, can be enabled)

## Demo Notes

This is a frontend-only demo application. The booking submission currently shows a success screen without backend integration. To integrate with a real backend:

1. Set up Firebase or custom API
2. Implement authentication
3. Connect booking form to database
4. Add email notifications
5. Implement admin panel

## Contact

For inquiries or support:
- Phone: +91 98765 43210
- Email: info@homeshiftingmart.com

---

**Note**: This is a demo application created for demonstration purposes.
