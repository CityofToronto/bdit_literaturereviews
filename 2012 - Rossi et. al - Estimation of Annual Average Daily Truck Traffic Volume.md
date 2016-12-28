## Estimation of Annual Average Daily Truck Traffic Volume. Uncertainty treatment and data collection requirements (2012)

#### Authors
* Rossi, Riccardo - University of Padova
* Gastaldi, Massimiliano - University of Padova
* Gecchele, Gregorio - University of Padova
* Kikuchi, Shinya - Virginia Tech

#### Research Question
Estimating AADTs of trucks from STPCs, along with measures of uncertainty to identify need for further data collection.

#### Data Sources Used
* Automatic Traffic Recorders (ATRs) - for use in generating seasonality profiles
* Short Term Period Counts (SPTCs) - to generate AADTs where ATRs do not exist

#### Methodology

##### Old Approach (FHWA)
AADTs are currently estimated by the FHWA using the following four-step methodology:

1. Grouping of ATR sites with similar temporal variations using a variety of varying techniques:
  - grouped by reciprocal of seasonal adjustment factors (below).
  
2. Determining seasonal adjustment factors for each group:
  - Seasonal Adjustment Factors, f: f(month i, dow j, site k) = AADT(site k) / ADT(month i, dow j, site k)

3. Assign road section with SPTC to one of groups defined in *1*.

4. Apply seasonality adjustment to SPTC to arrive at AADT.

##### New Approach (FHWA)

1. Group ATR sites using *fuzzy C-means algorithm* based on seasonal adjustment factors.
  - "fuzzy" indicative of non-restrictive boundaries between groups.
  - C determines number of groups
  - algorithm provides degree to which each ATR belongs to each group

2. Assign road segment with STPC to *one or more* groups using neural networks.

3. Calculate measures of uncertainty associated with this assignment.
  - N(m): measure of non-specificity (i.e. with how much certainty can this SPTC be said to belong to this road group?)
  - D(m): measure of conflict (i.e. one time period indicates one road group, while another time period indicates a different road group)

4. Estimated AADT using seasonal adjustment factors weighted by assignment to road groups.

##### Case Study

- Study used 2005 data from 50 ATRs in Venice to establish road groups. 
- Same dataset was sampled to form SPTCs of varying duration (24 - 72 hrs) and then used to estimate AADTs. 
- Used 70% training / 30% test dataset.
- 18 seasonality factors: 3 day-types (Weekdays, Saturdays, Sundays) and 6 month-types (Jan-Feb, Mar-Apr, etc.)
- Algorithm tested different values of C (2 to 20) and evaluated them using the Dunn Index, Silhouette Measure, Pseudo F Statistic, and G2 Index: resulted in C = 5.

#### Findings
- Look into details of "fuzzy" clustering for time-of-day approach.
- Validation approach used in this study may be useful, even at more granular level.
- Need to take a closer look into how artificial neural networks (ANN) may be useful for assignment of new road segments to existing road groups.

#### References of Interest
* FHWA. (2001). Traffic Monitoring Guide. U.S. Department of Transportation.
* Tsapakis, I., Schneider, W., Bolbol, A., & Skarlatidou, A. (2011). Discriminant Analysis for Assigning Short-Term Counts to Seasonal Adjustment Factor Groupings. Transportation Research Record, 2256, 112-119.
* Li, M.-T., Zhao, F., & Chow, L. (2006). Assignment of Seasonal Factor Categories to Urban Coverage Count Stations Using a Fuzzy Decision Tree. Journal of Transportation Engineering, 132(8), 654-662.
* Gulati, B. (1995). Precision of AADT Estimates from Short Period Traffic Counts. M.S. thesis, University of Regina. Saskatchewan, Canada.

