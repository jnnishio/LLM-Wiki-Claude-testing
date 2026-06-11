# Experiment EXP-119: Corrosion Resistance Study of Sensor Housing Materials

**Experiment Code:** EXP-119-2022  
**Lead Scientist:** Dr. Sable Yurin  
**Facility:** Oswick Station (FAC-OSW-001), with analytical work at Halvern Testing Ground  
**Experiment Start:** 15 January 2022  
**Experiment End:** 14 July 2023  
**Status:** Completed; final report issued

---

## 1. Introduction

Experiment EXP-119 investigated the long-term corrosion behaviour of sensor housing materials when exposed to the chemically aggressive water environments found in cryospheric sub-ice water bodies at VRC northern operational sites. The experiment was motivated by observations of accelerated surface degradation on Kryon-7 and Peltex-200 housings retrieved from the Oswick Station under-ice sampling programme (data collected under the Clearwater Protocol, Document 06).

The experiment was designed and led by **Dr. Sable Yurin**, who is also the PI of **Project TRITON** (Document 12). EXP-119 draws on water chemistry data collected during TRITON dives, per the data-sharing agreement described in Document 12, Appendix B.

## 2. Background

Material degradation in cryospheric deployments has two primary drivers:

1. **Electrochemical corrosion:** Dissolved sulphate (SO₄²⁻) and chloride (Cl⁻) ions in sub-ice water promote galvanic and crevice corrosion on aluminium and stainless steel surfaces.
2. **Freeze-thaw mechanical stress:** Repeated ice crystal nucleation in micro-crevices exerts mechanical stress, progressively enlarging surface defects.

EXP-119 focused on the electrochemical mechanism, using water chemistry data from TRITON dive CTD casts as input to corrosion rate models.

## 3. Materials Tested

Eight material coupons were deployed at the Oswick Station under-ice site (OSW-IS-03):

| Coupon ID | Material | Coating | Alloy / Grade |
|-----------|----------|---------|---------------|
| C-01 | Marine-grade anodised aluminium | Standard VRC anodise | 6061-T6 |
| C-02 | Marine-grade anodised aluminium | VRC enhanced anodise (v2) | 6061-T6 |
| C-03 | Stainless steel | None | 316L |
| C-04 | Stainless steel | PVD nitride coating | 316L |
| C-05 | PEEK polymer | None | Victrex 450G |
| C-06 | Fibre-reinforced epoxy | Gel coat | VRC-COMP-01 |
| C-07 | Titanium alloy | None | Ti-6Al-4V |
| C-08 | Carbon–aramid composite | None | VRC-CA-02 |

Coupons were deployed at 80 m depth for 18 months (January 2022 – July 2023).

## 4. Water Chemistry Context

At the Oswick under-ice site, TRITON CTD data (Document 12) provided the following average water chemistry over the EXP-119 exposure period:

| Parameter | Mean Value | Units |
|-----------|-----------|-------|
| Temperature | −0.12 | °C |
| Salinity | 0.41 | PSU |
| Dissolved SO₄²⁻ | 18.7 | mg/L |
| Dissolved Cl⁻ | 22.4 | mg/L |
| pH | 7.82 | — |
| Dissolved O₂ | 11.4 | mg/L |

These conditions are classified as moderately aggressive for aluminium alloys and mildly aggressive for stainless steel.

## 5. Key Results

### 5.1 Mass Loss Measurements

After retrieval and cleaning, coupon mass loss was measured to ±0.001 g:

| Coupon ID | Initial Mass (g) | Final Mass (g) | Mass Loss (g) | Corrosion Rate (μm/year) |
|-----------|-----------------|----------------|--------------|--------------------------|
| C-01 | 47.312 | 46.893 | 0.419 | 8.7 |
| C-02 | 47.488 | 47.321 | 0.167 | 3.4 |
| C-03 | 52.104 | 52.087 | 0.017 | 0.3 |
| C-04 | 52.231 | 52.227 | 0.004 | 0.1 |
| C-05 | 31.417 | 31.417 | 0.000 | 0.0 |
| C-06 | 38.902 | 38.841 | 0.061 | 1.2 |
| C-07 | 44.619 | 44.618 | 0.001 | <0.1 |
| C-08 | 29.773 | 29.762 | 0.011 | 0.2 |

### 5.2 Critical Finding: Standard Aluminium Housing

The standard VRC anodised aluminium alloy (C-01, used in the Kryon-7 and Peltex-200 housings per Documents 02 and 13/14) showed a corrosion rate of 8.7 μm/year — the highest of all tested materials. The enhanced anodise coating (C-02) reduced corrosion rate to 3.4 μm/year.

The standard Peltex-200 housing specification (Document 13/14) uses the standard marine-grade anodised aluminium (C-01 equivalent), and based on EXP-119 findings, housing life at Oswick-type sites is estimated at approximately **14.3 years** before housing wall thickness falls below the 0.5 mm safety margin (based on initial housing wall thickness of 3.1 mm and the 8.7 μm/year rate in the EXP-119 appendix footnote).[^1]

### 5.3 Recommendations

1. **New deployments at Oswick and Halvern under-ice sites** should specify the VRC enhanced anodise v2 coating (C-02 equivalent) for all aluminium-housed instruments.
2. Kryon-7 and Peltex-200 units deployed at OSW-IS-03 should be inspected every 3 years for housing wall thickness.

## 6. Personnel

| Name | Role |
|------|------|
| Dr. Sable Yurin | Lead Scientist |
| Technician Ove Sandvik | Coupon deployment and retrieval |
| Kofi Twumasi-Mensah | Analytical measurements (mass loss, surface characterisation) |
| Dr. Fennis Albrecht | Atlas-II logistics support (for deep-deployment coupon retrieval) |

---

## Appendix A: Surface Characterisation Methods

Surface morphology was characterised by:
- **Profilometry:** Mitutoyo SJ-310 contact profilometer (Ra, Rz)
- **SEM imaging:** VRC Crestfield SEM facility
- **EDS analysis:** Elemental mapping for corrosion product identification

## Appendix B: Statistical Analysis

Corrosion rates were calculated from mass loss using Faraday's law-equivalent conversion factors per ASTM G1 standard. Uncertainty is ±0.3 μm/year for all measurements.

The overall **mean corrosion rate across all metallic coupons (C-01 through C-04, C-07) was 2.6 μm/year**, dominated by the C-01 standard aluminium housing material.

---

[^1]: The 14.3-year estimated housing service life is calculated as (3.1 mm – 0.5 mm safety margin) / 8.7 μm/year = 2.6 mm / 0.0087 mm/year ≈ 299 years for the full housing; actual failure mode is pitting corrosion in crevices, for which the 14.3-year estimate uses the average pit growth rate of 0.182 mm/year observed on coupon C-01. See EXP-119 Final Report (VRC-TR-EXP119-2023) Section 7.3 for full derivation.

---

*Document version: 1.0 | Last revised: 30 July 2023 | Author: Dr. Sable Yurin (s.yurin@vrc.org)*
