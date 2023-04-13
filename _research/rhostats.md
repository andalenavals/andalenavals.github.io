---
title: "Propagation of PSF errors in cosmological estimates"
excerpt: "PSF diagnostic functions serve to control systematic uncertainties and quantify PSF biases in cosmological estimates.. <br/><img src='/images/research/DES_thumbnail.jpg'>"
collection: research
author_profile: false
---

Rho-statistics are the two-point correlation function of residual errors from the Point Spread Function (PSF) modeling. Stars are point sources, and the images we obtain from stars are actually a representation of the PSF. Therefore, we can use images of stars for modeling the PSF. The PSF has two main contributions: the optics of the telescope and the atmospheric smearing, and it is position and wavelength-dependent. The PSF needs to be interpolated to the galaxy's position, and this interpolation might introduce errors given the variance of the PSF across the field of view. To study systematic biases that might arise from the interpolation scheme, a set of stars is left out from the PSF modeling. Then, by comparing the shape measurements of those reserved stars with the expected shape using the interpolation scheme, we can obtain residuals of the PSF that will help identify problematic sources, exposures, or regions where the PSF systematics exceed the requirements. Additionally, we can use these residuals as building blocks of PSF residual point correlation functions, which can be propagated in the likelihood analysis to study the consequences on final cosmological estimates.

PSF errors
======
Biases in weak gravitational lensing are studied using the linear approximation

$$
\begin{equation}
  \hat{g_{i}}-g^{\rm{true}}_{i}=\mu_{i}g^{\rm{true}}_{i}+c_{i}+\rm{noise},
  \label{eq:biasdef}
\end{equation}
$$

