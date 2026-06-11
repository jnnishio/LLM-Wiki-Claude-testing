---
title: Kryon-7X Advanced Variant
created: 2026-06-10
updated: 2026-06-10
type: concept
tags: [sensor, atmospheric, calibration, optical]
sources: [raw/documents/document_18.md, raw/documents/document_19.md, raw/documents/document_22.md]
confidence: high
---

# Kryon-7X Advanced Variant

**System Code:** SYS-KRY7X-002 (hardware revision 2.1)  
**Developer:** [[team-crestfield]] (issued by [[renna-holt]])  
**Spec document:** Document 18 (revision 2.1, issued 12 June 2022)  
**Predecessor:** [[kryon-7]] (SYS-KRY7-001)

## Overview

Advanced successor to the [[kryon-7]], with substantially improved noise floor (~15× better), extended spectral range (6 bands vs 4), and enhanced environmental ratings. Designed for high-altitude, low-light, and GPS-degraded environments. Primary sensor for [[project-sable]] (polar night photometry) and transitioning into [[project-nova]] Zone C.

## Physical Specifications

| Parameter | Kryon-7X | Kryon-7 |
|-----------|---------|---------|
| Dimensions | 340 × 210 × 94 mm | 310 × 195 × 88 mm |
| Mass (without bracket) | 2.48 kg | 2.14 kg |
| Enclosure rating | IP68 | IP67 |
| Operating temperature | −65°C to +55°C | −55°C to +50°C |
| Power consumption (active) | 11.2 W | 8.4 W |
| Connector | Veltrix-16P | Veltrix-12P |

**Connector incompatibility:** Kryon-7X uses Veltrix-16P — not pin-compatible with Kryon-7 Veltrix-12P. Adapter cable VRC-ADAPT-KRY-7to7X available for legacy integration.

## Spectral Bands (6 bands, vs Kryon-7's 4)

| Band | Wavelength | Detector | Rate |
|------|-----------|----------|------|
| Band 1 | 0.3–0.6 μm | UV-optimised silicon PV | 20 Hz |
| Band 2 | 0.6–1.0 μm | Silicon PV | 20 Hz |
| Band 3 | 1.0–1.7 μm | InGaAs PV | 10 Hz |
| Band 4 | 1.7–2.5 μm | Extended-InGaAs PV | 10 Hz |
| Band 5 | 2.5–4.0 μm | HgCdTe PV | 5 Hz |
| Band 6 | 4.0–8.0 μm | HgCdTe PV | 2 Hz |

## Performance vs Kryon-7

| Parameter | Kryon-7X | Kryon-7 |
|-----------|---------|---------|
| Dynamic range | 102 dB | 86 dB |
| Linearity error | <0.04% | <0.08% |
| Cross-channel isolation | >62 dB | >52 dB |
| Warm-up time | 6 minutes | 8 minutes |
| **Aggregate noise floor** | **3.11 × 10⁻⁹ V/√Hz** | **4.72 × 10⁻⁸ V/√Hz** |
| Noise improvement | ~15× better | — |

The noise floor improvement is the key differentiator enabling SABLE's low-light polar night photometry. ^[raw/documents/document_18.md]

## Communication

- Primary: GigE (1000BASE-T) — supports 20 Hz streaming for all 6 bands simultaneously
- Secondary: RS-422 at 230,400 baud (compatibility mode)
- Sync: 1 PPS GPS
- Telemetry: Irixon-4 compatible (KRY7X-TEL-MOD-02)

## Firmware

- **Current:** KRY7X-FW-v1.2.3 (released 08 February 2023)
- Different firmware track from [[kryon-7]] (KRY7-FW) — not interchangeable

## Calibration

- Interval: **12 months** (more frequent than Kryon-7's 18 months, due to HgCdTe detector sensitivity drift)
- Procedure: VRC-CAL-PROC-KRY7X-001
- Specialist: Kofi Twumasi-Mensah ([[team-crestfield]])
- Location: HLV-B03, [[halvern-testing-ground]]
- Calibration checksum: CRC-16 `9E3A` (Rev 2.1); mismatch requires return to [[team-crestfield]]

## Platform Integration

| Platform | Bracket | Notes |
|----------|---------|-------|
| Atlas-X | VRC-MNT-ATL-04 | Primary configuration |
| Atlas North | VRC-MNT-ATL-N-06 | Combined with [[valdyne-spectral-array]] (5.9 kg total) |
| Fixed mast | VRC-MNT-ST-04 | NEXUS ground installation |

## Fleet and Transition Status

Fleet: 7 units as of end-2023 (expanded from 3 in 2023). ^[raw/documents/document_25.md]

| Platform/Program | Transition Date | Status |
|-----------------|----------------|--------|
| Atlas North / SABLE | November 2022 | Completed |
| Atlas-X AETHER profiles | January 2023 | Completed |
| NOVA Zone C Atlas-X nodes | Q2 2024 (planned) | Pending |
| NOVA Zone A/B fixed nodes | Not planned | Remains [[kryon-7]] |

## Related

[[kryon-7]] | [[project-nova]] | [[project-sable]] | [[project-aether]] | [[project-nexus]] | [[atlas-platform-family]] | [[team-crestfield]] | [[comparisons/kryon-7-vs-kryon-7x]]
