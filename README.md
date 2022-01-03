[![License](https://img.shields.io/badge/License-BSD%203--Clause-blue.svg)](https://opensource.org/licenses/BSD-3-Clause)
[![JSON Schema](https://img.shields.io/badge/JSON%20Schema-valid-green)](https://github.com/uw-biomedical-ml/uwhvf/blob/master/schema.json)
[![Datasheet](https://img.shields.io/badge/Datasheet-available-green)](https://github.com/uw-biomedical-ml/uwhvf/blob/master/datasheet.md)


# UWHVF: A real-world, open source dataset of Humphrey Visual Fields (HVF) from the University of Washington

If you use this dataset, please cite:

`Giovanni Montesano, Andrew Chen, Randy Lu, Cecilia S. Lee, Aaron Y. Lee; UWHVF: A Real-World, Open Source Dataset of Perimetry Tests From the Humphrey Field Analyzer at the University of Washington. Trans. Vis. Sci. Tech. 2022;11(1):2. doi: https://doi.org/10.1167/tvst.11.1.1.`


**Dataset Description:** JSON file containing 28,943 Humphrey Visual Field (HVF) tests from 3,871 patients and 7,428 eyes. This file contains sensitivity values, TD values, age, laterality (left or right eye) and gender when specified. Sensitivity and TD values are stored both in long format (as a vector) and provided as an 8 x 9 matrix. The latter is meant to preserve the original spatial organization of the data, which is particularly useful in spatial-aware processing often employed in machine learning. All visual field data are stored as a right eye. Empty matrix cells are filled with a fixed value (100).

**Institution:** University of Washington

**Data Collection:** between 1998 and 2018.

**Filename:** alldata.json

**Description:** Dataset of 26,353 HVFs from 3895 patients and 7463 eyes. Data-structure consists of nested dictionaries in JSON file format. 

**Schema:** [JSON Schema](https://json-schema.org/) is available and [describes the dataset structure and data dictionary.](https://github.com/uw-biomedical-ml/uwhvf/blob/master/schema.json) 

**Datasheet for datasets:** As recommended by [Gebru et al.](https://arxiv.org/abs/1803.09010), we have provided a [structured datasheet](https://github.com/uw-biomedical-ml/uwhvf/blob/master/datasheet.md).

# Example Visual Fields
![Example HVFs](https://github.com/uw-biomedical-ml/uwhvf/raw/master/example.png)
Example HVFs with the raw float values extracted in the left column, the rounded values in the middle, and the HVF printout on the right column.


# Example Python Code 
```python
import json
import numpy as np

# Load data
with open("alldata.json") as fin:
  dat = json.loads(fin.read())

# Basic statistics
print(f"Total of {dat['pts']} patients, {dat['eyes']} eyes, and {dat['hvfs']} HVFs")
# Expected output: Total of 3871 patients, 7428 eyes, and 28943 HVFs

print(f"Age of first HVF of the right eye for patient 647: {dat['data']['647']['R'][0]['age']}")
# Expected output: Age of first HVF of the right eye for patient 647: 52.79671457905544

print(np.array(dat['data']['647']['R'][0]['hvf']))
# Expected output:
# [[100.   100.   100.    26.34  23.73  22.84  24.19 100.   100.  ]
#  [100.   100.    26.25  27.22  25.67  26.18  27.01  26.24 100.  ]
#  [100.    22.2   28.17  29.2   28.44  27.58  28.51  28.02  25.68]
#  [ 20.4   27.41  29.73  30.02  30.93  30.36  30.64  21.    27.89]
#  [ 20.45  25.88  28.9   32.17  31.89  30.91  28.8    0.    27.43]
#  [100.    27.16  29.98  32.74  29.95  32.07  29.84  26.99  27.3 ]
#  [100.   100.    26.88  29.43  29.82  28.64  29.81  28.24 100.  ]
#  [100.   100.   100.    28.88  27.3   26.82  28.18 100.   100.  ]]

print(np.array(dat['data']['647']['R'][0]['td']))
# Expected output:
# [[100.   100.   100.    -3.23  -5.88  -6.43  -4.72 100.   100.  ]
#  [100.   100.    -4.77  -4.51  -6.26  -5.42  -4.09  -4.29 100.  ]
#  [100.    -8.91  -4.39  -4.18  -5.29  -5.85  -4.3   -3.97  -5.51]
#  [ -9.04  -4.48  -3.82  -4.45  -3.83  -4.12  -3.21  21.    -4.07]
#  [ -9.04  -6.13  -4.78  -2.51  -3.16  -3.94  -5.34   0.    -4.91]
#  [100.    -4.35  -3.12  -1.36  -4.67  -2.36  -3.99  -6.09  -5.  ]
#  [100.   100.    -5.13  -3.57  -3.65  -4.73  -3.24  -4.27 100.  ]
#  [100.   100.   100.    -2.46  -4.54  -5.23  -3.82 100.   100.  ]]
```

