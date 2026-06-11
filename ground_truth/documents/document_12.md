# Project TRITON: Subsurface Mapping and Under-Ice Bathymetric Survey

**Project Code:** VRC-SUB-3304  
**Principal Investigator:** Dr. Sable Yurin  
**Program Start:** 01 November 2021  
**Status:** Active (Phase 2)

---

## 1. Program Overview

Project TRITON (code: VRC-SUB-3304) is the Veltrix Research Consortium's under-ice and subsurface mapping initiative, aimed at producing high-resolution bathymetric charts of sub-glacial and under-ice lake systems in VRC northern operational areas. The project uses the **Atlas-II** autonomous subsurface vehicle (Document 10) as its primary survey platform.

TRITON is led by Dr. Sable Yurin, whose name coincidentally matches the project **SABLE** (Document 22) — they are entirely separate initiatives. Dr. Yurin's background is in marine geophysics and sub-bottom sediment analysis; she is not affiliated with Project SABLE (which is led by Dr. Aldous Quirk).

## 2. Project Details

| Field | Value |
|-------|-------|
| Project Code | VRC-SUB-3304 |
| Principal Investigator | Dr. Sable Yurin |
| Program Start | 01 November 2021 |
| Phase 1 End | 31 October 2022 |
| Phase 2 Start | 01 November 2022 |
| Phase 2 Planned End | 31 October 2024 |
| Platform | Atlas-II (SYS-ATL-II003) |
| Primary Facility | Oswick Station (FAC-OSW-001) with operations at Halvern |

## 3. Scientific Objectives

### 3.1 Primary Goals

- Produce 1 m resolution bathymetric charts of the Oswick Under-Ice Lake system (area designation: VRC-UIL-OSW-01)
- Map sub-bottom sediment stratigraphy to a penetration depth of approximately 25 m
- Characterise water column turbidity, temperature, and salinity profiles
- Collect sediment core samples at selected locations for geochronological analysis

### 3.2 Phase 2 Goals (Additional)

- Extend surveys to the Halvern Sub-Ice Cavity system (VRC-UIL-HLV-02)
- Conduct time-lapse monitoring of selected seafloor features to detect sediment transport events
- Integrate CTD data with **EXP-119** corrosion study samples (Document 21) — water chemistry from TRITON dives informs the EXP-119 dissolved ion dataset

## 4. Survey Platform: Atlas-II

Full technical specifications for the Atlas-II are given in Document 10. The relevant operational parameters for TRITON are:

| Parameter | Value | Source |
|-----------|-------|--------|
| Maximum operating depth | 340 m | Doc 10, Sec 2 |
| TRITON Phase 2 target depth (primary site) | 280 m | This document |
| TRITON Phase 2 target depth (secondary site) | 340 m | This document |
| Positioning system | USBL acoustic, ±1.5 m | Doc 10, Sec 4 |
| Tether length (standard) | 400 m | Doc 10, Sec 2 |

The 340 m depth rating of the Atlas-II was established specifically to meet TRITON's secondary-site requirements, as documented in Appendix B of Document 10.

## 5. Survey Areas

### 5.1 Oswick Under-Ice Lake (VRC-UIL-OSW-01)

- **Location:** Beneath the OSW ice sheet, accessed via Oswick Station ice shaft OSW-IS-03
- **Estimated surface area:** 4.7 km²
- **Estimated maximum depth:** 290–310 m (pending Phase 2 survey completion)
- **Access hole dimensions:** 800 mm × 800 mm (OSW-IS-03 standard)

### 5.2 Halvern Sub-Ice Cavity (VRC-UIL-HLV-02)

- **Location:** Beneath the Halvern Glacier, accessed via Halvern ice facility FAC-HLV-002-ICE
- **Estimated surface area:** Unknown — primary motivation for Phase 2 surveys
- **Estimated maximum depth:** Unknown
- **Access hole dimensions:** 500 mm × 500 mm (Phase 2 engineering work required for expansion)

## 6. Survey Operations

### 6.1 Typical Dive Sequence

A standard TRITON survey dive follows this sequence:

1. **Pre-dive preparation** (3–4 hours): Atlas-II system checkout per Document 10 Section 7.2; tether deployment; USBL transducer array deployment
2. **Descent phase** (30–90 min depending on target depth): Atlas-II descends at 0.5 m/s to survey altitude (10 m above bottom)
3. **Survey phase** (3–6 hours): Lawnmower-pattern coverage at 1.0 m/s horizontal speed
4. **Ascent and recovery** (30–90 min)
5. **Data download and QC** (2–3 hours)

### 6.2 Data Products

| Product | Description | Resolution | Format |
|---------|-------------|-----------|--------|
| DTM | Digital terrain model (bathymetry) | 1 m | GeoTIFF |
| SSS mosaic | Side-scan sonar image | 0.25 m | GeoTIFF |
| SBP profile | Sub-bottom stratigraphy transects | 0.5 m vertical | SEG-Y |
| CTD cast | Water column profiles | 0.5 m vertical | NetCDF |

## 7. Personnel

| Name | Role |
|------|------|
| Dr. Sable Yurin | Principal Investigator |
| Dr. Fennis Albrecht | Atlas-II technical authority (VRC Autonomous Systems Group) |
| Technician Ove Sandvik | Oswick Station dive operations |
| Engineer Pilar Serrano | Telemetry and data systems (Team Velanthor liaison) |
| Technician Brix Halvorsen | Halvern operations (Phase 2) |

---

## Appendix A: Phase 1 Survey Summary

Phase 1 (November 2021 – October 2022) completed 16 successful dives at VRC-UIL-OSW-01, achieving maximum depth of 312 m (Dive 8, 04 October 2022 — the first occasion any VRC platform reached this depth in the study area). Total survey area covered: 2.1 km² of the estimated 4.7 km² lake extent.

Key Phase 1 findings:
- Confirmed existence of a deep basin in the southern portion of VRC-UIL-OSW-01, maximum depth measured at 294 m
- Identified three sediment mound features suggestive of hydrothermal activity
- Collected 7 sediment push-core samples

## Appendix B: Interface with EXP-119

CTD water chemistry data collected during TRITON dives, particularly dissolved sulphate and chloride concentrations, are shared with Dr. Sable Yurin's secondary research activity under **EXP-119** (Document 21). The TRITON-EXP-119 data sharing agreement (VRC-DSA-2022-TRITON-119) was executed on 15 January 2022.

*Note: Dr. Yurin is the PI of both TRITON and EXP-119. The two programs share a PI but have separate funding, reporting, and scientific scopes.*

---

*Document version: 2.1 | Last revised: 05 November 2022 | Maintained by: Dr. Sable Yurin (s.yurin@vrc.org)*
