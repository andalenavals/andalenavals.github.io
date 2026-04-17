---
layout: page
title: "MomentsML"
description: Custom connected neuronal networks to accurately predict graviational shear
img: assets/images/research/euclid_thumbnail.jpg
importance: 1
category: work
collection: research
author_profile: false
date: 2023-03-01
---

MomentsML is a machine learning method designed to provide accurate shear estimates. It involves training a shallow neural network using realistic simulations with known shear values, to recover the shear signal. This is a challenging process given the multiple sources of noise and biases, such as PSF errors, blending of galaxies, detector effects, low signal-to-noise ratios, galaxy morphologies, and others.

The Euclid Satellite, which aims to study the dark exotic components of the universe and reveal insights about cosmological tensions, uses MomentsML as one of its three independent shear measurement methods.

# Toy model of a simple inverse regression

In this example, a simple network is created to inverse regress the function  
$ f(\theta) = \sqrt{1.0 + \theta^{2}} $.

This means we want to predict $ \hat{\theta} $, given a set of noisy measurements of $ f(\theta) $.

We created 3D mock data with the structure `(ncases, nreas, nfeats)`:
- **ncases**: number of target values  
- **nreas**: number of realizations (different noise draws)  
- **nfeats**: number of features  

Two feature setups are tested:
- $ (f(\theta) + n) $
- $ (f(\theta) + n, n) $

---

## Point estimate inverse regression

Training of a neural network with:
- one hidden layer (5 neurons)
- one output node
- loss functions: **MSE** and **MSB**
- using the two feature sets mentioned above

![Using MSE](/assets/images/research/momentsml/point_noise_regression_animation_2feats_mse/validation/inverse_regression.gif)

![Using MSB](/assets/images/research/momentsml/point_noise_regression_animation_2feats_msb/validation/inverse_regression.gif)

---

## Point estimate inverse regression with Dropout

Training of a neural network with:
- one hidden layer (5 neurons)
- one output node
- **MSB loss function**
- different dropout probabilities

![Dropout probability 0.2](/assets/images/research/momentsml/point_noise_regression_dropout_animation_2feats_msb_dp0.20/validation/inverse_regression.gif)

![Dropout probability 0.4](/assets/images/research/momentsml/point_noise_regression_dropout_animation_2feats_msb_dp0.40/validation/inverse_regression.gif)

---
