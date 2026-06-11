# Project AETHER: High-Altitude Atmospheric Sampling Program

**Project Code:** VRC-ALT-4450  
**Principal Investigator:** Dr. Petra Olmstead  
**Program Start:** 01 April 2022  
**Status:** Active (Phase 1 — balloon platform operations)

---

## 1. Program Overview

Project AETHER (code: VRC-ALT-4450) is the Veltrix Research Consortium's high-altitude atmospheric sampling program, targeting the stratosphere and upper troposphere at altitudes from 12,000 m to a maximum of **32,000 m AMSL**. AETHER deploys instrument payloads on stratospheric balloon platforms and, for profile measurement below 8,200 m, on **Atlas-X** autonomous aircraft (Document 09).

AETHER operates as a companion program to **Project NOVA** (Document 01), which covers the lower troposphere. Together, NOVA and AETHER provide a vertically integrated atmospheric dataset from ground level to the stratosphere. AETHER also provides the upper-atmosphere context needed to validate **Project HELIOS** (Document 04) solar irradiance retrievals.

## 2. Program Details

| Field | Value |
|-------|-------|
| Project Code | VRC-ALT-4450 |
| Principal Investigator | Dr. Petra Olmstead |
| Deputy PI | Dr. Mara Fenwick (Team Velanthor) |
| Operations Base | Halvern Testing Ground (FAC-HLV-002) |
| Program Start | 01 April 2022 |
| Phase 1 End (planned) | 31 March 2025 |
| Maximum altitude | 32,000 m AMSL |
| Funding | Category III (multi-program) |
| Budget allocation | 8.7M VRC-credits |

## 3. Scientific Objectives

AETHER targets four science questions:

1. **Stratospheric aerosol inventory:** Quantify loading and particle size distribution of sulfate and organic aerosols in the 18–30 km altitude band
2. **Ozone column variability:** Measure ozone mixing ratio profiles to characterise seasonal and inter-annual variability in the lower stratosphere
3. **Gravity wave characterisation:** Detect atmospheric gravity wave signatures in temperature and wind profiles from 12 to 30 km altitude
4. **Upper-atmosphere irradiance:** Measure solar spectral irradiance above the tropospheric aerosol layer for HELIOS cross-validation

## 4. Platform Architecture

AETHER uses two platform types:

### 4.1 Stratospheric Balloon (primary, >8,200 m)

AETHER deploys zero-pressure polyethylene stratospheric balloons (supplied under VRC procurement contract VRC-PROC-AETHER-2021) with payload gondolas of up to 45 kg. Each balloon flight is a single-use ascent mission; the gondola descends by parachute following balloon burst.

Flight profile:
- Ascent rate: approximately 5 m/s
- Float altitude: programme-dependent, typically 20,000–28,000 m
- Float duration: 4–12 hours depending on altitude and payload
- Horizontal drift: typically 50–300 km depending on stratospheric winds

### 4.2 Atlas-X Aircraft (lower-stratosphere profiling, <8,200 m)

For the altitude range covered by the Atlas-X (up to 8,200 m AMSL per Document 09), AETHER uses Atlas-X units operated by Team Velanthor. Two Atlas-X units are dedicated to AETHER (as noted in Document 07, Team Velanthor equipment table). These fly profile ascent/descent patterns to characterise the troposphere–stratosphere transition.

## 5. Instrumentation

### 5.1 Balloon Gondola Payload

The standard AETHER balloon gondola carries:

| Instrument | Model / Code | Measurement | Mass |
|-----------|-------------|-------------|------|
| Aerosol counter | VRC-APS-04 | Particle size distribution | 4.2 kg |
| UV/Vis spectrometer | Valdyne VSA-Mini | O₃, NO₂, aerosol | 3.1 kg |
| Frost-point hygrometer | VRC-FPH-02 | Water vapour | 2.8 kg |
| Radiosonde | Halvdyne RS-50 | T, P, RH, GPS | 0.9 kg |
| Solar irradiance sensors | Kryon-7 (Band 1–3) | Spectral irradiance | 2.14 kg |
| Data logger | VRC-DL-STRAT-01 | — | 1.2 kg |
| **Total standard gondola** | | | **14.3 kg** |

