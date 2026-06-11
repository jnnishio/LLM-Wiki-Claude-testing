---
title: Halvern Testing Ground
created: 2026-06-10
updated: 2026-06-10
type: entity
tags: [facility, atmospheric, platform]
sources: [raw/documents/document_16.md, raw/documents/document_25.md]
confidence: high
---

# Halvern Testing Ground

**Facility Code:** FAC-HLV-002  
**ICAO:** XHLV  
**Location:** 68°51'42.3" N, 18°24'09.6" E (2,847 m AMSL)  
**Facility Commander:** Lt. Cmd. [[bellamy-vorsch]] (concurrent with [[oswick-station]] since March 2023)  
**Manual Version:** 3.0 (issued 10 January 2023)

## Overview

VRC's primary inland test and operations facility. Unlike [[oswick-station]] (which focuses on polar field research), Halvern is primarily an engineering and operational-support facility: platform development, sensor calibration, data processing, and VRC Data Processing Centre (VDPC). Home base of [[team-velanthor]] and sub-office for [[team-crestfield]] (calibration lab HLV-B03).

## Location and Access

- **Primary:** Paved road from Halvdalen (22 km S), year-round with snow-clearing
- **Secondary:** Fixed-wing to XHLV airstrip (2,100 m paved)
- Accessible by standard vehicle year-round (unlike Oswick's seasonal constraints)

## Infrastructure

| Structure | Type | Area (m²) | Notes |
|-----------|------|-----------|-------|
| HLV-B01 | Main office and laboratory | 1,840 | Includes VDPC server room |
| HLV-B02 | Platform hangar | 2,200 | Atlas family maintenance; 12 m internal height |
| HLV-B03 | Sensor calibration laboratory | 440 | ISO 7 clean room ([[team-crestfield]]) |
| HLV-B04 | Accommodation block | 960 | 40-bed capacity |
| HLV-B05 | Power plant | 220 | Grid-connected + backup |
| HLV-ETC | Environmental test chambers | 180 | ETC-1 and ETC-2 (to −80°C) |
| HLV-ICE | Under-ice access facility | 310 | Glacier access; Atlas-II deployment pool |
| HLV-MAST-01 | Meteorological mast | — | 44 m, continuous operation |
| HLV-MAST-02 | Research mast | — | 28 m, reconfigurable (used in EXP-441) |

### Environmental Test Chambers

| Chamber | Volume | Temperature Range | Primary Use |
|---------|--------|------------------|-------------|
| ETC-1 | 12 m³ | −40°C to +85°C | Electronics testing |
| ETC-2 | 4 m³ | −80°C to +60°C | Cold qualification (Atlas North qualification done here) |

### UAV Test Corridor

- HLV-CORRIDOR-01: 3 km × 0.8 km, oriented 045°/225°, 500 m AGL ceiling
- Extended airspace for AETHER balloon ops: up to 32,000 m (AETHER-NOTAM)
- [[exp-441]] flew 47 sorties in this corridor (March–November 2023)

## Programs Operated Here

| Program | Lead |
|---------|------|
| [[project-nova]] VDPC; Zone B nodes | [[mara-fenwick]] |
| [[project-helios]] ground station (PEL-200-0031) | Dr. Osias Prewitt |
| [[atlas-platform-family]] maintenance (all variants) | Dr. Fennis Albrecht |
| [[exp-441]] thermal boundary testing | Dr. Noel Hartbury |
| [[project-sable]] winter flight operations | [[aldous-quirk]] |
| [[team-velanthor]] primary office | [[mara-fenwick]] |
| [[team-crestfield]] calibration sub-office | [[renna-holt]] |
| [[project-triton]] Phase 2 (Halvern Sub-Ice Cavity) | [[sable-yurin]] |
| [[project-nexus]] (all sensors at Halvern) | [[tarquin-selvidge]] |

## Key Reference Measurements

- Facility elevation: **2,847 m AMSL** — used as altitude reference for all NOVA/HELIOS data from Halvern
- HLV-MAST-02 height: 28 m — reference array for [[exp-441]]
- ETC-2 minimum temperature: −80°C — cold qualification limit

## Safety

- UAV operations require pre-flight notification to HLV Airspace Control (radio ch. 7 or ext. 6-CTRL)
- Cryosphere operations comply with [[clearwater-protocol]] v2.3; sub-ice pressure threshold 1.67 bar
- Emergency: ext. 7-700

## Related

[[oswick-station]] | [[bellamy-vorsch]] | [[team-velanthor]] | [[team-crestfield]] | [[atlas-platform-family]] | [[project-nova]] | [[project-nexus]] | [[exp-441]]
