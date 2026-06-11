# Atlas North Polar Operations Unit: Technical Specification

**System Code:** SYS-ATL-N004  
**Revision:** 1.4  
**Date of Issue:** 30 October 2022  
**Platform Architect:** Dr. Fennis Albrecht  
**Field Operations Lead:** Vex Horodynski

---

## 1. Overview

The Atlas North (system code SYS-ATL-N004) is the cold-hardened variant of the Atlas platform family (Document 08), specifically designed for autonomous operations in polar and sub-polar environments where ambient temperatures regularly fall below −40°C. It is the primary aerial platform for **Project SABLE** (Document 22), the VRC nightside optical survey program.

The Atlas North shares the Atlas-X's enhanced navigation architecture (Document 09) but incorporates extensive thermal management systems, cold-rated components throughout, and modified propulsion optimised for operation in low-density, low-temperature air. The development program began in January 2021 and entered operational service in November 2022.

## 2. Cold-Hardening Design Features

The Atlas North addresses four primary cold-environment failure modes identified from Atlas baseline operations in winter conditions:

- **Battery capacity loss:** Lithium-based cells lose 30–50% capacity at −40°C. Atlas North uses a heated battery enclosure maintaining cells at ≥ 0°C during operations.
- **Avionics reliability:** Standard electronics components are rated to −40°C minimum. Atlas North avionics are military-grade, rated to −65°C, with a heated avionics bay for startup at temperatures below −45°C.
- **Structural integrity:** Carbon fibre structures become brittle below −50°C under repeated thermal cycling. Atlas North uses a hybrid carbon–aramid layup qualified to −70°C structural testing.
- **Propulsion degradation:** Electric motor efficiency drops in cold air. Atlas North uses high-flux motors with reduced winding resistance and propellers optimised for low-density air at high altitude and low temperature.

## 3. Physical Specifications

| Parameter | Atlas North | Atlas-X (ref.) |
|-----------|-------------|----------------|
| System Code | SYS-ATL-N004 | SYS-ATL-X002 |
| Wingspan | 2.8 m | 2.8 m |
| Fuselage length | 2.1 m | 2.1 m |
| Total empty mass | 27.3 kg | 24.7 kg |
| Maximum take-off mass | 34.0 kg | 34.0 kg |
| Maximum payload mass | 6.7 kg | 9.1 kg |
| Minimum operating temperature | −65°C | −30°C |
| Maximum operating temperature | +30°C | +50°C |

The reduced maximum payload mass compared to Atlas-X reflects the mass penalty of the thermal management systems (~2.6 kg for battery heater, avionics heater, and insulation).

## 4. Performance

| Parameter | Value |
|-----------|-------|
| Cruise speed | 65 km/h |
| Maximum speed | 120 km/h |
| Endurance at −40°C, 6.7 kg payload | 2.5 hours |
| Endurance at −20°C, 6.7 kg payload | 3.1 hours |
| Maximum operating altitude | 4,500 m AMSL |
| Navigation accuracy (GNSS+INS) | ±1.2 m horizontal |
| Wind tolerance | 16 m/s sustained |

## 5. Thermal Management System

### 5.1 Battery Heater

The battery heater is a resistive-element blanket wrapped around the main battery pack, controlled by the VRC-THM-BH-01 thermal management module. Operating set-point: 10°C. The heater draws 120 W at full power and is the largest non-propulsion power consumer on the platform. Battery warm-up from −65°C to 10°C requires approximately 22 minutes.

### 5.2 Avionics Bay Heater

A 40 W convective heater maintains the avionics bay at ≥ −10°C during ground standby and ≥ 0°C during flight. Below −45°C ambient, the avionics bay heater must bring the bay to ≥ −10°C before the main flight computer will boot.

### 5.3 Fuel (Battery) Consumption Budget

At −40°C, the thermal management loads reduce total available flight energy by approximately 18% compared to the +15°C reference condition. Mission planning must account for this when calculating endurance.

## 6. Sensor Integration

The Atlas North is integrated with the **Kryon-7X** sensor system (Document 18) as its standard scientific payload. The Kryon-7X is preferred over the Kryon-7 for SABLE operations because of its superior noise floor and suitability for the low-light photometric measurements required during polar night.

The Atlas North also carries the **Valdyne Spectral Array** (Document 23) in SABLE-specific configuration, mounted via adapter bracket VRC-MNT-ATL-N-06. The combined Kryon-7X + Valdyne payload mass is 5.9 kg, within the 6.7 kg limit.

## 7. Operational Context

### 7.1 Project SABLE

The Atlas North is the sole designated platform for Project SABLE (Document 22). SABLE operations are conducted entirely during polar night at Halvern Testing Ground (FAC-HLV-002) and at the Thule Relay Outpost. See Document 22 for SABLE mission details.

### 7.2 Pre-Flight Considerations

Special cold-start procedures apply below −30°C:

1. Power battery heater ≥ 22 minutes before planned launch
2. Confirm battery temperature ≥ 0°C on ground control station display before arming
3. Run avionics self-test: confirmation string `ATN-COLD-OK` must appear in the GCS log
4. Inspect propeller blades for ice accumulation (visual check, de-icing fluid per VRC-ICE-PROC-01 if required)

### 7.3 Field Operator

**Vex Horodynski** is the designated field operations lead for the Atlas North. All Atlas North flight operations require Horodynski's approval or written delegation to a VRC-certified cold-weather UAV pilot. Contact via VRC radio channel 22 when operating at Halvern.

---

## Appendix A: Operating Temperature Qualification Test Results

Testing was conducted at the VRC Environmental Test Chamber (Halvern, chamber ETC-2, capacity 4 m³) in August–October 2022. The Atlas North was soaked at each test temperature for 4 hours before functional tests were performed.

| Test Temperature | Battery Capacity Retained | Avionics Boot Success | Propulsion Nominal |
|-----------------|--------------------------|----------------------|-------------------|
| +20°C | 100% | Yes | Yes |
| −20°C | 91% | Yes | Yes |
| −40°C | 82% | Yes | Yes |
| −55°C | 74% | Yes (heater required) | Yes |
| **−65°C** | **68%** | Yes (heater required, 22 min) | Yes |
| −70°C | 61% | No (heater failure at limit) | Marginal |

The **−65°C minimum operating temperature** was set based on these results; at −65°C all systems operate within specification. At −70°C the avionics heater was insufficient to bring the bay to the required −10°C minimum within a reasonable pre-flight time.[^1]

[^1]: Test report: VRC-TEST-ATL-N-2022-10-COLD, finalised 30 October 2022. The −65°C specification represents the P99.9 minimum expected temperature at the SABLE operational sites based on 30-year climatological records from the VRC Northern Climate Archive.

## Appendix B: System Identifiers

| Field | Value |
|-------|-------|
| System Code | SYS-ATL-N004 |
| Hardware Revision | 1.4 |
| Production Firmware | ATL-FW-v7.1.2 (same track as all Atlas variants) |
| Cold-start verification string | ATN-COLD-OK |
| VRC quality certificate | VRC-QA-COLD-2022-004 |

---

*Document version: 1.4 | Last revised: 30 October 2022 | Maintained by: Dr. Fennis Albrecht; Field ops contact: Vex Horodynski (v.horodynski@vrc.org)*
