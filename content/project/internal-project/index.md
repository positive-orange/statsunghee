---
date: "2016-04-27T00:00:00Z"
external_link: ""
image:
  caption: ECM procedure for the EBI method
  focal_point: Smart
# slides: example
summary: We propose a new framework of envelope block-wise imputation (EBI) to address block-wise missingness. The proposed method considers canonical correlations of multi-source data and impute the missing parts by estimating canonical correlations.
tags:
- EBI
title: Enveloped Block-wise Imputation
url_code: ""
url_pdf: ""
url_slides: ""
url_video: ""
---

## **Motivation**

* Integrating information from multiple sources of the same observation is one way to ensure the power of the analysis under cost constraints. 
* In the case of the data integration, the small overlapped observations may hinder the feasibility of such integrative analysis. 
* Matrix completion can be considered to a problem of a missing imputation.
* We proposed a **multiple block-wise matrix completion method** so called "Envelope Block-wise Imputation (**EBI**)".

## **Envelope method**

The Envelope method proposed on the context of the multivariate linear model with a view toward prediction and coefficient estimation. 
* By using a material variation provides information that is directly relevant to the regression, 
* while the immaterial variation is essentially irrelevant to the regression and serves to increase estimative variation.
* A **simultaneous envelope method** proposed for joint reduction of the responses and predictors.
* The method is simultaneously separating the material and immaterial variation in the responses and in the predictors.

## **Envelope Blockwise Imputation (EBI) method**

### Block-wise missing structure

Assume that two data sets are partially overlapped into the common samples where
* Common part: $\mathbf{X}_{k}^{c}, \enspace k=1,2$, 
* Unique part: $\hspace{0.8em} \textbf{X}_{k}^{u}, \enspace k=1,2$,
* Missing part: $\hspace{0.45em} \textbf{X}_{k}^{\star}, \enspace k=1,2$.

The block-wise missing structure is displayed in the first figure on this page.

### ECM algorithm

We apply Expectation Conditional-Maximization (ECM) algorithm to update our parameters under the Simultaneous Envelope structure as follows. 

* First, **initiate** the envelope parameters from the overlapped (common) samples.
* Next, calculate expected values of the missing parts with unique and common samples (**E-step**).
* Lastly, update the envelope parameters in **CM-step** until convergence.

We assume normality on the data sets for m.l.e. derivations.

![ECM algorithm](algorithm.png)

### Simulation results

* For comparison, we use six different methods including the EBI method.
  * “**CCA**” uses a standard canonical correlation analysis (CCA) method.
  * “**ENV**” uses the simultaneous envelope method to estimate canonical correlations, corresponding directions, and regression coefficients.
  * “**ORA**” means that we use an oracle data set that has all samples without any missing parts. Thus, the “ORA” estimator could be judged as an ideal case.
  * “**COM**” estimator means we only use common samples to estimate the canonical estimators.
  * “**EBI-2set**” uses the proposed EBI method on two block-wise missing data sets.

* Also, we use three different scenarios for the covariance structures.
  * "**M1**" assumes identity structures
  * "**M2**" assumes general covariance structures (which have non-overlapping eigen-values on matrix decomposition)
  * "**M3**" assumes randomly generated covariance structures

* Table 1 tabulates true and estimated canonical correlations under the unique sample size is 100 and 500. The commomn sample size is 30. 

* The estimators use the oracle samples (ORA) to achieve the closest correlations to the true canonical correlation. In contrast, the canonical correlations that use only common samples (COM) are overestimated than the true canonical correlations. Meanwhile, the EBI method achieves better estimators for the true canonical correlations.

![ECM algorithm](output_correlation.png)

* The Figure 4 displays Frobenius norm losses of three subplots by the model assumptions (M1, M2, M3).

* The proposed EBI method accomplishes better results in terms of the matrix completion problem. Particularly, (M3) shows a competitive performance of the “EBI” method even with we just considered randomized covariance structure without envelope assumptions.

![ECM algorithm](output_Frob_norm.png)

* We also compare our proposed EBI method to a structured matrix completion method(Cai, Cai & Zhang,2016) which assumed low-rank structure for only one block-wise missing part.

* The EBI method always attains lower Frobenius norm losses in different dimensions of data sets and true canonical correlations.

![ECM algorithm](output_comparison_SMC.png)

### Real data analysis

* We apply the proposed EBI method to impute randomized missing parts of multi-view data on breast cancer from the cancer genome atlas (TCGA) data.
* We consider two different data sources: gene expression (GE) and DNA methylation (ME).
* Since the ME data set has 802 complete subjects, we impute missed GE subjects with 348 matched (common) subjects using the EBI and SMC methods and compare the estimated canonical correlations.

* Table 5 represents the standardized Frobenius norm losses of the EBI method and the SMC method with 50 replicates for each envelope dimension. The EBI method achieves signiﬁcantly small losses in different envelope dimensions.
![ECM algorithm](real_correlation.png)
* In Figure 7, we display the first estimated canonical correlations in different envelope dimensions from 2 to 20. The estimated canonical correlation of EBI-1set achieves much closer than the SMC method.


![ECM algorithm](real_corr_plot.png)



