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

Assume that two data sets are partially overlapped into the common samples where
* Common part: $\mathbf{X}_{k}^{c}, \enspace k=1,2$, 
* Unique part: $\hspace{0.8em} \textbf{X}_{k}^{u}, \enspace k=1,2$,
* Missing part: $\hspace{0.45em} \textbf{X}_{k}^{\star}, \enspace k=1,2$. 

We use Expectation Conditional-Maximization (ECM) algorithm to update our parameters under the Simultaneous Envelope structure. 

* First, we **initiate** the envelope parameters from the overlapped (common) samples.
* Next, we calculate expected values of the missing parts with unique and common samples (**E-step**).
* Finally, we update the parameters in **CM-step** until convergence.



## Simultaneous Envelope Structure


Inline math: $$ \varphi = \dfrac{1+\sqrt5}{2}= 1.6180339887… $$

#Block math:

#$$ \sigma(t) = \cfrac{1}{1 + e^{-t}} $$