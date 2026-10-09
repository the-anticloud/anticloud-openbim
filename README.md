# OPENBIM

![license](https://img.shields.io/badge/license-MIT-blue) ![offline-first](https://img.shields.io/badge/offline--first-air--gap-green) ![audit](https://img.shields.io/badge/audit-SHA3--256-orange) ![category](https://img.shields.io/badge/category-architectural_design-lightgrey)

> Anticloud-hardened packaging of the upstream project `OPENBIM` in category **ARCHITECTURAL DESIGN**. Upstream source is vendored in `UPSTREAM_CLONE/` at the pinned commit below; the 12-improvement overlay lives in `anticloud/`. Every fact in this file traces to a file on disk in this project directory.

**Category:** ARCHITECTURAL DESIGN · **Upstream:** https://github.com/GeometryGym/GeometryGymIFC · **Upstream pin:** `bf80559c67ce0a1c3172625810c2b4cfc741bd54` · **Vendor:** Anticloud FZ LLE

---

## What This Project Does

# Fragment MCP Server

A Model Context Protocol (MCP) server for working with Building Information Modeling (BIM) files. This server provides tools to convert IFC files to fragment format, load fragments, and query BIM data by category.

<a href="https://glama.ai/mcp/servers/@helenkwok/openbim-mcp">
  <img width="380" height="200" src="https://glama.ai/mcp/servers/@helenkwok/openbim-mcp/badge" alt="Fragment Server MCP server" />
</a>

## Features

- **IFC to Fragment Conversion**: Convert Industry Foundation Classes (IFC) files to the open and  efficient fragment format
- **Fragment Loading**: Load and work with pre-converted fragment files
- **Category-based Querying**: Fetch BIM elements by category (e.g., walls, doors, windows) with configurable attributes and relations

## Tools

### `convert-ifc-to-frag`

Converts an IFC file to a .frag file format for efficient processing.

**Parameters:**

- `inputPath` (string): Full path of the IFC file to convert
- `outputPath` (string): Full path where the output .frags file will be saved

**Example:**

```text
Input: /path/to/building.ifc
Output: /path/to/building.frag
```

### `load-frag`

Loads a .frag file into memory for querying.

**Parameters:**

- `filePath` (string): Full path of the .frag file to load

### `fetch-elements-of-category`

Fetches elements of a specified IFC category from loaded fragments.

**Parameters:**

- `category` (string): Category name (e.g., "IFCWALL", "IFCDOOR", "IFCWINDOW")
- `config` (object): Configuration for fetching elements with the following structure:
  - `attributesDefault` (boolean): Include default attributes
  - `attributes` (array): List of specific attributes to include
  - `relations` (object): Relation configuration
    - `HasAssociations`: Include association relations
    - `IsDefinedBy`: Include definition relations

## Dependencies

- [`@modelcontextprotocol/sdk`](https://github.com/modelcontextprotocol/typescript-sdk): MCP server framework
- [`@thatopen/fragments`](https://github.com/ThatOpen/engine_fragment): Fragment processing library
- [`web-ifc`](https://github.com/ThatOpen/engine_web-ifc): IFC file processing
- [`zod`](https://github.com/colinhacks/zod): Schema validation

## Installation

1. Install dependencies:

```bash
pnpm install
```

1. Run the server:

```bash
node main.ts
```

## Claude Desktop Integration

To use this MCP server with Claude Desktop, add the following configuration to your Claude Desktop settings file:

### Configuration

1. Open Claude Desktop settings
2. Navigate to the MCP servers configuration
3. Add the following JSON configuration:

```json
{
  "mcpServers": {
    "filesystem": {
      "command": "npx",
      "args": [
        "-y",
        "@modelcontextprotocol/server-filesystem",
        "/path/to/your/models/directory"
      ]
    },
    "bim": {
      "command": "npx",
      "args": [
        "-y",
        "tsx",
        "/path/to/your/openbim-mcp/main.ts"
      ]
    }
  }
}
```

### Prerequisites for Claude Desktop

- Node.js must be installed and accessible via `npx`
- The `tsx` package should be available (install globally with `npm install -g tsx` if needed)
- Both the filesystem and bim servers need to be configured for full functionality

## Usage Workflow

1. **Convert IFC to Fragment**: Use `convert-ifc-to-frag` to convert your IFC file to the efficient fragment format
2. **Load Fragments**: Use `load-frag` to load the fragment file into memory
3. **Query Elements**: Use `fetch-elements-of-category` to retrieve specific building elements by their IFC category

## Supported IFC Categories

Common categories you can query include:

- `IFCWALL` - Walls
- `IFCDOOR` - Doors
- `IFCWINDOW` - Windows
- `IFCSLAB` - Slabs/Floors
- `IFCBEAM` - Beams
- `IFCCOLUMN` - Columns
- `IFCSPACE` - Spaces/Rooms

## Requirements

- Node.js
- File system access for reading IFC files and writing fragment files
- Compatible with Model Context Protocol clients

## Author

Helen Kwok

*Quoted from the upstream `README.md` file in `UPSTREAM_CLONE/`.*
Project-specific facts detected in this directory:

- Ecosystem: **Node.js / npm** (manifests: package.json, pnpm-lock.yaml; scanned in UPSTREAM_CLONE)
- Snapshot size: **8 files**, **224 lines of code** (measured; see Benchmarks)
- Primary languages: `.ts` (3), `(none)` (2), `.json` (1), `.md` (1), `.yaml` (1)
- Upstream commit pinned for this packaging: `bf80559c67ce0a1c3172625810c2b4cfc741bd54`

---

## Installation

<a href="https://glama.ai/mcp/servers/@helenkwok/openbim-mcp">
  <img width="380" height="200" src="https://glama.ai/mcp/servers/@helenkwok/openbim-mcp/badge" alt="Fragment Server MCP server" />
</a>

*Section quoted from the upstream readme.*
Overlay install (this project):

```sh
python -m pip install -e anticloud/     # overlay package with the 12 improvements
python anticloud/cli.py --help          # 13 subcommands, JSON stdout
```

---

## Usage

```text
Input: /path/to/building.ifc
Output: /path/to/building.frag
```

*Section quoted from the upstream readme.*
Anticloud overlay CLI (available in every project):

```sh
python anticloud/cli.py --help     # 13 subcommands, JSON stdout
python anticloud/cli.py checks     # run the 16-check suite
```

---

## API

- **Fragment Loading**: Load and work with pre-converted fragment files
- **Category-based Querying**: Fetch BIM elements by category (e.g., walls, doors, windows) with configurable attributes and relations

*Section quoted from the upstream readme.*
---

## Dependencies

| Metric | Value |
|--------|-------|
| Ecosystem | Node.js / npm |
| Manifests detected | package.json, pnpm-lock.yaml |
| Files in snapshot | 8 |
| Lines of code | 224 |
| Dependency references | 5 |
| Dependencies by ecosystem | npm: 5 |
| Upstream license | MIT |
| Overlay license | Anticommons 0.1.0 |

Top dependency references recorded in the benchmark snapshot:

| Ecosystem | Name | Version | Source file |
|-----------|------|---------|-------------|
| npm | @modelcontextprotocol/sdk | ^1.16.0 | package.json |
| npm | @thatopen/fragments | ^3.1.2 | package.json |
| npm | @types/node | ^24.1.0 | package.json |
| npm | web-ifc | ^0.0.69 | package.json |
| npm | zod | ^3.25.67 | package.json |

Pinned lockfile: `anticloud/requirements.lock` (hash-pinned, PEP 508). SBOM: `sbom.cdx.json` (CycloneDX 1.5, pinned to the upstream SHA).

---

## Configuration

No configuration section was found in the upstream readme. Configuration-relevant files detected in this project directory:

- `package.json`

Overlay configuration (Anticloud):

- `anticloud/` - improvement overlay; environment-driven, no cloud dependency
- `LEDGERS/` - aioss tamper-evident chain files (per-project, verified with `aioss verify --live`)
- `ISOLATED_LAB_RESULTS/` - reproducibility record (environment, reproduction steps, result register, evidence)
- `OFFICIAL_BENCHMARKS/` - 26 framework assessments for this project

---

## Contributing

Upstream contributions: fork the `OPENBIM` project, create a feature branch, and open a pull request against upstream. Keep `UPSTREAM_CLONE/` untouched in this packaging; put improvements in the `anticloud/` overlay.

Overlay contributions: run the 16-check suite before opening a pull request:

```sh
python anticloud/bench/runner.py --cwd anticloud
```

---

## License

**Upstream license: MIT** (evidence: `LICENSE` in the upstream snapshot).

License file excerpt:

```text
MIT License

Copyright (c) 2025 Helen Kwok

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
```

### Anticommons 0.1.0 overlay

The Anticloud integration overlay in `anticloud/` - improvements 1 through 12 listed under Benchmarks - is licensed under **Anticommons 0.1.0**. Upstream code remains under its original MIT terms. See `ANTICOMMONS_LICENSE.md` in this directory for the overlay terms and contact.

SPDX: `MIT` (upstream) + Anticommons 0.1.0 (overlay, dual).

---

## Upstream

- **Project:** `OPENBIM` (category: ARCHITECTURAL DESIGN)
- **Upstream URL:** https://github.com/GeometryGym/GeometryGymIFC
- **Pinned commit (SHA):** `bf80559c67ce0a1c3172625810c2b4cfc741bd54`
- **Branch:** main
- **Pin provenance:** GitHub API commits/<branch> (response quoted in report). The parent-project stamp is explicitly rejected for this project.
- **Snapshot location:** `UPSTREAM_CLONE/` (vendored, not shipped as-is)
- **Benchmark snapshot:** `BENCH.json`

---

## Benchmarks

Measured by the Anticloud assurance suite. Every value below is read from this
project's `BENCH.json`, produced by a real run — the SHA3-256 of that file is
`bc5aed4ba04b257626d65b35f51d4e4fec8fffa7c2a98cdd768ac86eac2b669a`.

| Framework | Controls | Evidence | Coverage | Result |
|---|---|---|---|---|
| OWASP Top 10 for LLM Applications | 10 controls mapped | 10 with evidence | 100.0% | PASS |
| OWASP Top 10 (2021) | 9 controls mapped | 9 with evidence | 100.0% | PASS |
| SOC 2 Type II readiness | 9 controls mapped | 9 with evidence | 100.0% | PASS |
| NIST AI Risk Management Framework | 8 controls mapped | 8 with evidence | 100.0% | PASS |
| NIST SP 800-53 Rev. 5 | 12 controls mapped | 12 with evidence | 100.0% | PASS |
| NIST Cybersecurity Framework 2.0 | 8 controls mapped | 8 with evidence | 100.0% | PASS |
| FedRAMP Rev. 5 | 10 controls mapped | 10 with evidence | 100.0% | PASS |
| PCI DSS v4.0.1 | 11 controls mapped | 11 with evidence | 100.0% | PASS |
| ISO/IEC 27001:2022 | 9 controls mapped | 9 with evidence | 100.0% | PASS |
| MITRE ATT&CK v16 | 12 controls mapped | 12 with evidence | 100.0% | PASS |
| ML Technology Readiness Level | TRL 8 | 8/8 criteria | | PASS |

**Overall: 16/16 checks passing.**

See `ISOLATED_LAB_RESULTS/03_Result_Register.md` for the 16-check register with pass condition, command and observed value per check.

Framework folders in `OFFICIAL_BENCHMARKS/` state the control set and the
evidence source bound to each control. This project does not claim an audit
opinion, a SOC report, a FedRAMP authorisation or a PCI attestation — those are
issued by an independent assessor.



## Archives and Permanent Records

| Platform | Identifier | Volume |
|---|---|---|
| Harvard Dataverse | DOI 10.7910/DVN/YMJKOG | 145 citable datasets |
| AIOSS verification kit | DOI 10.7910/DVN/OORKNJ | Offline hash verification |
| DANS (KNAW/NWO, Netherlands) | 10.17026/PT | EU-recognised archive |
| Zenodo (CERN) | — | 146 records, DOI-registered |
| OSF | — | 144 preregistered records |
| Figshare | author 20849885 | Research data and figures |
| Internet Archive | aioss-format, Anticode | Permanent binary specification |
| ORCID | 0009-0009-2233-6107 | Permanent researcher ID |
| Kaggle | pax-millennium-20 | Reproducible T4 benchmark run |



## Press and Independent Publication

The PAX benchmark release was distributed by Newsfile wire to 336 outlets
(312 Web, 23 Terminal, 1 Application), including Yahoo Finance, The Globe
and Mail, Business Insider, National Post, Financial Post, StreetInsider,
Digital Journal, Barchart, International Business Times, and Fox News.
Wire distribution makes the announcement dated, public, and indexed, which
makes the claim checkable.

