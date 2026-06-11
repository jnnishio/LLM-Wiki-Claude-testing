# Atlas Autonomous Platform: System Overview and Family Description

**System Identifier:** SYS-ATL-BASE  
**Platform Architect:** Dr. Fennis Albrecht, VRC Autonomous Systems Group  
**Document Issue Date:** 10 April 2020  
**Document Revision:** 2.0 (Updated 03 January 2023)

---

## 1. Introduction

The **Atlas** is a family of autonomous aerial platforms designed and maintained by the VRC Autonomous Systems Group for scientific payload deployment in remote and extreme environments. The Atlas family was conceived to address the need for repeatable, precisely navigated low-altitude atmospheric and surface survey missions where ground access is impractical or hazardous.

The Atlas family comprises four variants, each optimised for a different operational envelope:

| Variant | System Code | Primary Role | Key Document |
|---------|-------------|--------------|--------------|
| Atlas (baseline) | SYS-ATL-001 | General scientific survey | This document |
| Atlas-X | SYS-ATL-X002 | Enhanced navigation, high-altitude | Document 09 |
| Atlas-II | SYS-ATL-II003 | Subsurface mapping (tethered) | Document 10 |
| Atlas North | SYS-ATL-N004 | Polar operations, cold-hardened | Document 11 |

All variants share a common avionics core and payload interface standard (VRC-PAYIF-2019-01) but differ in airframe, propulsion, thermal management, and sensor integration.

## 2. Atlas Baseline Specifications

### 2.1 Physical

| Parameter | Atlas Baseline |
|-----------|---------------|
| System Code | SYS-ATL-001 |
| Airframe type | Fixed-wing with VTOL assist |
| Wingspan | 2.4 m |
| Fuselage length | 1.8 m |
| Empty mass | 22.4 kg |
| Maximum take-off mass | 30.2 kg |
| Maximum payload mass | 7.6 kg |
| Propulsion | 4× electric rotors + 1× pusher propeller |

### 2.2 Performance

| Parameter | Value |
|-----------|-------|
| Cruise speed | 65 km/h |
| Maximum speed | 120 km/h |
| Endurance (cruise, full payload) | 3.2 hours |
| Maximum operating altitude | 4,500 m AMSL |
| Navigation accuracy (GNSS+IMU) | ±2.5 m horizontal |
| Wind tolerance | 12 m/s sustained |

### 2.3 Avionics Core

The Atlas avionics core is common to all variants:

- **Flight computer:** VRC-FC-500 (dual redundant)
- **IMU:** Veltrix IMU-3 (6-axis, 200 Hz)
- **GNSS:** Dual-constellation (GPS + GLONASS), RTK-capable
- **Datalink:** 900 MHz spread-spectrum, range 25 km LOS
- **Telemetry protocol:** VRC-ATL-ICD-2019-01

### 2.4 Payload Interface

All Atlas variants use the **VRC-PAYIF-2019-01** standard payload bay interface, which provides:
- Mechanical: 4-point locking tray, max 200 mm × 180 mm × 80 mm (H) footprint
- Electrical: 28 VDC power (max 60 W), USB 3.0 data, RS-422 command
- Approved payloads: See VRC Payload Approved List (PAL-2023-ATL)

Approved sensor payloads include the Kryon-7 (via adapter bracket VRC-MNT-ATL-03) and the Kryon-7X (via adapter VRC-MNT-ATL-04). See Documents 02 and 18 respectively.

## 3. Family Differentiation Summary

### 3.1 Why Multiple Variants

The Atlas baseline meets most standard survey requirements. The specialised variants were developed to address limitations in specific contexts:

- **Atlas-X** adds redundant navigation hardware and a higher-authority autopilot for operations in GPS-degraded environments and at altitudes above 4,500 m. It also accommodates heavier payloads and the Kryon-7X sensor.
- **Atlas-II** is a tethered underwater/under-ice variant sharing the avionics architecture but using a completely different chassis designed for subsurface deployment to depths of 340 m. It is the primary platform for **Project TRITON** (Document 12).
- **Atlas North** is a cold-hardened version of the Atlas-X with heated avionics bays, insulated battery packs, and modified propulsion optimised for low-temperature operation. It is the primary platform for **Project SABLE** (Document 22).

### 3.2 Common Maintenance and Logistics

All Atlas variants are maintained under a single consolidated maintenance programme (document reference: VRC-ATL-MAINT-2020-03). Spare parts are held at:
- Halvern Testing Ground (FAC-HLV-002) — primary maintenance facility
- Oswick Station (FAC-OSW-001) — forward spares cache (Atlas and Atlas North only)

Dr. Fennis Albrecht holds technical authority for all Atlas variants. Operational deployment decisions for each program are the responsibility of the respective project principal investigator.

## 4. Operational History

| Year | Milestone |
|------|-----------|
| 2018 | Atlas baseline design initiated |
| 2019 | First flight, Halvern Testing Ground (04 July 2019) |
| 2020 | Atlas-X variant design completed; SYS-ATL-II003 (Atlas-II) prototyped |
| 2021 | Atlas North design initiated (cold-hardened program) |
| 2022 | All four variants in active operational service |
| 2023 | VRC-PAYIF-2019-01 v2 update; Atlas-X payload limit revised (see Document 09) |

---

## Appendix A: Variant Cross-Reference

| Feature | Atlas | Atlas-X | Atlas-II | Atlas North |
|---------|-------|---------|----------|-------------|
| VTOL | Yes | Yes | N/A | Yes |
| Max altitude | 4,500 m | 8,200 m | 340 m depth | 4,500 m |
| Cold hardened | No | No | No | Yes |
| Tethered | No | No | Yes | No |
| Primary sensor | Kryon-7 | Kryon-7X | Custom sonar | Kryon-7X |

## Appendix B: Firmware Baseline

All Atlas variants ship with avionics firmware from the **ATL-FW** track. Current production firmware: **ATL-FW-v7.1.2** (released 15 September 2023). An over-the-air firmware update mechanism is available for the flight computer only; all other firmware must be updated by VRC-certified technicians at Halvern.

---

*Document version: 2.0 | Last revised: 03 January 2023 | Maintained by: Dr. Fennis Albrecht, VRC Autonomous Systems Group (f.albrecht@vrc.org)*
