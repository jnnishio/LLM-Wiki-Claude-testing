# Project SABLE: Nightside Optical Survey Program

**Project Code:** VRC-OPT-5512  
**Principal Investigator:** Dr. Aldous Quirk  
**Program Start:** 01 November 2022  
**Status:** Active (Phase 1)

---

## 1. Program Overview

Project SABLE (code: VRC-OPT-5512) is the Veltrix Research Consortium's nightside optical survey program, dedicated to high-precision astronomical and atmospheric optical measurements conducted exclusively during polar night. SABLE operations take advantage of the extended darkness at high-latitude VRC sites to achieve measurement conditions unavailable during daytime operations.

SABLE uses the **Atlas North** autonomous platform (Document 11) as its primary airborne instrument carrier, fitted with the **Kryon-7X** sensor (Document 18) and the **Valdyne Spectral Array** (Document 23). Ground-based optical measurements are also made from fixed installations at Halvern Testing Ground (Document 16) and the Thule Relay Outpost.

> **Important disambiguation:** The name "SABLE" refers to this project (led by Dr. Aldous Quirk). It should not be confused with the name of **Dr. Sable Yurin**, who leads Project TRITON (Document 12) and Experiment EXP-119 (Document 21). These are entirely separate programs.

## 2. Project Details

| Field | Value |
|-------|-------|
| Project Code | VRC-OPT-5512 |
| Principal Investigator | Dr. Aldous Quirk |
| Operations Base | Halvern Testing Ground (FAC-HLV-002) |
| Secondary Site | Thule Relay Outpost (FAC-TRL-007) |
| Phase 1 Period | November 2022 – October 2025 |
| Operational Season | November–February (polar night window) |
| Budget Allocation | 6.2M VRC-credits |

## 3. Scientific Objectives

SABLE targets three primary observation programmes:

### 3.1 Airglow and Auroral Emission Mapping

SABLE characterises the spatial and temporal structure of:
- Hydroxyl (OH) airglow emissions at 1.5–1.7 μm (Meinel bands)
- Oxygen airglow at 0.558 μm (green line) and 0.630 μm (red line)
- Auroral emissions in the Kryon-7X Band 1–2 range during geomagnetic events

These measurements extend the NOVA atmospheric dataset (Document 01) into the night-time boundary layer and mesosphere.

### 3.2 Astronomical Point-Source Photometry

SABLE measures the photometric stability of bright reference stars in the VRC photometric standard catalogue (VRC-PHOT-CAT-2020) to calibrate instrumental throughput for other VRC optical programs.

Target precision: **0.003 arcseconds** for astrometric position solutions; photometric repeatability < 2 mmag.

### 3.3 Noctilucent Cloud (NLC) Survey

At altitudes 75–85 km, SABLE detects and characterises noctilucent clouds using the Valdyne Spectral Array's near-UV sensitivity. NLC detection requires the sun to be at least 6° below the horizon at the observation altitude — a condition met throughout the polar night window.

## 4. Platform Configuration

### 4.1 Atlas North

The Atlas North (Document 11) is the SABLE airborne platform. Specific SABLE configuration:

- Payload: Kryon-7X (SYS-KRY7X-002) + Valdyne Spectral Array (SYS-VAL-004) combined at 5.9 kg total
- Minimum operating temperature: −65°C (covers entire expected polar night range at Halvern)
- Navigation: Triple GNSS (from Atlas-X heritage) — essential for precise ephemeris-correlated photometry
- Field operator: Vex Horodynski (as designated in Document 11)

### 4.2 Ground Installations

Fixed optical benches at Halvern and Thule carry:
- Valdyne Spectral Array (full configuration, Document 23)
- All-sky imager (VRC-ASI-02, custom fisheye lens system)
- Absolute photometer (Halvdyne AP-200)

## 5. Observation Schedule

| Observation Type | Platform | Season | Frequency |
|----------------|----------|--------|-----------|
| Airglow mapping | Atlas North | Nov–Feb | 3–4 nights/week |
| Auroral emission | Atlas North + ground | Event-triggered | 8–15 events/year typical |
| Stellar photometry | Ground (Halvern) | Nov–Feb | Nightly |
| NLC survey | Ground (Halvern, Thule) | Nov–Jan | Nightly |
| Extended NLC | Atlas North | Dec–Jan | 2–3 nights/week |

## 6. Data Quality

All SABLE data are subject to the **Duskline Protocol** (Document 20) for anomaly management. Dr. Aldous Quirk serves as both SABLE PI and Duskline Protocol author, and handles SABLE's Duskline compliance directly. The twilight pre-filter (see Document 20, Appendix B) is waived for SABLE, as all observations occur during full polar night.

## 7. Personnel

| Name | Role |
|------|------|
| Dr. Aldous Quirk | Principal Investigator; Duskline Protocol author |
| Vex Horodynski | Atlas North field operator |
| Eng. Vesper Quillan | Valdyne Spectral Array technical support (Team Crestfield) |
| Dr. Renna Holt | Kryon-7X technical authority |
| Analyst Dafydd Emlyn | Data processing (Team Velanthor, on secondment) |

---

## Appendix A: Phase 1 Observing Summary (November 2022 – March 2023)

First operational season metrics:

| Metric | Value |
|--------|-------|
| Atlas North flights completed | 47 |
| Hours of airborne science data | 118 h |
| Ground-based observing nights (Halvern) | 63 |
| Confirmed auroral events captured | 9 |
| Stellar photometry catalogue updated | 412 stars |
| Lowest ambient temperature during operations | −61°C (Halvern, 12 January 2023) |

## Appendix B: Key Performance Parameters

| Parameter | Target | Achieved (Phase 1) |
|-----------|--------|-------------------|
| Astrometric precision | 0.003 arcsec | 0.003 arcsec (met) |
| Photometric repeatability | < 2 mmag | 1.4 mmag (exceeded) |
| Atlas North mission availability | > 80% scheduled flights | 89% |
| Kryon-7X noise floor | < 5 × 10⁻⁹ V/√Hz | 3.11 × 10⁻⁹ (spec; confirmed) |

The SABLE astrometric precision of **0.003 arcseconds** is the defining optical performance requirement of the program. It was achieved in Phase 1 using the Atlas North's inertial-stabilised pointing system in combination with the Valdyne array's high-resolution optical axis.[^1]

[^1]: The 0.003 arcsecond precision value corresponds to approximately 14 μrad, which at the observation distances relevant to NLC altitude characterisation (~80 km range) translates to a spatial resolution of ~1.1 m. This requirement was set to resolve fine-scale NLC morphological features predicted by theoretical models of gravity-wave-driven NLC variability.

---

*Document version: 1.1 | Last revised: 15 April 2023 | Maintained by: Dr. Aldous Quirk (a.quirk@vrc.org)*
