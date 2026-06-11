# Wiki Schema

## Domain
The Veltrix Research Consortium (VRC) — a polar and atmospheric research organisation operating high-latitude field stations, sensor networks, autonomous platforms, and long-duration scientific programs. Covers projects, instrumentation, protocols, facilities, teams, and personnel.

## Conventions
- File names: lowercase, hyphens, no spaces (e.g., `project-nova.md`)
- Every wiki page starts with YAML frontmatter (see below)
- Use `[[wikilinks]]` to link between pages (minimum 2 outbound links per page)
- When updating a page, always bump the `updated` date
- Every new page must be added to `index.md` under the correct section
- Every action must be appended to `log.md`
- **Provenance markers:** On pages synthesising 3+ sources, append `^[raw/documents/document_NN.md]` at the end of paragraphs whose claims come from a specific source.
- **Superseded documents:** Note explicitly when a document, spec, or value has been superseded. Flag the current version clearly.

## Frontmatter
```yaml
---
title: Page Title
created: YYYY-MM-DD
updated: YYYY-MM-DD
type: entity | concept | comparison | query | summary
tags: [from taxonomy below]
sources: [raw/documents/document_NN.md]
confidence: high | medium | low
contested: true                        # optional; set when the page has unresolved contradictions
contradictions: [other-page-slug]      # optional; pages this one conflicts with
---
```

### raw/ Frontmatter
```yaml
---
source_url:           # blank for local documents; URL if web-sourced
ingested: YYYY-MM-DD
sha256: <hex digest of body content>
---
```

## Tag Taxonomy

### Programs & Experiments
- `project` — active or completed research projects (NOVA, HELIOS, etc.)
- `experiment` — bounded experiments (EXP-119, EXP-441)
- `atmospheric` — atmospheric measurement programs
- `subsurface` — under-ice/underwater programs
- `optical` — optical/photometric programs
- `solar` — solar irradiance programs
- `fusion` — multi-sensor integration programs

### Instruments & Platforms
- `sensor` — measurement instruments (Kryon-7, Peltex-200, Valdyne)
- `platform` — autonomous vehicle or balloon platforms (Atlas family)
- `calibration` — calibration procedures, errors, corrections
- `superseded` — documents/specs replaced by newer versions

### Organisation
- `team` — VRC research teams (Velanthor, Crestfield)
- `facility` — field stations and labs (Oswick, Halvern)
- `person` — individual researchers and personnel
- `protocol` — standard operating procedures

### Science
- `aerosol` — aerosol/particulate measurement
- `irradiance` — solar and atmospheric irradiance
- `bathymetry` — under-ice/seafloor mapping
- `cryosphere` — ice-related science and safety
- `anomaly` — data quality and anomaly management

### Status
- `active` — currently operational
- `completed` — finished programs/experiments
- `integration` — in integration/commissioning phase

## Page Thresholds
- **Create a page** when an entity/concept appears in 2+ sources OR is central to one source
- **Add to existing page** when a source mentions something already covered
- **DON'T create a page** for passing mentions or minor details
- **Split a page** when it exceeds ~200 lines

## Entity Pages
One page per notable entity. Include overview, key facts, relationships ([[wikilinks]]), sources.

## Concept Pages
One page per concept/topic. Include definition, current state, open questions, related concepts ([[wikilinks]]).

## Comparison Pages
Side-by-side analyses with table format and verdict/synthesis.

## Update Policy
When new information conflicts with existing content:
1. Check dates — newer sources generally supersede older ones
2. If genuinely contradictory, note both positions with dates and sources
3. Mark in frontmatter: `contradictions: [page-name]`
4. Flag for user review in lint report
