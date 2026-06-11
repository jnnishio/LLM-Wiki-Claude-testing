# Project NEXUS: Multi-Sensor Fusion Platform

**Project Code:** VRC-FUS-6671  
**Principal Investigator:** Prof. Tarquin Selvidge  
**Program Start:** 01 September 2023  
**Status:** Active (Integration Phase)

---

## 1. Program Overview

Project NEXUS (code: VRC-FUS-6671) is the Veltrix Research Consortium's flagship data fusion initiative, designed to integrate measurements from six different sensor modalities onto a single co-located platform to enable multi-variable geophysical retrievals impossible with any single sensor. NEXUS is directed by **Prof. Tarquin Selvidge**, VRC Director of Research, reflecting its status as the VRC's highest-priority new initiative.

NEXUS is distinguished from all other VRC programs by its explicit goal of cross-sensor information fusion: it is not a single-discipline science program but an enabling infrastructure that benefits NOVA, HELIOS, SABLE, AETHER, and TRITON by providing multi-variable co-located reference datasets for algorithm validation.

## 2. Project Details

| Field | Value |
|-------|-------|
| Project Code | VRC-FUS-6671 |
| Principal Investigator | Prof. Tarquin Selvidge |
| Deputy PI | Dr. Renna Holt (Team Crestfield) |
| Operations Base | Halvern Testing Ground (FAC-HLV-002) |
| Phase 1 (Integration) | September 2023 – August 2024 |
| Phase 2 (Operations) | September 2024 – August 2027 |
| Budget | 22.1M VRC-credits (Phase 1 + 2) |
| Funding | Category I (VRC Consortium priority) |

## 3. Sensor Suite

NEXUS integrates **six sensor modalities** in a co-located ground station at Halvern:

| Modality | Instrument | System Code | Document | Lead |
|----------|-----------|-------------|----------|------|
| 1. Multi-spectral atmospheric | Kryon-7X | SYS-KRY7X-002 | Doc 18 | Team Crestfield |
| 2. Broadband solar irradiance | Peltex-200 | SYS-PEL200-R02 | Doc 14 | Team Crestfield |
| 3. Optical spectroscopy | Valdyne Spectral Array | SYS-VAL-004 | Doc 23 | Team Crestfield |
| 4. Sub-surface geophysics | Halvdyne GRP-500 | — | Internal | VRC Geophysics |
| 5. Microwave radiometry | VRC-MWR-03 | — | Internal | VRC Instrumentation |
| 6. Acoustic atmospheric | Veltrix SODAR-1 | — | Internal | VRC Instrumentation |

### 3.1 Sensor 1: Kryon-7X

The Kryon-7X (Document 18) provides multi-spectral atmospheric measurements across 6 bands (0.3–8.0 μm). The NEXUS installation uses a fixed-mast configuration on HLV-MAST-02, with the Kryon-7X mounted at 20 m height. The calibration checksum `9E3A` must be verified at each calibration cycle (per Document 18).

### 3.2 Sensor 2: Peltex-200

The Peltex-200 (Document 14, current specification SYS-PEL200-R02) provides broadband solar irradiance. The NEXUS unit (serial PEL-200-0087, manufactured post-January 2022) applies the corrected K_cal = 0.00391 from factory and does not require the firmware update described in Document 14.

### 3.3 Sensor 3: Valdyne Spectral Array

The Valdyne Array (Document 23) provides high-resolution optical spectroscopy for atmospheric emission and aerosol optical depth. The NEXUS installation uses the full configuration on a fixed optical bench in HLV-B03.

### 3.4 Sensors 4–6

Sensors 4–6 (sub-surface geophysics, microwave radiometry, and acoustic atmospheric) are unique to NEXUS and not used in other VRC programs. Their specifications are held in VRC internal documents VRC-NEXUS-SEN-004, -005, and -006 respectively.

## 4. Data Integration Architecture

### 4.1 Data Collection Node

