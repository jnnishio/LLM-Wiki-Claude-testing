# Kryon-7X Advanced Variant: Technical Specification

**System Code:** SYS-KRY7X-002  
**Revision:** 2.1  
**Date of Issue:** 12 June 2022  
**Issuing Authority:** Dr. Renna Holt, Team Crestfield Instrumentation Division

---

## 1. Introduction

The Kryon-7X (system code SYS-KRY7X-002) is the advanced successor to the Kryon-7 (Document 02, SYS-KRY7-001), developed by Team Crestfield (Document 19) to address performance limitations of the Kryon-7 in demanding high-altitude, low-light, and GPS-degraded environments. The Kryon-7X is not merely an incremental update; it uses a redesigned optical system with a new detector array, substantially reducing the noise floor and extending the spectral range.

The Kryon-7X is the designated sensor for:
- **Atlas-X** platform (Document 09) — replaces Kryon-7 in new deployments
- **Atlas North** platform (Document 11) — primary sensor for Project SABLE
- **Project NEXUS** (Document 24) — one of six sensor modalities in the multi-sensor fusion stack

## 2. Physical Specifications

| Parameter | Kryon-7X | Kryon-7 (ref., Doc 02) |
|-----------|---------|----------------------|
| System Code | SYS-KRY7X-002 | SYS-KRY7-001 |
| Dimensions | 340 × 210 × 94 mm | 310 × 195 × 88 mm |
| Mass (without bracket) | 2.48 kg | 2.14 kg |
| Enclosure rating | IP68 | IP67 |
| Operating temperature | −65°C to +55°C | −55°C to +50°C |
| Power consumption (active) | 11.2 W | 8.4 W |
| Connector type | Veltrix-16P locking | Veltrix-12P locking |

*Note: The Kryon-7X uses the Veltrix-16P connector; it is not pin-compatible with the Kryon-7 Veltrix-12P connector. Adapter cable VRC-ADAPT-KRY-7to7X is available for legacy integration scenarios.*

## 3. Optical and Electrical Specifications

### 3.1 Spectral Bands

The Kryon-7X extends Band coverage from 4 bands (Kryon-7) to 6 bands:

| Band | Wavelength Range | Detector Type | Sampling Rate |
|------|-----------------|---------------|---------------|
| Band 1 | 0.3–0.6 μm | UV-optimised silicon PV | 20 Hz |
| Band 2 | 0.6–1.0 μm | Silicon PV | 20 Hz |
| Band 3 | 1.0–1.7 μm | InGaAs PV | 10 Hz |
| Band 4 | 1.7–2.5 μm | Extended-InGaAs PV | 10 Hz |
| Band 5 | 2.5–4.0 μm | HgCdTe PV | 5 Hz |
| Band 6 | 4.0–8.0 μm | HgCdTe PV | 2 Hz |

### 3.2 Performance Comparison

| Parameter | Kryon-7X | Kryon-7 |
|-----------|---------|---------|
| Dynamic range | 102 dB | 86 dB |
| Linearity error | < 0.04% full-scale | < 0.08% |
| Cross-channel isolation | > 62 dB | > 52 dB |
| Warm-up time | 6 minutes | 8 minutes |
| Number of spectral bands | 6 | 4 |

### 3.3 Noise Floor

The Kryon-7X achieves a substantially improved noise floor compared to the Kryon-7, critical for low-light applications such as Project SABLE:

| Parameter | Kryon-7X | Kryon-7 (ref.) |
|-----------|---------|----------------|
| Aggregate noise floor (V/√Hz) | 3.11 × 10⁻⁹ | 4.72 × 10⁻⁸ |
| Improvement factor | ~15× | — |

The **Kryon-7X aggregate noise floor of 3.11 × 10⁻⁹ V/√Hz** (measured at ADC input, full spectral range) represents a 15-fold improvement over the Kryon-7. This was achieved through a combination of low-noise pre-amplifier redesign, improved shielding, and a new detector bonding process.

