# PIDS DRG Dependencies

Container repository that pins the PIDS DRG data helper projects as git submodules so they can be fetched in one clone with full history.

**Last Updated:** December 2025

---

## Progress Since June 2025

### Key Accomplishments

| Date | Milestone |
|------|-----------|
| **Jun 2025** | Created container repo, added initial submodules |
| **Jul 2025** | Added FDA scraper submodule with drug/food scrapers |
| **Aug 2025** | Added WHO ATC scraper submodule with parallelized crawling |
| **Sep 2025** | Added DrugBank generics exporter with lean tables |
| **Oct 2025** | Added shadow billing sandbox for DRG claim analysis |
| **Dec 2025** | Refreshed all submodule READMEs, documented container usage |

### Current Status

All 4 submodules are operational:
- **pids-drg-fda-scraper:** Active FDA PH drug/food catalog scraping
- **pids-drg-drugbank-generics:** DrugBank lean export pipeline (8 data tables + 6 lookup tables)
- **pids-drg-who-atc:** WHO ATC hierarchy scraping with Level-5 molecule exports
- **pids-drg-shadow-billing-sandbox:** DRG claim CSV merging for shadow billing analysis

---

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
