---
title: Atlas Autonomous Platform Family
created: 2026-06-10
updated: 2026-06-10
type: entity
tags: [platform, atmospheric, subsurface]
sources: [raw/documents/document_08.md, raw/documents/document_09.md, raw/documents/document_10.md, raw/documents/document_11.md]
confidence: high
---

# Atlas Autonomous Platform Family

**System Identifier:** SYS-ATL-BASE  
**Platform Architect:** Dr. Fennis Albrecht, VRC Autonomous Systems Group  
**First flight:** 04 July 2019 (Atlas baseline, [[halvern-testing-ground]])  
**Common firmware track:** ATL-FW (current: v7.1.2, released 15 September 2023)  
**Common maintenance programme:** VRC-ATL-MAINT-2020-03

## Family Overview

Four variants sharing a common avionics core (VRC-FC-500 dual-redundant flight computer, Veltrix IMU-3, VRC-ATL-ICD-2019-01 telemetry protocol) and a common payload interface standard (VRC-PAYIF-2019-01). All variants maintained at [[halvern-testing-ground]] (primary) with Oswick Station holding a forward spares cache (Atlas and Atlas North only).

## Variant Comparison

| Feature | Atlas (Baseline) | Atlas-X | Atlas-II | Atlas North |
|---------|-----------------|---------|----------|-------------|
| System Code | SYS-ATL-001 | SYS-ATL-X002 | SYS-ATL-II003 | SYS-ATL-N004 |
| Medium | Aerial | Aerial | Subsurface (tethered) | Aerial |
| Max altitude / depth | 4,500 m | 8,200 m | 340 m depth | 4,500 m |
| Max payload | 7.6 kg | 9.1 kg (Rev 4.x) | 18 kg | 6.7 kg |
| Cold hardened | No | No | No | Yes (−65°C) |
| Wind tolerance | 12 m/s | 16 m/s | N/A | 16 m/s |
| Primary sensor | [[kryon-7]] | [[kryon-7x]] | Custom sonar | [[kryon-7x]] + [[valdyne-spectral-array]] |
| Primary program | General survey | [[project-nova]] Zone C, [[project-aether]] | [[project-triton]] | [[project-sable]] |
| Introduced | 2019 | Sep 2020 | Oct 2021 | Nov 2022 |

## Atlas-X Notable Details

- Payload limit has changed between revisions — **only Rev 4.x (Jan 2023+) limit of 9.1 kg is current**; earlier limits of 8.0 kg (Rev 1.x) and 8.4 kg (Rev 2.x–3.x) are superseded. ^[raw/documents/document_09.md]
- Tare mass of avionics sub-assembly: 3.871 kg (Rev 4.x production; earlier revisions: 3.644 kg)
- CRC-32 integrity code for Rev 4.1 firmware image: `A3F7C901` — must be verified before each deployment
- Navigation: Triple GNSS + Veltrix IMU-7 fibre-optic + terrain-relative navigation; INS-only drift ±8.5 m/hr
- Primary deployment: [[project-nova]] Zone C (2 units) and [[project-aether]] profiling (2 units)

## Atlas-II Notable Details

- Completely different chassis (pressure-rated torpedo body) despite sharing avionics
- Depth rating: 340 m (certified to Sep 2026; emergency surge to 360 m voids warranty)
- At 340 m depth: external pressure ~34.3 bar; hull rated to 48.0 bar (1.4× safety factor)
- Tether: 400 m standard, 600 m extended option, 3.2 kN breaking strength
- USBL acoustic positioning: ±1.5 m; no GNSS subsurface
- Deepest deployment: Dive 8 (04 Oct 2022, 312 m in Oswick Under-Ice Lake)

## Atlas North Notable Details

- Heated battery enclosure (maintains ≥0°C), heated avionics bay, hybrid carbon-aramid structure
- Minimum operating temperature: −65°C (tested Oct 2022 in ETC-2 at [[halvern-testing-ground]])
- Battery warm-up from −65°C: ~22 minutes
- Cold-start verification string: `ATN-COLD-OK`
- Payload reduced to 6.7 kg vs Atlas-X 9.1 kg due to ~2.6 kg thermal management mass penalty
- Field operations lead: Vex Horodynski (contact: v.horodynski@vrc.org)
- Lowest ambient temperature operated: −61°C (Halvern, 12 January 2023, [[project-sable]])

## Payload Interface Standard (VRC-PAYIF-2019-01)

Common across all variants (aerial versions). Provides:
- Mechanical: 4-point locking tray (max 200×180×80 mm)
- Electrical: 28 VDC (max 60 W), USB 3.0 data, RS-422 command
- Approved payloads include [[kryon-7]] (VRC-MNT-ATL-03), [[kryon-7x]] (VRC-MNT-ATL-04), [[peltex-200]] (VRC-MNT-ATL-05)

## Related

[[project-nova]] | [[project-aether]] | [[project-triton]] | [[project-sable]] | [[kryon-7]] | [[kryon-7x]] | [[halvern-testing-ground]] | [[comparisons/atlas-variants]]
