# PIDS DRG dependencies

Container repo that pins the PIDS DRG data helpers as git submodules so they can be fetched in one clone with full history.

## Submodules
- `pids-drg-fda-scraper` – Python scrapers for FDA Philippines drug and food catalogs; outputs brand→generic maps and caches raw downloads. Can copy drug outputs into `inputs/drugs/` for downstream pipelines.
- `pids-drg-drugbank-generics` – R script to build lean DrugBank exports (generics, synonyms, brands, dosages, salts, products, ATC, lookup tables) used for matching and FDA correction.
- `pids-drg-who-atc` – R scraper/exporter for WHO ATC/DDD; produces dated raw snapshots plus canonical Level‑5 molecule and excluded placeholder CSVs.
- `pids-drg-shadow-billing-sandbox` – RMarkdown notebooks that merge DRG claim CSVs into master tables for shadow billing analysis.

## Getting started
```bash
# clone with submodules
git clone --recurse-submodules https://github.com/carlosresu/pids-drg-dependencies.git

# if already cloned
git submodule update --init --recursive

# refresh submodules to latest tracked commits
git submodule update --remote --merge
```

Default branch is `master`. Each submodule carries its own README with detailed usage and setup.
