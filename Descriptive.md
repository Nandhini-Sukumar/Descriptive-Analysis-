```python
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt


```


```python
# This Dataset contains only the numerical values:

Data = pd.read_csv("C:/Users/SasiKumar/Documents/winequality_white.csv")
Data.head()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>fixed_acidity</th>
      <th>volatile_acidity</th>
      <th>citric_acid</th>
      <th>residual_sugar</th>
      <th>chlorides</th>
      <th>free_sulfur_dioxide</th>
      <th>total_sulfur_dioxide</th>
      <th>density</th>
      <th>ph</th>
      <th>sulphates</th>
      <th>alcohol</th>
      <th>quality</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>7.0</td>
      <td>0.27</td>
      <td>0.36</td>
      <td>20.7</td>
      <td>0.045</td>
      <td>45.0</td>
      <td>170.0</td>
      <td>1.0010</td>
      <td>3.00</td>
      <td>0.45</td>
      <td>8.8</td>
      <td>6</td>
    </tr>
    <tr>
      <th>1</th>
      <td>6.3</td>
      <td>0.30</td>
      <td>0.34</td>
      <td>1.6</td>
      <td>0.049</td>
      <td>14.0</td>
      <td>132.0</td>
      <td>0.9940</td>
      <td>3.30</td>
      <td>0.49</td>
      <td>9.5</td>
      <td>6</td>
    </tr>
    <tr>
      <th>2</th>
      <td>8.1</td>
      <td>0.28</td>
      <td>0.40</td>
      <td>6.9</td>
      <td>0.050</td>
      <td>30.0</td>
      <td>97.0</td>
      <td>0.9951</td>
      <td>3.26</td>
      <td>0.44</td>
      <td>10.1</td>
      <td>6</td>
    </tr>
    <tr>
      <th>3</th>
      <td>7.2</td>
      <td>0.23</td>
      <td>0.32</td>
      <td>8.5</td>
      <td>0.058</td>
      <td>47.0</td>
      <td>186.0</td>
      <td>0.9956</td>
      <td>3.19</td>
      <td>0.40</td>
      <td>9.9</td>
      <td>6</td>
    </tr>
    <tr>
      <th>4</th>
      <td>7.2</td>
      <td>0.23</td>
      <td>0.32</td>
      <td>8.5</td>
      <td>0.058</td>
      <td>47.0</td>
      <td>186.0</td>
      <td>0.9956</td>
      <td>3.19</td>
      <td>0.40</td>
      <td>9.9</td>
      <td>6</td>
    </tr>
  </tbody>
</table>
</div>




```python
# Counts of column

Data.sum().to_frame()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>0</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>fixed_acidity</th>
      <td>33574.75000</td>
    </tr>
    <tr>
      <th>volatile_acidity</th>
      <td>1362.82500</td>
    </tr>
    <tr>
      <th>citric_acid</th>
      <td>1636.87000</td>
    </tr>
    <tr>
      <th>residual_sugar</th>
      <td>31305.15000</td>
    </tr>
    <tr>
      <th>chlorides</th>
      <td>224.19300</td>
    </tr>
    <tr>
      <th>free_sulfur_dioxide</th>
      <td>172939.00000</td>
    </tr>
    <tr>
      <th>total_sulfur_dioxide</th>
      <td>677690.50000</td>
    </tr>
    <tr>
      <th>density</th>
      <td>4868.74609</td>
    </tr>
    <tr>
      <th>ph</th>
      <td>15616.13000</td>
    </tr>
    <tr>
      <th>sulphates</th>
      <td>2399.27000</td>
    </tr>
    <tr>
      <th>alcohol</th>
      <td>51498.88000</td>
    </tr>
    <tr>
      <th>quality</th>
      <td>28790.00000</td>
    </tr>
  </tbody>
</table>
</div>




