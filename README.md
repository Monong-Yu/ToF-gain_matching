# ToF-gain_matching
Steps:
0. Install jupyter notebook, scipy, astropy and iminuit;
1. Open "Fit_SiPM.ipynb". This code reads the scans and saves the fitting parameters of each SiPM (or each FEE, if requiring column2 == -1);
2. After checking the fitting qualities, open "Gain_matching.ipynb". This code opens the fitting parameters of this run and the voltage setting of current configurations. Right now I just copy and paste the voltage settings from the configuration file. You can generate an automatic way.

Fitting procedure:
0. The choice of fitting functions is in my dissertation Appendix A and C, or Stephane's slides.
1. Find the fitting range. We only need pedestal, 1 PE and 2 PE (line 18 - 22).
2. Make a straight line connects the first point and the last point of the range we found (line 23 - 25). Then find the distance between the line and the scan curve. This will help to determine the fitting range of each function (line 27 - 33). 
3. Some fits may fail. Then define the fitting range manually (line 38 - 50). Every scan differs, so there will be more and more exceptions... If you have a better fitting scheme, that may help.
