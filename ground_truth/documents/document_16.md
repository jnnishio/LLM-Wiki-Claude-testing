# Halvern Testing Ground: Facility Operations Manual

**Facility Code:** FAC-HLV-002  
**Facility Commander:** Lt. Cmd. Bellamy Vorsch (concurrent with Oswick Station command, since March 2023)  
**Manual Version:** 3.0  
**Date of Issue:** 10 January 2023

---

## 1. Facility Overview

Halvern Testing Ground is the Veltrix Research Consortium's primary inland test and operations facility, serving as the main base for platform development, sensor calibration, data processing, and operational support for multiple VRC research programs. It is also the home base for **Team Velanthor** (Document 07), which maintains the VRC Data Processing Centre (VDPC) at this facility.

Unlike **Oswick Station** (Document 03), which focuses on polar field research, Halvern is primarily an engineering and operational-support facility, though it conducts some direct field research activities including winter atmospheric measurements and UAV test flights.

## 2. Location and Access

| Parameter | Value |
|-----------|-------|
| Facility Code | FAC-HLV-002 |
| Latitude | 68°51'42.3" N |
| Longitude | 18°24'09.6" E |
| Elevation | 2,847 m AMSL |
| ICAO Designator | XHLV |
| Nearest Settlement | Halvdalen (22 km S) |

Access routes:

- **Primary:** Paved road from Halvdalen (Route VRC-HLV-ROAD-01), passable year-round with snow-clearing
- **Secondary:** Fixed-wing to XHLV airstrip (2,100 m paved)

The Halvern facility is accessible by standard vehicle year-round, in contrast to Oswick Station's seasonal access limitations.

## 3. Infrastructure

### 3.1 Buildings and Structures

| Structure ID | Type | Area (m²) | Year Built | Notes |
|-------------|------|-----------|-----------|-------|
| HLV-B01 | Main office and laboratory block | 1,840 | 2001 | Includes VDPC server room |
| HLV-B02 | Platform hangar | 2,200 | 2008 | Atlas family maintenance |
| HLV-B03 | Sensor calibration laboratory | 440 | 2012 | Clean room (ISO 7) |
| HLV-B04 | Accommodation block | 960 | 2001 | 40-bed capacity |
| HLV-B05 | Power plant | 220 | 2001 | Grid-connected + backup |
| HLV-ETC | Environmental test chamber | 180 | 2018 | ETC-1 and ETC-2 (to −80°C) |
| HLV-ICE | Under-ice access facility | 310 | 2019 | Glacier access, Atlas-II deployment |
| HLV-MAST-01 | Sensor mast (meteorological) | — | 2003 | 44 m, standard met instruments |
| HLV-MAST-02 | Sensor mast (research) | — | 2014 | 28 m, reconfigurable for experiments |

### 3.2 Test Flight Operations

Halvern operates a designated UAV test flight zone:

- **Corridor HLV-CORRIDOR-01:** 3 km × 0.8 km, oriented 045°/225°, centred 800 m NE of HLV-B02
- **Airspace ceiling:** 500 m AGL (coordinated with national airspace authority under VRC-AIRSPACE-2019)
- **Standard operating altitude:** 30–150 m AGL (most UAV experiments)
- **Maximum altitude ceiling for AETHER balloon ops:** 32,000 m (separate airspace agreement AETHER-NOTAM)

### 3.3 Environmental Test Chambers

Halvern operates two environmental test chambers (ETCs) in HLV-ETC:

| Chamber | Volume | Temperature Range | Humidity Control | Primary Use |
|---------|--------|------------------|-----------------|-------------|
| ETC-1 | 12 m³ | −40°C to +85°C | Yes | Electronics testing |
| ETC-2 | 4 m³ | −80°C to +60°C | No | Cold qualification |

ETC-2 was used for Atlas North cold-start qualification testing (Document 11, Appendix A) in August–October 2022.

## 4. Program Operations Hosted

| Program | Code | Lead Contact | Operations at Halvern |
|---------|------|--------------|----------------------|
| Project NOVA | VRC-ATM-2201 | Dr. Mara Fenwick | VDPC; Zone B sensor nodes |
| Project HELIOS | VRC-SOL-1887 | Dr. Osias Prewitt | Ground station PEL-200-0031 |
| Atlas platform maintenance | All variants | Dr. Fennis Albrecht | Hangar HLV-B02 |
| EXP-441 | EXP-441-2023 | Dr. Noel Hartbury | Test flight corridor |
| Project SABLE | VRC-OPT-5512 | Dr. Aldous Quirk | Winter flight operations |
| Team Velanthor (base) | TM-VEL-001 | Dr. Mara Fenwick | Primary office |
| Team Crestfield (sub-office) | TM-CRE-002 | Dr. Renna Holt | Calibration lab HLV-B03 |

## 5. Safety and Operational Protocols

### 5.1 UAV Flight Safety

All UAV operations in HLV-CORRIDOR-01 require:

- Pre-flight notification to HLV Airspace Control (radio channel 7 or ext. 6-CTRL)
- Active observer at HLV-OBS-01 (elevated position NW corner of corridor)
- Compliance with VRC UAV Operating Procedures VRC-UAV-OPS-2021

The Duskline Protocol (Document 20) applies to all UAV data quality assessments conducted from Halvern.

### 5.2 Cryosphere Operations

The Halvern ice facility (HLV-ICE) and under-ice operations comply with the **Clearwater Protocol v2.3** (Document 06). The sub-ice pressure threshold of **1.67 bar** (revised from 1.43 bar per Document 06) applies to all HLV-ICE sampling operations.

### 5.3 Emergency Contacts

- Facility Commander: Lt. Cmd. Bellamy Vorsch (ext. 5-300)
- VRC Emergency Operations Centre: ext. 7-700
- Local emergency services: Route via VRC EOC

---

## Appendix A: Key Dimensions and Reference Measurements

| Measurement | Value | Notes |
|------------|-------|-------|
| Facility elevation | 2,847 m AMSL | Used as altitude reference for all NOVA/HELIOS data from Halvern |
| HLV-MAST-02 height | 28 m | Research mast, EXP-441 reference array |
| HLV-MAST-01 height | 44 m | Met mast, continuous operation |
| Hangar HLV-B02 internal height | 12 m | Limits Atlas family storage to folded-wing configuration |
| ETC-2 minimum temperature | −80°C | Cold qualification limit |

## Appendix B: Maintenance and Calibration Schedule

| System | Responsible Party | Interval | Last Done |
|--------|-----------------|----------|-----------|
| HLV-B03 ISO 7 clean room certification | External | Annual | April 2023 |
| ETC-1 / ETC-2 temperature calibration | Team Crestfield | Annual | March 2023 |
| HLV-MAST-01/02 structural inspection | VRC Engineering | Biennial | June 2022 |
| Atlas-family scheduled maintenance (all units) | Dr. Fennis Albrecht | Per ATL-MAINT-2020-03 | Rolling |

---

*Document version: 3.0 | Last revised: 10 January 2023 | Approved by: Lt. Cmd. Bellamy Vorsch (b.vorsch@vrc.org)*
