# Simple QR Code Scanner and Generator App (Android)

This Android application allows users to both scan QR codes using their device's camera and generate QR codes from text input.

## Overview

The `MainActivity` class provides the main functionality of the application. It includes the following features:

* **Scanning QR Codes:** Uses the `zxing-android` library to integrate a camera-based QR code scanning functionality.
* **Generating QR Codes:** Takes text input from the user and generates a corresponding QR code image.

## Functionality

The main screen (`activity_main.xml` layout, not shown here) contains the following interactive elements:

* **Text View (`tv_scan_result`):** Displays the result of a successful QR code scan.
* **Edit Text (`et_qr_string`):** Allows the user to enter text to be encoded into a QR code.
* **Image View (`iv_qr_image`):** Displays the generated QR code image.
* **Button (`btn_scan_barcode`):** When clicked, it launches the camera activity for scanning a QR code.
* **Button (`btn_add_qrcode`):** When clicked, it takes the text from the `EditText` and generates a QR code, which is then displayed in the `ImageView`.

### Scanning a QR Code

1.  Click the "Scan Barcode" button.
2.  This will open the camera interface provided by the `CaptureActivity` from the `zxing-android` library.
3.  Point the camera at a QR code.
4.  If the scan is successful, the decoded text from the QR code will be displayed in the `TextView` (`tv_scan_result`).

### Generating a QR Code

1.  Enter the desired text into the `EditText` (`et_qr_string`).
2.  Click the "Generate QR Code" button.
3.  A QR code representing the entered text will be generated and displayed in the `ImageView` (`iv_qr_image`).
4.  If the `EditText` is empty when the "Generate QR Code" button is clicked, a toast message will inform the user that the text cannot be empty.

## Dependencies

This application relies on the following external library:

* **`zxing-android`:** This library provides the necessary components for capturing (scanning) and encoding (generating) QR codes and barcodes. The specific dependencies are likely managed through Gradle in the project's `build.gradle` files (not shown here). You would typically see dependencies like:
    ```gradle
    implementation 'com.journeyapps:zxing-android-embedded:3.x.x' // For the CaptureActivity
    implementation 'com.google.zxing:core:3.x.x' // For the core ZXing functionality
    ```

## Getting Started (Conceptual)

To build and run this application, you would typically:

1.  Set up an Android development environment with Android Studio.
2.  Create a new Android project or open an existing one.
3.  Add the necessary `zxing-android` library dependencies to your project's `build.gradle` files.
4.  Create the layout file (`activity_main.xml`) with the described UI elements.
5.  Copy this `MainActivity.java` file into your project's source code directory.
6.  Build and run the application on an Android emulator or a physical Android device.

## Notes

* This code snippet focuses on the `MainActivity` logic. The layout file (`activity_main.xml`) and the implementation details of the `CaptureActivity` and `EncodingHandler` (from the `zxing-android` library) are not included here.
* Error handling for camera permissions and potential exceptions during QR code generation could be further enhanced in a production application.
* The size of the generated QR code (350 pixels in this case) can be adjusted in the `EncodingHandler.createQRCode()` method.
