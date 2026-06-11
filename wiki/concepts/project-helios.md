---
title: Project HELIOS
created: 2026-06-10
updated: 2026-06-10
type: concept
tags: [project, solar, irradiance, active]
sources: [raw/documents/document_04.md, raw/documents/document_14.md, raw/documents/document_25.md]
confidence: high
---

# Project HELIOS

**Project Code:** VRC-SOL-1887  
**PI:** Dr. Osias Prewitt (Team Velanthor)  
**Deputy PI:** [[mara-fenwick]]  
**Start:** 01 August 2021  
**Duration:** 10 years (2021–2031)  
**Current Phase:** Phase 3 (Ground network consolidation, Feb 2023–Jan 2025)  
**Status:** Active  
**Classification:** Open (unrestricted publication)

## Overview

Long-duration solar radiometric measurement program using [[peltex-200]] sensors at four ground stations. Establishes a 10-year solar spectral irradiance (SSI) baseline. Originated from VRC Science Committee recommendation VRC-SC-REC-2019-11.

Companion programs: [[project-nova]] (provides aerosol context) and [[project-aether]] (upper-atmosphere irradiance cross-validation).

## Science Objectives

**Primary:**
- Establish 10-year SSI baseline at 4 ground stations
- Quantify sub-daily, seasonal, inter-annual UV/VIS/NIR variability
- Detect long-period solar cycle signatures

**Secondary:**
- Cross-validate against VORCA orbital archive (V3)
- Support Peltex-200 calibration traceability
- Provide ancillary irradiance data to [[project-nova]] for AOD retrievals

## Ground Station Network

| Station | Unit ID | Firmware | Affected by Cal Error? | Status |
|---------|---------|----------|----------------------|--------|
| [[oswick-station]] (FAC-OSW-001) | PEL-200-0022 | v2.4.1 | Yes — updated 28 Jan 2022 | Correct |
| [[halvern-testing-ground]] (FAC-HLV-002) | PEL-200-0031 | v2.4.1 | Yes — updated 03 Feb 2022 | Correct |
| Crestfield Lab (FAC-CRF-003) | PEL-200-0041 | v2.4.1 | Yes — updated Feb 2022 | Correct |
| Thule Relay Outpost (FAC-TRL-007) | PEL-200-0055 | v2.4.1 | Yes — updated Feb 2022 | Correct |

## CRITICAL: Calibration Error History

The original [[peltex-200]] calibration constant (K_cal = 0.00447 in Document 13/v1.0) was found to contain a **14.3% systematic positive error** discovered December 2021. Corrected to K_cal = 0.00391 (Document 14/v2.1, January 2022).

- All affected units (PEL200-0022, -0031, -0041, -0055) updated to firmware v2.4.1 by February 2022
- All HELIOS L1a+ data reprocessed on 15 April 2022 under corrected constant
- Reprocessed data tagged: **`HELIOS-REPR-2022`**
- **Any HELIOS data lacking this tag (pre-15 April 2022) must not be used for quantitative analysis without reprocessing** ^[raw/documents/document_04.md]

## Data Products

| Level | Description |
|-------|-------------|
| L0 | Raw instrument counts (unmodified) |
| L1a | Radiometrically calibrated spectral irradiance (corrected constant) |
| L1b | Spectrally integrated broadband irradiance at 1-minute resolution |
| L2 | Daily/monthly/annual SSI composites with uncertainty bounds |
| L3 | Multi-station merged SSI anomaly maps (annual release) |

L2/L3 published to VRC Open Data Repository (VRC-ODR-HELIOS).

## Phase 3 Milestones

| Milestone | Target | Status |
|-----------|--------|--------|
| Network quality audit | Apr 2023 | Completed |
| Instrument inter-comparison | Aug 2023 | Completed |
| VORCA cross-validation report | Feb 2024 | In progress |
| Phase 3 data release | Jun 2024 | Pending |
| Phase 3 final report | Jan 2025 | Pending |

## Processing Chain Versions

| Version | Date | Key Change |
|---------|------|-----------|
| HELIOS-PROC-v1.0 | Aug 2021 | Initial; K_cal = 0.00447 (erroneous) |
| HELIOS-PROC-v1.1 | Apr 2022 | K_cal corrected to 0.00391; all L1a+ reprocessed |
| HELIOS-PROC-v1.2 | Sep 2023 | Thule station added; UTC offset corrected for PEL-200-0055 |
| HELIOS-PROC-v1.3 | Q2 2024 (pending) | EXP-441 airborne bias correction algorithm incorporated |

## Related

[[peltex-200]] | [[project-nova]] | [[project-aether]] | [[project-nexus]] | [[exp-441]] | [[team-velanthor]] | [[oswick-station]] | [[halvern-testing-ground]] | [[mara-fenwick]]
