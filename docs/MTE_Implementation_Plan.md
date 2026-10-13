# MTE Implementation Plan

## Current phase
Project structure and dataset audit preparation.

## To complete next
- [ ] Confirm the SIRscan archive is available locally.
- [ ] List files and inspect archive/folder structure.
- [ ] Inspect metadata column names and sample rows.
- [ ] Verify label definitions (for example, S/I/R) and antibiotic mapping.
- [ ] Check whether images are linked to isolate IDs and individual antibiotic discs.
- [ ] Check whether independent inhibition-zone reference annotations exist.
- [ ] Document limitations before choosing the model task.

## Planned implementation
- [ ] Create a dataset index without duplicating large image files.
- [ ] Create isolate-level train/validation/test split manifests.
- [ ] Train a baseline model only after label mapping is verified.
- [ ] Evaluate with suitable metrics, including macro-F1 and resistant-to-susceptible errors where applicable.
- [ ] Apply Grad-CAM and compare with verified reference regions if available.

## Integrity notes
Do not report model accuracy or claim results before running experiments. Avoid image-level random splitting when images from the same isolate can appear in multiple splits.
