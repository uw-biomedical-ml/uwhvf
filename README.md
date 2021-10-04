Title: Humphrey Visual Field database 


————————————————————— JSON ————————————————————
Dataset Description: JSON file containing 26,353 Humphrey Visual Field (HVF) tests from 3895 patients and 7463 eyes. This file contains sensitivity values, TD values, age, laterality (left or right eye) and gender when specified. Sensitivity and TD values are stored both in long format (as a vector) and provided as an 8 x 9 matrix. The latter is meant to preserve the original spatial organization of the data, which is particularly useful in spatial-aware processing often employed in machine learning. All data are stored as a right eye. Empty matrix cells are filled with a fixed value (100).

Institution: University of Washington
Data Collection: between 1998 and 2018.

Filename: alldata.json
Description: Dataset of 26,353 HVFs from 3895 patients and 7463 eyes. Data-structure consists of nested dictionaries in JSON file format. 

Data-structure:

“Pts” : number of patients
“Eyes” : number of eyes in dataset
“Hvfs” : number of visual field samples 
“Coords” : Visual field coordinates 

—Patient ID :
——Gender: (M/F)
———Year Collected
————Eye laterality: (R/L)
—————Pt Age 
—————“Hvf” : HVF data in raw vector format
—————“hvf_seq” : HVF data in matrix form
—————“td” : total deviation in raw vector format
—————“td_seq” : total deviation in matrix form
————Eye laterality: (R/L)
—————Pt Age 
—————“Hvf” : HVF data in raw vector format
—————“hvf_seq” : HVF data in matrix form
—————“td” : total deviation in raw vector format
—————“td_seq” : total deviation in matrix form
——————————————————————————————————————————————

————————————————————— CSV ——————————————————————
Filename: VF_Data.csv
Description: same dataset as in the JSON file. Columns are as follows
	- PatID: patient identifier
	- Gender: gender of the patient
	- Eye: laterality (Right/Left)
	- FieldN: sequential test number for each eye (time ordered)
	- Age: patient age at each test (years)
	- Time_from_Baseline: calculated as Age (at test N) - Age (at test 1)
	- MS: Mean Sensitivity
	- MS_Cluster1 to 6: MS for each cluster
	- MTD: Mean Total Deviation
	- PSD: Pattern Standard Deviation
	- MTD_Cluster1 to 6: MTD for each cluster
	- GH: General Height (7th highest TD value)
	- Sens_1 to 54: Sensitivity values for each location
	- TD_1 to 54: Total Deviation values for each location (missing for blind spot locations)
	- PD_1 to 54: Pattern Deviation values for each location (missing for blind spot locations)

Filename: Series_Summary.csv
Description: Summary data for each eye (test series). Columns are as follows
	- PatID: patient identifier
	- Eye: laterality (Right/Left)
	- Gender: gender of the patient
	- Baseline_Age: age at the first test in the series (years)
	- Baseline_MS: MS at the first test
	- Baseline_MTD: MTD at the first test
	- Baseline_PSD: MTD at the first test
	- Baseline_MTD_Cluster1 to 6: MTD at the first test for each cluster
	- Follow_up_length: length of the series in years
	- N_fields: number of tests in the series
	- Interval: average inter-test interval (years)
	- Intercept_MS: linear regression intercept for MS
	- Slope_MS: linear regression slope for MS
	- pvalue_MS: linear regression p-value for MS slope
	- Intercept_MTD: linear regression intercept for MTD
	- Slope_MTD: linear regression slope for MTD
	- pvalue_MTD: linear regression p-value for MTD slope

Filename: Coord_242.csv
Description: Coordinates for a 24-2 grid (right eye). Columns are as follows
	- X: x-coordinate (horizontal) in visual degrees
	- Y: y-coordinate (vertical) in visual degrees
	- Cluster: visual field cluster for each location. Blind spot locations are marked as 0
	- LocID: test location number, as the appear ordered in all the other files.

Filename: All other CSV files
Description: All other CSV files have the same structure. 
	- The rows are  *PatID*_*Eye*
	- The columns are the different locations or clusters of the visual field, following the order in Coord_242.csv

Cluster-wise
- Cluster_Intercept_MS.csv reports the linear regression intercepts of MS over time for each cluster
- Cluster_Slope_MS.csv reports the linear regression slopes of MS over time for each cluster
- Cluster_pvalue_MS.csv reports the p-value for the linear regression slope of MS over time for each cluster
- Cluster_Intercept_MTD.csv reports the linear regression intercepts of MTD over time for each cluster
- Cluster_Slope_MTD.csv reports the linear regression slopes of MTD over time for each cluster
- Cluster_pvalue_MTD.csv reports the p-value for the linear regression slope of MTD over time for each cluster

Point-wise
- Location_Intercept_S.csv reports the linear regression intercepts of sensitivity over time for each location
- Location_Slope_S.csv reports the linear regression slopes of sensitivity over time for each location
- Location_pvalue_S.csv reports the p-value for the linear regression slope of sensitivity over time for each location
- Location_Intercept_TD.csv reports the linear regression intercepts of TD over time for each location
- Location_Slope_TD.csv reports the linear regression slopes of TD over time for each location
- Location_pvalue_TD.csv reports the p-value for the linear regression slope of TD over time for each location

