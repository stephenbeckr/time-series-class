
# Day-by-day schedule

Spring 2022
#### Week 1 (review; define ACF and key terms and examples)
- [Mon, Jan 10]  Logistics, worksheet (prob review, intro to R)
- [Wed, Jan 12]  [Lecture 1](Notes/1_Probability_regression_review.pdf) (probability and regression review) and then [RegressionExample.ipynb](Code/RegressionExample.ipynb): define expectation, variance, covariance, time series, notation. OLS regression. For the code, we went until almost the end (but did not yet cover the overfitting).
- [Fri, Jan 14]  (asynchronous) [Lecture 2](Notes/2_Stationarity_and_Autocorrelation.pdf) and [Lecture 3](Notes/3_Examples_of_stationary_time_series.pdf), defining stationarity, ACF, ACVF, and giving examples MA(1) and AR(1); 1.4 and 2.1 in the book.

#### Week 2 (stationarity, trend)
- [Mon, Jan 17] No school (MLK holiday)
- [Wed, Jan 19] [Lecture 4](Notes/4_PropertiesACF_GPs_strict_stationarity.pdf) on ACF properties and Gaussian Processes and strict stationarity. Then we did the [FirstLookAt_AR_and_MA.ipynb](Code/FirstLookAt_AR_and_MA.ipynb) R notebook which showed AR(1) and MA(1) time series, their ACFs, and then had a very fun game on matching time series realizations with sample ACFs
- [Fri, Jan 21] [Lecture 5](Notes/5_SampleEstimators.pdf) on sample estimators for ACF etc (1.4.1 and 2.4); then [Lecture 6](Notes/6_MultivariateNormal.pdf) on the multivariate normal distribution (see appendices A.2 and A.3); then [Lecture 7](Notes/7_EliminatingTrends.pdf) on decomposition models and eliminating trends (1.5.1). We did lecture 7 up to right before Box-Jenkins differencing

#### Week 3 (almost) back in person (trend, seasonality, residual tests, ARMA(1,1) )
- [Mon, Jan 24] (ONLINE STILL; instructor is in isolation) Section 1.5.2 in book on seasonality; see [Lecture 7](Notes/7_EliminatingTrends.pdf). Demos: [TrendRemoval](Code/TrendRemoval.ipynb)
- [Wed, Jan 26] (ONLINE STILL; instructor is in isolation) 1.6 in book on testing residuals; see [Lecture 8](Notes/8_TestingResiduals.pdf). Demos: [QQPlots](Code/QQPlots.ipynb) and [VisualizeWhiteNoise](Code/VisualizeWhiteNoise.ipynb)
- [Fri, Jan 28] (ONLINE STILL; instructor is in isolation) Sections 2.1--2.3 and 3 of the book; [Lecture 9: ARMA models](9_ARMA_models.pdf). Introduce ARMA(1,1), some calculations, notions of **causal** and **invertible** ARMA processes; linear models, and general ARMA(p,q) models

#### Week 4 (ARMA processes)
- [Mon, Jan 31] Prove ARMA(p,q) is causal iff phi(z) has no roots for |z| <= 1.  Misc discussion of ARMA(p,q). Mostly chapter 3.1
- [Wed, Feb 2]  [no school, snow day!]
- [Fri, Feb 4] Example finding coefficients for psi(z), theorem on invertibility of general ARMA(p,q) (no roots of theta in unit ball)

#### Week 5 (ARMA processes)
- [Mon, Feb 7] Define linear processes, Proposition 2.2.1, and Theorem 2.6 (Wold decomposition); Remark 2 in section 3.1 (can usually represent ARMA process as causal and invertible); example with MA(1) with theta=5 and theta=1/5
- [Wed, Feb 9] Shared roots of phi and theta; ACF for ARMA (section 3.2 in the book)
- [Fri, Feb 11] Finish method 2 for ACF for ARMA; introduce partial correlation

