# Fluxomics 2026

This repository contains the computational part of a thesis project focused on fluxomics, metabolic flux analysis, and Flux Balance Analysis (FBA).

The project uses COBRApy and genome-scale metabolic models to study how predicted metabolic flux behavior changes under different model and medium conditions.

## Project structure

The repository includes four Jupyter notebooks:

1. 01_cobrapy_textbook_baseline.ipynb
2. 02_ecoli_medium_comparison.ipynb
3. 03_ecoli_model_comparison_iML1515_iJO1366.ipynb
4. 04_published_fluxomics_datasets_review.ipynb

## Notebook 01: COBRApy textbook baseline

This notebook uses the small COBRApy textbook model as a pilot model.

The goal of this notebook is to set up and test the basic computational workflow:

- model loading
- initial FBA optimization
- inspection of reactions, metabolites, and genes
- basic flux extraction
- output generation

The textbook model is used only as a tutorial/pipeline setup model. It is not treated as an equivalent genome-scale model for the final biological comparison.

## Notebook 02: E. coli iML1515 medium comparison

This notebook uses the iML1515 genome-scale metabolic model of Escherichia coli.

The goal is to compare the same model under different medium conditions. The model is kept constant, while the carbon source and oxygen availability are changed.

The tested conditions are:

- glucose aerobic
- fructose aerobic
- galactose aerobic
- glycerol aerobic
- succinate aerobic
- acetate aerobic
- glucose anaerobic

For each condition, the following metrics are extracted and compared:

- FBA objective value
- number of active/nonzero fluxes
- number of blocked reactions
- blocked reaction fraction
- top internal fluxes

This notebook represents the main medium-condition comparison of the project.

## Notebook 03: E. coli model comparison between iML1515 and iJO1366

This notebook compares two genome-scale metabolic models of Escherichia coli:

- iML1515
- iJO1366

Both models are tested under the same seven medium conditions used in Notebook 02.

The goal is to examine whether different metabolic reconstructions of the same organism produce similar or different FBA predictions.

The comparison includes:

- model size comparison
- required exchange reaction checks
- FBA objective value comparison
- active flux comparison
- blocked reaction comparison
- numerical difference tables between models

This notebook represents the model-reconstruction comparison of the project.

## Notebook 04: Published fluxomics datasets review

This notebook summarizes selected published fluxomics and 13C-MFA datasets that are relevant to the computational FBA analysis.

The goal is not to fully reanalyze raw 13C-MFA data, but to compare published experimental fluxomics datasets with the structure of the FBA simulations performed in the previous notebooks.

The reviewed datasets include published E. coli fluxomics studies related to:

- glucose and xylose metabolism under aerobic and anaerobic conditions
- glucose and galactose flux behavior
- high-resolution 13C-MFA experimental workflows
- glycerol-based metabolic flux analysis

This notebook is used as an external literature-based comparison and helps clarify the relationship between FBA predictions and experimental 13C-MFA flux estimates.

## Outputs

Generated output files are saved in the outputs folder.

Tables are saved in:

outputs/tables

Figures are saved in:

outputs/figures

Important output files include:

- iML1515_medium_comparison_summary.csv
- iML1515_medium_comparison_report_table.csv
- iML1515_top10_internal_fluxes_all_conditions.csv
- iML1515_common_top_internal_reactions.csv
- ecoli_model_comparison_iML1515_iJO1366_summary.csv
- ecoli_model_comparison_iML1515_iJO1366_report_table.csv
- ecoli_model_comparison_objective_differences.csv
- ecoli_model_comparison_blocked_reaction_differences.csv
- published_fluxomics_datasets_review.csv
- published_datasets_to_fba_conditions_mapping.csv
- fba_vs_13c_mfa_comparison_limitations.csv

## Notes

The FBA results in this repository are computational predictions based on stoichiometric constraints, medium composition, and objective functions.

They should not be interpreted as direct experimental fluxomics measurements.

Published 13C-MFA datasets are included for qualitative and methodological comparison, because 13C-MFA provides experimentally constrained intracellular flux estimates, while FBA provides model-based predicted flux distributions.

Therefore, objective values and blocked reactions from FBA are not directly comparable with 13C-MFA outputs. However, carbon source effects, oxygen availability effects, and intracellular flux behavior can be compared qualitatively when the biological context is similar.

## Main scientific logic

The project follows three levels of comparison:

1. Textbook model as pilot workflow setup.
2. Same model under different medium conditions.
3. Same organism represented by different genome-scale reconstructions.
4. Published fluxomics datasets as external methodological comparison.

This structure allows the project to compare computational flux predictions while also connecting the analysis to independent published fluxomics studies.