# Vertical_Climate_Velocity

In this repository there are three jupyter notebooks:

**Climate_Velocity_Calculations.ipynb**
* This notebook contains code to
  1. Download the Glorys12 temperature data for each LME
     - **copernicusmarine_datastore** is the function used
     - You will need to register (free!) with Copernicus Marine at https://marine.copernicus.eu/
     - **LME_data_retrieval_2** subsets the data to only the region around the LME
  2. Calculate the horizontal and vertical climate velocity for each LME
     - **in_shape_alldepths_glorys** crops the data to the specific LME shape
     - **interpolate_5m_2** linearly interpolates the temperature data at 5m spacing in the upper 200m
     - **temptrend_vcv** calculates the slope and pvals of any significant linear trend of temperature at each gridpoint within the LME
     - **vertical_spat_grad** calculates the vertical spatial gradient
     - **temptrend_hcv** calculates the slope and pvals of any significant linear trend of temperature at each gridpoint within the LME using only the original uppermost bin (closest to the surface)
     - **horiz_spatgrad_hcv** calculates the horizontal spatial gradient in the method of Burrows et al. (2011)
     - **VCV_HCV** combines the outputs of all the previous functions and returns xr datasets with all the vertical and horizontal climate velocity data
     - **climate_vel_subsets_more** uses all previous functions to create and save vertical and horizontal climate velocity

**Species_shifts_and_Manuscript_Figures.ipynb**
* This notebook contains code to
  1.  Create main text and extended data figures (except figure 5 see Simulated_Species_Shifts.iynb below) in the manuscript "Vertical climate Velocity adds a critical dimension to species' shifts"
  2.  The calculation of biomass weighted mean lat, lon, and depth for species in trawl data from the Gulf of Mexico, the Northeast U.S. Continental Shelf, and the East Bering Sea
  3.  The calculation of any significant latitudinal or depth shifts based on (ii.)
     
**Simulated_Species_Shifts.ipynb**
* This notebook contains code to
  1. Compute simulated species shifts based on 11 scenarios of combinations of horizontal and vertical climate velocity over 50 years within the Northeast U.S. Continental Shelf, East Bering Sea, and Gulf of Mexico LMEs.
  2. Creates Figure 5.
