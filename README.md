[![OSE Lab cataloged](https://img.shields.io/badge/OSE%20Lab-catalogued-critical)](https://www.oselab.org/gallery)
[![Python 3.7.4+](https://img.shields.io/badge/python-3.7.4%2B-blue.svg)](https://www.python.org/downloads/release/python-374/)

# Normalized Peak Plot of Dow Jones Industrial Average (DJIA)
The code in this repository allows the user to create a normalized peak plot of the Dow Jones Industrial Average (DJIA) over the last 15 recessions, from the Great Depression (Aug. 1929 to Mar. 1933) to the current COVID-19 recession (likely started in March 2020). The dynamic version of this plot, which is updated regularly, is available to manipulate and explore at [https://www.oselab.org/gallery/djia_npp_mth](https://www.oselab.org/gallery/djia_npp_mth).

A normalized peak plot takes the maximum level of the DJIA at the beginning of a recession (within two months of the NBER declared beginning month) and normalizes the entire series so that the value at that peak equals 1.0. As such, the normalized time series shows the percent change from that peak. This is an intuitive way to compare the progression of average stock prices across recessions. The following figure is the normalized peak plot of the DJIA from May 29, 2020.

![](images/DJIA_NPP_mth_2020-05-29.png)

## Running the code and generating the dynamic visualization
The code for creating this visualization is written in the [Python](https://www.python.org/) programming language. It requires the following two files:
* [`get_djia_data.py`](get_djia_data.py): a Python module that can either retrieve the DJIA data from [Stooq.com](https://stooq.com/) over the internet or retrieve the data from a file saved previously on your local hard drive in the [data](data/) directory of this repository.
* [`djia_npp_bokeh.py`](djia_npp_bokeh.py): a Python script that creates the dynamic visualization of the normalized peak plot of the DJIA over the last 15 recessions. This script calls the [`get_djia_data()`](get_djia_data.py#L33) function from the [`get_djia_data.py`](get_djia_data.py) module. It then uses the [`Bokeh`](https://bokeh.org/) library to create a dynamic visualization using HTML and JavaScript to render the visualization in a web browser.

The most standard way to successfully run this code if you are using the [Anaconda distribution](https://www.anaconda.com/products/individual) of Python is to install and activate the `djia-npp-dev` [conda environment](https://docs.conda.io/projects/conda/en/latest/user-guide/concepts/environments.html) defined in the [environment.yml](environment.yml) file, then run the [`djia_npp_bokeh.py`](djia_npp_bokeh.py) Python script using the appropriate options. Use the following steps.
1. Either fork this repository then clone it to your local hard drive or clone it directly to your local hard drive from this repository.
2. Install the [Anaconda distribution](https://www.anaconda.com/products/individual) of Python to your local machine.
3. Update `conda` and `anaconda` by opening your terminal and typing `conda update conda` and following the instructions, then typing `conda update anaconda` and following the instructions.
4. From the terminal (or Conda command prompt), navigate to the directory to which you cloned this repository and run `conda env create -f environment.yml`. This will create the conda environment with all the necessary dependencies to run the script to create the dynamic visualization.
5. Activate the conda environment by typing in your terminal `conda activate djia-npp-dev`.
6. Run the python script [`djia_npp_bokeh.py`](djia_npp_bokeh.py) by making the correct modifications to the first ? lines of the script, then typing `python djia_npp_bokeh.py` in the terminal in the `DJIA_NormPeakPlot` directory.
