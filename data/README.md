```markdown
# Data Folder

The full processed datasets are not included in this repository.

During development, this project used processed datasets derived from ChEMBL, DrugBank, SIDER, and STITCH. Some processed files, especially the DrugBank-derived feature tables and triplet training files, are excluded because they may be large and/or subject to redistribution restrictions.

Excluded examples include:

- `drugbank_processed_enhanced.parquet`
- `train_features.parquet`
- `val_features.parquet`
- `test_features.parquet`
- `triplet_train.parquet`
- `triplet_val.parquet`
- `triplet_test.parquet`

To reproduce these files, obtain the original datasets from their official sources and run the preprocessing notebooks in the `notebooks/` folder.

Full citations are provided in `CITATIONS.md`.
