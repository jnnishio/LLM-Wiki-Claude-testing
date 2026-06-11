---
title: Clearwater Protocol
created: 2026-06-10
updated: 2026-06-10
type: concept
tags: [protocol, cryosphere, safety]
sources: [raw/documents/document_06.md, raw/documents/document_05.md, raw/documents/document_16.md]
confidence: high
contested: false
---

# Clearwater Protocol

**Protocol Code:** PROT-CLW-002 (current) | PROT-CLW-001 (superseded)  
**Author:** Dr. Tamsin Elloway  
**Current version:** v2.3 (issued 18 November 2022, minor update 14 March 2023)  
**Approved by:** Prof. [[tarquin-selvidge]]  
**Superseded version:** v1.0/v1.1 (PROT-CLW-001, Document 05) — retained for historical reference only

## Overview

Standard operating procedure for environmental sampling at or adjacent to cryospheric water bodies at VRC facilities. Governs sample collection, in-situ measurement, and chain-of-custody for water chemistry, suspended particulate, and dissolved gas analyses.

**Applies to:** [[oswick-station]] (northern polar lake sampling) and [[halvern-testing-ground]] (glacial meltwater monitoring). Also any temporary field camp within 500 m of a designated cryospheric water body.

**Interface with [[duskline-protocol]]:** When a sampling event results in anomalous readings, the Duskline Protocol governs the subsequent 72-hour observation window. ^[raw/documents/document_06.md]

## CRITICAL: Pressure Threshold (v1.0 vs v2.3)

> ⚠️ **The v1.0 pressure threshold of 1.43 bar is NO LONGER OPERATIVE.** Use 1.67 bar only.

| Version | Pressure Threshold | Source |
|---------|--------------------|--------|
| v1.0 (PROT-CLW-001) | **1.43 bar** — SUPERSEDED | Document 05 |
| v2.3 (PROT-CLW-002) | **1.67 bar** — CURRENT | Document 06 |

The 1.43 bar threshold was raised following investigation of the **Halvern Incident** (VRC-INC-2022-HLV-08, August 2022): the original threshold proved over-conservative and caused unnecessary sampling suspensions without actual hazard. Analysis of 30 years of sub-ice pressure data from [[oswick-station]] supported raising it to 1.67 bar. ^[raw/documents/document_06.md]

## Summary of Changes: v1.0 → v2.3

| Section | Change | Reason |
|---------|--------|--------|
| Sec 5.2 | Pressure threshold: 1.43 → **1.67 bar** | Halvern Incident investigation |
| Sec 5.3 | Wind speed threshold: 12 → **15 m/s** | Operational review (3-year incident data) |
| Sec 6.1 | Reporting deadline: 24 h → **48 h** | Field team constraints at Oswick |
| New Sec 7 | Pressure sensor calibration requirement added | Root cause of Halvern Incident |
| App. C | Emergency contacts updated | Personnel changes |

## Current Thresholds (v2.3)

- **Sub-ice pressure suspension trigger:** >1.67 bar (immediate suspension + notify Station Commander within 30 min)
- **Resume sampling after pressure event:** pressure <1.67 bar for ≥6 hours AND written clearance from station commander
- **Wind speed:** Suspend if >15 m/s; resume after ≥30 min below threshold
- **Visibility:** Suspend if <500 m

## Ice Thickness Requirements (unchanged from v1.0)

| Activity | Minimum Ice Thickness |
|----------|----------------------|
| Walking access (≤75 kg person) | 15 cm |
| Light equipment (≤200 kg) | 30 cm |
| Tracked vehicle (≤2,000 kg) | 70 cm |

## Key Procedures

- **Sampling node establishment** (Section 3.1): GPS record to ±3 m, water depth profile at 0.5 m intervals, VRC-WINCH-CRYO-02 winch installed
- **Sample collection** (CRYO-COLLECT): ≤0.5 m/s descent, ≤0.3 m/s ascent, transfer within 5 min of retrieval
- **Chain-of-custody:** Form VRC-COC-WTR-01 (unchanged from v1.0)
- **Pressure sensor calibration** (new in v2.3, Section 7): Required at start of each field season AND after any pressure-event suspension. Procedure VRC-CAL-PROC-PRES-01. Records retained ≥5 years.
- **Field log submission:** Within 48 h (was 24 h in v1.0). Form VRC-FIELD-CLW.
- **Pressure event reporting:** Form VRC-PRES-EVENT-01, submitted to VRC EMG within 5 days.

## Emergency Contacts (v2.3, Appendix C)

| Role | Name | Contact |
|------|------|---------|
| Oswick Station Commander | [[bellamy-vorsch]] | ext. 5-210 |
| Halvern Station Commander | [[bellamy-vorsch]] | ext. 5-300 |
| VRC Environmental Monitoring Group | Dr. Tamsin Elloway | ext. 4-112 |
| VRC Emergency Operations Centre | — | ext. 7-700 |

## Related

[[oswick-station]] | [[halvern-testing-ground]] | [[duskline-protocol]] | [[project-triton]] | [[bellamy-vorsch]] | [[exp-119]]
