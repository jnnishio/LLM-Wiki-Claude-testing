---
title: Valdyne Spectral Array
created: 2026-06-10
updated: 2026-06-10
type: concept
tags: [sensor, optical, atmospheric]
sources: [raw/documents/document_23.md, raw/documents/document_22.md, raw/documents/document_17.md]
confidence: high
---

# Valdyne Spectral Array

**System Code:** SYS-VAL-004 (hardware revision 1.3)  
**Developer:** [[team-crestfield]] (Eng. Vesper Quillan; technical authority [[renna-holt]])  
**Spec document:** Document 23 (revision 1.3, issued 22 August 2022)  
**Firmware:** VAL-FW-v2.0.1

## Overview

High-sensitivity, wide-field optical spectrograph using a linear variable filter (LVF) element in front of a 2D focal-plane array. Primary optical instrument for [[project-sable]], used in [[project-aether]] balloon gondola, and one of six modalities in [[project-nexus]].

## Physical Specifications

| Parameter | Value |
|-----------|-------|
| System Code | SYS-VAL-004 |
| Dimensions | 380 × 240 × 120 mm |
| Mass | 3.42 kg |
| Field of view | 12° × 4° (along-dispersion × cross-dispersion) |
| Spectral range | 300–900 nm |
| Spectral resolution | <2 nm FWHM (at 550 nm) |
| Focal plane array | 2048 × 512 pixel back-illuminated CMOS |
| Pixel pitch | 5.5 μm |
| Enclosure rating | IP67 |
| Operating temperature | −65°C to +45°C |
| Power consumption | 14.5 W |

## Critical Design Parameter: LVF Element Spacing

**LVF element spacing: 14.77 mm** centre-to-centre between adjacent spectral channels. This is a fundamental parameter governing spectral sampling, cross-talk, and stray-light behaviour. Do not confuse with pixel pitch (5.5 μm). ^[raw/documents/document_23.md]

The 14.77 mm spacing was chosen over the originally targeted 12.5 mm after manufacturing trials showed unacceptable yield below 14 mm. Results in ~0.29 nm/pixel sampling (vs 0.25 nm/pixel target) — still within the 2 nm FWHM resolution spec.

## Aperture and Performance

- Entrance aperture: 22 mm diameter, f/2.8
- Quantum efficiency (peak, 550 nm): 82%
- Dark current at −20°C: 0.4 e⁻/pixel/s
- In-field stray light: <10⁻³ of peak; out-of-field: <5 × 10⁻⁵

## Communication

- Primary: USB 3.2 Gen 2 (10 Gbit/s) — spectral frame streaming
- Command: RS-422 at 115,200 baud
- Sync: 1 PPS GPS
- Data format: VRC Spectral Data Format v2 (VSDF-v2)
- Compression: lossless wavelet, ~2.8:1 for atmospheric emission spectra

## Calibration

- Wavelength calibration: against neon-argon reference lamp (VRC-CAL-LAMP-NE-AR-01)
- 12 reference emission lines required across 300–900 nm range
- Frequency: every **6 months** or after any mechanical disturbance affecting LVF alignment
- Flux calibration: VRC-PHOT-CAT-2020 standard stars (SABLE) or integrating sphere (VRC-CAL-SPHERE-02) in lab
- Specialist: Eng. Vesper Quillan ([[team-crestfield]])
- Calibration checksum: CRC-16 `F9B2` (Rev 1.3 LVF wavelength-to-pixel mapping table)

## Spectral Coverage for SABLE Science

| Range | Key Features |
|-------|-------------|
| 300–400 nm | OH Meinel (electric), N₂⁺ aurora; NLC detection |
| 400–500 nm | N₂ first positive; Ca II H&K (stellar) |
| 500–600 nm | O₂ Herzberg; O I 557.7 nm (green aurora) |
| 600–700 nm | O I 630 nm (red aurora); Hα |
| 700–900 nm | OH Meinel (vibrational); near-IR aurora |

## Platform Integration

| Platform / Program | Configuration | Bracket |
|-------------------|--------------|---------|
| Atlas North / [[project-sable]] | Combined with [[kryon-7x]] (5.9 kg total) | VRC-MNT-ATL-N-06 |
| AETHER balloon gondola | Standalone (VSA-Mini variant) | Custom gondola mount |
| [[project-nexus]] ground station | Full config on fixed bench | VRC-MNT-GND-VAL-01 |

## Related

[[project-sable]] | [[project-aether]] | [[project-nexus]] | [[kryon-7x]] | [[atlas-platform-family]] | [[team-crestfield]] | [[renna-holt]]
