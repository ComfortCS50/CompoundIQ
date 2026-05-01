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


## Repository Structure
```text
compoundiq/
├── README.md
├── notebooks/
│   ├── drugbank/
│   │   └── drugbank_feature_engineering_clean_final.ipynb
│   ├── biobert/
│   │   └── biobert_testing.ipynb
│   ├── vae/
│   │   └── compoundiq_vae.ipynb
│   ├── gnn/
│   │   ├── task6_gnn_architecture.ipynb
│   │   └── task6_threeway_gnn.ipynb
│   └── eda/
│       └── task7_eda.ipynb
├── docs/
│   ├── compoundiq_project_proposal.pdf
│   └── compoundiq_testing_questions.docx
└── data/
    └── processed/
        ├── drugbank_processed_enhanced.parquet
        ├── train_features.parquet
        ├── val_features.parquet
        ├── test_features.parquet
        ├── triplet_train.parquet
        ├── triplet_val.parquet
        └── triplet_test.parquet

