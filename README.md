# Explainable Deep Learning for Antimicrobial Resistance Prediction

## Project status
Initial implementation structure prepared for Mid-Term Evaluation (MTE).

## Goal
Investigate antibiotic-specific susceptibility prediction from verified SIRscan disk-diffusion images and evaluate model explanations using Grad-CAM where suitable reference annotations are available.

## Important note
Dataset labels, image-to-antibiotic mapping, and the availability of reference inhibition-zone annotations must be verified before model training. No experimental results are claimed at this stage.

## Structure
- `data/raw/`: original dataset files; keep unchanged
- `data/metadata/`: dataset documentation and label-mapping notes
- `data/processed/`: small indexes and split manifests
- `notebooks/`: exploratory analysis and experiments
- `src/data/`: dataset indexing and loading code
- `src/preprocessing/`: image and label preprocessing
- `src/models/`: model definitions and training code
- `src/evaluation/`: metrics and error analysis
- `src/explainability/`: Grad-CAM implementation and analysis
- `outputs/`: generated plots, metrics, and reports
- `docs/`: MTE notes and dataset audit

## Planned milestones
1. Verify dataset contents, labels, and antibiotic mapping.
2. Create an image/metadata index.
3. Establish an isolate-level train/validation/test split.
4. Build and evaluate a baseline model.
5. Apply Grad-CAM and assess explanations if verified reference regions are available.
