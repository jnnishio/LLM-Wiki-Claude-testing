---
title: Project TRITON
created: 2026-06-10
updated: 2026-06-10
type: concept
tags: [project, subsurface, cryosphere, active]
sources: [raw/documents/document_12.md, raw/documents/document_10.md, raw/documents/document_25.md]
confidence: high
---

# Project TRITON

**Project Code:** VRC-SUB-3304  
**PI:** [[sable-yurin]]  
**Start:** 01 November 2021  
**Phase 1:** Nov 2021 – Oct 2022 (16 dives, 2.1 km² surveyed)  
**Phase 2:** Nov 2022 – Oct 2024 (planned)  
**Status:** Active (Phase 2)  
**Primary facility:** [[oswick-station]]; Phase 2 also [[halvern-testing-ground]] (ice facility)  
**Platform:** Atlas-II (SYS-ATL-II003)

## Overview

VRC's under-ice and subsurface mapping initiative. Produces high-resolution bathymetric charts of sub-glacial and under-ice lake systems using the Atlas-II autonomous subsurface vehicle. First operational deployment of the Atlas-II.

## Science Objectives

**Phase 1 & 2:**
- 1 m resolution bathymetric charts of Oswick Under-Ice Lake (VRC-UIL-OSW-01)
- Sub-bottom sediment stratigraphy to ~25 m penetration
- Water column turbidity, temperature, salinity profiles

**Phase 2 additions:**
- Extend surveys to Halvern Sub-Ice Cavity (VRC-UIL-HLV-02) — area/depth unknown
- Time-lapse monitoring of seafloor sediment transport features
- Integration with [[exp-119]] (water chemistry from TRITON CTD dives)

## Survey Areas

### Oswick Under-Ice Lake (VRC-UIL-OSW-01)
- Location: beneath OSW ice sheet; access via ice shaft OSW-IS-03 (800×800 mm)
- Estimated area: 4.7 km²
- Estimated max depth: 290–310 m (Phase 2 survey ongoing)
- Phase 1 covered: 2.1 km² (confirmed deep basin at 294 m in southern portion)
- 3 sediment mound features suggestive of hydrothermal activity identified

### Halvern Sub-Ice Cavity (VRC-UIL-HLV-02)
- Access: via HLV-ICE facility (500×500 mm; Phase 2 engineering work needed for expansion)
- Area and depth: unknown — primary motivation for Phase 2

## Atlas-II Key Parameters for TRITON

| Parameter | Value |
|-----------|-------|
| Max operating depth | 340 m |
| Phase 2 target depth (primary site) | 280 m |
| Phase 2 target depth (secondary site) | 340 m |
| USBL positioning accuracy | ±1.5 m |
| Standard tether length | 400 m |

The 340 m Atlas-II depth rating was set specifically to meet TRITON's secondary-site requirements. ^[raw/documents/document_10.md]

## Data Products

| Product | Format | Resolution |
|---------|--------|-----------|
| Digital terrain model (bathymetry) | GeoTIFF | 1 m |
| Side-scan sonar mosaic | GeoTIFF | 0.25 m |
| Sub-bottom stratigraphy transects | SEG-Y | 0.5 m vertical |
| Water column CTD profiles | NetCDF | 0.5 m vertical |

## Dive History (Phase 1 highlights)

| Dive | Date | Location | Depth | Notes |
|------|------|----------|-------|-------|
| TRITON Dive 1 | 12 Mar 2022 | Oswick Under-Ice | 187 m | First operational |
| TRITON Dive 8 | 04 Oct 2022 | Oswick Under-Ice | **312 m** | Deepest VRC AV deployment to date |
| TRITON Dive 14 | 22 Feb 2023 | Halvern Ice Facility | 194 m | Instrument calibration dive |

## EXP-119 Data Sharing

TRITON CTD water chemistry (sulphate, chloride concentrations) shared with [[exp-119]] under VRC-DSA-2022-TRITON-119 (executed 15 Jan 2022). Both programs led by [[sable-yurin]].

## Personnel

| Name | Role |
|------|------|
| [[sable-yurin]] | Principal Investigator |
| Dr. Fennis Albrecht | Atlas-II technical authority |
| Ove Sandvik | Oswick Station dive operations |
| Engineer Pilar Serrano | Telemetry, data systems |
| Technician Brix Halvorsen | Halvern operations (Phase 2) |

## Related

[[atlas-platform-family]] | [[sable-yurin]] | [[exp-119]] | [[oswick-station]] | [[halvern-testing-ground]] | [[clearwater-protocol]] | [[veltrix-research-consortium]]