#### Week 6 (PACF, forecasting)
- [Mon, Feb 14] Section 3.2 in the book on partial autocorrelation (PACF) function; examples for AR(p)
- [Wed, Feb 16] Mention sample PACF; then start on Forecasting. Discuss generic probabilistic forecasting, and calibration and sharpness. Examples of uncalibrated weather forecasts.  Introduce scoring rules and the logarithmic scoring rule.
  - Since scoring rules are not in our book, see [Evaluating probabilistic forecasts with scoringRules](https://arxiv.org/abs/1709.04743) (userguide for an R package) or [Probabilistic forecasts, calibration and sharpness](https://sites.stat.washington.edu/raftery/Research/PDF/Gneiting2007jrssb.pdf) by Gneiting, Balabdaoui and Raftery 2006.
  - For fun popular press reading, try Nate Silver's "The Signal and the Noise" (2012) which includes, among many topics, a visit to Boulder's NCAR and discussion with CU's CS professor Aaron Clauset
  - The book "Superforecasting" by Philip Tetlock and Dand Gardner (2015) is also entertaining.
- [Fri, Feb 18] In-class **midterm**. This is closed-note, closed-book.  


#### Week 7 (forecasting for time series)
- [Mon, Feb 21] Review scoring rules, proper scoring rules; interval vs point forecasts; loss functions
- [Wed, Feb 23] Forecasting for stationary time series (2.5 and 3.3 in book); mean-squared error and linear estimators and motivation; best linear predictors and best linear unbiased predictors (BLUP)
- [Fri, Feb 25] Details on BLUP, properties (unbiasedness, variance, etc.); brief comments on inverting the sample autocovariance matrix (which is symmetric Toeplitz), e.g., Cholesky, or better, fast and recursive methods like Levinson-Durbin (see `scipy.linalg.solve_toeplitz`). Example with forecasting AR(1).  


#### Week 8 (finish forecasting, start estimation)
- [Mon, Feb 28] Details on Durbin-Levinson algorithm (2.5.3 in book); innovations algorithm (2.5.4, 3.3 for specialized to ARMA process)
- [Wed, Mar 2] Prediction from infinite past (2.5.6). Skip ch 4 for now and start ch 5 on estimation (of parameters of ARMA(p,q)). High-level overview of process (detrend/deseasonalize; estimate; forecast; add back in trend/season). Overview of methods in 5.1.1 -- 5.1.4 (Yule-Walker, Burg, innovations, Hannan-Rissanen). In R, `ar` function does simple estimation methods. Start on details of Yule-Walker
- [Fri, Mar 4] Finish details of Yule-Walker; skip Hannan-Rissanen etc. Introduce Maximum Likelihood Estimation (MLE); start MLE for AR(1)

#### Week 9 (estimation, order selection; spectral methods)
- [Mon, Mar 7] Finish MLE for AR(1). MLE for ARMA(p,1), Gaussian assumptions
- [Wed, Mar 9] Order selection (5.5): FPE, AIC, AICC, BIC. Diagnostic checking (5.3). Start ch 4 (spectral methods)
- [Fri, Mar 11] Did [TimeSeries_ModelSelectionExample.ipynb demo](Demos/TimeSeries_ModelSelectionExample.ipynb) on model order selection. Then start **spectral methods**. Comparing the 4 types of Fourier Transforms: Fourier Transform; Discrete-time Fourier-Transform; Fourier Series; Discrete Fourier Transform (DFT) and FFT. Introduce concept of spectral analysis via [TimeSeries_FrequencyDemo.ipynb demo](Demos/TimeSeries_FrequencyDemo.ipynb) (this was in Python; showed websites with beats and spectrograms, then do basic periodogram on a music clip)

#### Week 10 (spectral methods)
- [Mon, Mar 14] Continue with 4 types of Fourier transforms; details on DFT (section 4.2)
- [Wed, Mar 16] More DFT; Nyquist frequency and aliasing. Spectral densities (4.1)
- [Fri, Mar 18] Power spectral density, Wiener-Khintchine theorem (cf. Proakis DSP book section 14.1). Herglotz theorem (special case of Bochner's theorem), linking properties of ACVF and spectral density. Simple cases (absolute summability of ACVF) and more general case (spectral *distribution*, discrete spectra)

#### Week 11 (spectral methods)
- [Mon, Mar 28] Spectral density examples (white noise, MA(1), AR(1)). Introduce periodogram (4.2)
- [Wed, Mar 30] Periodogram to estimate density: asymptotically unbiased but inconsistent.  Background on Fourier transform: time shift is multiplication by complex exponential in frequency, convolution is multiplication in frequency.
- [Fri, Apr 1] Consistent spectrum estimation via smoothed periodogram. Filtering: bias vs resolution tradeoff. See demos.  Take-home exam assigned.

#### Week 12 (finish spectral methods; start unit roots and the I in ARIMA)
- [Mon, Apr 4] Time-invariant Linear Filters (analogous to LTI systems). Convolution theorem with spectral density; examples with causal ARMA process.
- [Wed, Apr 6] Brief mention of rational approximation of spectral densities (4.4.1) to justify ARMA models.  Spectral leakage demo. Start ch 6 on nonstationary (ARIMA) and seasonal (SARIMA) time series models. Define ARIMA (p,d,q), discuss unit roots. We did the demo [TimeSeries_SpectralMethodsDemo](Demos/TimeSeries_SpectralMethodsDemo.ipynb)
- [Fri, Apr 8] ARIMA(1,1,0) example. Unit roots (6.3), via looking at ACF or via Dickey-Fuller test (which can reject the hypothesis of no unit root). DF hypothesis test example with AR(1). Unit roots for MA models (6.3.2). We did the demo [TimeSeries_NonstationaryAndARIMA](Demos/TimeSeries_NonstationaryAndARIMA.ipynb)

#### Week 13 (forecasting; regression with non-iid residuals)
- [Mon, Apr 11] Forecasting with ARIMA models (6.4)
- [Wed, Apr 13] More forecasting, and forecasting Seasonal ARIMA (6.5). Regression with ARMA errors (6.6), introducing generalized (aka weighted) least squares (GLS).
- [Fri, Apr 15] More GLS, view as whitening. Combined covariance and GLS via MLE (6.6.2) or simple alternating method.  See demos on [ARIMA predictions](Demos/TimeSeries_ARIMApredictions.ipynb) and [GLS](Demos/TimeSeries_GeneralizedLeastSquares.ipynb).

#### Week 14 (multivariate; causality; state-space models)
- [Mon, Apr 18] Ch 8, multivariate time series. Examples, basic definitions and extensions. Most important parts of 8.1 and 8.2. 8.3.3. 8.4 on multivariate ARMA.
- [Wed, Apr 20] Cross-spectrum [skip 8.5-8.7]. Details on Granger causality (not in book), correlation vs causality. Ideal Granger causality vs how it is usually done in practice (ignoring hidden variables). Use `lmtest::grangertest` or `MSBVAR::granger.test` in `R`, for example. We did some demos; see [TimeSeries_MultivariateDemo](Demos/TimeSeries_MultivariateDemo.ipynb)
- [Fri, Apr 22] Ch 9, state-space models. Define basic model, local-level and other examples.

#### Week 15 (more state space models, and start Kalman filter)
- [Mon, Apr 25] AR(1) and ARMA(1,1) as state-space models, covering 9.2 and 9.3. Kalman recursions (9.4) including Kalman filtering (and prediction and smoothing).
- [Wed, Apr 27] More on Kalman recursions (mostly prediction and filtering, skip smoothing). Example with 1D kinematics, projectile with inexact positions and velocities.  See the demo [TimeSeries_KalmanFiltering](Demos/TimeSeries_KalmanFiltering.ipynb).
