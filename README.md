# Isotope Ratio Method (IRM)
This repository contains supplementary material for the article [Assessing Uncertainty in Plutonium Production Estimates Based on the Isotope Ratio Method](https://doi.org/10.1080/08929882.2022.2060599).
Here we provide several jupyter notebooks to illustrate the methods we describe in the manuscript.
We cannot provide a complete, integrated implentation, since this would require the reactor simulation code `SERPENT 2`, which is not distributed with an open source license (http://montecarlo.vtt.fi).

## IRM Implementation
The jupyter notebook [`irm-demonstration.ipynb`](irm-implementation/irm-demonstration.ipynb) explains the IRM reconstruction procedure as we implemented it for the analysis presented in the manuscript.
All functions defined in the notebook are also defined a [separate file](irm-implementation/average_batch_irm.py) so that they can be used without the jupyter notebook.
Example data is provided to enable users to run the notebook in its current state.

The [`irm_with_samples.ipynb`](irm-with-samples/irm_with_samples.ipynb) notebook shows how the IRM implementation is applied to the results of a set of reactor simulations with varied input parameters.

## Cross-Section Uncertainty
The jupyter notebook [`xs_uncertainty.ipynb`](cross-section-uncertainties/xs_uncertainty.ipynb) illustrates how the uncertainty intervals for the cross-section parameters were estimated.
It also shows how we transformed the unifromly distributed samples generated by the Sobol sequence into normally distributed samples for the cross-section parameters.

## Tolerance Intervals
The jupyter notebook [`tolerance_intervals.ipynb`](tolerance-intervals/tolerance_intervals.ipynb) uses a subset of our data to illustrate how and why we calculate non-parametric tolerance intervals for the plutonium estimates.

## Senitivity Analysis
The `SALib` package was used to compute the global sensitivity indices.
Examples on how to use it can be found in the documentation (https://salib.readthedocs.io/en/latest/)
It also provides an implementation of the Sobol sequence that can be used to input parameter samples.
