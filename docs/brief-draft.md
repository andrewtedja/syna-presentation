# Syna — working presentation brief

## Source and purpose
Redesigned from the supplied 8-slide proposal PDF and 10-page project brief (Oct 27). Audience: mobile application development midterm proposal. Up to 5 minutes. Required: team roles/skills/experience, topic/motivation, technologies/resources, implementation plan. The image also mentions feedback submissions for other teams; that is a course action, not pitch content.

## Product
Android offline P2P messenger and Friend Finder. Direct nearby communication, authenticated encrypted sessions, QR public-key exchange, opt-in GPS sharing, last-known locations on an offline map, distance/bearing compass with directional edge glow. Communication requires supported nearby range. Last received locations remain accessible after disconnecting. Not a rescue guarantee or turn-by-turn navigator.

## Ten-slide story / 300 seconds
1. Syna: Stay close, even off-grid — 20s
2. Team: Rafael / Andrew / Ahsan and ownership — 25s
3. Motivation: messages fail, coordinates lack context — 30s
4. Product journey: connect, share, find — 30s
5. Messaging: animated concept chat — 30s
6. Friend Finder: animated compass and freshness — 35s
7. Architecture: local Android stack and nearby peer — 35s
8. Requirements/resources: MVP, validation and boundaries — 35s
9. Implementation: four weeks plus buffer — 45s
10. Conclusion and feedback — 15s

## Functional requirements preserved
FR01 local registration/login/profiles; FR02 QR key exchange; FR03 friend rename/delete; FR04 nearby discovery; FR05 encrypted 1:1 chat; FR06 saved/deletable chat history; FR07 GPS sharing; FR08 offline map and friend locations; FR09 distance, bearing and directional compass; FR10 connection/delivery status and timestamps. Slides summarize these; the original brief remains authoritative for detailed acceptance.

## Non-functional requirements
Core flow offline; encryption in authenticated sessions; private keys remain on device; delivery target <3s under stable connectivity; responsive consistent UI; persistence across restarts; graceful permissions/GPS/disconnect handling; explicit location consent; timestamps and unreliable-heading feedback.

## Technology and resources
Kotlin, Jetpack Compose/Material 3, MVVM, Room/SQLite, Google Nearby Connections, Keystore and standard crypto libraries, ZXing or ML Kit, Android Location Services, MapLibre and offline tiles, rotation-vector sensor, Compose Canvas. Android Studio, Git/GitHub, at least two physical Android phones and a predownloaded offline map region.

## Team / confirm before delivery
Original slide names: Rafael (network/security); Andrew (database/business logic); Ahsan (frontend). Brief initials: EL/AT/AMAF. Confirm exact names and initial mapping. Relevant skills and experience are unknown and remain visible placeholders. Ownership is planned responsibility, not evidence of prior experience.

## Calendar from supplied brief
Proposal Nov 3. W1 Nov 4–10: validate offline payload exchange. W2 Nov 11–17: QR identity/authenticated messaging and persistence. W3 Nov 18–24: map/location/compass. W4 Nov 25–Dec 1: integration. Dec 2–7: buffer. Demos Dec 8 and 15. These are supplied project dates, not a verified live course schedule.

## Risks and mitigations
Validate Nearby on real devices in W1. UI uses mock repositories to avoid backend blocking. Use standard security libraries; transport proof is not application-level identity verification. Prepackage a small tile region; coordinate radar fallback. Show sensor accuracy/calibration feedback. Freeze new features after W3.

## Outside MVP
Multi-hop mesh, file sharing, group messaging, voice/video, cloud sync, turn-by-turn navigation.

## Editorial choices
Removed unsupported blanket comparisons about all mesh messengers. Kept last-shared semantics explicit. Did not repeat ECDH from the old slides as a confirmed implementation choice because the brief leaves the cryptographic library/algorithm open. Demo messages, distances, bearings and location ages are illustrative. Proposed UI, not actual app screenshots or completed implementation.


## Current revision
The original ten-slide outline above is superseded by the twelve-slide audience-first version in revision-v2.md. Use speaker-notes.md for current order and timings. The scope and source facts remain unchanged.
