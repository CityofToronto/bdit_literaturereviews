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
  - D(m): measure of conflict (i.e. 

4. Estimated AADT using seasonal adjustment factors weighted by assignment to road groups.

#### Findings
Summarize conclusions/findings of article succinctly, focusing on outcomes relevant to your own research.

#### References of Interest
List other papers referenced in this article that may potentially be of interest to you.
