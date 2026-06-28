# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What this project is

A Python research project applying Traveling Salesman Problem (TSP) algorithms to the Harzer Wandernadel (HWN) — 222 hiking stamp locations across the Harz Mountains in Germany. The goal is to find an optimal route visiting all stamp locations.

## Setup

```bash
pip install -r requirements.txt
```

All work happens in Jupyter notebooks. Launch with:

```bash
jupyter notebook
```

## Running notebooks

Notebooks live in `source/notebooks/`. They are standalone scripts — run cells top-to-bottom. The helper `source/utils/utilities.py` provides `get_root_path()` which resolves to the repo root, used for constructing paths to data files.

## Data layout

- `source/gpx/` — raw GPX files downloaded from HWN website, plus Excel exports of their waypoints (e.g. `HWN2024.gpx` → `HWN2024_exported_from_gpx.xlsx`)
- `source/excel/all_stamps.xlsx` — master list of all 222 HWN stamp locations
- `source/excel/all_stamps_visited.xlsx` — personal tracking of visited stamps
- `source/arrays/all_stamps_distances.npy` — precomputed NumPy distance matrix (direct/as-the-crow-flies distances between all stamp pairs)
- `source/gpx_routes/` — GPX route files between specific stamp pairs; `HWN110_HWN111.gpx` is a working example downloaded from Komoot
- `source/my_trips/` — personal hiking journal data

## Notebook responsibilities

| Notebook | Purpose |
|---|---|
| `export_gpx_to_df.ipynb` | Parse GPX waypoints → Excel |
| `calculate_distanses.ipynb` | Build the distance matrix, save to `.npy` |
| `plot_stamps_on_map.ipynb` | Visualize all stamp locations on a map |
| `plot_graph.ipynb` | Graph theory visualization of connections |
| `add_visited_by_me_and_image.ipynb` | Merge personal visit data into master stamp list |
| `harz_add_special.ipynb` | Handle special/bonus stamps |
| `create_single_gps_tour.ipynb` | Experiment with generating GPX routes |
| `one_tour_sandbox.ipynb` | Sandbox for TSP route experiments |
| `parse_hiking_jornal_to_csv.ipynb` | Parse personal hiking journal to CSV |

## Key dependencies and their roles

- `gpxpy` — parse `.gpx` files into waypoints
- `ezgpx` — plot GPX tracks visually
- `pandas` / `openpyxl` — read/write Excel files
- `numpy` — distance matrix storage (`.npy` format)
- `matplotlib` / `Pillow` — plotting

`kompy` (Komoot API wrapper) is listed but commented out in requirements because it fails to install. The current workaround is manually downloading Komoot-generated GPX routes for individual stamp pairs.

## Current state and open problems

- Direct distances between all 222 stamps are computed and cached in `all_stamps_distances.npy`
- Realistic walking routes (using actual trails) are not yet computed at scale — only one example pair (`HWN110_HWN111`) has a Komoot route
- Komoot API authentication is broken for programmatic route creation; routes must currently be created manually on komoot.com and downloaded
- TSP algorithm selection and implementation is still in the research/TODO phase
- See `project_journal.md` for dated progress notes
