# time-series-forecasting-sarimax
Implementation and evaluation of a SARIMAX model for time series forecasting.

# **What is SARIMAX**?
SARIMAX (Seasonal AutoRegressive Integrated Moving Average with eXogenous regressors) is a powerful statistical model used for **time series forecasting**. It builds on the ARIMA model by **adding seasonal components** and allowing the use of **external (exogenous) variables** to improve prediction accuracy.

Its components are:

* **Seasonal (S):** Captures recurring patterns like weekly or monthly trends.
* **AutoRegressive (AR):** Uses past values (lags) of the series to predict future ones.
* **Integrated (I):** Applies differencing between a value and its previous one to make the series **stationary**. This differencing can be of first or second order. The number of times differencing is applied corresponds to the “I” parameter in SARIMA — for example, if differencing needs to be applied twice (i.e., the difference of the difference), the value of I will be 2, indicating a second-order differencing.
* **Moving Average (MA):**  Models the relationship between the current value and past forecast errors. Instead of relying on past values like in the AR component, the MA part adjusts predictions based on how much the model previously over- or under-estimated. For example, if the model underpredicted by 10 units yesterday, it may correct today's forecast accordingly.
* **eXogenous Regressors (X):** Incorporates external influences (e.g., holidays, promotions).

### What is a stationary series?

A **stationary time series** is one whose **statistical properties—mean, variance, and autocorrelation—remain constant over time**. Stationarity is essential for many time series models, including ARIMA and SARIMAX, to produce reliable forecasts. If the series is not stationary, the model might misinterpret trends or seasonal effects as meaningful patterns, leading to poor predictions. The **"Integrated"** part of SARIMAX refers to the differencing process used to **transform a non-stationary series into a stationary one** before modeling.
