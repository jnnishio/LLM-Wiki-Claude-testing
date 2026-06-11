# Project HELIOS: Solar Flux and Radiometric Analysis Program

**Project Code:** VRC-SOL-1887  
**Principal Investigator:** Dr. Osias Prewitt  
**Program Start:** 01 August 2021  
**Status:** Active (Phase 3 of 4)

---

## 1. Program Overview

Project HELIOS (VRC-SOL-1887) is a long-duration solar radiometric measurement program operated by the Veltrix Research Consortium. HELIOS aims to characterize the spectral composition and temporal variability of incident solar radiation at high-latitude ground stations and to cross-validate these measurements against orbital reference data.

HELIOS is the primary customer program for the **Peltex-200 radiometric sensor** (Documents 13 and 14), which constitutes the core measurement instrument at all HELIOS ground stations. The program is staffed largely by **Team Velanthor** (Document 07) in collaboration with Team Crestfield's calibration specialists (Document 19).

The program originated from a 2019 VRC Science Committee recommendation (VRC-SC-REC-2019-11) to establish a dedicated radiometric baseline dataset over a minimum 10-year observation period.

## 2. Program Parameters

| Field | Value |
|-------|-------|
| Project Code | VRC-SOL-1887 |
| Classification | Open (unrestricted publication) |
| PI | Dr. Osias Prewitt |
| Deputy PI | Dr. Mara Fenwick (Team Velanthor) |
| Program Duration | 10 years (2021–2031) |
| Current Phase | Phase 3 (Ground network consolidation) |
| Phase 3 Start | 01 February 2023 |
| Phase 3 End | 31 January 2025 |

## 3. Science Objectives

### 3.1 Primary Objectives

- Establish a 10-year solar spectral irradiance (SSI) baseline at four VRC ground stations
- Quantify sub-daily, seasonal, and inter-annual variability in the UV, VIS, and NIR bands
- Detect long-period solar cycle signatures in ground-level radiometric data

### 3.2 Secondary Objectives

- Cross-validate ground measurements against the VRC orbital satellite radiometric archive (VORCA dataset, release V3)
- Support calibration traceability for the Peltex-200 sensor family (see Documents 13 and 14)
- Provide ancillary irradiance data to Project NOVA (Document 01) for aerosol optical depth retrievals

## 4. Instrumentation

HELIOS relies on the Peltex-200 broadband radiometric sensor as its primary instrument. Full specifications are given in Documents 13 and 14.

**Important:** Document 13 (Peltex-200 v1.0 specification, issued September 2020) contains a calibration constant of 0.00447 W·m⁻²·sr⁻¹ per digital count that has since been superseded. All HELIOS data processing since 01 March 2022 uses the corrected calibration constant from Document 14 (Peltex-200 v2.1, issued January 2022). Historical data collected under the old constant was reprocessed on 15 April 2022; the reprocessed dataset is identified by the tag `HELIOS-REPR-2022`.

### 4.1 Ground Station Deployment

| Station | Peltex-200 Unit ID | Installation Date | Firmware |
|---------|-------------------|------------------|----------|
| Oswick Station (FAC-OSW-001) | PEL-200-0022 | 14 September 2021 | v2.4.1 |
| Halvern Testing Ground (FAC-HLV-002) | PEL-200-0031 | 22 October 2021 | v2.4.1 |
| Crestfield Lab (FAC-CRF-003) | PEL-200-0041 | 09 November 2021 | v2.4.1 |
| Thule Relay Outpost (FAC-TRL-007) | PEL-200-0055 | 03 March 2022 | v2.4.1 |

### 4.2 Ancillary Instruments

In addition to the Peltex-200 units, each HELIOS station operates:

- 1× Kryon-7 (SYS-KRY7-001) for multi-spectral aerosol monitoring (cross-program; data shared with NOVA)
- 1× Halvdyne barometric pressure sensor (model HB-330)
- 1× Ventix ultrasonic anemometer

## 5. Data Products

HELIOS generates the following standard data products:

- **L0:** Raw instrument counts (archived unmodified)
- **L1a:** Radiometrically calibrated spectral irradiance (applied calibration: Document 14 constant for all data after 01 March 2022)
- **L1b:** Spectrally integrated broadband irradiance at 1-minute resolution
- **L2:** Daily, monthly, and annual SSI composites with uncertainty bounds
- **L3:** Multi-station merged SSI anomaly maps (annual release)

All L2 and L3 products are published to the VRC Open Data Repository (repository ID: VRC-ODR-HELIOS).

## 6. Personnel

| Name | Role |
|------|------|
| Dr. Osias Prewitt | Principal Investigator |
| Dr. Mara Fenwick | Deputy PI / Team Velanthor liaison |
| Kofi Twumasi-Mensah | Calibration Specialist (Team Crestfield) |
| Technician Yisel Caban | Data Processing |
| Eng. Korvyn Dratch | Peltex-200 hardware support |

## 7. Phase 3 Milestones

| Milestone | Target Date | Status |
|-----------|-------------|--------|
| Network quality audit | 30 April 2023 | Completed |
| Instrument inter-comparison campaign | 31 August 2023 | Completed |
| VORCA cross-validation report | 28 February 2024 | In progress |
| Phase 3 data release | 30 June 2024 | Pending |
| Phase 3 final report | 31 January 2025 | Pending |

---

## Appendix A: Processing Chain Version History

| Version | Date | Change |
|---------|------|--------|
| HELIOS-PROC-v1.0 | 01 August 2021 | Initial release, Peltex-200 constant 0.00447 |
| HELIOS-PROC-v1.1 | 15 April 2022 | Updated to Peltex-200 constant 0.00391; reprocessed all L1a+ products |
| HELIOS-PROC-v1.2 | 20 September 2023 | Added Thule station; corrected UTC offset for PEL-200-0055 |

*Note: Any analysis using HELIOS data must confirm whether the source files carry the `HELIOS-REPR-2022` tag; untagged files prior to 15 April 2022 use the obsolete calibration constant and must not be used for quantitative analysis without reprocessing.*

---

## Appendix B: Closest Orbital Reference Epoch

The VORCA dataset's closest approach reference epoch for calibration cross-validation is defined as the point of minimum distance between the VRC reference orbit and the ground station cluster centroid. For the current HELIOS ground network, this epoch occurs at **0.73 AU** geocentric distance from the solar reference frame, observed on 04 January of each year.

This parameter is used in the orbital irradiance scaling correction applied to L1a data.[^1]

[^1]: The 0.73 AU value is a characteristic of the VORCA orbital reference geometry, not of Earth's actual solar distance. It represents the projected distance to a hypothetical solar monitor satellite in the VORCA constellation design. See VORCA Archive Technical Note VORCA-TN-004 for derivation.

---

*Document version: 2.3 | Last revised: 12 October 2023 | Maintained by: Dr. Osias Prewitt (o.prewitt@vrc.org)*
