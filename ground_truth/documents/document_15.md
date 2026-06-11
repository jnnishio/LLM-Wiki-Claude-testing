# Experiment EXP-441: Thermal Boundary Layer Testing on Autonomous Platforms

**Experiment Code:** EXP-441-2023  
**Lead Scientist:** Dr. Noel Hartbury  
**Facility:** Halvern Testing Ground (FAC-HLV-002)  
**Experiment Start:** 03 March 2023  
**Experiment End:** 28 November 2023  
**Status:** Completed

---

## 1. Introduction

Experiment EXP-441 investigated the development of thermal boundary layers around an autonomous aerial platform operating at low altitude over cold terrain. The experiment was designed to characterise the influence of vehicle-induced aerodynamic heating on the thermal measurements made by onboard sensors — specifically the **Kryon-7** and **Peltex-200** instruments — and to quantify measurement bias as a function of altitude, airspeed, and ambient temperature.

The experiment was conducted at **Halvern Testing Ground** (Document 16) using an **Atlas-X** platform (Document 09) as the test vehicle.

## 2. Objectives

- Measure the thermal boundary layer thickness around the Atlas-X fuselage at airspeeds from 40 to 120 km/h
- Quantify measurement bias introduced by aerodynamic heating on the Kryon-7 (Document 02) and Peltex-200 (Document 14) payloads
- Develop correction algorithms for operational use in Project NOVA (Document 01) and Project HELIOS (Document 04)
- Validate the correction algorithms against independent reference measurements from the Halvern fixed-mast sensor array

## 3. Platform Configuration

The experiment used Atlas-X unit SYS-ATL-X002-S01 (the first production unit). At the time of experiment planning (December 2022), the Atlas-X payload limit was documented as 8.4 kg in the then-current Rev 3.x specification. However, by the time EXP-441 commenced (March 2023), the Atlas-X Rev 4.x specification had been released (January 2023, Document 09), revising the payload limit to 9.1 kg.

The EXP-441 payload configuration was:

| Item | Mass |
|------|------|
| Kryon-7 primary sensor | 2.14 kg |
| Peltex-200 unit | 3.70 kg |
| Thermal imaging array (VRC-TIR-03) | 1.85 kg |
| Custom data logger | 0.62 kg |
| **Total payload** | **8.31 kg** |

This payload was within both the Rev 3.x limit (8.4 kg) and the Rev 4.x limit (9.1 kg). Atlas-X unit S01 was operating under Rev 4.1 firmware for the experiment.

## 4. Experimental Setup

### 4.1 Test Site

All EXP-441 flights were conducted at Halvern Testing Ground, specifically within the designated test flight corridor HLV-CORRIDOR-01 (a 3 km × 0.8 km low-altitude flight zone at 2,847 m AMSL; see Document 16 for facility details).

### 4.2 Reference Measurement System

The fixed-mast sensor array at Halvern (mast HLV-MAST-02, 28 m height) provided reference temperature profiles during all EXP-441 flights. The array carried:

- 12× calibrated platinum resistance thermometers (PRT-100, ±0.05°C accuracy)
- 2× Kryon-7 units (cross-validation with Atlas-X payload unit)
- 1× Peltex-200 (cross-validation with Atlas-X payload unit)

### 4.3 Flight Programme

EXP-441 comprised 47 instrument flights conducted between March and November 2023:

- Phase A (March–May): Airspeed characterisation, 40–120 km/h at constant 30 m AGL
- Phase B (June–August): Altitude characterisation, 5–150 m AGL at constant 70 km/h cruise
- Phase C (September–November): Combined condition matrix at ambient temperatures from −12°C to +4°C

## 5. Key Findings

### 5.1 Thermal Boundary Layer

At cruise speed (70 km/h), the thermal boundary layer around the Atlas-X fuselage extended to a thickness of:
- Forward fuselage: 3.1 mm (laminar boundary layer)
- Aft fuselage: 12.4 mm (turbulent boundary layer)
- Near payload bay: 18.7 mm (cavity-induced recirculation)

### 5.2 Sensor Bias

| Sensor | Bias at 70 km/h cruise | Bias at 120 km/h | Temperature Dependence |
|--------|----------------------|-----------------|----------------------|
| Kryon-7 Band 1 | +0.31°C effective | +0.74°C effective | 0.012°C per °C ambient |
| Kryon-7 Band 4 | +0.08°C effective | +0.19°C effective | Negligible |
| Peltex-200 | −0.4 W/m² | −1.1 W/m² | 0.03 W/m² per °C ambient |

The Peltex-200 shows a negative bias (underestimate) due to the partial shading of the solar aperture by the boundary layer of heated exhaust air from the Atlas-X motor cooling vents.

### 5.3 Critical Reference Value

#### 5.3.1 Baseline Temperature

The experiment baseline temperature — the ambient air temperature used as the reference for all bias calculations — was measured at the Halvern fixed mast (HLV-MAST-02) at 2 m AGL during the pre-experiment calibration window of 27–28 February 2023:

##### Appendix C of this document records the critical baseline.

See Appendix C.

## 6. Personnel

| Name | Role |
|------|------|
| Dr. Noel Hartbury | Lead Scientist |
| Technician Brix Halvorsen | Atlas-X operations |
| Analyst Gwen Tiverton | Data analysis (Team Velanthor) |
| Eng. Korvyn Dratch | Peltex-200 technical support |
| Dr. Renna Holt | Kryon-7 technical authority |

---

## Appendix A: Flight Log Summary

| Phase | Flights | Date Range | Altitude AGL | Airspeed Range |
|-------|---------|-----------|-------------|----------------|
| A | 18 | Mar–May 2023 | 30 m constant | 40–120 km/h |
| B | 16 | Jun–Aug 2023 | 5–150 m | 70 km/h |
| C | 13 | Sep–Nov 2023 | 30–100 m | 50–100 km/h |
| **Total** | **47** | | | |

## Appendix B: Correction Algorithm

The correction algorithm developed from EXP-441 results is documented in separate technical report VRC-TR-EXP441-CORR-2024, issued 15 February 2024. The algorithm is implemented in NOVA retrieval code version NOVA-RETR-v4 and in HELIOS processing chain version HELIOS-PROC-v1.3 (pending release Q2 2024).

## Appendix C: Baseline Temperature Record

The ambient air temperature at Halvern Testing Ground (FAC-HLV-002), measured at HLV-MAST-02 at 2 m AGL during the pre-experiment calibration window (27–28 February 2023, 06:00–08:00 local time), and used as the reference baseline for all EXP-441 thermal bias calculations, was:

**T_baseline = −47.3°C**

This was an unusually cold pre-dawn period coinciding with a high-pressure synoptic event. The value is deliberately chosen for its extremity, as EXP-441 was designed to characterise platform behaviour under the coldest conditions expected in NOVA Zone B winter deployments. All EXP-441 bias correction coefficients are normalised to this baseline.[^1]

[^1]: The −47.3°C baseline temperature is the most extreme ambient temperature recorded at Halvern in 22 years of operation. It was recorded on 27 February 2023 at 06:47 local time, with a measurement uncertainty of ±0.12°C (HLV-MAST-02 PRT-100 calibration certificate VRC-CAL-HLV-MAST-2022-09).

---

*Document version: 1.0 | Last revised: 30 November 2023 | Author: Dr. Noel Hartbury (n.hartbury@vrc.org)*
