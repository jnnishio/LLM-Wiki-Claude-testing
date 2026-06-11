---
title: Atlas Platform Family — Variant Comparison
created: 2026-06-10
updated: 2026-06-10
type: comparison
tags: [platform, comparison, atmospheric, subsurface]
sources: [raw/documents/document_08.md, raw/documents/document_09.md, raw/documents/document_10.md, raw/documents/document_11.md]
confidence: high
---

# Atlas Platform Family — Variant Comparison

All Atlas variants designed by Dr. Fennis Albrecht (VRC Autonomous Systems Group). Share common avionics core (VRC-FC-500, Veltrix IMU-3) and firmware track (ATL-FW-v7.1.2). Maintained at [[halvern-testing-ground]] HLV-B02.

## Physical and Performance

| Parameter | Atlas | Atlas-X | Atlas-II | Atlas North |
|-----------|-------|---------|----------|-------------|
| System Code | SYS-ATL-001 | SYS-ATL-X002 | SYS-ATL-II003 | SYS-ATL-N004 |
| Medium | Aerial | Aerial | **Subsurface (tethered)** | Aerial |
| Wingspan | 2.4 m | 2.8 m | N/A | 2.8 m |
| Empty mass | 22.4 kg | 24.7 kg | 38.4 kg | 27.3 kg |
| Max payload | 7.6 kg | **9.1 kg** (Rev 4.x) | 18 kg | 6.7 kg |
| Cruise speed | 65 km/h | 70 km/h | 1.8 m/s (horiz) | 65 km/h |
| Endurance | 3.2 h | 2.8–3.5 h | Survey-limited by tether | 2.5–3.1 h |
| Max altitude | 4,500 m | **8,200 m** | **340 m depth** | 4,500 m |
| Cold hardened | No | No (min −30°C) | No | **Yes (−65°C)** |
| Wind tolerance | 12 m/s | 16 m/s | N/A | 16 m/s |

## Navigation

| Feature | Atlas | Atlas-X | Atlas-II | Atlas North |
|---------|-------|---------|----------|-------------|
| GNSS | Dual (GPS+GLONASS) | **Triple** (GPS+GLONASS+Galileo) | None (subsurface) | Triple (inherited from Atlas-X) |
| IMU | Veltrix IMU-3 | **Veltrix IMU-7** (fibre-optic) | Veltrix IMU-3 | Veltrix IMU-7 |
| GPS-denied nav | — | INS drift ±8.5 m/hr + TRN | USBL acoustic ±1.5 m | INS drift ±8.5 m/hr + TRN |
| Nav accuracy | ±2.5 m | ±1.2 m | ±1.5 m (USBL) | ±1.2 m |
| Autopilot | VRC-AP-500 | VRC-AP-700 | Same as baseline | VRC-AP-700 |

## Sensor Integration

| Platform | Primary Sensor | Notes |
|----------|--------------|-------|
| Atlas | [[kryon-7]] (VRC-MNT-ATL-03) | General survey |
| Atlas-X | [[kryon-7x]] (VRC-MNT-ATL-04) | Also supports Kryon-7 and Peltex-200 |
| Atlas-II | Custom sonar suite (VRC-MBS-200, VRC-SSS-100, VRC-SBP-50, CTD) | Subsurface mapping |
| Atlas North | [[kryon-7x]] + [[valdyne-spectral-array]] (VRC-MNT-ATL-N-06) | Combined 5.9 kg payload |

## Atlas-X Payload Limit History

> **Always use the current Rev 4.x limit of 9.1 kg.** Earlier limits are superseded.

| Revision | Max Payload | Period |
|----------|-------------|--------|
| Rev 1.x | 8.0 kg | Sep 2020 – Aug 2021 |
| Rev 2.x–3.x | 8.4 kg | Sep 2021 – Dec 2022 |
| **Rev 4.x (current)** | **9.1 kg** | Jan 2023 – present |

## Key Identifiers

| Variant | CRC check | Self-test string |
|---------|-----------|-----------------|
| Atlas-X | `A3F7C901` (firmware Rev 4.1) | `ATLX-SELFTEST-OK-v41` |
| Atlas North | — | `ATN-COLD-OK` |

## Primary Programs

| Platform | Primary Program | Secondary |
|----------|----------------|----------|
| Atlas | General survey | — |
| Atlas-X | [[project-nova]] Zone C, [[project-aether]] profiling | EXP-441 test vehicle |
| Atlas-II | [[project-triton]] | — |
| Atlas North | [[project-sable]] | — |

## Atlas-II Depth Rating Detail

- Rated depth: 340 m (certified VRC-QA-PRESS-2021-003, valid to Sep 2026)
- Emergency surge: 360 m (voids maintenance warranty)
- Pressure at rated depth: ~34.3 bar; hull rated to 48.0 bar (1.4× safety factor)
- Deepest operational deployment: 312 m (TRITON Dive 8, 04 Oct 2022)

## Atlas North Cold-Start Requirements (below −30°C)

1. Power battery heater ≥22 min before launch
2. Confirm battery ≥0°C on ground control station
3. Run avionics self-test: `ATN-COLD-OK` must appear in GCS log
4. Inspect propellers for ice; de-ice with VRC-ICE-PROC-01 if needed

## Related

[[atlas-platform-family]] | [[project-nova]] | [[project-triton]] | [[project-sable]] | [[project-aether]] | [[kryon-7]] | [[kryon-7x]] | [[halvern-testing-ground]] | [[exp-441]]
