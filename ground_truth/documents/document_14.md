# Peltex-200 Radiometric Sensor: Technical Specification — Version 2.1 (CURRENT)

**System Code:** SYS-PEL200-R02  
**Document Status:** CURRENT — Supersedes Document 13 (Peltex-200 v1.0, SYS-PEL200-R01)  
**Hardware Lead:** Eng. Korvyn Dratch, VRC Instrumentation Laboratory  
**Date of Issue:** 17 January 2022  
**Approved By:** Dr. Renna Holt, Team Crestfield

---

## 1. Introduction

This document (SYS-PEL200-R02) is the current technical specification for the Peltex-200 broadband radiometric sensor. It supersedes Document 13 (SYS-PEL200-R01, issued September 2020) in its entirety.

The principal change from v1.0 is a corrected calibration constant, replacing the erroneous value of 0.00447 W·m⁻²·sr⁻¹ per count specified in Document 13 with the corrected value of **0.00391 W·m⁻²·sr⁻¹ per count** derived from recalibration against verified reference standards. All other physical and electrical specifications are unchanged from Document 13.

The Peltex-200 is deployed across the HELIOS ground network (Document 04) and is also integrated into **Project NEXUS** (Document 24) as one of the six sensor modalities in the NEXUS multi-sensor fusion platform.

## 2. Physical Specifications

*(Unchanged from SYS-PEL200-R01. See Document 13 Section 2.)*

| Parameter | Value |
|-----------|-------|
| System Code | SYS-PEL200-R02 |
| Dimensions | 420 × 420 × 185 mm |
| Mass | 3.7 kg |
| Detector type | Black-body thermopile (64-element) |
| Spectral range | 300–2500 nm |
| Cosine response error | < 3% for angles ≤ 80° |

## 3. Electrical and Communication

*(Unchanged from SYS-PEL200-R01. See Document 13 Section 3.)*

## 4. Calibration (Version 2.1 — CURRENT)

### 4.1 Background: Calibration Error in Version 1.0

In December 2021, an audit of the VRC Metrology Laboratory revealed that the solar irradiance reference standard used for Peltex-200 factory calibrations in August 2020 (reference: VRC-CAL-PEL200-2020-08) had a systematic positive offset of approximately 14.3% due to a traceable uncertainty failure in the reference standard's own calibration chain. This affected the K_cal constant embedded in units manufactured before January 2022 and documented in SYS-PEL200-R01.

All affected units (serial numbers PEL200-0001 through PEL200-0060) were recalled for firmware update in January–February 2022. All HELIOS data products derived from affected units prior to the firmware update were reprocessed under the corrected constant (reprocessed data tagged `HELIOS-REPR-2022`; see Document 04, Appendix A).

### 4.2 Temperature Correction Polynomial

The temperature correction polynomial is unchanged:

```
ΔC_temp = −0.0012 × T² + 0.047 × T − 0.31
```

### 4.3 Calibration Constant (CURRENT)

The corrected calibration constant, derived from recalibration against NVIST-primary standard SVS-NVIST-P04 (calibration date: 10 January 2022, certificate: VRC-CAL-PEL200-2022-01):

**K_cal = 0.00391 W·m⁻²·sr⁻¹ per digital count (post temperature correction)**

This value is embedded in production firmware v2.4.1 and higher. Units still running firmware v2.3.x or earlier should be updated immediately.

### 4.4 Calibration Validity

| Calibration Date | Valid Until | Reference Standard | Certificate |
|-----------------|-------------|-------------------|-------------|
| 10 January 2022 | 09 January 2024 | SVS-NVIST-P04 | VRC-CAL-PEL200-2022-01 |
| 15 January 2024 | 14 January 2026 | SVS-NVIST-P04 | VRC-CAL-PEL200-2024-01 |

Field recalibration is required every **24 months** using procedure VRC-CAL-PROC-PEL200-002 (v2.0, January 2022).

### 4.5 Calibration Specialist

Kofi Twumasi-Mensah (Team Crestfield) is the designated calibration specialist for the Peltex-200 fleet. All calibration activities must be coordinated through him. Contact: k.twumasi-mensah@vrc.org.

## 5. Firmware

Current production firmware: **v2.4.1** (released 14 January 2022)

Firmware v2.4.1 automatically applies K_cal = 0.00391 to all output data. Units still running v2.3.x apply K_cal = 0.00447 (the erroneous value) and must be updated.

| Firmware | K_cal Applied | Status |
|----------|--------------|--------|
| v2.4.1+ | 0.00391 (correct) | Required |
| v2.3.x | 0.00447 (erroneous) | Must update |
| v2.2.x and earlier | 0.00447 (erroneous) | Must update |

## 6. Deployment and Operations

*(Unchanged from SYS-PEL200-R01. See Document 13 Section 5.)*

## 7. Integration with Other Programs

| Program | Document | Use |
|---------|----------|-----|
| Project HELIOS | Doc 04 | Primary radiometric instrument |
| Project NEXUS | Doc 24 | One of 6 modalities in multi-sensor fusion |
| EXP-441 | Doc 15 | Ancillary irradiance reference during thermal tests |

---

## Appendix A: Summary of Changes from Version 1.0

| Section | Change |
|---------|--------|
| Section 4.3 | K_cal corrected from 0.00447 to **0.00391** |
| Section 4.4 | Calibration validity table added |
| Section 4.5 | Calibration specialist contact added |
| Section 5 | Firmware version table updated |
| Appendix A | Affected serial number range documented |
| Appendix B | Updated recalibration procedure reference |

## Appendix B: Affected Unit Tracking

| Serial Range | Calibration Error Present | Firmware Update Applied | Status |
|-------------|--------------------------|------------------------|--------|
| PEL200-0001 – PEL200-0060 | Yes (v1.0) | Yes (Jan–Feb 2022) | Corrected |
| PEL200-0061 – present | No | N/A | Correct from factory |

*Note: Units PEL200-0022 (Oswick Station, HELIOS) and PEL200-0031 (Halvern, HELIOS) are in the affected range and received firmware updates on 28 January 2022 and 03 February 2022 respectively.*

---

*Document version: 2.1 | Last revised: 17 January 2022 | Author: Eng. Korvyn Dratch | Approved: Dr. Renna Holt, Team Crestfield (r.holt@vrc.org)*
