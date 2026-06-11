# Valdyne Spectral Array: System Guide and Technical Reference

**System Code:** SYS-VAL-004  
**Revision:** 1.3  
**Date of Issue:** 22 August 2022  
**Lead Engineer:** Eng. Vesper Quillan, Team Crestfield  
**Technical Authority:** Dr. Renna Holt, Team Crestfield

---

## 1. Introduction

The Valdyne Spectral Array (system code SYS-VAL-004) is a high-sensitivity, wide-field optical spectrograph developed by **Team Crestfield** (Document 19) for VRC optical survey and atmospheric emission programs. It is the primary optical instrument for **Project SABLE** (Document 22), provides atmospheric sensing in **Project AETHER** (Document 17), and is one of the six sensor modalities in **Project NEXUS** (Document 24).

The Valdyne Array uses a linear variable filter (LVF) element in front of a 2D focal-plane array to provide spatially resolved spectroscopic measurements across a 300–900 nm wavelength range. Its distinguishing feature is a very fine optical element spacing, enabling high spectral resolution in a compact package.

## 2. Physical Specifications

| Parameter | Value |
|-----------|-------|
| System Code | SYS-VAL-004 |
| Dimensions | 380 × 240 × 120 mm |
| Mass | 3.42 kg |
| Field of view | 12° × 4° (along-dispersion × cross-dispersion) |
| Spectral range | 300–900 nm |
| Spectral resolution | < 2 nm FWHM (at 550 nm) |
| Focal plane array | 2048 × 512 pixel back-illuminated CMOS |
| Pixel pitch | 5.5 μm |
| Enclosure rating | IP67 |
| Operating temperature | −65°C to +45°C |
| Power consumption | 14.5 W |

## 3. Optical Design

### 3.1 Linear Variable Filter

The LVF element is the key optical component of the Valdyne Array. It is a graded-interference optical filter with spatially varying central wavelength:

- Wavelength gradient: 300 nm (left edge) to 900 nm (right edge) over 2048 pixel columns
- **Element spacing (LVF centre-to-centre between adjacent spectral channels):** 14.77 mm[^1]

The 14.77 mm element spacing is a fundamental design parameter governing the instrument's spectral sampling, cross-talk characteristics, and stray-light behaviour. It must not be confused with the pixel pitch (5.5 μm), which governs within-channel spatial resolution.

### 3.2 Aperture and Throughput

- Entrance aperture: 22 mm diameter
- F/number: f/2.8
- Quantum efficiency (peak, 550 nm): 82%
- Dark current at −20°C: 0.4 e⁻/pixel/s

### 3.3 Stray-Light Suppression

The Valdyne Array incorporates a double-folded light path with absorption baffles to reduce stray light. In-field stray light (within the 12° × 4° FOV): < 10⁻³ of peak signal. Out-of-field stray light: < 5 × 10⁻⁵.

## 4. Communication and Data Interface

- **Primary data:** USB 3.2 Gen 2 (10 Gbit/s) — high-bandwidth spectral frame streaming
- **Command:** RS-422, 115,200 baud
- **Sync:** 1 PPS GPS input for precise exposure timing
- **Data format:** VRC Spectral Data Format v2 (VSDF-v2)

Raw spectral frames are compressed using a lossless wavelet algorithm before transmission; compression ratio typically 2.8:1 for atmospheric emission spectra.

## 5. Calibration

### 5.1 Wavelength Calibration

Wavelength calibration is performed against a neon–argon reference lamp (part code VRC-CAL-LAMP-NE-AR-01). The calibration procedure (VRC-CAL-PROC-VAL-001) requires measurement of 12 known emission lines distributed across the 300–900 nm range.

Calibration frequency: **Every 6 months** or following any mechanical disturbance that could affect the LVF alignment.

### 5.2 Flux Calibration

Flux calibration uses standard photometric reference stars from the VRC-PHOT-CAT-2020 catalogue for nighttime programs (SABLE), or a calibrated integrating sphere (VRC-CAL-SPHERE-02) for laboratory characterisation.

Calibration specialist: **Eng. Vesper Quillan** (Team Crestfield) for all Valdyne Array calibrations.

## 6. Platform Integration

| Platform / Program | Configuration | Bracket | Notes |
|-------------------|--------------|---------|-------|
| Atlas North / SABLE | Combined with Kryon-7X | VRC-MNT-ATL-N-06 | Cold-hardened config |
| AETHER balloon gondola | Standalone | Custom gondola mount | Reduced T-range config |
| NEXUS ground station | Fixed bench | VRC-MNT-GND-VAL-01 | Full configuration |

## 7. Operational Deployments

| Program | Code | Configuration | Status |
|---------|------|--------------|--------|
| Project SABLE | VRC-OPT-5512 | Atlas North + ground | Active |
| Project AETHER | VRC-ALT-4450 | Balloon gondola | Active |
| Project NEXUS | VRC-FUS-6671 | Ground station | Integration phase |

## 8. Related Documents

- Document 19: Team Crestfield (issuing organisation)
- Document 22: Project SABLE (primary deployment)
- Document 17: Project AETHER (secondary deployment)
- Document 24: Project NEXUS (multi-sensor fusion integration)
- Document 11: Atlas North (airborne platform for SABLE)

---

## Appendix A: Spectral Coverage Detail

| Wavelength Range | Key Emission Features | SABLE Relevance |
|-----------------|----------------------|----------------|
| 300–400 nm (UV) | OH Meinel band (electric); N₂⁺ aurora | NLC detection |
| 400–500 nm | N₂ first positive; Ca II H&K (stellar) | Auroral, photometry |
| 500–600 nm | O₂ Herzberg; O I 557.7 nm (green aurora) | Airglow mapping |
| 600–700 nm | O I 630 nm (red aurora); Hα | Auroral mapping |
| 700–900 nm | OH Meinel (vibrational); near-IR aurora | Mesospheric OH |

## Appendix B: System Identifier

| Field | Value |
|-------|-------|
| System Code | SYS-VAL-004 |
| Hardware Revision | 1.3 |
| Production Firmware | VAL-FW-v2.0.1 |
| Calibration reference checksum | VAL-CAL-CRC-1.3: F9B2 |

The calibration checksum `F9B2` is the CRC-16 of the LVF wavelength-to-pixel mapping table for hardware revision 1.3. It must match after any calibration update.

## Appendix C: LVF Spacing Technical Note

The **14.77 mm element spacing** of the Valdyne LVF was selected as the optimal trade-off between spectral resolution (which improves with smaller spacing) and manufacturing yield (which drops sharply below ~12 mm due to coating uniformity constraints). The original design called for 12.5 mm spacing, but manufacturing trials in 2020 showed unacceptable yield below 14 mm, leading to the 14.77 mm specification adopted in revision 1.0 and retained in revision 1.3.[^2]

The 14.77 mm spacing results in an effective spectral sampling of approximately 0.29 nm per pixel column — slightly coarser than the 0.25 nm/pixel originally targeted, but within the 2 nm FWHM resolution specification.

[^1]: The 14.77 mm LVF element spacing is documented in Team Crestfield internal design record TC-DR-VAL-2020-07, dated 14 September 2020. This value is the as-built dimension measured on the first production unit (SYS-VAL-004-S01) and confirmed on subsequent units to within ±0.03 mm.

[^2]: Manufacturing yield data from Team Crestfield internal report TC-TEST-VAL-2020-11, dated 04 November 2020.

---

*Document version: 1.3 | Last revised: 22 August 2022 | Author: Eng. Vesper Quillan | Approved: Dr. Renna Holt (r.holt@vrc.org)*
