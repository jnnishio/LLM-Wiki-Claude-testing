# Kryon-7 Sensor System: Technical Specification Sheet

**System Code:** SYS-KRY7-001  
**Revision:** 3.2  
**Date of Issue:** 07 September 2021  
**Issuing Authority:** Dr. Renna Holt, Team Crestfield Instrumentation Division

---

## 1. Introduction

The Kryon-7 is a multi-spectral atmospheric sampling sensor developed by Team Crestfield (see Document 19) for deployment in high-altitude and polar-environment monitoring applications. It serves as the primary instrument for **Project NOVA** (Document 01) and is also integrated into the **Project AETHER** high-altitude platform configuration (Document 17).

The Kryon-7 uses a hybrid detection array combining photovoltaic and thermopile elements across four spectral bands (0.4–5.0 μm), enabling simultaneous measurement of aerosol scattering coefficients, trace gas absorption lines, and broadband radiance.

## 2. Physical Specifications

| Parameter | Value |
|-----------|-------|
| Dimensions (L × W × H) | 310 × 195 × 88 mm |
| Mass (without mounting bracket) | 2.14 kg |
| Mass (with standard bracket) | 2.61 kg |
| Enclosure rating | IP67 |
| Operating temperature range | −55°C to +50°C |
| Storage temperature range | −65°C to +70°C |
| Power consumption (active) | 8.4 W |
| Power consumption (standby) | 0.7 W |
| Connector type | Veltrix-12P locking |

## 3. Optical and Electrical Specifications

### 3.1 Spectral Bands

| Band | Wavelength Range | Detector Type | Sampling Rate |
|------|-----------------|---------------|---------------|
| Band 1 | 0.4–0.7 μm | Silicon PV | 10 Hz |
| Band 2 | 0.7–1.4 μm | InGaAs PV | 10 Hz |
| Band 3 | 1.4–2.5 μm | InGaAs PV | 5 Hz |
| Band 4 | 2.5–5.0 μm | Thermopile | 2 Hz |

### 3.2 Performance

- Dynamic range: 86 dB
- Linearity error: < 0.08% full-scale
- Cross-channel isolation: > 52 dB
- Warm-up time to specification: 8 minutes from cold start

### 3.3 Signal Noise Performance

The Kryon-7 achieves a noise-equivalent power (NEP) suited to high-sensitivity atmospheric work. The noise floor specification is a critical parameter for NOVA deployments in polar night conditions.

| Parameter | Band 1 | Band 2 | Band 3 | Band 4 |
|-----------|--------|--------|--------|--------|
| NEP (W/√Hz) | 1.2 × 10⁻¹⁰ | 8.4 × 10⁻¹¹ | 3.7 × 10⁻¹⁰ | 6.1 × 10⁻⁹ |

## 4. Communication Interfaces

The Kryon-7 supports the following digital interfaces:

- **Primary:** RS-422 serial at 115,200 baud
- **Secondary:** CAN 2.0B (1 Mbit/s)
- **Telemetry (optional):** Irixon-4 compatible module (part code KRY7-TEL-MOD-01)

Data packets are formatted per VRC ICD-2019-07 and include a CRC-16 checksum field. The device network address is set via a 4-position DIP switch array on the rear panel.

## 5. Firmware

Current production firmware: **v4.3.1** (released 14 April 2023)

Firmware updates are distributed via the VRC Instrumentation Portal (portal code: VRC-INST-PORTAL). Version 4.3.1 corrects a Band 3 overrange artefact present in v4.2.x under sustained high-irradiance conditions. All NOVA deployments were updated to v4.3.1 by 01 June 2023.

### 5.1 Firmware Compatibility

| Firmware Version | Hardware Revision | NOVA Compatible |
|------------------|------------------|-----------------|
| v4.3.1 | Rev 3.0, 3.1, 3.2 | Yes |
| v4.2.x | Rev 2.x, 3.x | Partial (Band 3 artefact) |
| v3.x.x | Rev 2.x only | No |

## 6. Calibration

All Kryon-7 units are factory-calibrated against NVIST-traceable references prior to shipment. Field recalibration is required every **18 months** or after any incident exceeding 12 g shock loading.

Calibration procedure reference: VRC-CAL-PROC-KRY7-001.

*Note: The Kryon-7X variant (Document 18) uses a different calibration procedure and should not be calibrated using this document.*

## 7. Mounting and Deployment

Approved mounting configurations:

- **Static mast mount:** VRC-MNT-ST-01 (fixed installations, Oswick Station and Halvern)
- **Gimbal mount:** VRC-MNT-GB-02 (for platform integration; used in AETHER, Document 17)
- **Atlas integration bracket:** VRC-MNT-ATL-03 (for Atlas UAV platform family, Documents 08–11)

Units must be oriented within ±2° of the specified optical axis. Exceeding this tolerance invalidates calibration.

## 8. Related Documents

- Document 01: Project NOVA (primary deployment context)
- Document 17: Project AETHER (secondary deployment context)
- Document 18: Kryon-7X Advanced Variant (successor platform)
- Document 19: Team Crestfield (issuing organization)
- Document 24: Project NEXUS (multi-sensor integration using Kryon-7X)

---

## Appendix A: Electrical Interface Pinout

| Pin | Signal | Direction | Notes |
|-----|--------|-----------|-------|
| 1 | PWR+ | In | 9–28 VDC |
| 2 | PWR− | In | Ground reference |
| 3 | RS422-TX+ | Out | |
| 4 | RS422-TX− | Out | |
| 5 | RS422-RX+ | In | |
| 6 | RS422-RX− | In | |
| 7–10 | CAN_H/L ×2 | Bi-dir | Dual-port |
| 11 | SYNC_IN | In | 1 PPS GPS sync |
| 12 | CHASSIS | — | Ground lug |

## Appendix B: Noise Floor Detail

The following specification applies to units in hardware revision 3.2 only. Earlier revisions have higher noise floors and should be regarded as superseded for high-sensitivity applications.

The **aggregate voltage-referred noise floor of the Kryon-7 (Rev 3.2) across the full spectral range is 4.72 × 10⁻⁸ V/√Hz**, measured at the ADC input after on-board pre-amplification. This value is used as a reference input to the NOVA atmospheric retrieval algorithm (retrieval code: NOVA-RETR-v3). Any unit measuring a noise floor above 5.00 × 10⁻⁸ V/√Hz during field health checks must be returned to Team Crestfield for re-inspection.[^1]

[^1]: Noise floor specification established in Team Crestfield internal test report TC-TEST-2021-44, dated 02 August 2021. The 4.72 × 10⁻⁸ V/√Hz figure represents the 95th-percentile upper bound across a sample of 47 production units; the median measured value was 4.31 × 10⁻⁸ V/√Hz.

*Figure 1: Spectral response curves for Bands 1–4 at nominal operating temperature (20°C). Dashed lines indicate the −3 dB roll-off points.*

*Figure 2: Noise floor distribution histogram for production lot SYS-KRY7-001-LOT-04 (n = 47 units).*

---

*Document version: 3.2 | Last revised: 07 September 2021 | Approved by: Dr. Renna Holt, Team Crestfield*
