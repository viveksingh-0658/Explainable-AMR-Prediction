# Explainable Deep Learning for Antimicrobial Resistance Prediction

## Project Overview

Antimicrobial resistance (AMR) is an important challenge in healthcare. Disk-diffusion testing is commonly used to study bacterial susceptibility to antibiotics. In this method, antibiotic discs are placed on an agar plate, and the inhibition zones around the discs provide evidence about bacterial growth in the presence of antibiotics.

This project explores whether deep learning and computer vision can be used to analyse disk-diffusion images and predict antibiotic susceptibility. Along with the prediction, the project focuses on identifying the inhibition-zone regions relevant to the model's decision and evaluating the reliability of its visual explanations.

## Research Idea

**Explainable AMR Prediction with Zone-Level Evidence**

The main idea is to combine antibiotic-specific susceptibility prediction, inhibition-zone localisation, and Grad-CAM-based visual explanations.

The study will investigate whether the regions highlighted by Grad-CAM agree with independently verified inhibition-zone regions and whether this agreement is related to prediction errors.

This research question will be evaluated experimentally. The novelty and usefulness of the approach will be assessed after reviewing existing studies and analysing the dataset.

## Objectives

- Verify the dataset images, metadata, susceptibility labels, and antibiotic mapping.
- Locate antibiotic discs and their corresponding inhibition zones where the available annotations permit.
- Develop a baseline deep-learning model for antibiotic-specific susceptibility prediction.
- Generate Grad-CAM heatmaps to examine the image regions influencing model predictions.
- Quantitatively compare model explanations with verified reference regions, where suitable annotations are available.
- Evaluate classification performance, localisation quality, explanation agreement, and prediction errors.
- Document the experimental results, limitations, and findings for the research paper.

## Dataset

**Candidate dataset:** SIRscan disk-diffusion image dataset.

**Source:** [Dryad Dataset](https://datadryad.org/dataset/doi:10.5061/dryad.5dv41nsfj)

The dataset will be audited before model development. The audit will check the available image files, metadata fields, sample identifiers, antibiotic names, susceptibility labels, and any inhibition-zone annotations.

The final prediction labels and experimental setup will be selected only after confirming that images and reference labels can be mapped reliably.

## Proposed Methodology

1. **Dataset audit:** Inspect the image files, metadata, label definitions, and sample-to-antibiotic mapping.
2. **Data preparation:** Remove invalid records, prepare images, and create a reproducible dataset manifest.
3. **Data splitting:** Separate training, validation, and test data at the isolate level where isolate identifiers are available.
4. **Zone localisation:** Detect or annotate antibiotic discs and inhibition zones, depending on the available reference annotations.
5. **Baseline model:** Train and evaluate an appropriate image-based susceptibility classifier.
6. **Explainability:** Generate Grad-CAM heatmaps for model predictions.
7. **Evidence evaluation:** Compare heatmaps with independently verified inhibition-zone regions using suitable quantitative measures.
8. **Error analysis:** Examine incorrect predictions, including resistant samples incorrectly classified as susceptible.
9. **Reporting:** Record the experimental setup, results, limitations, and conclusions.

The exact model architecture and evaluation measures will be finalised after the dataset audit.

## Evaluation Plan

### Classification
- Accuracy
- Precision, recall, and F1-score
- Macro-F1 and balanced accuracy
- Confusion matrix
- Very major error rate, where the reference labels and test design support its calculation

### Zone Localisation
- Intersection over Union (IoU) or other suitable detection metrics, if verified reference annotations are available
- Disc and inhibition-zone localisation errors

### Explanation Quality
- Spatial agreement between Grad-CAM heatmaps and verified reference regions
- Comparison of explanation agreement across correct and incorrect predictions
- Analysis of cases where the highlighted regions do not match the expected evidence

Visual overlap alone will not be treated as proof that an explanation is biologically correct.

## Tools and Technologies

- Python
- PyTorch and Torchvision
- OpenCV and Pillow
- NumPy and Pandas
- Scikit-learn
- Matplotlib
- Grad-CAM
- Jupyter Notebook
- Git and GitHub

## Project Structure

```text
AMR_Project/
├── data/
│   ├── raw/
│   ├── metadata/
│   └── processed/
├── notebooks/
├── src/
│   ├── data/
│   ├── preprocessing/
│   ├── models/
│   ├── evaluation/
│   └── explainability/
├── outputs/
│   ├── figures/
│   ├── metrics/
│   └── reports/
├── docs/
├── requirements.txt
├── .gitignore
└── README.md
```

## Current Status

- [x] Initial project structure created
- [x] Initial project structure pushed to GitHub
- [ ] Verify the SIRscan dataset and its labels
- [ ] Create a reliable image-to-antibiotic mapping
- [ ] Prepare the dataset manifest and splits
- [ ] Establish a baseline model
- [ ] Evaluate susceptibility predictions
- [ ] Generate and evaluate Grad-CAM explanations
- [ ] Complete error analysis
- [ ] Prepare the research paper

## Research Limitations

The project depends on the quality and availability of the dataset's labels, metadata, and reference annotations. If verified inhibition-zone annotations are unavailable, additional annotation work or a revised evaluation method may be necessary.

The system is a research prototype and is not intended to replace standard laboratory antimicrobial susceptibility testing or clinical judgement.

## Authors

**Vivek Singh**  
**Utkarsh Kumar Singh**

School of Computer Science and Engineering  
Galgotias University
