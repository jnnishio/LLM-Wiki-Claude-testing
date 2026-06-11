---
title: Project SABLE
created: 2026-06-10
updated: 2026-06-10
type: concept
tags: [project, optical, active]
sources: [raw/documents/document_22.md, raw/documents/document_25.md]
confidence: high
---

# Project SABLE

**Project Code:** VRC-OPT-5512  
**PI:** [[aldous-quirk]]  
**Start:** 01 November 2022  
**Phase 1:** November 2022 – October 2025  
**Operational season:** November–February (polar night only)  
**Status:** Active (Phase 1)  
**Operations base:** [[halvern-testing-ground]]; secondary: Thule Relay Outpost  
**Budget:** 6.2M VRC-credits

> **Disambiguation:** SABLE refers to this project (led by [[aldous-quirk]]). It is NOT related to [[sable-yurin]], who leads [[project-triton]]. ^[raw/documents/document_22.md]

## Overview

Nightside optical survey program dedicated to high-precision astronomical and atmospheric optical measurements **during polar night only**. Uses Atlas North (for airborne) and fixed optical benches at Halvern and Thule. First VRC program achieving 0.003 arcsecond astrometric precision.

## Science Objectives

1. **Airglow and auroral emission mapping:** OH airglow (1.5–1.7 μm Meinel bands), O I green line (0.558 μm), O I red line (0.630 μm), auroral emissions in Kryon-7X Bands 1–2
2. **Stellar photometry:** Calibration of VRC photometric standard catalogue (VRC-PHOT-CAT-2020); target <2 mmag repeatability
3. **Noctilucent cloud (NLC) survey:** 75–85 km altitude; using Valdyne near-UV sensitivity; requires sun >6° below horizon at observation altitude

## Platform Configuration

### Atlas North (airborne)

- [[atlas-platform-family]] Atlas North (SYS-ATL-N004) — sole designated airborne platform
- Payload: [[kryon-7x]] + [[valdyne-spectral-array]] combined (5.9 kg total, within 6.7 kg limit)
- Field operator: Vex Horodynski (v.horodynski@vrc.org)
- Minimum operating temp covered: −65°C (lowest recorded during ops: −61°C, 12 Jan 2023)

### Ground Installations (Halvern + Thule)

- [[valdyne-spectral-array]] (full configuration)
- All-sky imager: VRC-ASI-02 (custom fisheye)
- Absolute photometer: Halvdyne AP-200

## Phase 1 Results (Nov 2022 – Mar 2023)

| Metric | Target | Achieved |
|--------|--------|---------|
| Astrometric precision | 0.003 arcsec | **0.003 arcsec (met)** |
| Photometric repeatability | <2 mmag | **1.4 mmag (exceeded)** |
| Atlas North mission availability | >80% scheduled | **89%** |
| Kryon-7X noise floor | <5 × 10⁻⁹ V/√Hz | **3.11 × 10⁻⁹ (spec confirmed)** |
| Atlas North flights | — | 47 |
| Hours of airborne science data | — | 118 h |
| Confirmed auroral events | — | 9 |

The 0.003 arcsecond precision (~14 μrad) corresponds to ~1.1 m spatial resolution at NLC altitude (~80 km range). ^[raw/documents/document_22.md]

## Data Quality

All SABLE data governed by [[duskline-protocol]]. [[aldous-quirk]] serves as both SABLE PI and Duskline compliance officer. Twilight pre-filter is **waived** (SABLE observes only in full polar night — the literal dusk line never occurs). ^[raw/documents/document_20.md]

## Related

[[atlas-platform-family]] | [[kryon-7x]] | [[valdyne-spectral-array]] | [[duskline-protocol]] | [[aldous-quirk]] | [[halvern-testing-ground]] | [[project-nova]] | [[sable-yurin]]
