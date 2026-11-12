# DvaraBell Terms & Conditions

**Effective Date:** June 3, 2026  
**Last Comprehensive Revision:** November 2026  
**Operated by:** BLSS — DvaraBell Team  
**Contact:** shivankpro23@gmail.com  

---

## 1. Introduction & Acceptance
These Terms & Conditions ("Terms") govern your access to and use of the DvaraBell smart intercom service, including our mobile applications (Android, iOS), web homeowner dashboard, visitor calling interface, download portals, and related servers, databases, and APIs (collectively, the "Service"), operated by BLSS ("BLSS", "we", "us", "our").

By downloading, installing, registering, scanning a DvaraBell QR placard, or using any part of the Service, you agree to be bound by these Terms. If you do not agree, do not use the Service.

---

## 2. Account Registration & Security
- You may register and access your account using an authorized email/password or third-party authentication such as Google Sign-In.
- You are responsible for maintaining the confidentiality of your login credentials and for all activities that occur under your account.
- You agree to provide accurate, current information and notify us immediately of any unauthorized use or security incident.

---

## 3. Service Architecture & Intercom Usage Rules
- **QR Placard Deployment & Ownership:** Homeowners are issued cryptographically unique QR placards and alphanumeric door codes. You agree to display QR placards solely on doors, gates, or property that you own, lease, or have explicit legal authority to manage.
- **Placard Revocation & Rotation:** Outdoor placards can be revoked, rotated, or reassigned at any time from the app Settings. Upon rotation, previous codes are immediately invalidated to prevent unauthorized calls.
- **Relayed WebRTC Media & IP Anonymity:** Active live calls are routed through secure TURN relays (`iceTransportPolicy: 'relay'`) using DTLS-SRTP encryption to safeguard homeowner and visitor privacy and prevent IP address discovery. Live video and audio streams are never recorded or stored on our servers unless two-way recording is explicitly initiated.
- **Voice Notes, Photos & 10-Day Retention:** Visitors may voluntarily submit voice notes, photo drop-offs, or text delivery instructions. All visitor notes and logs are subject to a strict **rolling 10-day automatic retention period**, after which they are permanently deleted from database storage.
- **Two-Way Call Recording:** Recording a live call triggers a prominent, visible on-screen red indicator (`🔴 REC`) and status banner on both participants’ screens. You agree to comply with all applicable local wiretapping and two-party consent recording laws.

---

## 4. Acceptable Use Policy & Prohibited Conduct
Subject to these Terms, BLSS grants you a personal, non-exclusive, non-transferable, revocable license to use the Service. You agree that you will NOT:
- Use the Service for harassment, stalking, unlawful surveillance, fraudulent caller impersonation, or nuisance ringing.
- Employ automated bots, scrapers, or scripts to repeatedly trigger doorbell calls or flood signaling APIs.
- Reverse engineer, decompile, or attempt to extract source code from our mobile binaries or signaling infrastructure.
- Display DvaraBell QR codes in deceptive contexts or on premises without authorization.

---

## 5. Service Availability, Network Dependencies & Ringing Disclaimers
DvaraBell incorporates a 4-tier alert pipeline (native push, household multi-device ringing, 15-second Twilio SMS/voice backup, and offline visitor self-service fallback). However:
- Real-time ring delivery depends upon the user’s mobile operating system, internet connectivity, and background permission settings.
- Android users must maintain background service and full-screen intent permissions and ensure DvaraBell is exempt from aggressive battery optimization.
- BLSS does not guarantee that rings or notifications will be delivered instantly or free from cellular network latency, power outages, or hardware disconnections. In the event a call goes unanswered, visitors are provided with the after-call screen to leave a note or photo.

---

## 6. Intellectual Property
All trademarks, logos, interface designs, codebase, documentation, and graphical assets related to DvaraBell are the exclusive property of BLSS. Nothing in these Terms grants you any title or ownership rights in our intellectual property.

---

## 7. Disclaimer of Warranties
THE SERVICE IS PROVIDED ON AN "AS IS" AND "AS AVAILABLE" BASIS. TO THE MAXIMUM EXTENT PERMITTED BY LAW, BLSS EXPRESSLY DISCLAIMS ALL WARRANTIES OF ANY KIND, WHETHER EXPRESS OR IMPLIED, INCLUDING MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE, AND NON-INFRINGEMENT. WE DO NOT GUARANTEE THAT THE SERVICE WILL FUNCTION UNINTERRUPTED OR ERROR-FREE UNDER ALL NETWORK CONDITIONS.

---

## 8. Limitation of Liability
TO THE MAXIMUM EXTENT PERMITTED BY LAW, IN NO EVENT SHALL BLSS, ITS DIRECTORS, EMPLOYEES, OR AFFILIATES BE LIABLE FOR ANY INDIRECT, INCIDENTAL, SPECIAL, OR CONSEQUENTIAL DAMAGES, LOSS OF PROFITS, PROPERTY LOSS, OR MISSED DELIVERIES ARISING OUT OF OR IN CONNECTION WITH THE USE OF THE SERVICE, DOORBELL PLACARDS, OR CALL NOTIFICATIONS.

---

## 9. Privacy Policy & Data Deletion
Your use of the Service is governed by our Privacy Policy. You may delete your account and all associated activity records permanently at any time via **Settings > Delete Account** in the mobile app or through the [Online Deletion Portal](https://dvarabell-y5j2.onrender.com/delete-account).

---

## 10. Governing Law & Dispute Resolution
These Terms shall be governed by and construed in accordance with the laws of India, without regard to its conflict of law provisions. Any legal action or proceeding arising under these Terms shall be instituted exclusively in the competent courts in India.

---

## 11. Contact Us
For questions regarding these Terms, contact:  
**Email:** shivankpro23@gmail.com  
**Organization:** BLSS — DvaraBell Team  
