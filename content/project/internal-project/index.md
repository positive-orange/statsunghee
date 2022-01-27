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

For comparison we used other estimators as follows.

* CCA-ORA 
* CCA-COM
* ENV-ORA
* ENV-COM
* EBI-2set

![ECM algorithm](output_correlation.png)

![ECM algorithm](output_Frob_norm.png)

![ECM algorithm](output_comparison_SMC.png)

### Real data analysis

![ECM algorithm](real_correlation.png)

![ECM algorithm](real_corr_plot.png)



