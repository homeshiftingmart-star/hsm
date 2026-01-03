# HSM App - Testing & Verification Guide

## ✅ Pre-Installation Checklist

Before installing the APK, make sure you have:

- [ ] Android device with Android 5.0 or higher
- [ ] 100 MB free storage space
- [ ] USB cable (if installing via computer)
- [ ] APK file: `app-release.apk`

## 📦 How to Install APK

### Method 1: Via USB Cable (Recommended)

1. Connect Android phone to computer via USB
2. Enable USB Debugging on phone:
   - Settings → About Phone → Tap "Build Number" 7 times
   - Go back → Developer Options → Enable USB Debugging
3. Run in PowerShell:
   ```powershell
   $env:PATH += ";D:\flutter\bin"
   adb install "d:\Kundan\kunadan app\app\hsm_app\build\app\outputs\flutter-apk\app-release.apk"
   ```

### Method 2: Direct APK Transfer

1. Copy APK file to phone's storage via USB
2. Open file manager on phone
3. Navigate to the APK file
4. Tap to install
5. Grant permissions if prompted

### Method 3: Email/Cloud

1. Send APK via email or upload to Google Drive
2. Download on phone
3. Open file manager and tap to install

## 🎯 Testing Flow (10-15 minutes)

After installation, follow this complete testing sequence:

### **Test 1: App Launch** (1 minute)
- [ ] App icon appears on home screen
- [ ] App launches without crashing
- [ ] Home Screen displays correctly

### **Test 2: Home Screen** (2 minutes)
**Expected UI:**
- HSM company header at top
- 4 service cards visible:
  - Home Shifting (Blue - H icon)
  - Office Relocation (Green - O icon)
  - Packing & Moving (Orange - P icon)
  - Vehicle Transport (Red - V icon)
- Contact section with phone/WhatsApp buttons
- "Book Now" button at bottom

**Actions to verify:**
- [ ] Scroll down to see all content
- [ ] All 4 service cards fully visible
- [ ] Tap any service card → Goes to Services Screen
- [ ] Contact buttons are visible and tappable

### **Test 3: Services Screen** (2 minutes)
**Expected UI:**
- Service name at top
- Service icon in circle
- Service description
- Features list (3-4 points)
- "Book This Service" button

**Services to check:**
- [ ] Tap "Home Shifting" from home → Shows home shifting details
- [ ] Tap "Book This Service" → Goes to Booking Form
- [ ] Go back and try another service (Office Relocation)
- [ ] Verify all 4 services have correct info

### **Test 4: Booking Form Screen** (3 minutes)
**Expected fields:**
- Customer Name (text input)
- Mobile Number (number input, 10 digits)
- From Address (location picker or text)
- To Address (location picker or text)
- Notes (optional text area)

**Validation tests:**
- [ ] Leave Name empty, try Next → Should show error
- [ ] Enter 5-digit phone number, try Next → Should show error
- [ ] Enter all required fields with valid data:
  - Name: "Raj Kumar"
  - Phone: "9876543210"
  - From: "123 Main Street, Delhi"
  - To: "456 Oak Avenue, Bangalore"
- [ ] Tap "Next" → Goes to Goods Selection Screen
- [ ] Verify data is remembered if going back

### **Test 5: Goods Selection Screen** (3 minutes)
**Expected items:**
- Sofa, Bed, Table, Chair, Fridge, Washing Machine, TV, Boxes

**Actions to test:**
- [ ] Tap items to select (should highlight)
- [ ] Tap selected item again to deselect
- [ ] Long press on item to adjust quantity:
  - Quantity increases from 1 → 2 → 3 etc.
  - Quantity decreases back to 1 and deselects
- [ ] Select at least 3 items with various quantities
- [ ] Can add custom items in text field
- [ ] Tap "Next" → Goes to Date/Time Selection

**Example selection:**
- Sofa (qty 1)
- Bed (qty 2)
- Table (qty 1)
- Fridge (qty 1)

### **Test 6: Date & Time Selection Screen** (3 minutes)
**Expected sections:**
1. **Shifting Date & Time**
   - Calendar icon
   - "Select Shifting Date" button
   - 8 time slots displayed

2. **Survey/Visiting Date & Time**
   - Calendar icon
   - "Select Survey Date" button
   - 8 time slots displayed

**Actions to test:**
- [ ] Tap "Select Shifting Date" → Date picker opens
- [ ] Select a date in future (e.g., Jan 15, 2025)
- [ ] Close date picker → Date shows in button
- [ ] Tap a time slot for shifting (e.g., 10:00 AM)
- [ ] Time slot highlights
- [ ] Repeat for Survey date and time
- [ ] All 4 selections made
- [ ] Tap "Next" → Goes to Confirmation Screen

### **Test 7: Booking Review Screen** (2 minutes)
**Expected sections:**
1. Service Details
   - Service name
   - Service icon

2. Customer Information
   - Name
   - Phone number
   - From address
   - To address

3. Goods Summary
   - List of selected items with quantities
   - Total item count

4. Shifting Details
   - Shifting date
   - Shifting time
   - Survey date
   - Survey time

5. Notes
   - Any special instructions entered

6. Action Buttons
   - "Confirm Booking" button
   - "Edit Details" button (optional)

**Actions to test:**
- [ ] Scroll to see all information
- [ ] Verify all data matches what was entered
- [ ] All dates and times are correct
- [ ] All selected goods are listed with quantities
- [ ] Tap "Confirm Booking" → Goes to Success Screen

