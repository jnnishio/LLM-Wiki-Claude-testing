---
title: Kryon-7 vs Kryon-7X — Sensor Comparison
created: 2026-06-10
updated: 2026-06-10
type: comparison
tags: [sensor, atmospheric, comparison, calibration]
sources: [raw/documents/document_02.md, raw/documents/document_18.md, raw/documents/document_19.md]
confidence: high
---

# Kryon-7 vs Kryon-7X

Side-by-side comparison of VRC's two primary multi-spectral atmospheric sensors. Both developed by [[team-crestfield]] under [[renna-holt]]. The Kryon-7X is the advanced successor, not a drop-in replacement.

## Physical

| Parameter | [[kryon-7]] (SYS-KRY7-001) | [[kryon-7x]] (SYS-KRY7X-002) |
|-----------|--------------------------|---------------------------|
| Hardware revision | 3.2 (current) | 2.1 (current) |
| Dimensions | 310 × 195 × 88 mm | 340 × 210 × 94 mm |
| Mass (without bracket) | 2.14 kg | 2.48 kg |
| Enclosure | IP67 | IP68 |
| Operating temperature | −55°C to +50°C | −65°C to +55°C |
| Power (active) | 8.4 W | 11.2 W |
| Connector | Veltrix-12P | **Veltrix-16P** (NOT compatible) |

## Optical Performance

| Parameter | Kryon-7 | Kryon-7X |
|-----------|---------|---------|
| Spectral bands | 4 (0.4–5.0 μm) | 6 (0.3–8.0 μm) |
| Dynamic range | 86 dB | **102 dB** |
| Linearity error | <0.08% | <0.04% |
| Cross-channel isolation | >52 dB | **>62 dB** |
| Warm-up time | 8 min | 6 min |
| **Aggregate noise floor** | **4.72 × 10⁻⁸ V/√Hz** | **3.11 × 10⁻⁹ V/√Hz** |
| Noise improvement | baseline | **~15× better** |

## Communication

| Parameter | Kryon-7 | Kryon-7X |
|-----------|---------|---------|
| Primary interface | RS-422 at 115,200 baud | **GigE (1000BASE-T)** |
| Secondary interface | CAN 2.0B | RS-422 at 230,400 baud |
| Data protocol | VRC ICD-2019-07 | Higher bandwidth (all 6 bands at 20 Hz) |

## Calibration

| Parameter | Kryon-7 | Kryon-7X |
|-----------|---------|---------|
| Interval | Every 18 months | Every **12 months** (HgCdTe drift) |
| Procedure | VRC-CAL-PROC-KRY7-001 | VRC-CAL-PROC-KRY7X-001 |
| Calibration specialist | Kofi Twumasi-Mensah | Kofi Twumasi-Mensah |
| Calibration checksum | — | CRC-16 `9E3A` (Rev 2.1) |
| Firmware track | KRY7-FW (v4.3.1) | KRY7X-FW (v1.2.3) |

## Platform Integration

| Platform | Kryon-7 | Kryon-7X |
|----------|---------|---------|
| Atlas (baseline) | ✓ (VRC-MNT-ATL-03) | With adapter only |
| Atlas-X | ✓ legacy | ✓ **Primary** (VRC-MNT-ATL-04) |
| Atlas North | Not used | ✓ **Primary** (VRC-MNT-ATL-N-06) |
| Atlas-II | N/A | N/A |
| Fixed mast | ✓ OSW-T01 | ✓ VRC-MNT-ST-04 (NEXUS) |

## Program Deployment

| Program | Kryon-7 | Kryon-7X |
|---------|---------|---------|
| [[project-nova]] Zone A/B | ✓ 11 fixed nodes | — |
| [[project-nova]] Zone C | ✓ (transitioning → KRY7X Q2 2024) | Pending |
| [[project-helios]] | ✓ 4 ancillary units | — |
| [[project-aether]] balloon | ✓ Bands 1–3 only | — |
| [[project-aether]] Atlas-X | (legacy) | ✓ (since Jan 2023) |
| [[project-sable]] | — | ✓ Atlas North primary |
| [[project-nexus]] | — | ✓ Ground station |

## Verdict

Use **Kryon-7** for: fixed-mast deployments where the 18-month calibration interval and simpler RS-422 interface are adequate; legacy NOVA Zone A/B nodes; balloon gondola at high altitude (Bands 1–3 only).

Use **Kryon-7X** when: low-light or nightside photometry (SABLE); high-altitude GPS-degraded flight (Atlas-X/North); 6-band coverage required; superior noise floor needed. Note the more frequent 12-month calibration requirement and incompatible connector.

## Related

[[kryon-7]] | [[kryon-7x]] | [[atlas-platform-family]] | [[team-crestfield]] | [[project-nova]] | [[project-sable]]