```python
# Mean value for each column

Data.mean().to_frame()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>0</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>fixed_acidity</th>
      <td>6.854788</td>
    </tr>
    <tr>
      <th>volatile_acidity</th>
      <td>0.278241</td>
    </tr>
    <tr>
      <th>citric_acid</th>
      <td>0.334192</td>
    </tr>
    <tr>
      <th>residual_sugar</th>
      <td>6.391415</td>
    </tr>
    <tr>
      <th>chlorides</th>
      <td>0.045772</td>
    </tr>
    <tr>
      <th>free_sulfur_dioxide</th>
      <td>35.308085</td>
    </tr>
    <tr>
      <th>total_sulfur_dioxide</th>
      <td>138.360657</td>
    </tr>
    <tr>
      <th>density</th>
      <td>0.994027</td>
    </tr>
    <tr>
      <th>ph</th>
      <td>3.188267</td>
    </tr>
    <tr>
      <th>sulphates</th>
      <td>0.489847</td>
    </tr>
    <tr>
      <th>alcohol</th>
      <td>10.514267</td>
    </tr>
    <tr>
      <th>quality</th>
      <td>5.877909</td>
    </tr>
  </tbody>
</table>
</div>




```python

```


```python
# Median Value for each column

Data.median().to_frame()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>0</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>fixed_acidity</th>
      <td>6.80000</td>
    </tr>
    <tr>
      <th>volatile_acidity</th>
      <td>0.26000</td>
    </tr>
    <tr>
      <th>citric_acid</th>
      <td>0.32000</td>
    </tr>
    <tr>
      <th>residual_sugar</th>
      <td>5.20000</td>
    </tr>
    <tr>
      <th>chlorides</th>
      <td>0.04300</td>
    </tr>
    <tr>
      <th>free_sulfur_dioxide</th>
      <td>34.00000</td>
    </tr>
    <tr>
      <th>total_sulfur_dioxide</th>
      <td>134.00000</td>
    </tr>
    <tr>
      <th>density</th>
      <td>0.99374</td>
    </tr>
    <tr>
      <th>ph</th>
      <td>3.18000</td>
    </tr>
    <tr>
      <th>sulphates</th>
      <td>0.47000</td>
    </tr>
    <tr>
      <th>alcohol</th>
      <td>10.40000</td>
    </tr>
    <tr>
      <th>quality</th>
      <td>6.00000</td>
    </tr>
  </tbody>
</table>
</div>




```python
# Mode Value for each column

Data.mode()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>fixed_acidity</th>
      <th>volatile_acidity</th>
      <th>citric_acid</th>
      <th>residual_sugar</th>
      <th>chlorides</th>
      <th>free_sulfur_dioxide</th>
      <th>total_sulfur_dioxide</th>
      <th>density</th>
      <th>ph</th>
      <th>sulphates</th>
      <th>alcohol</th>
      <th>quality</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>6.8</td>
      <td>0.28</td>
      <td>0.3</td>
      <td>1.2</td>
      <td>0.044</td>
      <td>29.0</td>
      <td>111.0</td>
      <td>0.992</td>
      <td>3.14</td>
      <td>0.5</td>
      <td>9.4</td>
      <td>6</td>
    </tr>
  </tbody>
</table>
</div>




```python
# Maximum value of the columns

Data.max().to_frame()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>0</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>fixed_acidity</th>
      <td>14.20000</td>
    </tr>
    <tr>
      <th>volatile_acidity</th>
      <td>1.10000</td>
    </tr>
    <tr>
      <th>citric_acid</th>
      <td>1.66000</td>
    </tr>
    <tr>
      <th>residual_sugar</th>
      <td>65.80000</td>
    </tr>
    <tr>
      <th>chlorides</th>
      <td>0.34600</td>
    </tr>
    <tr>
      <th>free_sulfur_dioxide</th>
      <td>289.00000</td>
    </tr>
    <tr>
      <th>total_sulfur_dioxide</th>
      <td>440.00000</td>
    </tr>
    <tr>
      <th>density</th>
      <td>1.03898</td>
    </tr>
    <tr>
      <th>ph</th>
      <td>3.82000</td>
    </tr>
    <tr>
      <th>sulphates</th>
      <td>1.08000</td>
    </tr>
    <tr>
      <th>alcohol</th>
      <td>14.20000</td>
    </tr>
    <tr>
      <th>quality</th>
      <td>9.00000</td>
    </tr>
  </tbody>
