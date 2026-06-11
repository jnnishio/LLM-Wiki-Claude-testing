---
title: Project NOVA
created: 2026-06-10
updated: 2026-06-10
type: concept
tags: [project, atmospheric, active]
sources: [raw/documents/document_01.md, raw/documents/document_07.md, raw/documents/document_25.md]
confidence: high
---

# Project NOVA

**Project Code:** VRC-ATM-2201  
**PI:** [[mara-fenwick]]  
**Start:** 14 March 2022  
**Scheduled End:** 8 June 2024 (847 days — extended from original 720-day plan on 30 Sep 2022)  
**Status:** Active (as of 2024 Annual Review)  
**Funding:** Category II (Consortium-funded) | **Budget:** 12.4M VRC-credits

## Overview

Flagship atmospheric monitoring program of the [[veltrix-research-consortium]], led by [[team-velanthor]]. Deploys a distributed [[kryon-7]] sensor network across three high-altitude zones to collect continuous data on aerosol density, trace gas concentrations, and stratospheric wind profiles.

Companion programs: [[project-aether]] (extends to stratosphere) and [[project-helios]] (surface irradiance reference).

## Scientific Objectives

1. Quantification of aerosol optical depth (AOD) over polar/sub-polar regions during boreal summer
2. Characterisation of methane flux variability at 12–28 km altitude
3. Detection of anomalous temperature gradients associated with polar vortex disruptions
4. Validation of radiative transfer models using multi-spectral in-situ measurements

## Sensor Deployment (14 active nodes)

| Zone | Nodes | Base | Notes |
|------|-------|------|-------|
| Zone A (Polar Fringe) | 6 | [[oswick-station]] (OSW-T01) | 1.2 dB signal attenuation during polar night |
| Zone B (Mid-Latitude) | 5 | [[halvern-testing-ground]] | Wind buffering causes 3.1% artefact rate in hourly records |
| Zone C (Transition Band) | 3 | Mobile (Atlas-X platforms) | Subject to [[duskline-protocol]] operational window constraints |

Node naming: `NV-[ZONE]-[SEQ]` (e.g. NV-A-004). All registered under batch NOVA-NODE-BATCH-003.

## Data Management

- Telemetry backbone: Irixon-4 → VRC Data Processing Centre (VDPC) at Halvern
- Data format: VBIF v2 with checksums against VBIF-HASH-2022-0314
- Anomaly management: [[duskline-protocol]] (72-hour observation window)
- Duskline compliance officer: Dafydd Emlyn (Team Velanthor)
- Atmospheric retrieval algorithm: NOVA-RETR-v3 (noise floor spec: 4.72 × 10⁻⁸ V/√Hz from Kryon-7 Rev 3.2)

## Personnel

| Name | Role |
|------|------|
| [[mara-fenwick]] | Principal Investigator |
| Dr. Petra Olmstead | Atmospheric Modelling Lead |
| Technician Ove Sandvik | Field Operations (Oswick) |
| Technician Yisel Caban | Data Processing (VDPC, Halvern) |

## Known Limitations and Issues

- Zone A Kryon-7 polar night attenuation — correction factors applied by band (see Document 01 Appendix A) ^[raw/documents/document_01.md]
- Zone B wind buffering artefacts (3.1% of hourly records)
- Zone C mobile nodes subject to [[duskline-protocol]] operational window constraints

## Milestones

- 847-day duration established to capture 2 full polar night cycles for Zone A statistical characterisation
- First full polar night observation cycle completed February 2023 — first validated application of Band 1–4 attenuation correction factors ^[raw/documents/document_25.md]
- Kryon-7X transition for Zone C planned Q2 2024

## Zone C Integration

Zone C uses [[atlas-platform-family]] Atlas-X (2 units, SYS-ATL-X002) operated by [[team-velanthor]]. Transitioning to [[kryon-7x]] sensor in Q2 2024 (Zone A/B fixed nodes remain on [[kryon-7]]).

## Related

[[project-aether]] | [[project-helios]] | [[kryon-7]] | [[kryon-7x]] | [[atlas-platform-family]] | [[oswick-station]] | [[halvern-testing-ground]] | [[team-velanthor]] | [[duskline-protocol]] | [[mara-fenwick]]
