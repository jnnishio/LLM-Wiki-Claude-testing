---
title: Peltex-200 Radiometric Sensor
created: 2026-06-10
updated: 2026-06-10
type: concept
tags: [sensor, irradiance, calibration, superseded]
sources: [raw/documents/document_14.md, raw/documents/document_13.md, raw/documents/document_04.md]
confidence: high
---

# Peltex-200 Radiometric Sensor

**Current system code:** SYS-PEL200-R02 (v2.1)  
**Developer:** VRC Instrumentation Laboratory (Eng. Korvyn Dratch, [[team-crestfield]])  
**Current spec:** Document 14 (SYS-PEL200-R02, issued 17 January 2022)  
**Superseded spec:** Document 13 (SYS-PEL200-R01, issued September 2020) — **DO NOT USE** for calibration

## Overview

Broadband ground-based radiometric sensor for long-duration solar irradiance monitoring. Primary instrument for [[project-helios]] and one of six modalities in [[project-nexus]]. Measures total solar irradiance (direct + diffuse) across 300–2500 nm.

## Physical Specifications (unchanged between v1.0 and v2.1)

| Parameter | Value |
|-----------|-------|
| System Code | SYS-PEL200-R02 |
| Dimensions | 420 × 420 × 185 mm |
| Mass | 3.7 kg |
| Detector type | Black-body thermopile (64-element) |
| Spectral range | 300–2500 nm |
| Cosine response error | <3% for angles ≤80° |
| Power | 12–24 VDC, ≤4 W |
| Output | 16-bit ADC, RS-232 at 9,600 bps |

## CRITICAL: Calibration Constant

> **The old calibration constant (0.00447) is erroneous and must NOT be used.**

| Version | K_cal | Status |
|---------|-------|--------|
| v1.0 (Doc 13) | **0.00447** W·m⁻²·sr⁻¹/count | **SUPERSEDED — 14.3% systematic high bias** |
| v2.1 (Doc 14) | **0.00391** W·m⁻²·sr⁻¹/count | **CURRENT — correct value** |

The error originated from a faulty reference standard used in August 2020 factory calibrations (VRC-CAL-PEL200-2020-08). Discovered December 2021. All units serialised PEL200-0001 through PEL200-0060 received the incorrect constant and required firmware update to v2.4.1. ^[raw/documents/document_14.md]

**Firmware check:** v2.4.1+ applies K_cal = 0.00391 automatically. Units running v2.3.x still apply the erroneous 0.00447 and **must be updated immediately**.

## Temperature Correction Polynomial (unchanged between versions)

```
ΔC_temp = −0.0012 × T² + 0.047 × T − 0.31
```

## HELIOS Ground Station Fleet

| Station | Unit ID | Installation Date | In Affected Range? | Status |
|---------|---------|------------------|--------------------|--------|
| Oswick Station | PEL-200-0022 | 14 Sep 2021 | Yes | Updated 28 Jan 2022 |
| Halvern Testing Ground | PEL-200-0031 | 22 Oct 2021 | Yes | Updated 03 Feb 2022 |
| Crestfield Lab | PEL-200-0041 | 09 Nov 2021 | Yes | Updated (Feb 2022) |
| Thule Relay Outpost | PEL-200-0055 | 03 Mar 2022 | Yes | Updated (Feb 2022) |

HELIOS data reprocessed with corrected constant and tagged `HELIOS-REPR-2022`. Any HELIOS data lacking this tag (pre-15 April 2022) must be reprocessed before use. ^[raw/documents/document_04.md]

## Calibration Validity

| Calibration Date | Valid Until | Certificate |
|-----------------|-------------|-------------|
| 10 January 2022 | 09 January 2024 | VRC-CAL-PEL200-2022-01 |
| 15 January 2024 | 14 January 2026 | VRC-CAL-PEL200-2024-01 |

Field recalibration: every **24 months**, procedure VRC-CAL-PROC-PEL200-002 (v2.0).  
Specialist: Kofi Twumasi-Mensah ([[team-crestfield]])

## Airborne Use: EXP-441 Bias

When mounted on Atlas-X at cruise (70 km/h), Peltex-200 shows **−0.4 W/m²** bias (negative; underestimate due to heated exhaust air partially shading solar aperture). At 120 km/h: −1.1 W/m². Correction algorithms from [[exp-441]] are being incorporated into HELIOS processing chain. ^[raw/documents/document_15.md]

## Housing Corrosion

Standard marine-grade anodised aluminium housing shows corrosion rate of 8.7 μm/year at Oswick under-ice sites. Estimated housing life ~14.3 years before hitting 0.5 mm safety margin (based on EXP-119 pit growth rate). Enhanced anodise v2 coating recommended for new under-ice deployments. See [[exp-119]]. ^[raw/documents/document_21.md]

## Related

[[project-helios]] | [[project-nexus]] | [[exp-441]] | [[exp-119]] | [[team-crestfield]] | [[halvern-testing-ground]] | [[oswick-station]] | [[kryon-7]]
