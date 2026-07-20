# fluxomics-2026
# Fluxomics 2026

This repository contains the computational part of an academic project focused on fluxomics and constraint-based metabolic modeling.

The analysis was performed in Python using COBRApy and genome-scale metabolic models of Escherichia coli. The main method used is Flux Balance Analysis (FBA), a constraint-based modeling approach that predicts metabolic flux distributions under defined environmental and medium conditions.

## Project scope

The computational analysis has two main levels:

1. Medium comparison within the same model
2. Model comparison under the same medium conditions

The first part uses the iML1515 model and compares different carbon sources and oxygen availability conditions.

The second part compares two Escherichia coli genome-scale models, iML1515 and iJO1366, under the same set of medium conditions.

## Models used

The models used in this project are:

- COBRApy textbook model
- iML1515
- iJO1366

The textbook model was used as a pilot model to test the workflow. The main analyses were performed using iML1515 and iJO1366.

## Medium conditions

The following medium conditions were analyzed:

- glucose_aerobic
- fructose_aerobic
- galactose_aerobic
- glycerol_aerobic
- succinate_aerobic
- acetate_aerobic
- glucose_anaerobic

For each condition, FBA was performed and the following metrics were extracted:

- objective value
- number of active/nonzero fluxes
- number of blocked reactions
- blocked reaction fraction
- top internal fluxes
- common top internal reactions

## Repository structure

```text
.
├── 01_cobrapy_textbook_baseline.ipynb
├── 02_ecoli_medium_comparison.ipynb
├── 03_ecoli_model_comparison_iML1515_iJO1366.ipynb
├── outputs/
│   ├── figures/
│   └── tables/
└── README.txt
