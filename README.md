# Geographic Flight Delay Patterns
This research analyzes the effect of the geographical dispersion of U.S. airports on flight delay patterns using statistical and machine learning methods. Based on a large database of flight data, the research applies several regression and ARMA time series modeling to investigate the comparative significance of regional, temporal, and operational factors in influencing flight delays. Arrival and departure delay-specific regression models are specified, and variable definitions are provided. The results indicate that geographic areas, in conjunction with meteorological conditions and transportation disruptions, impose considerable impacts on both arrival and departure delays. The findings' implications call for region-specific delay reduction strategies and form the basis of more efficient delay forecasting methods.

### Crash Data Analysis and Trends Identification

I conduct in-depth analysis and modeling of on time data to identify trends and patterns from aviation. By analyzing historical on time data, we aim to pinpoint specific conditions that may effect the delay of some of these flights. This data-driven approach allows us to make informed decisions from the consumers about choosing their next flight and from the aviation companies on how they can undermine the overall delay time.

### Methodology
Variable Definitions and Model Specification

A. Arrival Delay (ARR_DELAY) Model

Dependent Variable:

ARR_DELAY: Arrival delay in minutes.

Independent Variables:

DEST_REGION: Region of destination (categorical; dummy variables required).

DEST_AIRPORT_ID: Destination airport ID (categorical; dummy encoding or clustering if too many categories).

OP_CARRIER_AIRLINE_ID: Operating carrier airline ID (categorical).

IS_WEEKEND: Dummy variable (1 if flight was on a weekend, 0 otherwise).

ACTUAL_ELAPSED_TIME: Actual flight duration in minutes.

ARR_TIME: Scheduled or actual arrival time (numeric or categorical time blocks).

CARRIER_DELAY, WEATHER_DELAY, NAS_DELAY, SECURITY_DELAY, LATE_AIRCRAFT_DELAY: Components of delay by cause (all numeric).

** i indexes individual flights and t indexes time (day).**

Regression Model:

ARR_DELAYit =β0 +β1 DEST_REGIONi +β2 DEST_AIRPORT_IDi +β3 OP_CARRIER_AIRLINE_IDi +β4 IS_WEEKENDt +β5 ACTUAL_ELAPSED_TIMEit +β6 ARR_TIMEit +β7 CARRIER_DELAYit +β8 WEATHER_DELAYit +β9 NAS_DELAYit +β10 SECURITY_DELAYit +β11 LATE_AIRCRAFT_DELAYit +ϵit

B. Departure Delay (DEP_DELAY) Model

Dependent Variable:

DEP_DELAY: Departure delay in minutes.

Independent Variables:

ORIGIN_REGION: Region of origin (categorical; dummy variables required).

ORIGIN_AIRPORT_ID: Origin airport ID (categorical).

OP_CARRIER_AIRLINE_ID: Operating carrier airline ID (categorical).

IS_WEEKEND: Dummy variable (1 if Saturday or Sunday, 0 otherwise).

ACTUAL_ELAPSED_TIME: Actual flight duration in minutes.

DEP_TIME: Scheduled or actual departure time (continuous or binned).

CARRIER_DELAY, WEATHER_DELAY, NAS_DELAY, SECURITY_DELAY, LATE_AIRCRAFT_DELAY: Components of delay by cause (all numeric).

** i indexes individual flights and t indexes time (day).**

Regression Model:

DEP_DELAYit =β0 +β1 ORIGIN_REGIONi +β2 ORIGIN_AIRPORT_IDi +β3 OP_CARRIER_AIRLINE_IDi +β4 IS_WEEKENDt +β5 ACTUAL_ELAPSED_TIMEit +β6 DEP_TIMEit +β7 CARRIER_DELAYit +β8 WEATHER_DELAYit +β9 NAS_DELAYit +β10 SECURITY_DELAYit +β11 LATE_AIRCRAFT_DELAYit +ϵit

Note:

Categorical variables (regions, airports, airlines) are converted handled as fixed effects. Delay components are expected to have a positive association with the dependent variable.
