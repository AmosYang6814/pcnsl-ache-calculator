# ACHE Overall Survival Calculator for Newly Diagnosed PCNSL

Interactive closed-form browser calculator for individualized 12-, 24-, and 36-month overall survival (OS) probability estimation in newly diagnosed primary central nervous system lymphoma (PCNSL), using four routine pretreatment baseline measures:

- **Age** (years)
- **ECOG Performance Status** (0–4 points)
- **Hemoglobin (Hb)** (g/L)
- **C-Reactive Protein (CRP)** (mg/L)

## Live Web Calculator

Once GitHub Pages is enabled for this repository, access the calculator directly at:

`https://amosyang6814.github.io/pcnsl-ache-calculator/`

## Model Specification

All calculations run strictly in the user's browser with zero server transmission and zero patient-level data stored in this repository.

- Sigmoid transformation: $g_j(x_j; c_j, s_j) = 1 / [1 + \exp(-(x_j - c_j) / s_j)]$
- Centered linear predictor: $\eta_c = \sum_{j=1}^{4} \beta_j [g_j(x_j; c_j, s_j) - \mu_j] = R - 0.860136$
- Individualized OS probabilities: $\hat{S}(t \mid \mathbf{x}) = [S_0(t)]^{\exp(\eta_c)}$ for $t \in \{12, 24, 36\}$ months, with Breslow baseline survival estimates $S_0(12) = 0.816156$, $S_0(24) = 0.710476$, and $S_0(36) = 0.597072$.

## Research Use Disclaimer

This tool is provided solely for research reproduction and academic evaluation and is **not** intended for standalone clinical decision-making prior to prospective multicenter external validation and recalibration.
