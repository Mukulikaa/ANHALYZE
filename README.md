# ANHALIZE  (beta)

`ANHALIZE` is an analysis tool for the ANHA configuration of the NEMO model.

## Description

`ANHALIZE` is an analysis tool for the 
[Arctic and Northern Hemisphere Atlantic (ANHA)](https://canadian-nemo-ocean-modelling-forum-commuity-of-practice.readthedocs.io/en/latest/Institutions/UofA/Configurations/ANHA4/index.html) 
configuration of the [NEMO](https://www.nemo-ocean.eu/) model. The focus is on data manipulation, analysis, and visualization. 

This tool has been originally developed to support ocean modeling research at the 
Centre for Earth Observation Science (CEOS), at the University of Manitoba. 

NOTE: This code is stable, but new features are currently under development.

## Getting Started

### Dependencies

Dependencies are found in `requirements.txt`.

### Installing

After cloning this [GitHub repo](https://github.com/PORTAL-CEOS/ANHALIZE). \
Install with:

`python -m pip install .`

Future Note: This will become a PyPI application. 

## Usage

Once installed you can import library:

```
import anhalyze as ah
aa = ah.AnhaDataset(filename)
aaa = aa.sel(lat_range=[50,65],lon_range=[-93,-75])
```

### Example 

This simple example requires a .nc `grid` file, and a .nc `mask` file.

```
import anhalyze as ah

# Open file
aa = ah.AnhaDataset(filename)

# Apply mask file
aa.apply_mask(mask_filename)

# Do selection of lat_range, lon_range, and depth_range, in that order.
aaa = aa.sel([50,65],[-93,-75],[0,300])

# Plot region for a selected variable.
aaa.show_var_data_map(var='votemper')
``` 


## Version History

* 0.7 (upcoming)
    * To release `AnhalyzeLocation` class.
* 0.6 (upcoming)
    * To release `AnhalyzeProject` class.
* 0.5 (upcoming)
    * First release, includes:
      * `AnhaDataset` class
      * Basic selection and plotting functionality. 
    * See [commit change]() or See [release history]()
* 0.0.1
    * Current version in Beta. 

## License

This is a placeholder.



-------------------- Deprecated below this line. --------------------


Need to add the following environmental variables to your .bash_profile (or .bashrc, etc..), 
and edith paths to your needs:
``` 
#------------------------------------------------------------- 
#ANHALIZE setup
#-------------------------------------------------------------
export MASK_PATH='/root_path/user/ANALYSES/MASKS/'
export DATA_PATH='/root_path/user/NEMO/ANHA4/ANHA4-Wxx000-S/'
#-------------------------------------------------------------
```