</table>
</div>




```python
# Minimum value of each column

Data.min().to_frame()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>0</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>fixed_acidity</th>
      <td>3.80000</td>
    </tr>
    <tr>
      <th>volatile_acidity</th>
      <td>0.08000</td>
    </tr>
    <tr>
      <th>citric_acid</th>
      <td>0.00000</td>
    </tr>
    <tr>
      <th>residual_sugar</th>
      <td>0.60000</td>
    </tr>
    <tr>
      <th>chlorides</th>
      <td>0.00900</td>
    </tr>
    <tr>
      <th>free_sulfur_dioxide</th>
      <td>2.00000</td>
    </tr>
    <tr>
      <th>total_sulfur_dioxide</th>
      <td>9.00000</td>
    </tr>
    <tr>
      <th>density</th>
      <td>0.98711</td>
    </tr>
    <tr>
      <th>ph</th>
      <td>2.72000</td>
    </tr>
    <tr>
      <th>sulphates</th>
      <td>0.22000</td>
    </tr>
    <tr>
      <th>alcohol</th>
      <td>8.00000</td>
    </tr>
    <tr>
      <th>quality</th>
      <td>3.00000</td>
    </tr>
  </tbody>
</table>
</div>




```python
# Findout the Range of the column
max(Data['quality']) - min(Data['quality'])
```




    6




```python
# Quantile function

Data.quantile(0.25)

```




    [fixed_acidity             6.300000
     volatile_acidity          0.210000
     citric_acid               0.270000
     residual_sugar            1.700000
     chlorides                 0.036000
     free_sulfur_dioxide      23.000000
     total_sulfur_dioxide    108.000000
     density                   0.991723
     ph                        3.090000
     sulphates                 0.410000
     alcohol                   9.500000
     quality                   5.000000
     Name: 0.25, dtype: float64,
     fixed_acidity             6.80000
     volatile_acidity          0.26000
     citric_acid               0.32000
     residual_sugar            5.20000
     chlorides                 0.04300
     free_sulfur_dioxide      34.00000
     total_sulfur_dioxide    134.00000
     density                   0.99374
     ph                        3.18000
     sulphates                 0.47000
     alcohol                  10.40000
     quality                   6.00000
     Name: 0.5, dtype: float64,
     fixed_acidity             7.3000
     volatile_acidity          0.3200
     citric_acid               0.3900
     residual_sugar            9.9000
     chlorides                 0.0500
     free_sulfur_dioxide      46.0000
     total_sulfur_dioxide    167.0000
     density                   0.9961
     ph                        3.2800
     sulphates                 0.5500
     alcohol                  11.4000
     quality                   6.0000
     Name: 0.75, dtype: float64]




```python
# Describe Function

