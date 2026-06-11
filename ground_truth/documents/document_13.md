# Peltex-200 Radiometric Sensor: Technical Specification — Version 1.0

**System Code:** SYS-PEL200-R01  
**Document Status:** SUPERSEDED — See Document 14 (Peltex-200 v2.1, SYS-PEL200-R02) for current specification  
**Hardware Lead:** Eng. Korvyn Dratch, VRC Instrumentation Laboratory  
**Date of Issue:** 04 September 2020  
**Superseded By:** SYS-PEL200-R02 (Document 14, issued 17 January 2022)

---

> **NOTICE:** This document (SYS-PEL200-R01) has been superseded by the Peltex-200 v2.1 specification (Document 14). The calibration constant specified in Section 4.3 of this document (**0.00447 W·m⁻²·sr⁻¹ per digital count**) was found to contain a systematic error and has been replaced by the corrected value of **0.00391** in Document 14. All operational use of the Peltex-200 must reference Document 14.

---

## 1. Introduction

The Peltex-200 is a broadband ground-based radiometric sensor developed by the VRC Instrumentation Laboratory for long-duration solar irradiance monitoring. It is deployed across the HELIOS program ground network (Document 04) and in support of several ancillary VRC programs requiring radiometric reference measurements.

The sensor measures total solar irradiance (direct + diffuse) across a broadband response spanning 300–2500 nm, using a thermopile detector with a temperature-compensated housing.

## 2. Physical Specifications

| Parameter | Value |
|-----------|-------|
| System Code | SYS-PEL200-R01 |
| Dimensions | 420 × 420 × 185 mm (including levelling base) |
| Mass | 3.7 kg |
| Detector type | Black-body thermopile (64-element) |
| Spectral range | 300–2500 nm |
| Cosine response error | < 3% for angles ≤ 80° |
| Housing material | Marine-grade anodised aluminium |
| Desiccant cartridge | VRC-DESI-PEL-01 (replaceable, 6-month interval) |

## 3. Electrical and Communication

| Parameter | Value |
|-----------|-------|
| Power supply | 12–24 VDC, ≤ 4 W |
| Output signal | 16-bit ADC, digital RS-232 |
| Baud rate | 9,600 bps |
| Output rate | 1 Hz standard, 0.1 Hz or 0.01 Hz selectable |
| Communication protocol | VRC-PME-ICD-2018-02 |

## 4. Calibration (Revision 1.0 — SUPERSEDED)

### 4.1 Calibration Approach

The Peltex-200 converts raw ADC counts to physical irradiance units using a two-stage calibration:

1. **Temperature correction:** A thermistor measures the detector housing temperature, and a polynomial correction is applied to remove temperature-induced sensitivity drift
2. **Sensitivity correction:** A factory-derived calibration constant is applied to convert temperature-corrected counts to W·m⁻²·sr⁻¹

### 4.2 Temperature Correction Polynomial

The temperature correction polynomial (in Celsius):

```
ΔC_temp = −0.0012 × T² + 0.047 × T − 0.31
```

This polynomial is unchanged between versions 1.0 and 2.1.

### 4.3 Calibration Constant (SUPERSEDED)

**SUPERSEDED VALUE — DO NOT USE:**

The calibration constant specified in this version is:

**K_cal = 0.00447 W·m⁻²·sr⁻¹ per digital count (post temperature correction)**

*This value was derived from factory calibration runs conducted in August 2020 (reference: VRC-CAL-PEL200-2020-08). A systematic error in the reference standard used during this calibration campaign was discovered in December 2021, affecting all units manufactured before January 2022. The corrected calibration constant is K_cal = 0.00391 (Document 14, Section 4.3). The 0.00447 value produces irradiance estimates that are approximately 14.3% too high.*

### 4.4 Field Recalibration

Field recalibration is required every 24 months. The procedure is given in VRC-CAL-PROC-PEL200-001 (v1.0, also superseded — use v2.0).

## 5. Deployment

The Peltex-200 is designed for installation on a levelling platform (VRC-LEV-PEL-01) or fixed concrete pad. The optical aperture must have unobstructed hemispheric sky access for solar measurements.

Approved deployment facilities: HELIOS network stations (Document 04, Table 4.1). Units must not be deployed at unapproved locations without written authorisation from the VRC Instrumentation Laboratory.

## 6. Data Products

Raw output is in digital counts. Conversion to physical units requires application of the calibration pipeline (temperature correction then sensitivity correction). **For any data collected from Peltex-200 units manufactured before January 2022, the corrected calibration constant from Document 14 must be used; the constant in this document (Section 4.3) must not be applied.**

---

## Appendix A: Unit Serial Numbers Affected by Calibration Error

All Peltex-200 units with serial numbers in the range PEL200-0001 through PEL200-0060 were manufactured before January 2022 and may carry the incorrect K_cal = 0.00447 constant in their embedded firmware. These units require firmware update to v2.4.1 to apply the corrected constant automatically.

Units with serial numbers PEL200-0061 and above were manufactured after January 2022 and use the corrected constant.

## Appendix B: Revision Log

| Version | Date | Summary |
|---------|------|---------|
| v1.0 | 04 September 2020 | Initial issue |
| v1.1 | 12 April 2021 | Minor corrections to Section 3 output format description |

---

*Document version: 1.1 (final before supersession) | Issued: 04 September 2020 | Superseded: 17 January 2022 | Author: Eng. Korvyn Dratch (k.dratch@vrc.org)*
