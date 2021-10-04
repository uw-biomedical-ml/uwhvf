# A real-world, open source dataset of Humphrey Visual Field from the University of Washington


—————————————————————————————————————————

**Dataset Description:** JSON file containing 26,353 Humphrey Visual Field (HVF) tests from 3895 patients and 7463 eyes. This file contains sensitivity values, TD values, age, laterality (left or right eye) and gender when specified. Sensitivity and TD values are stored both in long format (as a vector) and provided as an 8 x 9 matrix. The latter is meant to preserve the original spatial organization of the data, which is particularly useful in spatial-aware processing often employed in machine learning. All data are stored as a right eye. Empty matrix cells are filled with a fixed value (100).

**Institution:** University of Washington

**Data Collection:** between 1998 and 2018.

**Filename:** alldata.json

**Description:** Dataset of 26,353 HVFs from 3895 patients and 7463 eyes. Data-structure consists of nested dictionaries in JSON file format. 

**Data-structure:**

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

——————————————————————————————————————


