# EHR Policy Impact Analysis using Difference-in-Differences and Propensity Score Matching

### A Causal Inference Approach to Evaluating Healthcare Technology Adoption

## Project Overview

This project explores the relationship between the implementation timing of the **Medicaid Electronic Health Record (EHR) Incentive Program** and EHR adoption across U.S. states.

The objective is to investigate whether states that implemented the program earlier experienced different changes in EHR adoption compared with states that implemented it later.

Since policy implementation was not randomly assigned, the analysis uses two causal inference techniques:

- **Difference-in-Differences (DiD)** to compare changes in EHR adoption between early- and late-implementation states.
- **Propensity Score Matching (PSM)** to improve comparability between the groups based on observed pre-policy characteristics.

The project also explores how **Retrieval-Augmented Generation (RAG) and Large Language Models (LLMs)** can provide additional context for interpreting healthcare policy outcomes.

## Research Question

**Did earlier implementation of the Medicaid EHR Incentive Program lead to greater improvements in EHR adoption compared with later implementation?**

The analysis investigates whether differences in implementation timing are associated with measurable changes in healthcare technology adoption.

## Methodology

### 1. Data Collection and Preprocessing

The analysis uses state-level EHR adoption data across multiple years, along with information on Medicaid EHR Incentive Program implementation timing.

Key preprocessing steps include:

- Organizing state-level observations into a longitudinal dataset.
- Identifying early- and late-implementation states.
- Defining treatment and post-policy indicators.
- Examining pre-policy adoption patterns.
- Preparing variables for regression analysis and propensity score estimation.

### 2. Difference-in-Differences (DiD)

Difference-in-Differences estimates how EHR adoption changed over time in early-implementation states relative to later-implementation states.

The basic regression specification is:

\[
Y_{it} = \beta_0 + \beta_1 Treatment_i + \beta_2 Post_t + \beta_3(Treatment_i \times Post_t) + \epsilon_{it}
\]

Where:

- \(Y_{it}\): EHR adoption rate for state \(i\) at time \(t\).
- \(Treatment_i\): Indicator for early-implementation states.
- \(Post_t\): Indicator for the post-policy period.
- \(\beta_3\): Difference-in-Differences estimate.

The analysis examines the **parallel trends assumption**, which is important for interpreting DiD estimates causally.

### 3. Propensity Score Matching (PSM)

Because states may differ in their characteristics before policy implementation, Propensity Score Matching is used to improve comparability between early- and late-implementation states.

The approach involves:

1. Estimating propensity scores using logistic regression and pre-policy characteristics.
2. Matching states with similar estimated probabilities of early implementation.
3. Assessing covariate balance and overlap between groups.
4. Re-estimating the DiD model using the matched sample.
5. Comparing estimates before and after matching.

PSM helps reduce observed selection bias, although it cannot eliminate bias from unobserved confounding factors.

### 4. RAG and LLM-Based Policy Interpretation

The project additionally explores Retrieval-Augmented Generation to support interpretation of the statistical findings.

Relevant healthcare policy documents can be retrieved and supplied as context to an LLM to investigate:

- Differences in state-level policy implementation.
- Eligibility requirements and administrative considerations.
- Potential barriers to EHR adoption.
- Factors that may help explain variation in adoption trends.

**The RAG component supports contextual interpretation; causal effect estimation remains the responsibility of the statistical models.**

## Tools and Technologies

| Category | Technologies |
|---|---|
| Programming | Python |
| Data Processing | Pandas, NumPy |
| Statistical Modeling | Statsmodels, Scikit-learn |
| Causal Inference | Difference-in-Differences, Propensity Score Matching |
| Visualization | Matplotlib, Seaborn |
| AI/NLP | RAG, Large Language Models |
| Development | Jupyter Notebook |

## Key Findings

The exploratory analysis suggested that early-implementation states did not necessarily experience larger improvements in EHR adoption than later-implementation states during the selected comparison period.

The analysis also demonstrated the importance of accounting for baseline differences between states when evaluating policy outcomes.

These findings should be interpreted cautiously because policy timing, observational confounding, and the assumptions underlying DiD and PSM can affect causal interpretation.

## Limitations

- State-level observational data cannot establish causality without additional assumptions.
- Propensity Score Matching adjusts only for observed characteristics.
- Difference-in-Differences relies on appropriate comparison groups and plausible parallel trends.
- Staggered policy implementation can complicate conventional DiD estimation.
- Policy documents retrieved through RAG provide context rather than independent causal evidence.

## Future Enhancements

- Extend the analysis using staggered-adoption DiD estimators.
- Incorporate additional state-level economic and healthcare characteristics.
- Perform robustness checks and sensitivity analyses.
- Evaluate alternative propensity score matching strategies.
- Expand document retrieval to provide evidence-grounded explanations of policy implementation differences.

## Research Significance

This project demonstrates how statistical modeling and causal inference methods can be applied to real-world healthcare policy questions.

By combining DiD, PSM, and LLM-assisted document analysis, the project explores both **quantitative policy evaluation** and **contextual interpretation of results**.

The broader goal is to move beyond predictive analytics toward understanding how policy decisions and technology adoption relate to measurable outcomes.

## Author

**Manasa Ganesh**

Master of Science in Data Science  
Texas A&M University

[GitHub](https://github.com/manasaganesh27)