The Kryon-7 (Document 02) is used on the balloon gondola in a reduced configuration (Bands 1–3 only; Band 4 thermopile is not flown above 20 km due to thermal equilibration constraints). Full Kryon-7 specifications apply to the unit itself; see Document 02.

### 5.2 Atlas-X Payload (AETHER configuration)

When used for AETHER lower-atmosphere profiling, Atlas-X aircraft carry:

| Instrument | Model/Code | Measurement |
|-----------|-----------|-------------|
| Kryon-7X | SYS-KRY7X-002 | Multi-spectral atmospheric | 
| Valdyne VSA compact | VRC-VAL-CMT | Ozone column |
| GPS radiosonde module | Halvdyne RS-50-A | T, P, position |

See Document 18 for Kryon-7X full specifications.

## 6. Operations

### 6.1 Launch Site

All balloon launches are conducted from the Halvern Testing Ground designated launch pad (HLV-LAUNCH-01), located 400 m NE of HLV-B02 hangar. AETHER balloon operations have an extended airspace agreement (AETHER-NOTAM) covering altitudes up to 32,000 m AMSL.

### 6.2 Flight Rate

The Phase 1 target flight rate is:
- Balloon flights: 8–12 per year (seasonal; primary window April–October)
- Atlas-X AETHER profiles: 30–50 per year (year-round, subject to weather)

### 6.3 Gondola Recovery

Recovery teams use VRC-TRACK-AETHER GPS tracking beacons embedded in each gondola. Recovery radius is typically 30–250 km from the launch site; recovery teams are based at Halvern.

## 7. Personnel

| Name | Role |
|------|------|
| Dr. Petra Olmstead | Principal Investigator |
| Dr. Mara Fenwick | Deputy PI / Team Velanthor liaison |
| Technician Brix Halvorsen | Balloon operations |
| Technician Ove Sandvik | Atlas-X profiling ops (when at Halvern) |
| Dr. Renna Holt | Instrument technical authority (Kryon-7/7X) |

---

## Appendix A: Balloon Flight Log (Phase 1 partial)

| Flight ID | Date | Max Altitude | Float Duration | Gondola Recovery | Notes |
|-----------|------|-------------|---------------|-----------------|-------|
| AETHER-B-001 | 15 May 2022 | 24,100 m | 6.2 h | Yes (88 km S of Halvern) | First operational flight |
| AETHER-B-005 | 12 August 2022 | 27,800 m | 3.4 h | Yes (143 km W) | New altitude record for program |
| AETHER-B-011 | 04 May 2023 | 31,650 m | 2.1 h | Yes (211 km NW) | Closest approach to 32 km ceiling |

## Appendix B: Relationship with NOVA and HELIOS

AETHER, NOVA, and HELIOS form a vertically integrated observing system:

- **NOVA** (Doc 01): surface to ~28 km using Kryon-7 sensor nodes (fixed and Atlas-X mobile)
- **AETHER** (this document): 12 km to 32 km using balloon gondolas and Atlas-X profiles
- **HELIOS** (Doc 04): surface reference irradiance using Peltex-200

The three programs share a common data format (VBIF v2) and submit merged datasets to the VRC Integrated Atmosphere Archive (VIAA, archive code VRC-VIAA-001) on a quarterly basis.[^1]

[^1]: The 32,000 m AETHER altitude ceiling is governed by both platform capability (maximum balloon altitude before burst probability >50%) and airspace authorisation limits under AETHER-NOTAM. Several AETHER balloon flights have approached this ceiling; the programme record is 31,650 m (Flight AETHER-B-011, 04 May 2023).

---

*Document version: 1.3 | Last revised: 20 July 2023 | Maintained by: Dr. Petra Olmstead (p.olmstead@vrc.org)*
