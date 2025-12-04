# pids-drg-dependencies

Container repo that pins the PIDS DRG-related data projects as git submodules. Use this to pull everything in one place with full history for each dependency.

## Included submodules
- `pids-drg-fda-scraper`
- `pids-drg-drugbank-generics`
- `pids-drg-who-atc`
- `pids-drg-shadow-billing-sandbox`

## Getting started
```bash
# clone with submodules
git clone --recurse-submodules https://github.com/carlosresu/pids-drg-dependencies.git

# if you already cloned without submodules
git submodule update --init --recursive

# update submodules to their latest tracked commits
git submodule update --remote --merge
```

## Notes
- Default branch is `master`.
- `.gitignore` covers common Python and R artifacts for convenience when working across the dependencies.
