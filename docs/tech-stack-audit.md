# Tech stack coverage audit

All rows refer to visible slide text, not only notes.

| Original / brief item | Current slide |
|---|---|
| Kotlin | 9 Architecture |
| Jetpack Compose | 9 Architecture |
| Material 3 | 9 Architecture |
| MVVM | 9 Architecture |
| Google Nearby Connections API | 9 + 10 |
| Wi-Fi / Bluetooth / BLE | 10 P2P transport |
| Android Keystore | 10 Security & QR |
| ECDH key exchange | 10, explicitly planned |
| ZXing / ML Kit | 10 Security & QR |
| Room / SQLite | 9 + 10 Local database |
| Profiles / chats / contacts / local waypoints | 10 Local database |
| MapLibre SDK | 10 Offline mapping |
| Prepackaged offline tiles | 10 Offline mapping |
| GPS / Android Location Services | Both visible on 10 |
| Rotation Vector Sensor | 10 Sensors & radar |
| Compose Canvas / ambient edge glow | 10 Sensors & radar; glow shown on 7 |
| Android Studio / Git / GitHub | 10 Build & test |
| Two physical Android devices | 10 Build & test |

## Accuracy decisions
- Nearby abstracts Wi-Fi, Bluetooth and BLE. Avoid claiming a specifically implemented Wi-Fi Direct transport. Official source: https://developers.google.com/nearby/connections/overview
- ECDH is a planned choice from the old proposal, not a completed implementation. Brief only promises standard crypto libraries. Validate authenticated-session design, platform support and key management during development. Keystore features: https://source.android.com/docs/security/features/keystore/features
- QR exchange does not by itself implement authenticated application-level encryption. Keep identity verification and cryptographic implementation explicit during W2 development.
- Target delivery <3 seconds is still a test target, not measured performance.
