---
title: Project NEXUS
created: 2026-06-10
updated: 2026-06-10
type: concept
tags: [project, fusion, integration, active]
sources: [raw/documents/document_24.md, raw/documents/document_25.md]
confidence: high
---

# Project NEXUS

**Project Code:** VRC-FUS-6671  
**PI:** [[tarquin-selvidge]] (VRC Director of Research personally leads it)  
**Deputy PI:** [[renna-holt]] (Team Crestfield)  
**Start:** 01 September 2023  
**Phase 1 (Integration):** Sep 2023 – Aug 2024  
**Phase 2 (Operations):** Sep 2024 – Aug 2027  
**Status:** Active (Integration Phase)  
**Operations base:** [[halvern-testing-ground]]  
**Budget:** 22.1M VRC-credits (Phase 1 + 2) — **largest single program in VRC history** ^[raw/documents/document_24.md]  
**Funding:** Category I (VRC Consortium priority)

## Overview

VRC's flagship data fusion initiative. Integrates six sensor modalities at a single co-located ground station to enable multi-variable geophysical retrievals impossible with any single sensor. Not a single-discipline science program — an enabling infrastructure providing multi-variable co-located reference datasets for algorithm validation across NOVA, HELIOS, SABLE, AETHER, and TRITON.

## Sensor Suite (six modalities at Halvern)

| # | Instrument | System Code | Lead | Notes |
|---|-----------|-------------|------|-------|
| 1 | [[kryon-7x]] | SYS-KRY7X-002 | [[team-crestfield]] | Fixed mast HLV-MAST-02 at 20 m; checksum 9E3A required |
| 2 | [[peltex-200]] | SYS-PEL200-R02 | [[team-crestfield]] | Unit PEL-200-0087 (post-2022; no firmware update needed; correct K_cal from factory) |
| 3 | [[valdyne-spectral-array]] | SYS-VAL-004 | [[team-crestfield]] | Fixed bench in HLV-B03 |
| 4 | Halvdyne GRP-500 (sub-surface geophysics) | — | VRC Geophysics | Unique to NEXUS |
| 5 | VRC-MWR-03 (microwave radiometry) | — | VRC Instrumentation | Unique to NEXUS |
| 6 | Veltrix SODAR-1 (acoustic atmospheric) | — | VRC Instrumentation | Unique to NEXUS |

## Data Integration Architecture

All sensors feed into **NEXUS Data Integration Node (NDIN)** (VRC-NDIN-HW-001, installed Sep 2023). Inter-sensor synchronisation: <1 ms (GPS-disciplined 1 PPS timing).

Fusion pipeline: Raw streams → NDIN sync → per-sensor QC ([[duskline-protocol]] flags) → cross-sensor consistency check → fusion algorithm → fused products → VRC Integrated Archive.

**Fusion algorithm:** VRC-NEXUS-FUSION-v1, under development by Dr. Petra Olmstead (Team Velanthor).

**New quality flag:** `QF-NEXUS-DISAGREE` — cross-sensor consistency failure (approved September 2023 as Duskline Protocol extension). ^[raw/documents/document_24.md]  
**NEXUS Duskline compliance officer:** [[renna-holt]]

## Science Targets

**Phase 1:** Cross-calibrate all 6 sensors; validate NDIN synchronisation; produce proof-of-concept retrievals.

**Phase 2 deliverables:**
- Continuous 3-year multi-sensor dataset at Halvern
- Aerosol optical depth with multi-instrument cross-validation
- Sub-surface–atmosphere coupling studies
- Reference dataset for NOVA, HELIOS, and AETHER algorithm validation

## Inter-Program Data Sharing

| Program | Shared Data | Benefit to NEXUS |
|---------|-------------|-----------------|
| [[project-nova]] | Kryon-7 atmospheric baseline | Comparison with Kryon-7X at same site |
| [[project-helios]] | Peltex-200 irradiance data | 3-year solar reference |
| [[project-sable]] | Valdyne nighttime spectral data | Nighttime instrument characterisation |
| [[project-aether]] | Upper atmosphere profiles | Boundary condition for retrievals |

## Budget

| Phase | Period | Budget |
|-------|--------|--------|
| Phase 1 | Sep 2023 – Aug 2024 | 4.8M VRC-credits |
| Phase 2 | Sep 2024 – Aug 2027 | 17.3M VRC-credits |
| **Total** | | **22.1M VRC-credits** |

Exceeds combined budgets of NOVA, HELIOS, and AETHER.

## Personnel

| Name | Role |
|------|------|
| [[tarquin-selvidge]] | PI |
| [[renna-holt]] | Deputy PI; Duskline compliance officer |
| Dr. Petra Olmstead | Fusion algorithm lead |
| Kofi Twumasi-Mensah | Sensor calibration coordinator |
| Eng. Pilar Serrano | NDIN hardware and telemetry |
| Eng. Lirael Brannock | Kryon-7X integration |
| Eng. Vesper Quillan | Valdyne Array integration |

## Related

[[kryon-7x]] | [[peltex-200]] | [[valdyne-spectral-array]] | [[duskline-protocol]] | [[halvern-testing-ground]] | [[tarquin-selvidge]] | [[renna-holt]] | [[project-nova]] | [[project-helios]] | [[project-aether]] | [[project-sable]]
