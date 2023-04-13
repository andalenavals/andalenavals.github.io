---
title: "Propagation of PSF errors in cosmological estimates"
excerpt: "PSF diagnostic functions serve to control systematic uncertainties and quantify PSF biases in cosmological estimates.. <br/><img src='/images/research/DES_thumbnail.jpg'>"
collection: research
author_profile: false
---

Rho-statistics are the two-point correlation function of residual errors from the Point Spread Function (PSF) modeling. Stars are point sources, and the images we obtain from stars are actually a representation of the PSF. Therefore, we can use images of stars for modeling the PSF. The PSF has two main contributions: the optics of the telescope and the atmospheric smearing, and it is position and wavelength-dependent. The PSF needs to be interpolated to the galaxy's position, and this interpolation might introduce errors given the variance of the PSF across the field of view. To study systematic biases that might arise from the interpolation scheme, a set of stars is left out from the PSF modeling. Then, by comparing the shape measurements of those reserved stars with the expected shape using the interpolation scheme, we can obtain residuals of the PSF that will help identify problematic sources, exposures, or regions where the PSF systematics exceed the requirements. Additionally, we can use these residuals as building blocks of PSF residual point correlation functions, which can be propagated in the likelihood analysis to study the consequences on final cosmological estimates.

# PSF errors

Biases in weak gravitational lensing are studied using the linear approximation

$$
\begin{equation}
  \hat{g_{i}}-g^{\rm{true}}_{i}=\mu_{i}g^{\rm{true}}_{i}+c_{i}+\rm{noise},
  \label{eq:biasdef}
\end{equation}
$$

where the mutiplicative bias $\mu_{i}$ and the additive one $c_{i}$ are obtained using a regression for a population of galaxies. To see the effect of miss estimation of PSF, we can consider as an estimator the observerd ellipticity without the correction for the PSF, and make simulations of galaxies with different shear and PSF. For avoiding other sources of biases and see just the PSF ones, we simulate only one galaxy with just a $e_{2}$ and then a shear is applied in the first component, this garantees there is not shape noise.

## PSF size errors
When changing only the size of the PSF we can observe a multiplicative bias contribution
<br/><img src='/images/research/rhostats/psf_size.gif' width="800">

## PSF anisotropy errors
When changing the ellipticity of the PSF, we can observe an additive contribution to the bias, when there is change in the first component of the shear PSF ellipticity, and a subtle multiplicative bias when the PSF is aligned with the galaxy ellipticity as ilustrated below

<br/><img src='/images/research/rhostats/psf_anisotropy.gif' width="800">

In the Y3 analysis of [DES](https://www.darkenergysurvey.org/)  the effects of PSF biases in the likelihood analysis using the shear two point correlation function goes like follows:
$$
\begin{itemize}
\item The multiplicative bias is treated as a nuisance parameter in the likelihood, there is is one for each of the four tomographic bins, and the mean and prior range are determined using simulations
\item The addive bias could be treated similarly, however his contribution can be neglected if we observe the PSF additive contamination to be subdominant.
\end{itemize}
$$