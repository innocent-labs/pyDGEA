pyDGEA is a python package that performs differential gene expression analysis with bulk RNA-seq data. 
You have to note that this package is just a mimic of DESeq2 and PyDESeq2. We are neither majors nor experts. 

Please refer to the following links : https://github.com/owkin/PyDESeq2 and https://hbctraining.github.io/DGE_workshop/lessons/04_DGE_DESeq2_analysis.html

There may be some errors in the code. We will fix as soon as possible. 
If you notice anything strange, please feel free to contact us at any time.

## Contents

1. Installation
2. How to use
3. License

---
## Installation
pyDGEA can be installed from PyPI using pip
```
pip install pyDGEA
```

---
## How to use
Import pydgea_dataset from pydgea.pdd. You may need to import pandas.
```python
import pandas as pd
from pydgea.pdd import pydgea_dataset
```
Create pydgea_dataset object. Here, count_data is a pandas.DataFrame containing raw counts, metadata is a pandas.DataFrame containing information about samples, and design is a string representing design formula.
```python
pdd = pydgea_dataset(count_data, metadata, design)
```
Estimate size factors, dispersions and log2 fold changes.
```python
pdd.dgea()
```
Perform wald tests for differential expression.
```python
contrast = ['factor of interest', 'treat', 'control']
res = pdd.summary(contrast)
```

## License
pyDGEA is released under an MIT license.

