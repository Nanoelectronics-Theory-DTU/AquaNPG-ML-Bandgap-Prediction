# Predictive AI Models for Nanoporous Graphene under Water

This repository contains reference datasets and Python scripts for predicting configuration-dependent bandgap energies of nanoporous graphene (NPG) and hybrid nitrogen-doped nanoporous graphene (h-NPG) in single-water and bulk-water environments.

The project supports both black-box and physics-informed grey-box machine-learning approaches, including Gaussian Process Regression (GPR), for near-DFT-level bandgap prediction accuracy.

## Repository Contents

```text
Feature_extraction.tar
HNPG_Bulkwater_Greybox.tar
HNPG_Bulkwater_SOAP.tar
HNPG_Water_Greybox.tar
HNPG_Water_SOAP.tar
NPG_Bulkwater_Greybox.tar
NPG_Bulkwater_SOAP.tar
NPG_Water_Greybox.tar
NPG_Water_SOAP.tar
```

`Feature_extraction.tar` contains Python scripts for generating SOAP descriptors and physics-informed grey-box descriptors for water–NPG/h-NPG systems.

Each dataset archive contains preprocessed training and testing files, typically including:

```text
x_train.xlsx
x_test.xlsx
y_train.xlsx
y_test.xlsx
x_train_best_features.xlsx
x_test_best_features.xlsx
```

The `x_train.xlsx` and `x_test.xlsx` files contain the full descriptor sets. The `x_train_best_features.xlsx` and `x_test_best_features.xlsx` files contain optimized feature subsets selected using Recursive Feature Elimination (RFE), which improved model accuracy.

## Descriptor Types

The repository includes two main descriptor families:

**SOAP descriptors**
Black-box structural descriptors generated from atomic configurations.

**Physics-informed grey-box descriptors**
Physically meaningful descriptors describing water–graphene interactions, including water position, dipole moment, dipole orientation, O···H and N···H contact distances, hydrogen-contact counts-based features.

## Available Datasets

| Archive                      | System | Water Environment | Descriptor Type |
| ---------------------------- | ------ | ----------------- | --------------- |
| `NPG_Water_SOAP.tar`         | NPG    | Single water      | SOAP            |
| `NPG_Water_Greybox.tar`      | NPG    | Single water      | Grey-box        |
| `NPG_Bulkwater_SOAP.tar`     | NPG    | Bulk water        | SOAP            |
| `NPG_Bulkwater_Greybox.tar`  | NPG    | Bulk water        | Grey-box        |
| `HNPG_Water_SOAP.tar`        | h-NPG  | Single water      | SOAP            |
| `HNPG_Water_Greybox.tar`     | h-NPG  | Single water      | Grey-box        |
| `HNPG_Bulkwater_SOAP.tar`    | h-NPG  | Bulk water        | SOAP            |
| `HNPG_Bulkwater_Greybox.tar` | h-NPG  | Bulk water        | Grey-box        |

## Installation

Install the required Python packages:

```bash
pip install numpy pandas ase dscribe pynep openpyxl
```

Main dependencies include NumPy, Pandas, ASE, DScribe, PyNEP, and OpenPyXL.



## Machine-Learning Workflow

Use `x_train.xlsx`, `x_test.xlsx`, `y_train.xlsx`, and `y_test.xlsx` to train regression models for bandgap prediction. Alternatively, use the RFE-selected `x_train_best_features.xlsx` and `x_test_best_features.xlsx` files for improved model performance.

Both SOAP-based black-box models and physics-informed grey-box models can be developed using these datasets.





