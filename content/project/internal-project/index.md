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

The Envelope method proposed on the context of the multivariate linear model with a view toward prediction and coefficient estimation. 
* By using a material variation provides information that is directly relevant to the regression, 
* while the immaterial variation is essentially irrelevant to the regression and serves to increase estimative variation.
* A **simultaneous envelope method** proposed for joint reduction of the responses and predictors.
* The method is simultaneously separating the material and immaterial variation in the responses and in the predictors.

Assume that two data sets are partially overlapped into the common samples where
* Common part: $\mathbf{X}_{k}^{c}, \enspace k=1,2$, 
* Unique part: $\hspace{0.8em} \textbf{X}_{k}^{u}, \enspace k=1,2$,
* Missing part: $\hspace{0.45em} \textbf{X}_{k}^{\star}, \enspace k=1,2$. 

We use Expectation Conditional-Maximization (ECM) algorithm to update our parameters under the Simultaneous Envelope structure as follows. 

* First, **initiate** the envelope parameters from the overlapped (common) samples.
* Next, calculate expected values of the missing parts with unique and common samples (**E-step**).
* Lastly, update the envelope parameters in **CM-step** until convergence.

For m.l.e. derivations, we assume normality on the data sets.

