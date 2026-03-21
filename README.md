# HTML-TimeSender

HTML page that connects to a BLE UART client and send Time and date to it.

An iPhone/iPad app can be found in the Apple app store: search for: BLE time sender.<br>
and an Arduino Nano ESP32 sketch here: https://github.com/ednieuw/BLE-time-Sender.

With the web page interface "Web Bluetooth" a web site can make a BLE-connection.   

See my word clock pages how time and date are set in a Nano ESP32 sketch : https://github.com/ednieuw/Arduino-ESP32-Nano-Wordclock


<img width="800"  alt="image" src="https://github.com/user-attachments/assets/d092b023-c4f4-495d-8296-448bb8f0f81d" />

### Here's a clear overview of Web Bluetooth support (march 2026):

Browsers with full support

Chrome / Chromium-based browsers are the only ones with solid, out-of-the-box Web Bluetooth support. A subset of the Web Bluetooth API is available in ChromeOS, Chrome for Android 6.0, Mac (Chrome 56), and Windows 10 (Chrome 70). 

In some cases *chrome://flags* must be opened in the url adress bar and "Web Bluetooth" must be turned on.

Specifically:

- Chrome on Android – supported since Chrome 56 (Android 6.0+)
- Chrome on macOS – supported since Chrome 56
- Chrome on Windows – supported since Chrome 70, requires Windows 10 version 1703 (Creators Update) or later
- Chrome on ChromeOS – fully supported
- Edge (Chromium-based) – supported since version 79
- Opera on Android – supported since version 46
- Samsung Internet – the GATT Communication API is shipped without any flag in Samsung Internet v6.4 GitHub

Browsers without support

- Firefox – not implemented; Mozilla has concerns about the security model
- Safari / WebKit – not supported across all versions of Safari Testmu; this affects all browsers on iOS/iPadOS since Apple forces them to use WebKit
- Chrome on Linux – partially implemented but not supported; the #enable-experimental-web-platform-features flag must be enabled GitHub

# iOS workaround
WebBLE is an app for iOS that supports the GATT Communication API, created initially for the Puck.js project. Bluefy is a free alternative created by PNNSoft. GitHub These are third-party browser apps, not Safari itself.

# Important requirements

Web Bluetooth is only available in secure contexts (HTTPS). MDN Web Docs
It's still considered experimental, so treat it accordingly in production projects.
It only works with Bluetooth Low Energy (BLE/GATT) — not Classic Bluetooth. For Classic Bluetooth with RFCOMM, the Web Serial API is the alternative.

Bottom line for your ESP32 BLE projects: Chrome on Android, macOS, and Windows are your reliable targets. iOS remains the main gap unless users install a dedicated app like Bluefy.
