# Atlas-II Subsurface Survey Variant: Technical Specification

**System Code:** SYS-ATL-II003  
**Revision:** 2.3  
**Date of Issue:** 14 July 2022  
**Platform Architect:** Dr. Fennis Albrecht  
**Issuing Group:** VRC Autonomous Systems Group

---

## 1. Overview

The Atlas-II (system code SYS-ATL-II003) is a tethered subsurface survey vehicle sharing the Atlas platform's avionics architecture but built around a completely different chassis designed for under-ice and deep-water deployment. Unlike the aerial variants (Atlas baseline, Atlas-X, Atlas North), the Atlas-II operates below the surface, making it physically and operationally distinct despite sharing the common control and communication software stack.

The Atlas-II is the designated platform for **Project TRITON** (Document 12) and was developed in parallel with Project TRITON's requirements definition phase (2019–2020).

## 2. Physical Specifications

| Parameter | Value |
|-----------|-------|
| System Code | SYS-ATL-II003 |
| Chassis type | Pressure-rated torpedo body |
| Length | 1.4 m |
| Diameter | 280 mm |
| Dry mass | 38.4 kg |
| Buoyancy (in freshwater) | Slightly positive (+0.4 kg) |
| Depth rating | 340 m |
| Tether length | 400 m (standard), 600 m (extended option) |
| Tether diameter | 14 mm |
| Tether breaking strength | 3.2 kN |

The 340 m depth rating represents the maximum operating depth for continuous operations. Emergency surge capacity to 360 m exists but voids the maintenance warranty. Pressure testing was conducted at 408 m (1.2× rated depth) in factory acceptance testing.

## 3. Propulsion and Manoeuvring

The Atlas-II uses a four-thruster arrangement:

- 2× horizontal thrusters (forward/aft)
- 2× vertical thrusters (depth control)

Thruster type: Veltrix BTH-40 brushless direct-drive, rated to 340 m depth. Maximum horizontal speed: 1.8 m/s. Maximum vertical speed: 0.6 m/s (ascending), 0.8 m/s (descending).

## 4. Avionics and Control

The Atlas-II shares the common Atlas avionics core (VRC-FC-500, dual redundant; Veltrix IMU-3) with the aerial variants, but navigation is augmented by:

- **Acoustic positioning:** Ultra-short baseline (USBL) acoustic modem (VRC-USBL-01)
- **Depth sensor:** Paroscientific-class quartz resonator, accuracy ±0.1% full scale
- **Altitude sensor (bottom-following):** 675 kHz acoustic altimeter

GNSS is unavailable during subsurface operations; the USBL system provides positioning relative to a surface reference transducer deployed from the vessel or ice station.

## 5. Payload and Sensor Suite

### 5.1 Standard Payload

The Atlas-II standard survey payload consists of:

| Instrument | Model | Purpose |
|-----------|-------|---------|
| Multi-beam sonar | VRC-MBS-200 | Bathymetric mapping |
| Side-scan sonar | VRC-SSS-100 | Seabed texture |
| Sub-bottom profiler | VRC-SBP-50 | Sediment stratigraphy |
| CTD | Halvdyne CTD-Pro | Water column profiling |
| Turbidity sensor | VRC-TURB-01 | Suspended particle load |

### 5.2 Payload Interface

The Atlas-II uses the same **VRC-PAYIF-2019-01** payload interface standard as the aerial variants (electrical and data), but with a waterproof connector set (IP68 SubConn equivalent). Payload mass limit: **18 kg** (within the 38.4 kg total dry mass, with the standard payload weighing ~12 kg).

## 6. Communications

The Atlas-II communicates with the surface via the tether:

- **Control link:** 100 Mbit/s Ethernet over tether
- **Video:** H.264 over Ethernet, two channels
- **Power:** 48 VDC from surface power supply (1.2 kW max)

An acoustic telemetry link (1,200 baud) is available as a redundant command path in case of tether damage.

## 7. Deployment Procedure

### 7.1 Surface Vessel / Ice Station Requirements

The Atlas-II can be deployed from:
- Research vessel with A-frame or crane (min 500 kg SWL)
- Ice station access hole (minimum 500 mm × 500 mm, standard format IAH-500)
- Halvern Testing Ground ice facility (purpose-built deployment pool, doc. reference FAC-HLV-002-ICE)

### 7.2 Pre-Dive Checklist

Prior to every dive, the following must be verified:

- [ ] Tether integrity inspection (visual and electrical)
- [ ] Pressure sphere seals inspected (O-ring condition log: ATL-II-ORING-LOG)
- [ ] All payload instruments self-tested and confirmed operational
- [ ] USBL transducer deployed and tracking confirmed
- [ ] Dive supervisor designated and logged (VRC-DIVE-LOG-01)
- [ ] Emergency recovery procedure briefed

## 8. Operational History

The Atlas-II entered service in October 2021 following completion of factory acceptance testing. The first operational deployment was under Project TRITON in March 2022.

| Deployment | Date | Location | Depth Achieved | Notes |
|-----------|------|----------|---------------|-------|
| Factory acceptance | Aug–Sep 2021 | VRC Test Pool, Halvern | 80 m (pool limit) | All systems nominal |
| TRITON Dive 1 | 12 March 2022 | Oswick Under-Ice Site | 187 m | Science operations |
| TRITON Dive 8 | 04 October 2022 | Oswick Under-Ice Site | 312 m | New depth record |
| TRITON Dive 14 | 22 February 2023 | Halvern Ice Facility | 194 m | Instrument calibration dive |

---

## Appendix A: Depth Rating Certification

The Atlas-II depth rating of **340 m** was certified by VRC Quality Assurance under certificate VRC-QA-PRESS-2021-003, issued 22 September 2021. Certification is valid for 5 years (to September 2026) subject to annual pressure sphere seal inspections.

At the rated depth of 340 m, the external pressure on the main hull is approximately 34.3 bar. The pressure hull is rated to 48.0 bar (1.4× factor of safety), established during hydrostatic proof testing.

## Appendix B: Compatibility with TRITON Mission Profile

Project TRITON (Document 12) requires the Atlas-II to achieve a nominal survey depth of **280 m** at the primary survey site and a maximum exploratory depth of **340 m** at the secondary site. These requirements drove the 340 m rated depth specification. See Document 12 for the full TRITON mission profile and survey plan.

---

*Document version: 2.3 | Last revised: 14 July 2022 | Maintained by: Dr. Fennis Albrecht (f.albrecht@vrc.org)*
