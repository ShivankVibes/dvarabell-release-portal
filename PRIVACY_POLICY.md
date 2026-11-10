# DvaraBell Privacy Policy

**Effective Date:** June 3, 2026  
**Last Comprehensive Revision:** November 2026  
**Operated by:** BLSS — DvaraBell Privacy & Security Division  
**Contact:** shivankpro23@gmail.com  

---

## 1. Overview & Core Commitments
DvaraBell provides digital smart intercom and visitor communication services connecting outdoor QR placards with homeowner mobile applications. DvaraBell was engineered from the ground up to protect both homeowners and visitors:
- **Zero IP Address Exposure:** We enforce encrypted TURN relay proxies (`iceTransportPolicy: 'relay'`) so neither homeowners nor visitors ever expose their public IP address or location.
- **Strict 10-Day Automated Retention Window:** All activity logs, voice notes, recordings, and photo drop-offs are permanently purged after 10 days by an automated daily database worker.
- **Zero Live Stream Recording:** Live WebRTC audio and video travel peer-to-peer over encrypted TURN relays and are never recorded or stored on our servers.
- **Zero PII on Placards:** Outdoor QR codes encode only random cryptographic access tokens — zero phone numbers, street addresses, or names are embedded.

---

## 2. Granular Data Collection & Retention Schedule

| Category | Elements Collected | Purpose | Retention Window | Storage & Security Controls |
| :--- | :--- | :--- | :--- | :--- |
| **Account Credentials** | Name, email address, password hash (or Google OAuth profile tokens) | Authentication, door provisioning, household sharing | Active account lifetime; **purged immediately upon account deletion** | Passwords hashed with bcrypt (10 salt rounds). TLS 1.3 transit encryption. |
| **Door Placard & QR Config** | Unique access tokens, household routing IDs | Visitor call routing without sharing personal contacts | Active until rotated or revoked | Stored on AES-256 encrypted database volumes. No PII embedded in QR. |
| **Live Call Audio & Video** | Real-time WebRTC audio/video streams | 2-way live intercom communication | **0 seconds (ephemeral)** | Never stored on servers. Routed via TURN relays (`iceTransportPolicy: 'relay'`) with DTLS-SRTP encryption. |
| **Visitor Notes & Recordings** | Audio voice notes, call recordings (if triggered), photo drop-offs, text notes, drop-off options | Homeowner playback and review of missed visitors | **Strict 10-Day Rolling Retention Window** | Auto-purged after 10 days by automated worker (`$lt: cutoffDate`). One-tap manual clear available. |
| **Push Notification Tokens** | APNs (iOS) & FCM (Android) device tokens | Device wake-up & incoming ring delivery | Overwritten upon refresh; erased on logout or account deletion | Isolated per user; strictly transactional; zero third-party ad sharing. |
| **Backup Notification Config** | Optional secondary mobile number, SMS/Call preference | Unanswered ring backup alert after 15s | Retained while configured in Settings | Stored encrypted; transmitted via Twilio only upon verified unanswered calls. |

---

## 3. WebRTC Architecture: TURN Relays & IP Anonymization
Standard peer-to-peer WebRTC connections can expose public IP addresses to other participants during direct host candidate negotiation. **DvaraBell eliminates this privacy tradeoff:**
1. **Forced TURN Relay (`iceTransportPolicy: 'relay'`):** Direct peer-to-peer candidate discovery is suppressed. Media packets flow strictly through high-bandwidth encrypted TURN relay proxies over TLS/TCP (ports 443 and 80).
2. **Complete IP Masking:** Neither party can inspect, log, or discover the other's IP address, Internet Service Provider, or physical location.
3. **End-to-End Encryption:** Media is encrypted in transit using DTLS (Datagram Transport Layer Security) and SRTP (Secure Real-time Transport Protocol).
4. **Camera Privacy by Default:** Homeowner video is disabled by default upon answering and only activates if the homeowner explicitly taps the camera toggle.

---

## 4. QR Code Security, Revocation & Anti-Abuse Controls
- **Instant Rotation & Revocation:** Homeowners can revoke or rotate their active QR code at any time in app Settings. Revoked codes immediately return `404 Invalid Code` and cannot ring devices.
- **Cryptographic Ephemeral Sessions:** Scanning a placard generates an isolated, cryptographically random single-use session ID (UUIDv4) that auto-expires in 10 minutes. Calls auto-decline after 30 seconds if unanswered.
- **Server-Side Rate Limiting:** Backend signaling APIs enforce IP and device rate limiters to prevent automated ringing attacks.
- **Busy-Line Guard:** Subsequent scans while a call is in progress present a "Line Busy" notice rather than interrupting the ongoing call.

---

## 5. Visitor Consent & Recording Transparency
- **Visitor Voice Notes:** Captured only when a visitor explicitly taps and holds or presses the "Record Voice Note" button, reviews the timer, and presses submit.
- **Two-Way Call Recordings:** When either party triggers recording:
  1. A prominent flashing red recording indicator (`🔴 REC`) is displayed on both screens.
  2. Real-time banners announce recording is active.
  3. Visitors receive an immediate local copy (MP4/MP3) downloadable to their device upon call completion.
- **10-Day Automatic Expiry:** All recordings are purged after 10 days.

---

## 6. Ringing Reliability & Multi-Tiered Redundancy
Because mobile battery optimizers or cellular dead zones can impact single-channel alerts, DvaraBell implements a 4-tier alert pipeline:
- **Tier 1:** Native high-priority push (APNs VoIP PushKit & Android FCM + 24/7 Foreground Socket Service).
- **Tier 2:** Simultaneous household ringing across all family member devices.
- **Tier 3:** Fail-safe Twilio backup SMS or phone call dispatched if a call is unanswered after 15 seconds.
- **Tier 4:** Visitor self-service fallback (photo drop-off, voice note, text message, or package delivery instruction) ensuring zero lost visitor inquiries.

---

## 7. Account Deletion & Rights
Users can delete all account data, door placards, and activity logs instantly via:
- In-App: **Settings > Delete Account**
- Web: [https://dvarabell-y5j2.onrender.com/delete-account](https://dvarabell-y5j2.onrender.com/delete-account)
- Contact: shivankpro23@gmail.com
