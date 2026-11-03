# Syna — LGTM Team

13 slides / 300 seconds. UI and readings are illustrative.

## 1. Syna

15s | Syna is our proposed Android offline P2P messenger and Friend Finder. We help nearby friends talk and orient when internet is unavailable. All Android UI, map geometry and readings in this presentation are concept mockups, not actual application screenshots. Values are illustrative.

## 2. Motivation

20s | Think of hiking or a crowded festival: the internet drops but you are still near your friends. Internet-based messages stop arriving. GPS coordinates without context are not intuitive. We need an offline way to communicate and understand which direction to face. This is a nearby-use case, not a long-distance or rescue service.

## 3. The solution

15s | Users exchange public-key identities using QR, establish an authenticated nearby session, and exchange text or GPS with consent. The map gives spatial context and the compass gives orientation toward the last shared coordinate. No multi-hop relay is in the MVP. Signal-wave animation represents P2P communication, not voice calling; voice calls remain outside MVP.

## 4. Chat

25s | This is a concept chat playback: Rafael shares a meeting point and his location. Messages travel over direct nearby connectivity with authenticated encrypted sessions. Room stores history and permits deletion. The interface shows connection and delivery states. New messages require devices within supported nearby range. These states are illustrative, not measured behavior. The four visible steps explain QR friend onboarding, public-key exchange and local storage, direct encrypted messaging, and Room chat history. Only public keys are exchanged; private keys remain on device. Public-key exchange is part of identity setup, and the authenticated encryption design still needs implementation validation.

## 5. Offline map

25s | The map shows your own marker with an arrow indicating phone heading and friends as named markers with estimated distances. Rafael and Ahsan readings are sample values. GPS coordinates determine distance; rotation-vector orientation drives the self-heading arrow. MapLibre renders a map region downloaded or packaged in advance. Friends are placed at their most recently received coordinates; the visual is not live tracking or a route. Consent and timestamps are required. The street geometry here is a hand-authored schematic, not a real geographic map. Nearby Connections API is the communication transport, not a map rendering or long-range tracking API; MapLibre renders the map.

## 6. Compass

25s | The map answers where; Friend Finder helps you face toward the selected friend’s last shared coordinate. A directional ambient edge glow is aligned with the bearing and current phone orientation. Distance and bearing are estimates. The timestamp stays visible. Unreliable heading should produce calibration feedback. This is not turn-by-turn navigation and it cannot know a friend’s new position until another coordinate is received.

## 7. Value proposition

20s | User-requested comparison wording: Messaging-first P2P Apps versus Syna P2P Radar & Chat. This compares intended product focus, not a verified audit of every competitor. Syna combines offline P2P chat with directional friend finding and persists last-known coordinates, not guaranteed live coordinates. The sensor wording follows the supplied comparison: GPS Hardware + Magnetometer. The implementation stack still uses Android Rotation Vector Sensor for orientation, with hardware/sensor availability validated on test devices. No multi-hop store-and-forward relaying is in the Syna MVP.

## 8. Architecture

30s | Kotlin, Jetpack Compose, Material 3 and MVVM form the core framework. Room uses SQLite for profiles, contacts, chat history and last locations; Android Keystore protects private keys. Nearby Connections is the offline P2P transport. The next slide names every planned dependency. ECDH is retained from the original proposal as a planned key-agreement choice to validate, not a completed or finalized security implementation. Use standard cryptographic libraries, authenticated sessions and compatible target-device APIs. No cloud relay or multi-hop mesh is in the MVP.

## 9. Tech stack & resources

20s | Transport: Google Nearby Connections API over Wi-Fi, Bluetooth and BLE. Security: Android Keystore, planned ECDH key agreement, and ZXing or ML Kit QR exchange. Persistence: Room over SQLite for profiles, chats, contacts and waypoints. Maps: MapLibre SDK with a prepackaged offline region. Sensors: Android Location Services/GPS and Rotation Vector Sensor; Jetpack Compose Canvas and animations draw compass and ambient edge glow. Build/test: Android Studio, Git/GitHub and two physical Android phones. ECDH support and the authentication design require implementation validation; planned is not a completion claim. Nearby abstracts its radio selection, so do not promise a specific Wi-Fi Direct mechanism.

## 10. MVP boundaries

20s | The MVP includes local registration/login and profiles; QR friend exchange and contact rename/delete; encrypted one-to-one text and local chat-history deletion; explicit opt-in GPS; offline map; compass; and connection/delivery/location freshness states. Excluded: multi-hop mesh, group messaging, file sharing, voice/video, cloud sync and turn-by-turn navigation. A disconnected friend’s last received location remains available but must not be presented as a current position.

## 11. Implementation plan

45s | W1 validates the highest-risk dependency: two real devices exchanging text without internet. In parallel, set up MVVM, Room and mock UI repositories. W2 establishes QR identity, authenticated messaging and saved history. Delivery within three seconds under stable nearby connectivity is a test target, not a measured result. W3 adds opt-in GPS, downloaded tiles, map markers, bearing and compass. Freeze new features after W3. W4 is integration, reconnects, denied permissions, unavailable GPS and sensor feedback. If map setup fails, use a coordinate-based radar fallback. Brief calendar: Dec 2–7 rehearsal buffer, Dec 8 and 15 demos. Dates are supplied, not a verified live course calendar.

## 12. Team

25s | Team LGTM: Rafael owns Networking & Security: Nearby Connections API integration, P2P discovery, device handshake, public-key encryption and background GPS sensor streams. Andrew owns Backend & Business Logic: Room schema architecture, profile/contact CRUD, message persistence, QR key management and distance/bearing mathematical logic. Ahsan owns Frontend & UI/UX: Jetpack Compose screens, QR scanner UI, chat interface, offline MapLibre integration and animated compass radar UI. The responsibility bullets are assigned work. User-provided skills and experience: Rafael — low-level programming and DSA; Andrew — DBMS and backend engineering; Ahsan — Frontend Development, design and project management. Generic avatars are illustrations, not real likenesses.

## 13. Closing

15s | Our objective is a focused Android experience: communicate nearby, share a coordinate and orient toward a friend, all without internet. We prove the connection first and deliver an integrated demonstration. Thank you. We welcome feedback on scope and feasibility.