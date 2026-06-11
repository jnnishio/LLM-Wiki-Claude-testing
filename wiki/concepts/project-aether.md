---
title: Project AETHER
created: 2026-06-10
updated: 2026-06-10
type: concept
tags: [project, atmospheric, active]
sources: [raw/documents/document_17.md, raw/documents/document_07.md]
confidence: high
---

# Project AETHER

**Project Code:** VRC-ALT-4450  
**PI:** Dr. Petra Olmstead (Team Velanthor)  
**Deputy PI:** [[mara-fenwick]]  
**Start:** 01 April 2022  
**Phase 1 End (planned):** 31 March 2025  
**Status:** Active (Phase 1 — balloon platform operations)  
**Operations base:** [[halvern-testing-ground]]  
**Budget:** 8.7M VRC-credits (Category III, multi-program)

## Overview

High-altitude atmospheric sampling program targeting the stratosphere and upper troposphere (12,000–32,000 m). Uses stratospheric balloon platforms (above 8,200 m) and Atlas-X aircraft (below 8,200 m). Companion to [[project-nova]] (lower troposphere) and [[project-helios]] (surface irradiance reference) — together forming a vertically integrated observing system from ground level to the stratosphere.

## Science Objectives

1. Stratospheric aerosol inventory (18–30 km): sulfate and organic aerosol loading and particle size
2. Ozone column variability: seasonal/inter-annual mixing ratio profiles in lower stratosphere
3. Gravity wave characterisation: temperature and wind profiles at 12–30 km
4. Upper-atmosphere irradiance: solar spectral irradiance above tropospheric aerosol layer for [[project-helios]] cross-validation

## Platform Architecture

### Stratospheric Balloon (>8,200 m)

- Zero-pressure polyethylene balloons (VRC-PROC-AETHER-2021)
- Payload gondola: up to 45 kg
- Ascent rate: ~5 m/s; float typically 20,000–28,000 m; duration 4–12 h
- Horizontal drift: 50–300 km (recovered by GPS-tracked recovery teams)
- Single-use per flight; gondola parachutes down after balloon burst

**Standard gondola payload (14.3 kg total):**

| Instrument | Measurement | Mass |
|-----------|-------------|------|
| VRC-APS-04 (aerosol counter) | Particle size distribution | 4.2 kg |
| Valdyne VSA-Mini | O₃, NO₂, aerosol | 3.1 kg |
| VRC-FPH-02 (frost-point hygrometer) | Water vapour | 2.8 kg |
| Halvdyne RS-50 (radiosonde) | T, P, RH, GPS | 0.9 kg |
| [[kryon-7]] (Bands 1–3 only) | Spectral irradiance | 2.14 kg |
| VRC-DL-STRAT-01 (data logger) | — | 1.2 kg |

*Note: Kryon-7 Band 4 thermopile is NOT flown above 20 km due to thermal equilibration constraints. ^[raw/documents/document_17.md]*

### Atlas-X (lower-atmosphere profiling, <8,200 m)

- 2 Atlas-X units (SYS-ATL-X002) dedicated to AETHER, operated by [[team-velanthor]]
- AETHER payload: [[kryon-7x]], Valdyne VSA compact, Halvdyne RS-50-A radiosonde
- Profile ascent/descent patterns for troposphere-stratosphere transition characterisation

## Operations

- Launch site: HLV-LAUNCH-01 (400 m NE of HLV-B02 hangar), [[halvern-testing-ground]]
- Airspace: AETHER-NOTAM covers up to 32,000 m
- Phase 1 flight rate: 8–12 balloon flights/year + 30–50 Atlas-X profiles/year

## Flight Record (Phase 1 partial)

| Flight ID | Date | Max Altitude | Float Duration | Notes |
|-----------|------|-------------|---------------|-------|
| AETHER-B-001 | 15 May 2022 | 24,100 m | 6.2 h | First operational flight |
| AETHER-B-005 | 12 Aug 2022 | 27,800 m | 3.4 h | Program altitude record at time |
| AETHER-B-011 | 04 May 2023 | 31,650 m | 2.1 h | Closest approach to 32 km ceiling |

## Integrated Observing System

NOVA + AETHER + HELIOS form a vertically integrated dataset from ground to stratosphere, merged quarterly into VRC Integrated Atmosphere Archive (VIAA, VRC-VIAA-001) in common VBIF v2 format. ^[raw/documents/document_17.md]

## Related

[[project-nova]] | [[project-helios]] | [[kryon-7]] | [[kryon-7x]] | [[valdyne-spectral-array]] | [[atlas-platform-family]] | [[halvern-testing-ground]] | [[team-velanthor]] | [[mara-fenwick]]
