# Background
Species depend on specific environmental conditions to survive, making them vulnerable to habitat loss, degradation, and fragmentation driven by land use change. Habitat suitability models (HSMs) help address this challenge by linking species occurrences with environmental variables to map areas of potential habitat and guide conservation planning. This study focuses on Antrostomus vociferus (Eastern Whip-poor-will), a cryptic and nocturnal bird listed as threatened in Canada that has experienced a 35.2% population decline over the past 30 years. Traditional survey methods often fail to detect this species due to its nocturnal behavior and tendency to occur away from roads, making modeling approaches particularly valuable for understanding its habitat distribution. To estimate suitable habitat, this study compares two HSM approaches using the same occurrence and environmental datasets: a knowledge-driven Multi-Criteria Decision Analysis (MCDA) model and a data-driven Maximum Entropy (MaxEnt) model. MCDA integrates environmental variables based on expert-derived weightings, while MaxEnt uses machine learning to identify environmental conditions associated with known occurrences. By comparing these approaches, the study evaluates how expert knowledge and statistical inference differ in identifying suitable habitat and representing the ecological niche of A. vociferus.

![Whip-poor-will being banded by GBLT staff](wpw.jpg)



## Data and Methods
### Data
The study was conducted on protected lands managed by the Georgian Bay Land Trust (GBLT) along the eastern shore of Georgian Bay, Ontario, within the Georgian Bay Ecoregion of the Great Lakes–St. Lawrence Forest Region. This landscape contains a diverse mosaic of mixed, deciduous, and coniferous forests shaped by varied geology, soils, and terrain, creating structurally complex habitats important for Antrostomus vociferus (Eastern Whip-poor-will). Occurrence records from 2000–2025 were compiled from Georgian Bay Land Trust surveys, the Ontario Natural Heritage Information Centre (NHIC), and the Global Biodiversity Information Facility (GBIF). Environmental predictors included topography, land cover, distance to water and openings, canopy structure metrics, forest age, and dominant tree species derived from national forest monitoring datasets. All spatial layers were standardized to a common coordinate system, masked to the study area, and screened for multicollinearity before modelling.

### Methods
Habitat suitability for A. vociferus was estimated using two approaches: a machine-learning Maximum Entropy (MaxEnt) model and a knowledge-driven Multi-Criteria Decision Analysis (MCDA) framework. MaxEnt used occurrence records and environmental predictors to estimate the probability of suitable habitat across the study area, with model performance optimized through bias correction, regularization multiplier tuning, and five-fold cross validation. The MCDA model classified each environmental variable into suitability classes based on ecological literature and expert judgement, then combined them using weighted overlay derived from an Analytical Hierarchy Process. Model outputs were converted into five habitat suitability classes and compared by evaluating predicted area in each class and by generating a difference map to identify spatial agreement and disagreement between the two modelling approaches.

### Results
The MaxEnt model produced a moderate predictive performance (test AUC ≈ 0.73), with distance to opening emerging as the strongest predictor of Antrostomus vociferus habitat suitability, followed by canopy cover variability, slope, forest age, and tree species. Suitability decreased sharply as distance from forest openings increased, while areas with greater canopy heterogeneity and both young and older forest stands showed higher predicted suitability. The resulting MaxEnt suitability map identified several habitat hotspots across the Georgian Bay Land Trust study area, including regions not represented in the occurrence dataset. 

![Jackknife Results for MaxEnt](jackknife_rm2.png)

![Variable Importance for MaxEnt](variable_importance_rm2.png)

![MaxEnt Predicted Suitability](MaxEnt_Layout.png)

The MCDA model produced a comparable suitability surface using expert-derived weights, with canopy cover variability, distance to openings, and forest age ranked as the most influential variables and an overall point-prevalence validation accuracy of 0.63. 

![MCDA Predicted Suitability](MCDA_Layout.png)

Comparison of the two models showed broadly similar spatial patterns, though MaxEnt predicted more unsuitable habitat overall and highlighted several additional suitability hotspots, while MCDA predicted slightly more diffuse areas of moderate suitability across the landscape.

![MCDA Predicted Suitability](Difference_Layout.png)

![Area Comparison](comb_sum.png)
