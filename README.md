# BlackbodyFit
![alt text](figure.png)
# Curve Fitting

This is an open source algorithm that fits a blackbody curve to a given dataset to predict the temperature of the source. If the data contains instrumental flux, the function **blackbody_flux_fit** will cross-reference wavelength and corresponding intensity for the given spectral class of the source. If the spectral class is unknown, intensity data for an F0 star is selected. If no data is available for the specific spectral class selected, the algorithm will pick the closest spectral class available. As of now, the algorithm can only take in wavelength measurements ranging from 351.0 nm to 742.72 nm. Intensity measurements are from SPECLIB (JACOBY, HUNTER, AND CHRISTIAN 1984). See: http://adsabs.harvard.edu/abs/1984ApJS...56..257J

**_IMPORTANT_:** The algorithm performs best when the correct spectral class is selected, as it yields a more accurate correction factor to convert the instrumental flux to intensity. 

If input data is already in intensity, use the function **blackbody_fit**. This function is not limited to the wavelength range as **blackbody_flux_fit** is. 

Note that the algorithm scales the theoretial Planck curve by a scale ratio, defined by the integral of the data points divided by the integral of the theoretical planck curve. This scales the theoretical curve accordingly to allow for proper fitting. 

# Installation

Clone the repository or download to a local system as a ZIP file.

It's best to work off the same directory in which the package is saved, so that the modules can be called directly, such as:

from **blackbody_curve** import **blackbody_fit**

# Required libraries

This code utilizes three common python packages:

* numpy
* scipy
* matplotlib

These three packages are bundled with anaconda. If you have anaconda installed all these packages are installed in your machine already.

# Test Scripts

To make sure that the algorithm is working, you can run the four test scripts available in the **test** folder. 

* **test_script1**: Fits data for F4 star HD  23511.
* **test_script2**: Fits data for O7 star HD 35619
* **test_script3** Fits data for A0 star, Vega. Data contains instrumental flux as measured by the 16-inch telescope at Mt. Wilson. This script makes use of the **blackbody_flux_fit** function. 
* **test_script4** Fits data for Be star GSC 3984:1357. Data contains instrumental flux as measured by the 16-inch telescope at Mt. Wilson. This script makes use of the **blackbody_flux_fit** function. 

You can run any of these test scripts by typing, for example, *python test_script1.py* in a terminal.

# How to Contribute?

Want to contribute? Bug detections? Comments? Please email me : dg7541@bard.edu

# Acknowledgements

The author would like to thank the CUREA program at Mt. Wilson for the motivation and guidance necessary for the development of this program. Please see: http://physics.kenyon.edu/people/turner/cureaweb/CUREA.htm


