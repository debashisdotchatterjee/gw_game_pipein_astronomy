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