### **Test 8: Booking Success Screen** (1 minute)
**Expected UI:**
- Success checkmark or animation
- "Booking Confirmed!" heading
- **Booking ID:** HSM-XXXXX (unique number)
- Booking summary
- Instructions for next steps:
  1. Our team will contact you within 24 hours
  2. Confirm shifting details via phone/WhatsApp
  3. Arrange payment if needed
  4. Shifting happens on scheduled date

**Actions to test:**
- [ ] Booking ID is displayed (HSM- prefix)
- [ ] Summary shows all booking details
- [ ] Contact buttons are visible
- [ ] Tap "Home" button → Returns to Home Screen
- [ ] Test complete booking flow again with different service

## 🔄 Full Flow Test Checklist

Complete this checklist for full app validation:

### **Flow 1: Home Shifting**
- [ ] Select Home Shifting service
- [ ] Enter: "Amit Sharma", "8765432109", "234 Elm St", "567 Pine Ave"
- [ ] Select: Sofa(2), Bed(1), Washing Machine(1)
- [ ] Dates: Jan 20, 10:00 AM | Jan 19, 02:00 PM
- [ ] Confirm → Get Booking ID

### **Flow 2: Office Relocation**
- [ ] Select Office Relocation
- [ ] Enter: "Priya Singh", "9123456789", "Business Center", "New Corporate Park"
- [ ] Select: Table(3), Chair(4), TV(1), Boxes(5)
- [ ] Dates: Jan 25, 02:00 PM | Jan 24, 10:00 AM
- [ ] Confirm → Get Booking ID

### **Flow 3: Packing & Moving**
- [ ] Select Packing & Moving
- [ ] Enter: "Vikram Reddy", "7654321098", "Old Location", "New Location"
- [ ] Select: Sofa(1), Bed(1), Fridge(1)
- [ ] Dates: Feb 1, 04:00 PM | Jan 31, 09:00 AM
- [ ] Confirm → Get Booking ID

## 📊 Performance Tests

### **Speed Test**
- [ ] Home Screen loads in < 2 seconds
- [ ] Screen transitions smooth (no freezing)
- [ ] Date picker opens instantly
- [ ] Forms respond immediately to input

### **Memory Test**
- [ ] No app crashes during navigation
- [ ] No crashes on rapid back/forward
- [ ] Can go through multiple bookings without restart

### **Orientation Test**
- [ ] Rotate phone portrait → landscape
- [ ] Layout adapts correctly
- [ ] All content still visible
- [ ] Inputs preserved during rotation

## 🎨 UI/UX Verification

### **Visual Elements**
- [ ] Colors are vibrant and professional
- [ ] Text is readable at normal viewing distance
- [ ] Icons are clear and recognizable
- [ ] Buttons are easily tappable
- [ ] No overlapping text or elements

### **Responsiveness**
- [ ] Works on various screen sizes
- [ ] Content doesn't overflow
- [ ] Spacing looks balanced
- [ ] Images scale properly

### **Navigation**
- [ ] Back button works correctly
- [ ] Can navigate to previous screens
- [ ] No dead ends or unresponsive buttons
- [ ] Flow is logical and intuitive

## ❌ Common Issues & Solutions

### **Issue: App crashes on launch**
**Solution:**
- Uninstall app: `adb uninstall com.example.hsm_app`
- Clear cache: Settings → Apps → HSM App → Clear Cache
- Reinstall APK

### **Issue: Form validation too strict**
**Solution:**
- Phone must be exactly 10 digits
- Name must be 3+ characters
- Addresses cannot be empty

### **Issue: Date picker not opening**
**Solution:**
- Tap the date button, not the empty space
- Make sure you're on Date/Time selection screen
- Try back and forward navigation

### **Issue: Goods selection not working**
**Solution:**
- Single tap to select/deselect
- Long press (hold 2 seconds) to change quantity
- Don't double-tap too fast

## ✅ Success Criteria

Your app is working perfectly when:

- ✅ All 7 screens load without crashes
- ✅ All form fields validate correctly
- ✅ All buttons are clickable and responsive
- ✅ Navigation is smooth between screens
- ✅ Data persists through the complete flow
- ✅ Booking ID is generated on success
- ✅ UI looks professional on your device screen
- ✅ Complete booking takes 3-5 minutes

## 📱 Device Specifications to Test

If you have multiple devices, test on:

- [ ] Android 5.0 device (oldest supported)
- [ ] Android 8.0-10.0 device (mid-range)
- [ ] Android 12+ device (latest)
- [ ] Small screen phone (4-5 inches)
- [ ] Large screen phone (6+ inches)
- [ ] Tablet (if available)

## 📸 Screenshots to Capture

For documentation, capture these screens:

1. Home Screen showing all 4 services
2. A service details screen
3. Booking form with filled data
4. Goods selection with items selected
5. Date/Time selection screen
6. Booking review screen
7. Success screen with Booking ID

## 🚀 Deployment Checklist

Before considering the app ready:

- [ ] All 7 screens tested
- [ ] Complete booking flow works (home → success)
- [ ] No crashes or errors
- [ ] All data validates correctly
- [ ] UI looks professional
- [ ] Text is readable
- [ ] Buttons are responsive
- [ ] Navigation is intuitive
- [ ] Booking IDs are unique
- [ ] Successfully tested on at least 1 Android device

## 📞 Support

If you encounter any issues:

1. Check common issues section above
2. Try reinstalling the app
3. Clear app cache and data
4. Run `flutter clean` and rebuild if needed

---

**Testing Status:** Ready for quality assurance  
**Expected Test Duration:** 30-45 minutes for complete validation  
**Target Outcome:** Verified, production-ready mobile app

**All features implemented and ready for deployment!** ✅
