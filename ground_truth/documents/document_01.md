# Project NOVA: Atmospheric Monitoring Initiative

## Overview

Project NOVA (code: VRC-ATM-2201) is the flagship atmospheric monitoring program of the Veltrix Research Consortium (VRC), initiated on 14 March 2022. Under the leadership of Dr. Mara Fenwick, NOVA deploys a distributed sensor network across three high-altitude observation sites to collect continuous data on aerosol density, trace gas concentrations, and stratospheric wind profiles.

The project operates in close coordination with **Team Velanthor** (see Document 07) and relies on the **Kryon-7 sensor system** (see Document 02) as its primary data-collection instrument. Field operations are conducted primarily from **Oswick Station** (see Document 03) and **Halvern Testing Ground** (see Document 16).

## Project Details

| Field | Value |
|-------|-------|
| Project Code | VRC-ATM-2201 |
| Principal Investigator | Dr. Mara Fenwick |
| Start Date | 14 March 2022 |
| Scheduled End Date | 8 June 2024 |
| Total Duration | 847 days |
| Status | Active |
| Funding Level | Category II (Consortium-funded) |
| Budget Allocation | 12.4M VRC-credits |

## Scientific Objectives

NOVA targets four primary research questions:

1. Quantification of aerosol optical depth (AOD) over polar and sub-polar regions during the boreal summer
2. Characterization of methane flux variability at altitudes between 12 and 28 km
3. Detection of anomalous temperature gradients associated with projected polar vortex disruptions
4. Validation of radiative transfer models using in-situ multi-spectral measurements

## Sensor Deployment

The Kryon-7 sensor system (system code SYS-KRY7-001) is the core instrument for NOVA's atmospheric measurements. Each deployment node consists of a Kryon-7 primary unit paired with an onboard data logger running firmware version 4.3.1. Full sensor specifications are documented in the Kryon-7 System Specification Sheet (Document 02).

NOVA currently operates 14 active sensor nodes distributed across three deployment zones:

- **Zone A (Polar Fringe):** 6 nodes, anchored to Oswick Station infrastructure
- **Zone B (Mid-Latitude):** 5 nodes, managed by Team Velanthor from Halvern Testing Ground
- **Zone C (Transition Band):** 3 nodes, mobile deployment via AETHER high-altitude platforms (see Document 17)

### Node Naming Convention

All NOVA nodes follow the naming pattern `NV-[ZONE]-[SEQ]`, e.g., NV-A-004. Node identifiers are registered in the VRC Central Equipment Registry under batch ID NOVA-NODE-BATCH-003.

## Data Management

Raw sensor output is transmitted via the Irixon-4 telemetry backbone to the VRC Data Processing Centre (VDPC) at Halvern. Data files are written in the VRC binary interchange format (VBIF v2), with checksums validated against reference hash table `VBIF-HASH-2022-0314`.

Data quality flags follow the **Duskline Protocol** (see Document 20), which specifies a 72-hour observation window for anomaly confirmation before escalation.

## Personnel

| Name | Role | Affiliation |
|------|------|-------------|
| Dr. Mara Fenwick | Principal Investigator | Team Velanthor |
| Dr. Petra Olmstead | Atmospheric Modelling Lead | Team Velanthor |
| Technician Ove Sandvik | Field Operations | Oswick Station |
| Technician Yisel Caban | Data Processing | VDPC, Halvern |

## Known Limitations

- Kryon-7 units deployed in Zone A exhibit a 1.2 dB signal attenuation during polar night periods (see Appendix A for correction factors)
- Wind buffering above 2,500 m at Halvern introduces vibration artefacts in 3.1% of hourly records
- Zone C mobile nodes are subject to the operational window constraints of the Duskline Protocol

## Safety and Compliance

All NOVA field activities comply with VRC Safety Standard VSS-2019-04. Personnel operating in Zone A are subject to the Oswick Station safety protocols (Document 03, Section 4.2). Emergency contact for all field activities is the VRC Emergency Operations Centre at extension 7-700.

---

## Appendix A: Signal Attenuation Correction Factors

During polar night (defined as solar elevation < −6°), Kryon-7 units in Zone A require the following attenuation correction factors applied post-hoc during data processing. These values were derived from calibration runs conducted at Halvern in November 2021 and are specific to the SYS-KRY7-001 hardware revision.

| Frequency Band | Wavelength Range | Correction Factor | Applicable Months |
|----------------|-----------------|-------------------|-------------------|
| Band 1 | 0.4–0.7 μm | 1.142 | November–February |
| Band 2 | 0.7–1.4 μm | 1.089 | October–February |
| Band 3 | 1.4–2.5 μm | 0.997 | All (negligible) |
| Band 4 | 2.5–5.0 μm | 1.203 | November–January |

The **847-day total project duration** was established to ensure at least two full polar night cycles are captured in the Zone A dataset, enabling statistical characterisation of the seasonal attenuation effect and providing sufficient sample size for model validation.[^1]

[^1]: Attenuation model derived from pre-deployment calibration runs at Halvern Testing Ground, November 2021. Reference calibration log: VRC-CAL-2021-1104. The 847-day figure supersedes the originally proposed 720-day duration, which was extended by the VRC Science Committee on 30 September 2022 (meeting minutes: VRC-SC-MIN-2022-09).

---

## Appendix B: Quality Control Checksums

Data batches from all active nodes are verified against the following reference checksums. Any batch failing verification is quarantined for manual inspection and flagged in the NOVA anomaly log (file: `NOVA-ANOM-LOG-LIVE`).

| Node ID | Checksum Type | Reference Value |
|---------|--------------|-----------------|
| NV-A-001 | SHA-256 prefix | 8f3a2c91... |
| NV-A-002 | SHA-256 prefix | d71b0e44... |
| NV-B-001 | SHA-256 prefix | 4c99fa07... |
| NV-C-001 | SHA-256 prefix | 2e470138... |

*Figure 1: Sensor network topology map for NOVA deployment zones A–C. Nodes are represented as hexagonal markers; Oswick Station and Halvern Testing Ground are shown as anchor points.*

---

*Document version: 1.4 | Last revised: 02 January 2024 | Maintained by: Dr. Mara Fenwick (m.fenwick@vrc.org)*
