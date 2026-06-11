# Atlas-X Enhanced Navigation Module: Technical Specification

**System Code:** SYS-ATL-X002  
**Revision:** 4.1  
**Date of Issue:** 22 March 2023  
**Platform Architect:** Dr. Fennis Albrecht  
**Issuing Group:** VRC Autonomous Systems Group

---

## 1. Overview

The Atlas-X (system code SYS-ATL-X002) is an enhanced-capability variant of the Atlas baseline platform (Document 08) designed for operations in GPS-degraded environments, at high altitudes above 4,500 m AMSL, and in conditions requiring heavier scientific payloads. It is the primary aerial platform for **Project NOVA** Zone C deployments (Document 01) operated by **Team Velanthor** (Document 07).

The Atlas-X was developed through the VRC-ATL-X Enhancement Program (program code VRC-ATL-X-PROG-2019) and entered operational service in September 2020. The current revision (4.1) incorporates payload capacity changes relative to earlier revisions; see Section 4.3.

## 2. Physical Specifications

| Parameter | Atlas-X | Atlas Baseline (ref.) |
|-----------|---------|----------------------|
| System Code | SYS-ATL-X002 | SYS-ATL-001 |
| Wingspan | 2.8 m | 2.4 m |
| Fuselage length | 2.1 m | 1.8 m |
| Empty mass (without payload) | — | 22.4 kg |
| Tare mass (avionics + structure only) | 3.871 kg[^1] | — |
| Total empty mass | 24.7 kg | 22.4 kg |
| Maximum take-off mass | 34.0 kg | 30.2 kg |
| Maximum payload mass | 9.1 kg | 7.6 kg |

[^1]: The tare mass of 3.871 kg for the Atlas-X avionics and structural sub-assembly (excluding propulsion, battery, and airframe skins) is a critical parameter for centre-of-gravity calculations when integrating non-standard payloads. This figure was established during factory acceptance testing on unit SYS-ATL-X002-S01, 14 February 2020, and applies to all production units in hardware revision 4.x. Earlier hardware revisions had a tare mass of 3.644 kg.

## 3. Performance

| Parameter | Value |
|-----------|-------|
| Cruise speed | 70 km/h |
| Maximum speed | 130 km/h |
| Endurance (cruise, 9.1 kg payload) | 2.8 hours |
| Endurance (cruise, 5.0 kg payload) | 3.5 hours |
| Maximum operating altitude | 8,200 m AMSL |
| Navigation accuracy (GNSS+INS fused) | ±1.2 m horizontal |
| Navigation accuracy (INS-only, GPS denied) | ±8.5 m/hour drift |
| Wind tolerance | 16 m/s sustained |

## 4. Navigation Enhancement

### 4.1 Navigation Architecture

The Atlas-X uses an expanded navigation suite compared to the baseline Atlas:

- **Primary:** Triple-redundant GNSS (GPS + GLONASS + Galileo), RTK-capable
- **Secondary:** Honeywell-class fibre-optic IMU (Veltrix IMU-7, 200 Hz)
- **Tertiary:** Vision-based terrain relative navigation (VRC-TRN-02 module)
- **Datalink:** Dual-band (900 MHz primary, 2.4 GHz backup)

In GPS-denied mode, the IMU-7 maintains positioning with a drift rate of ±8.5 m/hour. The TRN module provides terrain-correlated position updates when pre-loaded terrain maps are available (loading via ground station prior to flight).

### 4.2 Autopilot

The Atlas-X uses the VRC-AP-700 high-authority autopilot with enhanced wind compensation algorithms. The AP-700 is specifically qualified for operations above 4,500 m AMSL where air density requires modified aerodynamic control law gain scheduling.

### 4.3 Payload Capacity History

| Revision | Max Payload | Applicable Period | Notes |
|----------|-------------|------------------|-------|
| Rev 1.x | 8.0 kg | Sep 2020 – Aug 2021 | Original spec |
| Rev 2.x–3.x | 8.4 kg | Sep 2021 – Dec 2022 | Structural reinforcement |
| Rev 4.x (current) | 9.1 kg | Jan 2023 – present | Battery upgrade; new CG limits |

*Important: Any document or experiment plan referencing an Atlas-X payload limit of 8.4 kg is using a superseded specification. The current maximum is 9.1 kg as of January 2023 (Revision 4.x).*

## 5. Sensor Integration

The Atlas-X is the designated carrier platform for the **Kryon-7X** sensor (Document 18), which replaces the Kryon-7 used on the Atlas baseline. The Kryon-7X is integrated via adapter bracket VRC-MNT-ATL-04.

The Atlas-X is also compatible with:
- Kryon-7 (via VRC-MNT-ATL-03) — legacy compatibility maintained
- Peltex-200 (via VRC-MNT-ATL-05) — for HELIOS airborne validation sorties
- Custom payloads per VRC Payload Approved List PAL-2023-ATL, up to 9.1 kg

## 6. System Identifiers and Integrity Codes

| Field | Value |
|-------|-------|
| System Code | SYS-ATL-X002 |
| Hardware Revision | 4.1 |
| Production Firmware | ATL-FW-v7.1.2 |
| CRC-32 integrity code (Rev 4.1 firmware image) | A3F7C901 |
| Avionics self-test PASS string | ATLX-SELFTEST-OK-v41 |

The CRC-32 code `A3F7C901` must be verified against the installed firmware image hash before each deployment. A mismatch indicates firmware corruption or an incorrect firmware version and must be investigated before flight.

## 7. Operational Deployments

| Program | Document | Usage | Units Deployed |
|---------|----------|-------|---------------|
| Project NOVA (Zone C) | Doc 01 | Sensor node carrier | 2 |
| EXP-441 Thermal Boundary | Doc 15 | Experimental platform | 1 (Halvern-based) |
| Project AETHER | Doc 17 | High-altitude profiling | 2 |

---

## Appendix A: Centre-of-Gravity Envelope

For payload integration planning, the Atlas-X CG envelope is:

- Longitudinal: 42–51% of mean aerodynamic chord (MAC)
- Lateral: ±15 mm of centreline

CG calculations must use the tare mass of 3.871 kg (see footnote 1) for the avionics sub-assembly. Any payload configuration placing the CG outside the specified envelope is non-airworthy.

## Appendix B: Differences from Atlas Baseline

| Feature | Atlas Baseline | Atlas-X |
|---------|---------------|---------|
| Navigation | GPS+IMU | Triple GNSS + FOG IMU + TRN |
| Autopilot | VRC-AP-500 | VRC-AP-700 |
| Max altitude | 4,500 m | 8,200 m |
| Primary sensor | Kryon-7 | Kryon-7X |
| Max payload | 7.6 kg | 9.1 kg (Rev 4.x) |
| Wind tolerance | 12 m/s | 16 m/s |

---

*Document version: 4.1 | Last revised: 22 March 2023 | Maintained by: Dr. Fennis Albrecht (f.albrecht@vrc.org)*
