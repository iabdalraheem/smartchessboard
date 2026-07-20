# ♟️ Smart Chessboard

An electronic chessboard that automatically detects piece movement and syncs live with a companion Android app over Bluetooth Low Energy (BLE).

Graduation project — Control and Automation Engineering, Technical Engineering Institute (Mechanical and Electrical), University of Aleppo.

---

## 📋 Overview

Smart Chessboard replaces manual move tracking with real-time, automatic detection. Each square uses a resistor-coded sensing circuit to identify which piece is present, while a Kotlin-based Android app displays the live board state, tracks match history, and communicates with the board over BLE.

## ✨ Features

- **Automatic piece detection** — 64-square sensing grid using analog multiplexing
- **Per-piece identification** — 12 unique resistor values (E12 series) distinguish each piece type and color
- **Square-level LED feedback** — highlights moves, captures, and invalid placements
- **BLE connectivity** — real-time sync with the mobile app (Nordic UART Service)
- **Match history** — automatic local storage of completed games
- **Noise-resistant readings** — multi-sample averaging, median filtering, and debounce logic for reliable detection

## 🔧 Hardware

| Component | Details |
|---|---|
| Microcontroller | ESP32 |
| Piece sensing | 8× CD74HC4051 analog multiplexers |
| Control lines | Shared A/B/C select lines (GPIO 18/19/21) |
| ADC input | ADC1-only pins (GPIO 32–39), avoids BLE/ADC2 conflict |
| Piece ID method | Voltage divider with 12 distinct resistor values (1kΩ–68kΩ) |
| LED control | RGB Adressable |

### 📸 Hardware Photos
<img width="100" height="244" alt="WhatsApp Image 2026-07-20 at 2 30 08 PM" src="https://github.com/user-attachments/assets/6ff2f65d-c128-40cc-a990-83503c81ff35" />

### 📸 FlowCHart
<img width="100" height="244" alt="WhatsApp Image 2026-07-20 at 2 24 40 PM" src="https://github.com/user-attachments/assets/21742d76-b484-4220-9916-6d221ae49997" />




<!-- Add photos once uploaded to /docs/images/ -->
<!-- ![Board Overview](docs/images/board-overview.jpg) -->
<!-- ![Circuit Detail](docs/images/circuit-detail.jpg) -->

## 📱 App

- **Language:** Kotlin
- **UI:** Jetpack Compose
- **Architecture:** MVVM (ViewModel + StateFlow)
- **Local storage:** Room database
- **Connectivity:** BLE (Nordic UART Service)
- **Development mode:** Mock BLE service for UI/UX testing without physical hardware

**App source code:** [Final-app repository](https://github.com/iabdalraheem/Final-app)

**Try the app:** [Download from Google Drive](#) <!-- replace # with your Drive link -->

### 📸 App ScreenShots

<img width="100" height="200" alt="WhatsApp Image 2026-07-20 at 2 23 50 PM" src="https://github.com/user-attachments/assets/a2d5b2a9-8cec-4247-aa5a-0eec5e218cf6" />
<img width="100" height="200" alt="WhatsApp Image 2026-07-20 at 2 23 50 PM" src="https://github.com/user-attachments/assets/af4241f6-c3a2-4ba2-8023-b96789d7ffca" />
<img width="100" height="200" alt="WhatsApp Image 2026-07-20 at 2 44 26 PM" src="https://github.com/user-attachments/assets/8e3dc8c2-9a66-4c30-9178-81b258bca211" />





## 📂 Repository Structure

```
smart-chessboard/
├── firmware/         # ESP32 source code
│   └── src/
├── app/              # Android application (Kotlin, Jetpack Compose)
├── docs/             # Circuit diagrams, hardware photos, documentation
└── README.md
```

## 🚀 Getting Started

### Firmware
1. Open `firmware/` in the Arduino IDE or PlatformIO
2. Select your ESP32 board
3. Flash the firmware

### App
1. Open `app/` in Android Studio
2. Build and run on a device or emulator
3. For UI testing without hardware, enable the mock BLE service

## 👥 Team

| Name | Role | Contact |
|---|---|---|
| Abdalraheem Alzaeem | Frimware & App | [LinkedIn](#) <!-- replace # with your link --> |
| Abdullah Taweel | HardWare | LinkedIn *(coming soon)* |
| Amro Qadi Riha | Hardware | LinkedIn *(coming soon)* |
| Sedra Zrek | Hardware | LinkedIn *(coming soon)* |
Supervised by **Eng. Heba Kharma**
## 📄 Final


<img width="500" height="207" alt="WhatsApp Image 2026-07-20 at 3 04 18 PM (1)" src="https://github.com/user-attachments/assets/a3f671d7-b6c2-4ae8-ab76-411a6769bcd6" />
<img width="600" height="360" alt="WhatsApp Image 2026-07-15 at 11 25 58 PM" src="https://github.com/user-attachments/assets/2a8a4a8a-616e-4b5f-80d6-1ed0b81ab295" />