Data.describe()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>fixed_acidity</th>
      <th>volatile_acidity</th>
      <th>citric_acid</th>
      <th>residual_sugar</th>
      <th>chlorides</th>
      <th>free_sulfur_dioxide</th>
      <th>total_sulfur_dioxide</th>
      <th>density</th>
      <th>ph</th>
      <th>sulphates</th>
      <th>alcohol</th>
      <th>quality</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>count</th>
      <td>4898.000000</td>
      <td>4898.000000</td>
      <td>4898.000000</td>
      <td>4898.000000</td>
      <td>4898.000000</td>
      <td>4898.000000</td>
      <td>4898.000000</td>
      <td>4898.000000</td>
      <td>4898.000000</td>
      <td>4898.000000</td>
      <td>4898.000000</td>
      <td>4898.000000</td>
    </tr>
    <tr>
      <th>mean</th>
      <td>6.854788</td>
      <td>0.278241</td>
      <td>0.334192</td>
      <td>6.391415</td>
      <td>0.045772</td>
      <td>35.308085</td>
      <td>138.360657</td>
      <td>0.994027</td>
      <td>3.188267</td>
      <td>0.489847</td>
      <td>10.514267</td>
      <td>5.877909</td>
    </tr>
    <tr>
      <th>std</th>
      <td>0.843868</td>
      <td>0.100795</td>
      <td>0.121020</td>
      <td>5.072058</td>
      <td>0.021848</td>
      <td>17.007137</td>
      <td>42.498065</td>
      <td>0.002991</td>
      <td>0.151001</td>
      <td>0.114126</td>
      <td>1.230621</td>
      <td>0.885639</td>
    </tr>
    <tr>
      <th>min</th>
      <td>3.800000</td>
      <td>0.080000</td>
      <td>0.000000</td>
      <td>0.600000</td>
      <td>0.009000</td>
      <td>2.000000</td>
      <td>9.000000</td>
      <td>0.987110</td>
      <td>2.720000</td>
      <td>0.220000</td>
      <td>8.000000</td>
      <td>3.000000</td>
    </tr>
    <tr>
      <th>25%</th>
      <td>6.300000</td>
      <td>0.210000</td>
      <td>0.270000</td>
      <td>1.700000</td>
      <td>0.036000</td>
      <td>23.000000</td>
      <td>108.000000</td>
      <td>0.991723</td>
      <td>3.090000</td>
      <td>0.410000</td>
      <td>9.500000</td>
      <td>5.000000</td>
    </tr>
    <tr>
      <th>50%</th>
      <td>6.800000</td>
      <td>0.260000</td>
      <td>0.320000</td>
      <td>5.200000</td>
      <td>0.043000</td>
      <td>34.000000</td>
      <td>134.000000</td>
      <td>0.993740</td>
      <td>3.180000</td>
      <td>0.470000</td>
      <td>10.400000</td>
      <td>6.000000</td>
    </tr>
    <tr>
      <th>75%</th>
      <td>7.300000</td>
      <td>0.320000</td>
      <td>0.390000</td>
      <td>9.900000</td>
      <td>0.050000</td>
      <td>46.000000</td>
      <td>167.000000</td>
      <td>0.996100</td>
      <td>3.280000</td>
      <td>0.550000</td>
      <td>11.400000</td>
      <td>6.000000</td>
    </tr>
    <tr>
      <th>max</th>
      <td>14.200000</td>
      <td>1.100000</td>
      <td>1.660000</td>
      <td>65.800000</td>
      <td>0.346000</td>
      <td>289.000000</td>
      <td>440.000000</td>
      <td>1.038980</td>
      <td>3.820000</td>
      <td>1.080000</td>
      <td>14.200000</td>
      <td>9.000000</td>
    </tr>
  </tbody>
</table>
</div>




```python

```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>0</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>fixed_acidity</th>
      <td>33574.75000</td>
    </tr>
    <tr>
      <th>volatile_acidity</th>
      <td>1362.82500</td>
    </tr>
    <tr>
      <th>citric_acid</th>
      <td>1636.87000</td>
    </tr>
    <tr>
      <th>residual_sugar</th>
      <td>31305.15000</td>
    </tr>
    <tr>
      <th>chlorides</th>
      <td>224.19300</td>
    </tr>
    <tr>
      <th>free_sulfur_dioxide</th>
      <td>172939.00000</td>
    </tr>
    <tr>
      <th>total_sulfur_dioxide</th>
      <td>677690.50000</td>
    </tr>
    <tr>
      <th>density</th>
      <td>4868.74609</td>
    </tr>
    <tr>
      <th>ph</th>
      <td>15616.13000</td>
    </tr>
    <tr>
      <th>sulphates</th>
      <td>2399.27000</td>
    </tr>
    <tr>
      <th>alcohol</th>
      <td>51498.88000</td>
    </tr>
    <tr>
      <th>quality</th>
      <td>28790.00000</td>
    </tr>
  </tbody>
</table>
</div>




```python

```
