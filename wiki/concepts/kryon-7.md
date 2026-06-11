---
title: Kryon-7 Sensor System
created: 2026-06-10
updated: 2026-06-10
type: concept
tags: [sensor, atmospheric, calibration]
sources: [raw/documents/document_02.md, raw/documents/document_01.md, raw/documents/document_19.md]
confidence: high
---

# Kryon-7 Sensor System

**System Code:** SYS-KRY7-001 (current hardware revision: 3.2)  
**Developer:** [[team-crestfield]] (issued by Dr. Renna Holt)  
**Spec document:** Document 02 (revision 3.2, issued 07 September 2021)  
**Successor:** [[kryon-7x]] (SYS-KRY7X-002)

## Overview

Multi-spectral atmospheric sampling sensor used across [[project-nova]], [[project-helios]], and [[project-aether]] balloon gondolas. Designed for high-altitude and polar-environment monitoring. Primary instrument for Project NOVA (14 units across 3 zones).

## Physical Specifications

| Parameter | Value |
|-----------|-------|
| Dimensions | 310 × 195 × 88 mm |
| Mass (without bracket) | 2.14 kg |
| Mass (with standard bracket) | 2.61 kg |
| Enclosure rating | IP67 |
| Operating temperature | −55°C to +50°C |
| Power consumption (active) | 8.4 W |
| Connector | Veltrix-12P locking |

## Spectral Bands

| Band | Wavelength | Detector | Rate |
|------|-----------|----------|------|
| Band 1 | 0.4–0.7 μm | Silicon PV | 10 Hz |
| Band 2 | 0.7–1.4 μm | InGaAs PV | 10 Hz |
| Band 3 | 1.4–2.5 μm | InGaAs PV | 5 Hz |
| Band 4 | 2.5–5.0 μm | Thermopile | 2 Hz |

## Performance

- Dynamic range: 86 dB
- Linearity error: <0.08% full-scale
- Cross-channel isolation: >52 dB
- Warm-up time: 8 minutes from cold start
- **Aggregate noise floor (Rev 3.2):** 4.72 × 10⁻⁸ V/√Hz — units exceeding 5.00 × 10⁻⁸ must be returned to [[team-crestfield]] for re-inspection ^[raw/documents/document_02.md]

## Communication Interfaces

- Primary: RS-422 serial at 115,200 baud
- Secondary: CAN 2.0B (1 Mbit/s)
- Telemetry: Irixon-4 compatible module (KRY7-TEL-MOD-01)
- Data format: VRC ICD-2019-07 with CRC-16 checksum

## Firmware

- **Current production:** v4.3.1 (released 14 April 2023)
- v4.3.1 corrects a Band 3 overrange artefact in v4.2.x under sustained high-irradiance conditions
- All NOVA deployments updated to v4.3.1 by 01 June 2023 ^[raw/documents/document_02.md]

| Firmware | HW Revision | NOVA Compatible |
|----------|-------------|-----------------|
| v4.3.1 | Rev 3.0–3.2 | Yes |
| v4.2.x | Rev 2.x–3.x | Partial (Band 3 artefact) |
| v3.x.x | Rev 2.x only | No |

## Calibration

- Factory-calibrated against NVIST-traceable references
- Field recalibration: every **18 months** or after shock >12 g
- Procedure: VRC-CAL-PROC-KRY7-001
- **Note:** Kryon-7X uses a different calibration procedure (VRC-CAL-PROC-KRY7X-001) — not interchangeable ^[raw/documents/document_02.md]

## Deployment

- **Zone A NOVA nodes:** 6 units on OSW-T01, [[oswick-station]]
- **Zone B NOVA nodes:** 5 units at [[halvern-testing-ground]]
- **Zone C NOVA nodes:** 3 units on Atlas-X (mobile, [[atlas-platform-family]])
- **HELIOS stations:** 4 units (cross-program ancillary data)
- **AETHER gondola:** Bands 1–3 only (Band 4 not flown above 20 km due to thermal constraints)

## Known Issues

- Zone A units exhibit **1.2 dB signal attenuation during polar night** (solar elevation <−6°). Correction factors apply by band and month (see Document 01 Appendix A). ^[raw/documents/document_01.md]
- Aerodynamic heating bias on Atlas-X at cruise speed: +0.31°C effective (Band 1), +0.08°C (Band 4) — correction algorithms from [[exp-441]]
- Housing (marine-grade anodised aluminium): corrosion rate 8.7 μm/year at Oswick under-ice sites — see [[exp-119]] for implications

## Transition

[[team-velanthor]]'s Atlas-X fleet is transitioning to [[kryon-7x]]. NOVA Zone A/B fixed nodes are **not planned** for transition; they remain on Kryon-7.

## Related

[[kryon-7x]] | [[project-nova]] | [[project-helios]] | [[project-aether]] | [[team-crestfield]] | [[exp-119]] | [[exp-441]] | [[comparisons/kryon-7-vs-kryon-7x]]
