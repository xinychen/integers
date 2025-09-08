# integers

**In**terpretable **t**ime **s**eries autoregression for periodicity quantification (**ints** ⮕ **integers**).

[![MIT License](https://img.shields.io/badge/license-MIT-green.svg)](https://opensource.org/licenses/MIT)
[![repo size](https://img.shields.io/github/repo-size/xinychen/integers.svg)](https://github.com/xinychen/integers/archive/master.zip)
[![GitHub stars](https://img.shields.io/github/stars/xinychen/integers.svg?logo=github&label=Stars&logoColor=white)](https://github.com/xinychen/integers)

<h6 align="center">Made by Xinyu Chen • :globe_with_meridians: <a href="https://xinychen.github.io">https://xinychen.github.io</a></h6>

<br>

<div align="center">
<img src="https://github.com/xinychen/integers/blob/main/graphics/integers.png" alt="logo" width="300px"/>
</div>

<br>

Which datasets we could provide for examination?

🦉🦉 [NYC ridesharing dataset](https://github.com/xinychen/integers/tree/main/NYC-ridesharing) (622 MB, see [source](https://www.nyc.gov/site/tlc/about/tlc-trip-record-data.page)) 🦉🦉 [Manhattan subway rideship dataset](https://github.com/xinychen/integers/tree/main/Manhattan-subway) (1.1 MB, see [source](https://data.ny.gov/Transportation/MTA-Subway-Hourly-Ridership-2020-2024/wujg-7c2s/about_data)) 🦉🦉 [Manhattan bikesharing dataset](https://github.com/xinychen/integers/tree/main/NYC-micromobility) (1.7 MB, see [source](https://s3.amazonaws.com/tripdata/index.html)) 🦉🦉 [Chicago ridesharing dataset](https://github.com/xinychen/integers/tree/main/Chicago-ridesharing) (92 MB, see [source](https://data.cityofchicago.org/Transportation/Transportation-Network-Providers-Trips-2018-2022-/m6dm-c72p/about_data)) 🦉🦉 [Hangzhou metro passenger flow dataset](https://github.com/xinychen/integers/tree/main/Hangzhou-metro) (4.7 MB, see [source](https://doi.org/10.5281/zenodo.3145404)) 🦉🦉 [North America climate variable dataset](https://doi.org/10.5281/zenodo.17080922) (3.0 GB, see [source](https://daac.ornl.gov/DAYMET)) 🦉🦉 [Sea surface temperature dataset](https://doi.org/10.5281/zenodo.17081473) (1.3 GB, see [source](https://www.ncei.noaa.gov/data/sea-surface-temperature-optimum-interpolation/v2.1/access/avhrr/)) 🦉🦉 [Wikipedia page view dataset](https://doi.org/10.5281/zenodo.17070469) (4.7 GB, see [source](https://dumps.wikimedia.org/other/pageviews/readme.html))

#

### Interactive Visualization Tool

What is time series periodicity? How to get started the modeling process with machine learning and optimization? One of the most intuitive ways might be anotating the time series periodicity on the interactive visualization tool.

<br>

<p align="center">
<a href="https://xinychen.github.io/ts_periodicity">
<img align="middle" src="https://github.com/xinychen/integers/blob/main/graphics/ts_periodicity.png" width="750" />
</a>
</p>

<p align = "center"> <b>Figure 1</b>. Anotating the time series periodicity of hourly ridesharing trip time series in Chicago since April 1, 2024.</p>

<br>

While human mobility exhibits clear regularity in **hourly**, **daily**, and **weekly cycles**, the greatest challenge lies in accurately modeling these patterns.

<br>

#

### Sparse Autoregression Explained

This work claims the practical contribution in the following ways:

- The classical autoregression can capture auto-correlations, but we do not know which are the dominant auto-correaltions.
- The sparse autoregression can limit the number of nonzero auto-correlations by imposing a sparsity level, allowing one to identify the dominant auto-correlations (e.g., time series periodicity).

<br>

<p align="center">
<a href="https://xinychen.github.io/slides/autoregression.pdf">
<img align="middle" src="https://github.com/xinychen/integers/blob/main/graphics/autoregression.png" width="750" />
</a>
</p>

<p align = "center"> <b>Figure 2</b>. Identification of the dominant auto-correlations from time series through sparse autoregression. The sparsity constraint allows one to find the dominant auto-correlated time lags (e.g., k = 1, 24, 167, 168).</p>

<br>

# 

### References

<ul style="padding-left: 20px;">
  <li style="font-size: 14px; color: gray; margin-bottom: 15px;">
    Xinyu Chen, Vassilis Digalakis Jr, Lijun Ding, Dingyi Zhuang, Jinhua Zhao (2025). <a href="https://arxiv.org/abs/2506.22895">Interpretable time series autoregression for periodicity quantification</a>. arXiv preprint arXiv:2506.22895.
  </li>

  <li style="font-size: 14px; color: gray; margin-bottom: 15px;">
    Xinyu Chen, Qi Wang, Yunhan Zheng, Nina Cao, HanQin Cai, Jinhua Zhao (2025). <a href="http://arxiv.org/abs/2508.03747">Data-driven discovery of mobility periodicity for understanding urban transportation systems</a>. arXiv preprint arXiv:2508.03747.
  </li>

</ul>


### Support

- For any questions and feedback, please contact Dr. Xinyu Chen (chenxy346@gmail.com).
- If you like this repository, share it with your friends and colleagues.

<br>
