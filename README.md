# CompoundIQ

CompoundIQ is an AI-driven drug combination design system focused on generating and evaluating 3-compound formulations. The project combines biomedical language understanding, molecular generation, drug interaction prediction, and safety-focused ranking to help identify promising compound combinations.

## Team
- Oyinade
- Nicole
- Oluchi
- Sharise

## Project Overview
The goal of CompoundIQ is to take a natural language therapeutic mechanism description and use it to guide a multi-stage pipeline that:
1. Interprets the mechanism text
2. Generates candidate molecules
3. Predicts pairwise and three-way drug interactions
4. Filters unsafe combinations
5. Ranks the safest and most relevant combinations

Example input:
> "Reduce muscle spasms through calcium channel blocking and GABA enhancement"

Example output:
> Ranked 3-compound combinations with safety analysis, interaction predictions, and overall scoring.

## Main Components
- **BioBERT mechanism interpreter** for converting therapeutic text into biomedical embeddings
- **Molecular VAE / JT-VAE workflow** for molecule generation and exploration
- **Pairwise GNN** for drug-drug interaction prediction
- **Three-Way GNN** for triplet-level interaction prediction
- **DrugBank feature engineering** for graph, CYP, severity, and similarity-based features
- **EDA and testing workflows** for analysis and presentation support

## Data Sources and Credits

This project uses data, derived features, and supporting references from the following publicly available biomedical and molecular data resources:

- **DrugBank** — used for drug records, drug-drug interaction data, enzyme-related features, and DrugBank-based feature engineering workflows.
- **ChEMBL** — used for bioactive compound and mechanism-related modeling support.
- **SIDER** — used for side effect and adverse reaction reference information.
- **STITCH** — used as a supporting resource for chemical/protein interaction context.
- **JT-VAE** — used as molecular generation basedon on the Junction Tree Variational Autoencoder (JT-VAE) approach by Jin, Barzilay, and Jaakkola (2018)

We gratefully acknowledge the teams and institutions that maintain these databases and make them available for research and education.

This repository is part of an academic project. Some raw datasets may not be redistributed here because of size, licensing, or access restrictions. Where needed, this repository includes processed outputs and project notebooks built from approved academic use of these resources.

Full academic references are provided in [CITATIONS.md](CITATIONS.md).

## Data Availability

The full processed datasets are not included in this repository because some source datasets are large and/or have redistribution restrictions.

This project used data from ChEMBL, DrugBank, SIDER, and STITCH. The notebooks in this repository show the preprocessing, feature engineering, model development, and evaluation workflow. Full processed files such as DrugBank-derived feature tables, train/validation/test feature splits, and triplet training datasets were used during development but are not redistributed in this public repository.

To reproduce the full processed datasets, users should obtain access to the original data sources and run the preprocessing notebooks in `notebooks/`.

## Repository Structure
The repository is organized by project component. The `notebooks/` folder contains the main development notebooks for DrugBank preprocessing, BioBERT testing, molecular generation, GNN modeling, and EDA. The `docs/` folder contains project documentation, testing questions, proposal materials, and result images. The `data/processed/` folder contains the cleaned and processed datasets used by the models.
```text
compoundiq/
├── README.md
├── CITATIONS.md
├── notebooks/
│   ├── drugbank/
│   │   └── drugbank_feature_engineering_clean_final.ipynb
│   ├── biobert/
│   │   ├── biobert_testing.ipynb
│   │   └── biobert_enhanced.ipynb
│   ├── vae/
│   │   └── compoundiq_vae.ipynb
│   ├── gnn/
│   │   ├── task6_gnn_architecture.ipynb
│   │   ├── task6_threeway_gnn.ipynb
│   │   └── threeway_gnn_fixed.ipynb
│   └── eda/
│       ├── eda_real_data.ipynb
│       └── task7_eda.ipynb
├── docs/
│   ├── proposal/
│   │   └── CompoundIQ_Final_Presentation_ITAI2277.pdf
│   ├── presentation/
│   │   └── compoundiq_final_presentation.pdf
│   ├── testing/
│   │   └── compoundiq_testing_questions.docx
│   └── training_curves.png
└── data/
│   ├──README.md
    └── processed/
        ├── chembl_processed_full.parquet
        ├── sider_detailed.parquet
        ├── stitch_detailed.parquet
        └── stitch_features.parquet
