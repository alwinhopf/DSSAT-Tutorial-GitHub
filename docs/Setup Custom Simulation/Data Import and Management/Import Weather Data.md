
_Note: This process takes almost the same effort for single vs. multiple years. If you plan on doing multi-year analysis, e.g., seasonal analysis with 30+ years, it would be useful to import all weather data at once. Some python/R solution exist that can automate the creation and import of large quantities of weather data in DSSAT.

Note: Irrigation, temperature/humidity control or other kind of climatic parameters that are part of the “treatment” are implemented via Simulation Settings. Weather Data should only includes the “natural” weather data as measured, so that it can later be differentiated by e.g. simulating with/without irrigation.

Download weather data from your source, e.g. FAWN. Make sure to include these columns: Tmin, Tmax, Rainfall, Solar Radiation, Windspeed. If the measurement interval is multiple times per day, you could downscale to 1 average measurement per day, although keeping the finer resolution is generally recommended. Save as .csv file with units in header for later identification, e.g. like this
![[Pasted image 20231114234151.png]]


Open DSSAT → Weather Data (left side of menu)

New Station

Select “Input or import raw weather data and then save as new station”

New widows “Data Import” will open, select “Open File” (top left corner)

Select weather data file from your computer, click “Open”, values will appear in “Data Import window
![[Pasted image 20231114234121.png]]

Right click on the column and specify variable type and unit in which the data comes, e.g. DATE and mm/dd/yyyy, click OK. DSSAT will convert data unit as needed.
Repeat this for all relevant columns, note how columns for which variable type and unit was specified will have the symbol in the header changes. Delete header column with the variable name at the end
![[Pasted image 20231114234110.png]]
![[Pasted image 20231114234113.png]]

Click on right symbol “Import Data into WM” when done. Select “Create new station..”. Specify 4-digit station name, e.g. UFHA for University of Florida Hastings, click “OK”
![[Pasted image 20231114234102.png]]
![[Pasted image 20231114234105.png]]

  

Click Save. Specify location and altitude, click OK (bottom right) once filled.

  ![[Pasted image 20231114234049.png]]
  ![[Pasted image 20231114234057.png]]
  

Loading might take few seconds or longer, depending on volume and length of weather data. Weather station overview will appear, double-check. Change 4-digit short code into a more descriptive name, e.g. “Hastings, Florida, USA”. Click “Update” at bottom.
![[Pasted image 20231114234043.png]]
Click on save button (diskette) to export files via “Write Files”. This weather station and data is now available for simulations in DSSAT. Close WeatherMan window.

![[Pasted image 20231114234324.png]]

Check via explorer or file manager that your new files (identified by short code, UFHA) are there in your DSSAT/Weather folder

Update weather list in main DSSAT window via “File” → “Update all List Files”
![[Pasted image 20231114234335.png]]

Select Experiment, Edit experiment, click “File” → “Refresh”

New weather station Hastings, Florida, USA (UFHA) should appear in Weather Station list under “Fields”
Edit remaining experimental settings as needed, save and run experiment with new weather file.
![[Pasted image 20231114234433.png]]

### Potential Issue: Missing entries in source data

Simple solution can be to fill with calculated mean and variance through WeatherMan
![[Pasted image 20231114235400.png]]

Check that missing values are replaced in “corrected tab”. Should still be missing in “Observed Data” tab

Save new weather files, select “Corrected Data” tab, “Write Files”

![[Pasted image 20231114235406.png]]