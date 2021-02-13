# Data analysis

## Useful links

- [Python org](https://www.python.org/)
- [Pandas documentation](https://pandas.pydata.org/docs/index.html#)
- [Numpy](https://numpy.org/)
- [Jupyter](https://jupyter.org)

## Jupyter notebook

### Installation

Official installation guidance is here https://jupyter.org/install. I am using Python3.9.

```shell
python3.9 -m pip install notebook
```

### Usage

Use this command to open it.

```
jupyter notebook
```

## Pandas

### Installation

```
pip install pandas
```

### Usage

```py
import pandas as pd

# Python codes come here
```

## if / else logic

In SAS, if/then logic can be used to create new columns. Reference: https://pandas.pydata.org/docs/getting_started/comparison/comparison_with_sas.html

```sas
data tips;
    set tips;
    format bucket $4.;

    if total_bill < 10 then bucket = 'low';
    else bucket = 'high';
run;
```

The same operation in pandas can be accomplished using the `where` method from `numpy`.

```
In [12]: tips["bucket"] = np.where(tips["total_bill"] < 10, "low", "high")

In [13]: tips.head()
Out[13]: 
   total_bill   tip     sex smoker  day    time  size bucket
0       14.99  1.01  Female     No  Sun  Dinner     2   high
1        8.34  1.66    Male     No  Sun  Dinner     3    low
2       19.01  3.50    Male     No  Sun  Dinner     3   high
3       21.68  3.31    Male     No  Sun  Dinner     2   high
4       22.59  3.61  Female     No  Sun  Dinner     4   high
```

This is the same of `case when` in SQL.
