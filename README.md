[![License](https://img.shields.io/badge/License-BSD%203--Clause-blue.svg)](https://opensource.org/licenses/BSD-3-Clause)
[![JSON Schema](https://img.shields.io/badge/JSON%20Schema-valid-green)](https://json-schema.org/)


# UWHVF: A real-world, open source dataset of Humphrey Visual Field from the University of Washington


**Dataset Description:** JSON file containing 26,353 Humphrey Visual Field (HVF) tests from 3895 patients and 7463 eyes. This file contains sensitivity values, TD values, age, laterality (left or right eye) and gender when specified. Sensitivity and TD values are stored both in long format (as a vector) and provided as an 8 x 9 matrix. The latter is meant to preserve the original spatial organization of the data, which is particularly useful in spatial-aware processing often employed in machine learning. All visual field data are stored as a right eye. Empty matrix cells are filled with a fixed value (100).

**Institution:** University of Washington

**Data Collection:** between 1998 and 2018.

**Filename:** alldata.json

**Description:** Dataset of 26,353 HVFs from 3895 patients and 7463 eyes. Data-structure consists of nested dictionaries in JSON file format. 

**Schema:** JSON Schema [available](https://github.com/uw-biomedical-ml/uwhvf/blob/master/schema.json)

![Example HVFs](https://github.com/uw-biomedical-ml/uwhvf/raw/master/example.png)
Example HVFs with the raw float values extracted in the left column, the rounded values in the middle, and the HVF printout on the right column.
