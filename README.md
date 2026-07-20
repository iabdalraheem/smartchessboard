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
| LED control | 74HC595 shift registers |

### 📸 Hardware Photos

<!-- Add photos once uploaded to /docs/images/ -->
<!-- ![Board Overview](docs/images/board-overview.jpg) -->
<!-- ![Circuit Detail](docs/images/circuit-detail.jpg) -->

*(Photos coming soon)*

## 📱 App

- **Language:** Kotlin
- **UI:** Jetpack Compose
- **Architecture:** MVVM (ViewModel + StateFlow)
- **Local storage:** Room database
- **Connectivity:** BLE (Nordic UART Service)
- **Development mode:** Mock BLE service for UI/UX testing without physical hardware

**App source code:** [Final-app repository](https://github.com/iabdalraheem/Final-app)

**Try the app:** [Download from Google Drive](#) <!-- replace # with your Drive link -->

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
| Raheem | Frimware & App | [LinkedIn](#) <!-- replace # with your link --> |
| Abdullah Taweel | HardWare | LinkedIn *(coming soon)* |
| Amro Qadi Riha | Hardware | LinkedIn *(coming soon)* |
| Sedra Zrek | Hardware | LinkedIn *(coming soon)* |
Supervised by **Eng. Heba Kharma**

## 📄 License

*(Add your preferred license here — MIT, Apache 2.0, etc.)*
