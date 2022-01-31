# Day-by-day schedule

Spring 2022
#### Week 1
- [Mon, Jan 10]  Logistics, worksheet (prob review, intro to R)
- [Wed, Jan 12]  [Lecture 1](Notes/1_Probability_regression_review.pdf) (probability and regression review) and then [RegressionExample.ipynb](Code/RegressionExample.ipynb): define expectation, variance, covariance, time series, notation. OLS regression. For the code, we went until almost the end (but did not yet cover the overfitting).
- [Fri, Jan 14]  (asynchronous) [Lecture 2](Notes/2_Stationarity_and_Autocorrelation.pdf) and [Lecture 3](Notes/3_Examples_of_stationary_time_series.pdf), defining stationarity, ACF, ACVF, and giving examples MA(1) and AR(1); 1.4 and 2.1 in the book.

#### Week 2
- [Mon, Jan 17] No school (MLK holiday)
- [Wed, Jan 19] [Lecture 4](Notes/4_PropertiesACF_GPs_strict_stationarity.pdf) on ACF properties and Gaussian Processes and strict stationarity. Then we did the [FirstLookAt_AR_and_MA.ipynb](Code/FirstLookAt_AR_and_MA.ipynb) R notebook which showed AR(1) and MA(1) time series, their ACFs, and then had a very fun game on matching time series realizations with sample ACFs
- [Fri, Jan 21] [Lecture 5](Notes/5_SampleEstimators.pdf) on sample estimators for ACF etc (1.4.1 and 2.4); then [Lecture 6](Notes/6_MultivariateNormal.pdf) on the multivariate normal distribution (see appendices A.2 and A.3); then [Lecture 7](Notes/7_EliminatingTrends.pdf) on decomposition models and eliminating trends (1.5.1). We did lecture 7 up to right before Box-Jenkins differencing

#### Week 3 (almost) back in person
- [Mon, Jan 24] (ONLINE STILL; instructor is in isolation) Section 1.5.2 in book on seasonality; see [Lecture 7](Notes/7_EliminatingTrends.pdf). Demos: [TrendRemoval](Code/TrendRemoval.ipynb)
- [Wed, Jan 26] (ONLINE STILL; instructor is in isolation) 1.6 in book on testing residuals; see [Lecture 8](Notes/8_TestingResiduals.pdf). Demos: [QQPlots](Code/QQPlots.ipynb) and [VisualizeWhiteNoise](Code/VisualizeWhiteNoise.ipynb)
- [Fri, Jan 28] (ONLINE STILL; instructor is in isolation) Sections 2.1--2.3 and 3 of the book; [Lecture 9: ARMA models](9_ARMA_models.pdf). Introduce ARMA(1,1), some calculations, notions of **causal** and **invertible** ARMA processes; linear models, and general ARMA(p,q) models

#### Week 4
- [Mon, Jan 31] Prove ARMA(p,q) is causal iff phi(z) has no roots for |z| <= 1.  Misc discussion of ARMA(p,q). Mostly chapter 3.1
- [Wed, Feb 2] *plan: more ARMA(p,q), mostly ch 3.1*
- [Fri, Feb 4] *plan: ARMA, ch 2 and 3 TBD*
