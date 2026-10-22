# SpecSuite .NET validation samples

Three existing SpecSuite-generated specification packages for integration testing.
Published by the repository owner for public review. These are saved September
2026 outputs, not fresh generation against the current SpecSuite release.

## Samples

| Directory | Original application | Included artifacts | Important limitation |
| --- | --- | --- | --- |
| [mini-quote](mini-quote) | Synthetic ASP.NET Core / .NET 8 quote calculator | Raw Forge specification, knowledge graph, analysis/gap reports, evaluation harness, and a separately reviewed specification | No generated architecture diagrams in this packet |
| [legacy-orders](legacy-orders) | .NET Framework 4.7.2 order-processing sample | Specification, JSON/YAML/HTML knowledge graphs, Mermaid diagrams, analysis/gap reports and evaluation harness | Small example; architecture overview is sparse and generated framework classification is inaccurate |
| [fleet-manager](fleet-manager) | Synthetic .NET Framework 4.8 / ASP.NET MVC 5 fleet-maintenance sample | Specification, JSON/YAML/HTML knowledge graphs, Mermaid architecture/dependency/data-flow/route/sequence diagrams, analysis/gap reports and evaluation harness | Saved analysis reports schema invalid and nine unresolved handler references |

Start with Mini Quote for a small specification/graph ingestion fixture. Use
FleetManager for larger graphs, richer diagrams and known-imperfect input handling.
Legacy Orders is another small .NET Framework fixture. No package is represented
as a complete, approved architecture or a production modernization result.

## File locations

- Mini Quote raw output: [mini-quote/forge-01](mini-quote/forge-01).
- Mini Quote reviewed input: [mini-quote/reviewed-01](mini-quote/reviewed-01).
  This is a distinct reviewed specification, not unchanged raw Forge output.
  The knowledge graph in `forge-01` belongs to the raw output; no regenerated
  reviewed graph is supplied.
- Legacy Orders entry point: [legacy-orders/spec.yaml](legacy-orders/spec.yaml).
- FleetManager entry point: [fleet-manager/spec.yaml](fleet-manager/spec.yaml).
- Diagrams: each ADO sample's `diagrams` directory, in Mermaid `.mmd` format.
- [manifest.json](manifest.json): SHA-256, byte size and origin for every exported
  artifact. Exported artifacts retain their original bytes.

The HTML graph viewers load D3 from `https://d3js.org/d3.v7.min.js`; opening them
requires access to that external script. JSON/YAML graphs and Mermaid sources
are provided for consumers that must not load external scripts. No rendered
diagram images are included.

## Quality boundaries

The retained analysis reports say:

| Sample | Schema valid | Resolved references | Graph entities / relationships |
| --- | --- | --- | --- |
| Mini Quote, raw Forge | Yes | 15 / 15 | See the supplied knowledge graph |
| Legacy Orders | Yes | 26 / 26 | 18 / 30 |
| FleetManager | **No** | **646 / 655** | 187 / 316 |

These are historical product-reported results, not independent schema
certification. A completeness score describes transcription of extractor output,
not complete source coverage or semantic correctness. Preserve the gap and
analysis reports when using or redistributing a packet. Generated descriptions
and diagrams can be generic or wrong, including Legacy Orders being described
as an ASP.NET Core service despite its .NET Framework source.

Evaluation harnesses are generated artifacts, not proof of passing tests.
Embedded source excerpts and evidence paths may be present in the specification;
this is not a source-free reconstruction benchmark. Paths such as `/work/source`
refer to the original analysis environment, not a runnable environment supplied
by this repository.

## Provenance

| Sample | Pinned origin |
| --- | --- |
| Mini Quote | `ParthVyas2912/specsuite-mini-quote`, commit `83254f93396c4c7b4653d7e3edc55ccdfed278bd`, `specification/forge-01` and `specification/reviewed-01` |
| Legacy Orders | Azure DevOps `partvyas/GHAS-demo`, build `87`, artifact `specforge-output-87`, generated 2026-09-09 |
| FleetManager | Azure DevOps `partvyas/GHAS-demo`, build `82`, artifact `specforge-output-82`, generated 2026-09-09 |

The original repositories and pipeline pages remain private; access to them is
not required to download these public exports.

This repository deliberately excludes private SpecSuite product/runtime code,
container images, credentials, analysis caches, attachment manifests, model
telemetry, operational logs, original repository history and generated application
builds. It contains selected specification artifacts, not the complete private
source archives. Do not execute embedded source or generated harnesses merely
because these files are public.

## Distribution

Public availability is not an open-source license grant. No license for private
SpecSuite product code, runtimes, dependencies or third-party components is
granted by this repository. Any broader licensing or redistribution rights
require a separate applicable license or permission from the rights holder.

SpecSuite is evolving field IP / a solution accelerator, not a supported Microsoft
product. These samples carry no production-readiness, fidelity or support claim.
