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

🦉 [NYC ridesharing dataset](https://github.com/xinychen/integers/tree/main/NYC-ridesharing) [[Source](https://www.nyc.gov/site/tlc/about/tlc-trip-record-data.page)] 🦉 [Chicago ridesharing dataset](https://github.com/xinychen/integers/tree/main/Chicago-ridesharing) [[Source](https://data.cityofchicago.org/Transportation/Transportation-Network-Providers-Trips-2018-2022-/m6dm-c72p/about_data)] 🦉 North America climate variable dataset 🦉 Sea surface temperature dataset 🦉 [Wikipedia page view dataset](https://doi.org/10.5281/zenodo.17070469) [[Source](https://dumps.wikimedia.org/other/pageviews/readme.html)]

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

### Data Sources

- [NYC ridesharing trip dataset (High Volume For-Hire Vehicle Trip Records, HVFHV)](https://www.nyc.gov/site/tlc/about/tlc-trip-record-data.page)
- [MTA Subway Hourly Ridership: 2020-2024](https://data.ny.gov/Transportation/MTA-Subway-Hourly-Ridership-2020-2024/wujg-7c2s/about_data)
- [Chicago ridesharing trip dataset (2018 - 2022)](https://data.cityofchicago.org/Transportation/Transportation-Network-Providers-Trips-2018-2022-/m6dm-c72p/about_data) [[2023 - 2024](https://data.cityofchicago.org/Transportation/Transportation-Network-Providers-Trips-2023-2024-/n26f-ihde/about_data)]
- [Daymet: Monthly Climate Summaries on a 1-km Grid for North America, Version 4 R1](https://daac.ornl.gov/cgi-bin/dsviewer.pl?ds_id=2131)
- [NOAA High-resolution Blended Analysis of Daily SST and Ice](https://psl.noaa.gov/data/gridded/data.noaa.oisst.v2.highres.html)
- [Kaggle Wikipedia web traffic daily dataset (without missing values)](https://zenodo.org/records/4656075)
- [Extended Wikipedia web traffic daily dataset (without missing values)](https://zenodo.org/records/7371038)
- [Wikipedia Traffic Data Exploration](https://www.kaggle.com/code/muonneutrino/wikipedia-traffic-data-exploration)


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
