# ESP32_NVS_Web

![VS Code](https://img.shields.io/badge/Editor-VS%20Code-blue?logo=visual-studio-code)
![PlatformIO](https://img.shields.io/badge/Platform-PlatformIO-orange?logo=platformio)
![License: MIT](https://img.shields.io/badge/License-MIT-green)

ESP32_NVS_Web is a project that builds a web server on the ESP32. The ESP32 connects to the network in two modes: Access Point (AP) and Station (STA). The web server serves a webpage stored in the SPIFFS storage, making it easier to manage HTML content separately from the main code.

## Learnings from the Project

1. How to use SPIFFS.
2. How to store WiFi credentials in NVS storage.
3. Using Async webserver and DNS for the local webpage.
4. Using Fetch API to post and get data.

## Features

- The main HTML page for the web server is stored in SPIFFS storage.
- The webpage contains a form to fill in the network credentials and includes four buttons:
  
  - **Button 1:** Deletes stored credentials from the NVS storage.
  - **Button 2:** Toggles the LED (ON/OFF).
  - **Button 3:** Prints `"Hello_I_am_ESP32"` in the Serial Monitor. If a 16x2 LCD display is attached, it shows `"Hello from ESP32"` for 2 seconds.
  - **Button 4:** Shows the weather in Canada. This button does not connect to the ESP32; it fetches weather data from a website and uses the ESP32 as a server to publish it on the local webpage.

## Tools Used

- **Visual Studio Code:** Used as the code editor.
- **PlatformIO:** Used as the development environment for building, debugging, and uploading code to the ESP32.

## Steps to Set Up the Code

1. Download all the necessary libraries from the library manager in PlatformIO:
   - `ESPAsyncWebServer`
   - `Preferences` (can use default methods)
   - `LiquidCrystal_I2C` (for driving the LCD display)
   - All other libraries used are built-in.

2. Set up SPIFFS:
   - Click the PlatformIO extension icon.
   - This opens the Project Tasks; under Platform:
     1. Click **Build FileSystem Image**.
     2. Click **Upload FileSystem Image**.

3. Upload the `main.c` file into the ESP32, and the setup will work perfectly.
---

Feel free to reach out if you have any questions or need further assistance!
