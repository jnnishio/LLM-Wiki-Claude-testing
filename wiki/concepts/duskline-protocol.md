---
title: Duskline Protocol
created: 2026-06-10
updated: 2026-06-10
type: concept
tags: [protocol, anomaly]
sources: [raw/documents/document_20.md, raw/documents/document_01.md, raw/documents/document_22.md]
confidence: high
---

# Duskline Protocol

**Protocol Code:** PROT-DSK-003  
**Version:** 2.0 (current)  
**Author:** [[aldous-quirk]], VRC Data Quality Office  
**Issued:** 30 September 2021  
**Approved by:** [[tarquin-selvidge]]

## Overview

Standard procedure for identifying, flagging, escalating, and resolving data quality anomalies across all VRC instrument data streams. Establishes a consistent framework for distinguishing genuine geophysical events from sensor artefacts, communication errors, and platform interference.

Named after the "dusk line" phenomenon in atmospheric optics (twilight transitions introducing ambiguous signals in multi-spectral sensors). All programs using automated data collection are subject to this protocol.

**Applies to:** [[project-nova]], [[project-helios]], [[project-aether]], [[project-sable]], [[project-nexus]], and any program adopting it by reference.

## Automated Detection Criteria (VAQCS)

All data streams processed by VRC Automated Quality Control System (VAQCS) at Halvern VDPC:

| Check | Criterion |
|-------|-----------|
| Spike detection | Single samples >4σ from rolling 24-hour mean |
| Step change detection | Sustained shift >2.5σ for ≥10 consecutive samples |
| Missing data | Any gap >15 minutes in nominally continuous stream |
| Cross-instrument inconsistency | Divergence >3σ between co-located sensors expected to agree within 1σ |

Manual flagging: any VRC personnel may submit a Duskline Anomaly Report (DAR, form VRC-DAR-001).

## The 72-Hour Observation Window

Upon detection, anomaly is assigned a **Duskline flag** and enters the observation window:

1. Program data manager notified automatically (VAQCS email alert)
2. Data segment tagged `QF-DUSK-WATCH` in VBIF v2
3. Flagged data may NOT be used in published products until resolved
4. Data manager reviews incoming data; instrument health checks performed

### Outcome Codes (assigned at window end)

| Code | Meaning | Action |
|------|---------|--------|
| `QF-ARTEFACT` | Sensor/platform artefact | Data excluded from products |
| `QF-EVENT` | Genuine environmental event | Data retained; event logged |
| `QF-EXTENDED` | Inconclusive | Window extended by 72 hours (max 2 extensions = 216 h total) |

## Escalation

- Any `QF-EVENT` or second `QF-EXTENDED`: escalate to program PI and VRC Data Quality Office ([[aldous-quirk]], ext. 4-220)
- **Safety-relevant anomalies** (e.g. Clearwater Protocol facility data): Station Commander notified **immediately**, regardless of window status

## VBIF v2 Quality Flag Codes

| Flag | Meaning |
|------|---------|
| `QF-DUSK-WATCH` | Under 72-hour observation window |
| `QF-ARTEFACT` | Confirmed artefact; exclude |
| `QF-EVENT` | Confirmed genuine event; retain |
| `QF-EXTENDED` | Window extended |
| `QF-SUSPECT` | Suspect data; use with caution |
| `QF-NEXUS-DISAGREE` | Cross-sensor consistency failure ([[project-nexus]] extension, Sep 2023) |

## Compliance Officer Assignments

| Program | Compliance Officer |
|---------|------------------|
| [[project-nova]] | Dafydd Emlyn (Team Velanthor) |
| [[project-helios]] | Analyst Gwen Tiverton (Team Velanthor) |
| [[project-aether]] | Technician Brix Halvorsen |
| [[project-sable]] | [[aldous-quirk]] (handles directly as protocol author) |
| [[project-nexus]] | [[renna-holt]] |

## Program-Specific Guidance

### NOVA-Specific
Twilight transitions at Zone A (solar elevation −6° to +6°) most likely to trigger false anomalies. Pre-filter: auto-assign `QF-SUSPECT` to data within 30 min of −6° solar elevation threshold at Zone A, pending manual review. ^[raw/documents/document_20.md]

### SABLE-Specific
SABLE operates exclusively during polar night — the literal dusk line never occurs. Standard Duskline Protocol applies for all other anomaly categories. Twilight pre-filter **waived** by [[aldous-quirk]]. ^[raw/documents/document_20.md]

## Related

[[project-nova]] | [[project-helios]] | [[project-aether]] | [[project-sable]] | [[project-nexus]] | [[aldous-quirk]] | [[clearwater-protocol]] | [[halvern-testing-ground]]