## 4. Communication Interfaces

The Kryon-7X uses an upgraded interface compared to the Kryon-7:

- **Primary:** GigE (1000BASE-T), supporting high-bandwidth streaming at 20 Hz for all 6 bands simultaneously
- **Secondary:** RS-422 at 230,400 baud (compatibility mode, reduced data rate)
- **Sync:** 1 PPS GPS input (same as Kryon-7)
- **Telemetry:** Irixon-4 compatible module (part code KRY7X-TEL-MOD-02)

## 5. Firmware

Current production firmware: **v1.2.3** (released 08 February 2023)

The Kryon-7X uses a different firmware track (KRY7X-FW) from the Kryon-7 (KRY7-FW). They are not interchangeable. Firmware updates are distributed via VRC Instrumentation Portal under section KRY7X.

## 6. Calibration

Calibration procedure: **VRC-CAL-PROC-KRY7X-001** (separate from Kryon-7 procedure).

Calibration interval: **12 months** (more frequent than Kryon-7's 18-month interval, due to HgCdTe detector sensitivity drift).

Calibration specialist: Kofi Twumasi-Mensah (Team Crestfield). All Kryon-7X calibrations are performed at the Team Crestfield laboratory at Halvern (HLV-B03).

## 7. Platform Integration

| Platform | Integration Bracket | Notes |
|----------|---------------------|-------|
| Atlas-X (Doc 09) | VRC-MNT-ATL-04 | Primary configuration |
| Atlas North (Doc 11) | VRC-MNT-ATL-N-06 (combined with Valdyne) | Cold-hardened configuration |
| Fixed mast | VRC-MNT-ST-04 | For NEXUS ground installations |

## 8. Transition from Kryon-7

Team Velanthor's Atlas-X fleet is transitioning from Kryon-7 to Kryon-7X payloads. The transition schedule:

| Platform/Program | Transition Date | Status |
|-----------------|----------------|--------|
| Atlas North / SABLE | November 2022 | Completed |
| Atlas-X AETHER profiles | January 2023 | Completed |
| NOVA Zone C Atlas-X nodes | Q2 2024 (planned) | Pending |
| NOVA Zone A/B fixed nodes | Not planned | Kryon-7 remains |

---

## Appendix A: Electrical Interface Pinout (Veltrix-16P)

| Pin | Signal | Direction | Notes |
|-----|--------|-----------|-------|
| 1–2 | PWR+ / PWR− | In | 12–28 VDC |
| 3–6 | GigE differential pairs | Bi-dir | |
| 7–10 | RS-422 TX+/TX−/RX+/RX− | Bi-dir | Compatibility mode |
| 11 | SYNC_IN | In | 1 PPS |
| 12–15 | Spare / future use | — | |
| 16 | CHASSIS | — | Ground |

## Appendix B: System Identifier

| Field | Value |
|-------|-------|
| System Code | SYS-KRY7X-002 |
| Hardware Revision | 2.1 |
| Production Firmware | KRY7X-FW-v1.2.3 |
| Production lot (current) | SYS-KRY7X-002-LOT-02 |
| CRC-16 calibration checksum | 9E3A |

The calibration checksum `9E3A` is the CRC-16 of the calibration coefficient table for hardware revision 2.1, computed over the full 64-byte coefficient block. It must match for calibration validation to pass.[^1]

[^1]: The 9E3A checksum is specific to hardware revision 2.1. Hardware revision 2.0 uses calibration checksum 7C11. A mismatch between expected and computed checksum during the Kryon-7X self-test indicates either a calibration memory corruption event or installation of an incorrect calibration file, and requires return to Team Crestfield for re-characterisation.

---

*Document version: 2.1 | Last revised: 12 June 2022 | Approved by: Dr. Renna Holt, Team Crestfield (r.holt@vrc.org)*
