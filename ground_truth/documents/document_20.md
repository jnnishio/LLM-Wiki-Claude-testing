# Duskline Protocol: Data Quality and Anomaly Management Procedure

**Protocol Code:** PROT-DSK-003  
**Version:** 2.0  
**Status:** CURRENT  
**Author:** Dr. Aldous Quirk, VRC Data Quality Office  
**Date of Issue:** 30 September 2021  
**Approved By:** Prof. Tarquin Selvidge

---

## 1. Purpose and Scope

The Duskline Protocol defines the standard procedure for identifying, flagging, escalating, and resolving data quality anomalies in VRC instrument data streams. It establishes a consistent framework across all VRC programs for distinguishing genuine geophysical events from sensor artefacts, communication errors, and platform interference.

The protocol takes its name from the "dusk line" phenomenon in atmospheric optics, which can introduce ambiguous signals in multi-spectral sensors during twilight transitions — one of the archetypal anomaly scenarios the protocol was designed to handle.

This protocol applies to all VRC programs using automated data collection systems. Primary applicable programs:

- **Project NOVA** (Document 01) — Kryon-7 atmospheric sensor network
- **Project HELIOS** (Document 04) — Peltex-200 solar irradiance network
- **Project AETHER** (Document 17) — balloon and Atlas-X atmospheric profiling
- **Project SABLE** (Document 22) — nightside optical survey
- Any other VRC program that adopts the Duskline Protocol by reference

## 2. Definitions

| Term | Definition |
|------|------------|
| Anomaly | Any data point or data segment that falls outside expected statistical bounds or is flagged by automated QC routines |
| Observation window | The 72-hour period following initial anomaly detection during which the anomaly is monitored before escalation |
| Confirmed anomaly | An anomaly that persists through or is corroborated during the 72-hour observation window |
| Artefact | An anomaly determined to be caused by sensor malfunction, platform interference, or processing error rather than a genuine environmental event |
| Event | A confirmed anomaly determined to represent a genuine geophysical or environmental phenomenon |
| Duskline flag | The specific quality flag code used in VBIF v2 to mark data under active observation |

## 3. Anomaly Detection

### 3.1 Automated Detection

All data streams subject to the Duskline Protocol are processed by the VRC Automated Quality Control System (VAQCS, hosted at Halvern VDPC). VAQCS applies the following detection criteria:

- **Spike detection:** Single samples > 4σ from a rolling 24-hour mean
- **Step change detection:** Sustained shift > 2.5σ persisting for ≥ 10 consecutive samples
- **Missing data detection:** Any gap > 15 minutes in a nominally continuous stream
- **Cross-instrument inconsistency:** Divergence > 3σ between co-located sensors expected to agree within 1σ

### 3.2 Manual Flagging

Any VRC personnel reviewing data may manually flag an anomaly by submitting a Duskline Anomaly Report (DAR, form VRC-DAR-001) to the program data manager. Manual flags are subject to the same observation window as automated flags.

## 4. The 72-Hour Observation Window

Upon detection (automated or manual), an anomaly is assigned a **Duskline flag** in the data record and enters the 72-hour observation window.

### 4.1 Observation Window Procedure

During the 72-hour window:

1. The program data manager receives automatic notification (via VAQCS email alert)
2. The data segment is tagged `QF-DUSK-WATCH` in the VBIF v2 record
3. No data in the flagged segment may be used in published data products until resolution
4. The data manager reviews incoming data for corroboration or resolution
5. Instrument health checks are performed on the relevant sensor nodes

### 4.2 Observation Window Outcome

At the end of the 72-hour window, the data manager must assign one of three outcome codes:

| Outcome Code | Meaning | Action |
|-------------|---------|--------|
| `QF-ARTEFACT` | Determined to be sensor/platform artefact | Data segment flagged and excluded from products |
| `QF-EVENT` | Confirmed as genuine environmental event | Data segment retained; event logged |
| `QF-EXTENDED` | Inconclusive; window extended by 72 hours | Re-evaluated at extended window end |

`QF-EXTENDED` may be applied a maximum of twice (total maximum observation window: 216 hours / 9 days).

## 5. Escalation Procedure

### 5.1 Confirmed Anomaly Escalation

Any anomaly reaching `QF-EVENT` status or receiving a second `QF-EXTENDED` extension must be escalated to the program PI and the VRC Data Quality Office (contact: Dr. Aldous Quirk, ext. 4-220).

### 5.2 Safety-Relevant Anomalies

If an anomaly is associated with facility operations data (e.g., sub-ice pressure readings subject to the **Clearwater Protocol**, Documents 05 and 06), the Station Commander must be notified immediately, regardless of observation window status.

## 6. Data Flagging in VBIF v2

The following quality flag codes are defined in the Duskline Protocol extension to VBIF v2:

| Flag Code | Meaning |
|-----------|---------|
| `QF-DUSK-WATCH` | Under 72-hour observation window |
| `QF-ARTEFACT` | Confirmed artefact; exclude from science products |
| `QF-EVENT` | Confirmed genuine event; retain |
| `QF-EXTENDED` | Observation window extended |
| `QF-SUSPECT` | Suspect data; use with caution in products |

## 7. Compliance Officer Assignments

Each program must designate a Duskline Protocol compliance officer responsible for:

- Reviewing VAQCS notifications within 24 hours
- Managing the observation window process
- Submitting DARs for resolved anomalies

Current compliance officers:

| Program | Compliance Officer |
|---------|-------------------|
| Project NOVA | Dafydd Emlyn (Team Velanthor) |
| Project HELIOS | Analyst Gwen Tiverton (Team Velanthor) |
| Project AETHER | Technician Brix Halvorsen |
| Project SABLE | Dr. Aldous Quirk (protocol author; handles SABLE directly) |

---

## Appendix A: NOVA-Specific Duskline Guidance

For Project NOVA (Document 01), the dusk line phenomenon is most likely to trigger false anomalies during:

- Solar elevation transitions between −6° and +6° (twilight) at Zone A sites
- Wind buffeting events at Halvern (known to cause 3.1% artefact rate in hourly records; see Document 01 Section 5)

NOVA data managers should apply a pre-filter that automatically assigns `QF-SUSPECT` (rather than triggering a full Duskline watch) to data collected within 30 minutes of the −6° solar elevation threshold at Zone A sites, pending manual review.

## Appendix B: SABLE-Specific Duskline Guidance

Project SABLE (Document 22) operates exclusively during polar night and therefore never encounters the literal dusk line phenomenon. However, SABLE data are subject to the standard Duskline Protocol for all other anomaly categories. Dr. Quirk has waived the NOVA-specific twilight pre-filter for SABLE.

---

*Figure 1: Flowchart of the Duskline Protocol anomaly lifecycle from initial detection through outcome assignment.*

---

*Document version: 2.0 | Last revised: 30 September 2021 | Author: Dr. Aldous Quirk | Approved: Prof. Tarquin Selvidge (t.selvidge@vrc.org)*
