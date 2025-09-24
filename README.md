# integers

**In**terpretable **t**ime **s**eries autoregression for periodicity quantification (**ints** ⮕ **integers**). [[Project description](https://xinychen.github.io/tutorial/integers.pdf)]

[![MIT License](https://img.shields.io/badge/license-MIT-green.svg)](https://opensource.org/licenses/MIT)
[![repo size](https://img.shields.io/github/repo-size/xinychen/integers.svg)](https://github.com/xinychen/integers/archive/master.zip)
[![GitHub stars](https://img.shields.io/github/stars/xinychen/integers.svg?logo=github&label=Stars&logoColor=white)](https://github.com/xinychen/integers)

<h6 align="center">Made by Xinyu Chen • :globe_with_meridians: <a href="https://xinychen.github.io">https://xinychen.github.io</a></h6>

<br>

<div align="center">
<img src="https://github.com/xinychen/integers/blob/main/graphics/integers.png" alt="logo" width="300px"/>
</div>

<br>

Which datasets we could provide for experimental evaluation?

- 🦉 [NYC ridesharing dataset (2019-2024)](https://github.com/xinychen/integers/tree/main/NYC-ridesharing) (622 MB, see [TLC trip record data](https://www.nyc.gov/site/tlc/about/tlc-trip-record-data.page)) 
- 🦉 [NYC yellow taxi dataset (2011-2024)](https://doi.org/10.5281/zenodo.17089134) (455 MB, see [TLC trip record data](https://www.nyc.gov/site/tlc/about/tlc-trip-record-data.page)) 
- 🦉 [Manhattan subway rideship dataset (2024)](https://github.com/xinychen/integers/tree/main/Manhattan-subway) (1.1 MB, see [MTA subway hourly ridership: 2020-2024](https://data.ny.gov/Transportation/MTA-Subway-Hourly-Ridership-2020-2024/wujg-7c2s/about_data)) 
- 🦉 [Manhattan bikesharing dataset (2024)](https://github.com/xinychen/integers/tree/main/NYC-micromobility) (1.7 MB, see [Citi bike system data - NYC](https://s3.amazonaws.com/tripdata/index.html)) 
- 🦉 [Chicago ridesharing dataset (2018-2024)](https://github.com/xinychen/integers/tree/main/Chicago-ridesharing) (92 MB, see [Transportation Network Providers (TNP) - Trips (2018 - 2022)](https://data.cityofchicago.org/Transportation/Transportation-Network-Providers-Trips-2018-2022-/m6dm-c72p/about_data)) 
- 🦉 [Hangzhou metro passenger flow dataset (2019)](https://github.com/xinychen/integers/tree/main/Hangzhou-metro) (4.7 MB, see [Hangzhou metro passenger data - 2019](https://doi.org/10.5281/zenodo.3145404)) 
- 🦉 [North America climate variable dataset (1980-2019)](https://doi.org/10.5281/zenodo.17080922) (3.0 GB, see [Daymet](https://daac.ornl.gov/DAYMET)) 
- 🦉 [Sea surface temperature dataset (1980-2019)](https://doi.org/10.5281/zenodo.17081473) (1.3 GB, see [Sea surface temperature optimum interpolation](https://www.ncei.noaa.gov/data/sea-surface-temperature-optimum-interpolation/v2.1/access/avhrr/)) 
- 🦉 [Wikipedia page view dataset (January 2024)](https://doi.org/10.5281/zenodo.17070469) (4.7 GB, see [Analytics datasets: Pageviews](https://dumps.wikimedia.org/other/pageviews/readme.html))

These mobility and climate datasets are formatted as multidimensional tensors and saved as NumPy arrays in the compressed form, i.e., `.npz`. 

<br>

<p align="center">
<img align="middle" src="https://github.com/xinychen/integers/blob/main/graphics/integers_frame.png" width="550" />
</p>

<p align = "center"> <b>Figure 1</b>. Conceptual overview of the diverse open datasets for periodicity quantification.</p>

<br>

In urban systems, how to align the mobility datasets of different travel modes (e.g., ridesharing, taxi, subway, and bikesharing) with the same spatial resolution? For instance, Manhattan has hundreds of subway and bikesharing stations and 69 taxi areas, one can first project subway and bikesharing stations onto taxi areas and then aggregate trip counts.

<br>

<p align="center">
<img align="middle" src="https://github.com/xinychen/integers/blob/main/graphics/Manhattan_stations.png" width="800" />
</p>

<p align = "center"> <b>Figure 2</b>. (A) Subway stations are projected onto 52 areas in Manhattan. (B) Bikesharing stations are projected onto 67 areas in Manhattan.</p>

<br>

#

### Interactive Visualization Tool

What is the time series periodicity? How to get started the modeling process with machine learning and optimization? One of the most intuitive ways might be anotating the time series periodicity on the interactive visualization tool.

<br>

<p align="center">
<a href="https://xinychen.github.io/ts_periodicity">
<img align="middle" src="https://github.com/xinychen/integers/blob/main/graphics/ts_periodicity.png" width="750" />
</a>
</p>

<p align = "center"> <b>Figure 3</b>. Anotating the time series periodicity of hourly ridesharing trip time series in Chicago since April 1, 2024.</p>

<br>

While human mobility exhibits clear regularity in **hourly**, **daily**, and **weekly cycles**, the greatest challenge lies in accurately modeling these patterns.

<br>

#

### Sparse Autoregression Explained

#### i) Statement

This work claims the practical contribution in the following ways:

- The classical autoregression can capture auto-correlations, but we do not know which are the dominant auto-correaltions.
- The sparse autoregression can limit the number of nonzero auto-correlations by imposing a sparsity level, allowing one to identify the dominant auto-correlations (e.g., time series periodicity).

<br>

<p align="center">
<a href="https://xinychen.github.io/slides/autoregression.pdf">
<img align="middle" src="https://github.com/xinychen/integers/blob/main/graphics/autoregression.png" width="750" />
</a>
</p>

<p align = "center"> <b>Figure 4</b>. Identification of the dominant auto-correlations from time series through sparse autoregression. The sparsity constraint allows one to find the dominant auto-correlated time lags (e.g., <img style="display: inline;" src="https://latex.codecogs.com/svg.latex?&space;k=1,24,167,168"/>).</p>

<br>

#### ii) Sample Time Series

The sample time series of as shown in Figures 1 and 2 is available at `Chicago-ridesharing/rideshare_ts.txt`.

```python
import pandas as pd
import numpy as np

data = pd.read_csv('rideshare_ts.txt', sep = ' ', header = None, index_col = 0, names = ['trip_count'])
```

One can draw the two-week time series as follows,

```python
import matplotlib.pyplot as plt

fig = plt.figure(figsize = (6, 1.4))
ax = fig.add_subplot(1, 1, 1)
plt.plot(data['trip_count'].values[: 2 * 7 * 24], color = 'purple', alpha = 0.75, linewidth = 2)
plt.xticks(np.arange(0, 24 * 7 * 3 + 1, 7 * 24))
plt.xlabel('Time (hour)')
plt.ylabel('Trip count')
plt.grid(axis = 'both', linestyle='dashed', linewidth = 0.1, color = 'gray')
ax.tick_params(direction = 'in')
ax.set_xlim([-1, 24 * 7 * 2])
plt.show()
```

<br>

#### iii) Mixed-Integer Optimization for Sparse Autoregression

We use `cplex` as the mixed-integer optimization solver in our Python implementation. The setting of sparse autoregression includes `d` (order) and `tau` (sparsity level). The optimization problem of sparse autoregression can be reformulated as follows,

<p align = "center"><img align="middle" src="https://latex.codecogs.com/svg.latex?&space;\min_{\boldsymbol{w},\,\boldsymbol{\beta}}\,\,\underbrace{\sum_{t=d+1}^{T}\left(x_{t}-\sum_{k=1}^{d}w_{k}x_{t-k}\right)^2}_{\text{\color{red}autoregression}}\quad\text{s.t.}\,\,\underbrace{-\alpha\cdot\beta_{k}\leq\,w_{k}\leq\alpha\cdot\beta_{k}}_{\text{\color{blue}bound}},\,\,\,\underbrace{\sum_{k=1}^{d}\beta_{k}\leq\tau}_{\text{\color{blue}sparsity}},\,\,\,\underbrace{\beta_{k}\in\{0,1\}}_{\text{\color{blue}binary}}"/></p>

by introducing binary decision variables.

<br>

```python
import numpy as np
from docplex.mp.model import Model

def obj(x, w, d):
    T = x.shape[0]
    loss = 0
    for t in range(d, T):
        loss += (x[t] - np.inner(w, np.flip(x[t - d : t]))) ** 2
    return loss

def sparse_ar(x, d, tau):
    model = Model()
    alpha = 1
    T = x.shape[0]
    w = [model.continuous_var(name = f'w_{k}') for k in range(d)]
    beta = [model.binary_var(name = f'beta_{k}') for k in range(d)]
    model.minimize(model.sum((x[t] - model.sum(w[k] * x[t - k - 1] for k in range(d))) ** 2 for t in range(d, T)))
    model.add_constraint(model.sum(beta[k] for k in range(d)) <= tau)
    for k in range(d):
        model.add_constraint(w[k] <= alpha * beta[k])
        model.add_constraint(w[k] >= - alpha * beta[k])
    solution = model.solve()
    return np.array(solution.get_values(w))
```

On the sample time series as mentioned above, please reproduce our results by running the following codes:

```python
import numpy as np

d = 168
for tau in range(1, 7):
    w = sparse_ar(data['trip_count'].values[: 2 * 7 * 24], d, tau)
    print('tau = {}'.format(tau))
    print('Objective function f = {}'.format(obj(x, w, d)))
    ind = np.where(w != 0)[0].tolist()
    print('Support set: {}'.format(ind))
    print('Nonzero coefficients: {}'.format(w[ind]))
    print()
```

Here, the result at the sparsity level `tau = 6` is given by

```python
tau = 6
Objective function f = 50844056.30946854
Support set: [0, 22, 23, 33, 166, 167]
Nonzero coefficients: [0.29769501 0.00173922 0.03533629 0.00832573 0.16595001 0.48356377]
```

<br>

# 

### References

<ul style="padding-left: 20px;">
  <li style="font-size: 14px; color: gray; margin-bottom: 15px;">
    Xinyu Chen, Vassilis Digalakis Jr, Lijun Ding, Dingyi Zhuang, Jinhua Zhao (2025). <a href="https://arxiv.org/abs/2506.22895">Interpretable time series autoregression for periodicity quantification</a>. arXiv preprint arXiv:2506.22895.
  </li>

  <li style="font-size: 14px; color: gray; margin-bottom: 15px;">
    Xinyu Chen, Qi Wang, Yunhan Zheng, Nina Cao, HanQin Cai, Jinhua Zhao (2025). <a href="http://arxiv.org/abs/2508.03747">Data-driven discovery of mobility periodicity for understanding urban systems</a>. arXiv preprint arXiv:2508.03747.
  </li>

</ul>


### Support

- For any questions and feedback, please contact Dr. Xinyu Chen (chenxy346@gmail.com).
- If you like this repository, share it with your friends and colleagues.

<br>
