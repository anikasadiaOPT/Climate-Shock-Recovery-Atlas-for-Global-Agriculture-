# Climate-Agriculture Shock–Recovery Atlas: A 33-Year Spatio-Temporal Analysis of Global Agricultural Resilience Using ECMWF and FAOSTAT Data


Short description:\n
This repository contains code and workflows used to build the Climate Shock–Recovery Atlas for global agriculture. The atlas links country-level crop production data (FAOSTAT) with gridded climate predictors (ECMWF ERA5 / ERA5‑Land), implements preprocessing and quality checks, and produces cleaned datasets and indicators used in modelling shock and recovery dynamics.

Key features
- Reproducible data-processing pipelines for harmonizing FAOSTAT and ERA5-derived predictors.
- Scripts to aggregate gridded climate data to countries (area-weighted) and compute seasonal predictors.
- Cleaned, documented output tables ready for modeling and visualization.

Table of contents
- Project status
- Quick start
- Data sources & licensing
- Folder structure
- Processing overview
- How to cite
- Contributing
- License & data license

Project status
- Data collection and preprocessing: implemented (scripts in /scripts)
- Processed datasets stored in: /data (keep sensitive or proprietary outputs out of the public repo)
- Analysis & visualization scripts: in /notebooks and /src (if present)

Quick start
1. Clone:
   git clone https://github.com/anikasadiaOPT/Climate-Shock-Recovery-Atlas-for-Global-Agriculture-.git
2. Create a Python environment:
   python -m venv venv
   source venv/bin/activate
   pip install -r requirements.txt
3. Data access:
   - FAOSTAT: download country-level crop tables (see Data sources & licensing below).
   - ERA5/ERA5‑Land: obtain via Copernicus Climate Data Store (CDS) API or ECMWF resources (see Data sources & licensing).
   Place raw downloads under data/raw/ following the README in /data or the scripts' configuration.

Data sources & licensing (important)
This project uses third-party data with their own licenses and attribution requirements. You must read and comply with those licenses before re-using or redistributing the raw or derived datasets.

- FAOSTAT (Food and Agriculture Organization of the United Nations)
  - Website: https://www.fao.org/faostat/en/#data/QCL
  - Citation and terms: Follow FAO/FAOSTAT citation and attribution policies. See DATA_LICENSE.md for recommended citation text and redistribution guidance.

- ERA5 / ERA5‑Land (ECMWF / Copernicus)
  - Website: https://confluence.ecmwf.int/display/CKB/ERA5%3A+data+documentation and https://cds.climate.copernicus.eu
  - Citation: Cite the Copernicus Climate Change Service (C3S) and the ERA5 dataset per the ECMWF guidance. See DATA_LICENSE.md for recommended citation lines and references.

Processed data and code licensing
- Code and repository materials are released under the MIT License (see LICENSE).
- Processed/derived datasets produced by these scripts may still be bound by the original data providers' terms — check DATA_LICENSE.md and the original providers. Where applicable, include provider attribution and license statements alongside any redistributed derivative data.

Folder structure (recommended)
- data/
  - raw/                # raw downloads (not committed)
  - processed/          # cleaned and harmonized tables (optionally committed)
- scripts/              # data processing scripts (ingestion, cleaning, aggregation)
- notebooks/            # exploratory analyses and visualization
- src/                  # code modules used by scripts/notebooks
- docs/                 # documentation and figures
- LICENSE
- DATA_LICENSE.md
- CITATION.cff
- README.md
- CONTRIBUTING.md
- CODE_OF_CONDUCT.md

Processing overview (high level)
1. Download raw FAOSTAT country-level crop tables and ERA5/ERA5-Land variables (t2m, tcc, tp, ssr, si10).
2. Harmonize country identifiers (ISO3), crop names, and year ranges.
3. Reproject and aggregate ERA5 to country polygons (area-weighted) and compute seasonal statistics (e.g., growing-season mean t2m, cumulative tp).
4. Quality checks: range checks, missingness reports, and minimal imputation where justified (documented in scripts).
5. Store cleaned tables in data/processed with provenance metadata (source URLs, query details, processing date).

Provenance & reproducibility
- Keep raw downloads outside version control (data/raw).
- Log exact download queries, API calls, and parameter selections in scripts and in per-run metadata files saved to data/processed/provenance/.
- If you publish processed datasets, include:
  - link to original data provider(s),
  - citation text,
  - date of download,
  - scripts and exact commit hash used to generate the artifact.

How to cite
Preferred citation for the repository (see CITATION.cff):
- Please cite this repository and the relevant FAO and ECMWF/ERA5 sources per their recommended citation text. See DATA_LICENSE.md for exact lines.

Contributing
See CONTRIBUTING.md for the contribution process, coding style, and tests.

Code of conduct
This project follows the Contributor Covenant Code of Conduct. See CODE_OF_CONDUCT.md.

Contact
Repo owner: anikasadiaOPT
For questions about data access or licensing, please open an issue.

Acknowledgements
- FAO/FAOSTAT for country-level agricultural statistics.
- ECMWF / Copernicus for ERA5 and ERA5-Land reanalysis datasets.

License
- Code: MIT (see LICENSE)
- Data: subject to provider licenses — see DATA_LICENSE.md for details.

