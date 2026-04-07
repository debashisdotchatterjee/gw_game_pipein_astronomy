# gw_game_pipein_astronomy

A reproducible Python pipeline for decentralized game-theoretic scheduling of electromagnetic follow-up observations for public gravitational-wave events using GWOSC sky maps, `ligo.skymap`, and `astroplan`.

## Overview

This repository accompanies the manuscript on decentralized game-theoretic follow-up of gravitational-wave alerts. The project develops a posterior-weighted scheduling framework in which multiple observatories are treated as autonomous agents acting on public sky-localization maps. The workflow combines:

- public gravitational-wave event products from GWOSC,
- HEALPix sky-map parsing through `ligo.skymap`,
- observability and site constraints through `astroplan`,
- a decentralized potential-game scheduler,
- benchmark comparisons against centralized greedy, selfish independent greedy, and random feasible baselines,
- realized Shapley-value credit allocation,
- automatic generation of figures, tables, and zipped output bundles.

The main goal is to provide a transparent and reproducible bridge between multimessenger astronomy, statistical decision-making, and operations research.

## Scientific scope

The repository is designed for methodological experiments on public compact-binary events such as:

- GW170817
- GW190814

The code can be extended to additional public GW events released through GWOSC.

## Repository contents

A typical run produces:

- event summaries,
- candidate tile tables,
- pruned action libraries,
- method-comparison tables,
- best-response histories,
- proposed and benchmark schedules,
- realized Shapley-credit tables,
- diagnostic figures,
- zipped per-event and aggregate output bundles.

## Installation

It is recommended to use Python 3.10+ in a clean environment.

```bash
pip install -r requirements_gw_game_pipeline.txt


## Methodological Components

The pipeline implements:

- Sky-map ingestion  
  Public event products are downloaded or queried through GWOSC and read using `ligo.skymap`.

- Candidate tile construction  
  High-probability tile centers are generated from the sky map.

- Feasible action library generation  
  Telescope-specific actions are filtered using visibility windows, observing slots, and instrumental constraints.

- Detection-weight construction  
  Each feasible action is assigned a posterior-weighted detection score based on sky probability, coverage, and observability.

- Scheduling algorithms  
  - Proposed decentralized potential-game scheduler  
  - Centralized greedy baseline  
  - Selfish independent greedy baseline  
  - Random feasible baseline

- Credit allocation  
  Realized Shapley values are computed from the final proposed schedule.

- Output generation  
  Tables, plots, and ZIP bundles are saved automatically.

---

# Outputs

The pipeline creates a directory structure similar to:
gw_game_outputs/ ├── GW170817/ │   ├── figures/ │   ├── tables/ │   └── GW170817_results.zip ├── GW190814/ │   ├── figures/ │   ├── tables/ │   └── GW190814_results.zip └── gw_game_all_outputs.zip


---

# Reproducibility

This repository is intended to support fully reproducible computational experiments.  
All main outputs used in the manuscript can be regenerated from the public data sources and the scripts provided here.

---

# License

This repository is distributed under the MIT License.  
See the LICENSE file for details.

---

# Citation

If you use this repository in academic work, please cite the associated manuscript and acknowledge the public data/software ecosystem used in the workflow, especially:

- GWOSC  
- ligo.skymap  
- astroplan

---

# Acknowledgement

This repository relies on public multimessenger astronomy infrastructure and on open scientific software made available by the gravitational-wave and astronomy communities.

---

# Contact

For questions, suggestions, or collaboration, please open an issue on the repository or contact the repository owner through GitHub.