All six sensors feed into the **NEXUS Data Integration Node (NDIN)**, a purpose-built data aggregation server hosted at Halvern VDPC. NDIN synchronises data streams to a common UTC time base using GPS-disciplined timing (1 PPS reference) to achieve inter-sensor synchronisation better than 1 ms.

NDIN hardware: VRC custom server, code VRC-NDIN-HW-001, installed September 2023.

### 4.2 Fusion Pipeline

The NEXUS data fusion pipeline:

```
Raw data streams → NDIN synchronisation → Per-sensor QC (Duskline Protocol flags)
    → Cross-sensor consistency check → Fusion algorithm engine
    → Fused geophysical retrieval products → VRC Integrated Archive
```

The fusion algorithm engine (VRC-NEXUS-FUSION-v1) is under development by a dedicated NEXUS algorithm team led by Dr. Petra Olmstead.

### 4.3 Data Quality

NEXUS data are subject to the **Duskline Protocol** (Document 20) for per-sensor anomaly management. The NEXUS-specific compliance officer: Dr. Renna Holt. Cross-sensor consistency failures generate a separate `QF-NEXUS-DISAGREE` quality flag (Duskline Protocol extension, approved September 2023).

## 5. Science Targets

### 5.1 Phase 1 (Integration): Validation Activities

- Cross-calibrate all six sensors against each other and against external standards
- Validate NDIN time synchronisation to < 1 ms
- Produce first proof-of-concept multi-sensor retrievals

### 5.2 Phase 2 (Operations): Science Deliverables

- Continuous 3-year multi-sensor dataset at Halvern
- Aerosol optical depth with multi-instrument cross-validation
- Sub-surface–atmosphere coupling studies
- Reference dataset for NOVA, HELIOS, and AETHER algorithm validation

## 6. Personnel

| Name | Role |
|------|------|
| Prof. Tarquin Selvidge | Principal Investigator |
| Dr. Renna Holt | Deputy PI; Team Crestfield liaison |
| Dr. Petra Olmstead | Fusion algorithm lead (Team Velanthor) |
| Kofi Twumasi-Mensah | Sensor calibration coordinator |
| Engineer Pilar Serrano | NDIN hardware and telemetry (Team Velanthor) |
| Eng. Lirael Brannock | Kryon-7X integration (Team Crestfield) |
| Eng. Vesper Quillan | Valdyne Array integration (Team Crestfield) |

---

## Appendix A: Inter-Program Data Sharing

| Program | Shared Data | Benefit to NEXUS | Benefit to Program |
|---------|-------------|-----------------|-------------------|
| NOVA (Doc 01) | Kryon-7 atmospheric baseline | Comparison with Kryon-7X at same site | Multi-sensor AOD cross-validation |
| HELIOS (Doc 04) | Peltex-200 irradiance data | 3-year solar reference | NEXUS Peltex validation |
| SABLE (Doc 22) | Valdyne nighttime spectral data | Nighttime instrument characterisation | Daytime NEXUS Valdyne calibration |
| AETHER (Doc 17) | Upper atmosphere profiles | Boundary condition for retrievals | Atmospheric context |

## Appendix B: Budget Summary

| Phase | Period | Budget (VRC-credits) |
|-------|--------|---------------------|
| Phase 1 (Integration) | Sep 2023 – Aug 2024 | 4.8M |
| Phase 2 (Operations) | Sep 2024 – Aug 2027 | 17.3M |
| **Total** | | **22.1M** |

NEXUS is the single largest investment in VRC's current programme portfolio, reflecting the consortium leadership's conviction that cross-sensor fusion is the highest-leverage investment for programme-wide science return.[^1]

[^1]: The 22.1M VRC-credit total budget for NEXUS was approved at the VRC Consortium Council meeting of 15 June 2023 (minutes: VRC-CC-MIN-2023-06). This exceeds the combined budgets of Projects NOVA, HELIOS, and AETHER, making NEXUS the largest single program in VRC history.

---

*Document version: 1.0 | Last revised: 15 October 2023 | Maintained by: Prof. Tarquin Selvidge (t.selvidge@vrc.org)*
