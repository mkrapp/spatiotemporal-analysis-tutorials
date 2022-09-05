# spatiotemporal-analysis-tutorials


## Installation

Clone repository and go into directory:
```
git clone https://github.com/mkrapp/spatiotemporal-analysis-tutorials.git
cd spatiotemporal-analysis-tutorials
```

Create a new `conda` environment, e.g., `winterschool`:
```
conda create --name winterschool
conda activate winterschool
```

Install all required packages:
```
conda install -c conda-forge matplotlib numpy pandas scipy xarray cartopy jupyter rise
```

Register `conda` environment `winterschool` for `jupyter` notebooks:
```
python -m ipykernel install --user --name=winterschool
```

Start `jupyter` with:
```
jupyter notebook
```

## Files

(ALL files are also available from [here](https://www.dropbox.com/sh/faxzxsugt19g048/AADuN5mVY4rqFlBY2XCZkBOVa?dl=0)!)

Download (and unpack) the New Zealand Coastline (Shapefile) from [here](https://data.linz.govt.nz/layer/50204-nz-coastlines-topo-1500k/])

Download the ERSSTv5 sea surface temperature data set (NetCDF file):
```
wget https://iridl.ldeo.columbia.edu/SOURCES/.NOAA/.NCDC/.ERSST/.version5/sst/data.nc -O data/sst_orig.nc
```

We need to fix the time dimension (i.e., the calendar) in that file:
```
ncatted -O -a calendar,T,o,c,"360_day" data/sst_orig.nc data/sst.nc
```
