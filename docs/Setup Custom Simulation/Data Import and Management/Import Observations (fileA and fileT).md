This is a recommended step before, but you might find a more suitable way for yourself: Organize all relevant observation data in a .csv sheet. One row with DSSAT variable names, another row with your variable names for easier interpretation

![](Pasted%20image%2020231119010140.png)

Open DSSAT → Experimental Data under “Tools” on left side. ATCreate window will open.

Click on “Edit File Header”. Specify experiment name, crop and description. Select if File A or File T, press OK.
![](Pasted%20image%2020231119010132.png)

If needed, Switch between A/T file by clicking on the letter in top row. A file is for once-per-season type of observation (phenology dates, final yield etc.), T file for within-season observations (continuous soil N observation e.g.).

![](Pasted%20image%2020231119010127.png)  
Use Magic Wizard tool, specify number of rows and columns needed

![](Pasted%20image%2020231119010117.png)

![](Pasted%20image%2020231119010120.png)

**Specify column headers with right click (variable name).** Select variable name and unit. Only select available variables. If the needed variable is not in the list, check in other file (A vs. T file). Make sure you use the correct unit (DAP vs. YYDOY, kg vs. tons).

Enter your observations into the table. Each in-season observation comes with a date (DATE) and treatment number (1 unless you have multiple treatments, then allocate treatment number appropriately). You will have a separate row for measurements from each date. If only some variables from all columns were measured, leave empty or enter -99.

![](Pasted%20image%2020231119010109.png)

Once finished: Delete unneeded rows (e.g. 2nd row with variable names if present) and columns. Do not leave any rows with -99 headers as this can cause errors. Double-check for empty cells (should be “-99”) etc. → write into .T file via save or save-as function. Exit (confirm if saved).

Back to DSSAT, Refresh experiment list and check data observation data shows up in “Data” tab. You can plot and view your observations here separately, double-check for missing or erroneous entries (e.g. wrong date, outliers due to wrong conversion or missing comma etc.)

![](Pasted%20image%2020231119010044.png)

![](Pasted%20image%2020231119010047.png)

![](Pasted%20image%2020231119010051.png)

![](Pasted%20image%2020231119010055.png)

You can also review and plot the observations. These observations will now be available in your simulation, to compare simulated and observed values.

Tip for easier processing: create a custom .csv file with only the headers you need, name the headers in the DSSAT acronym and import this file. You can use the “use current cell content as column header” function in AT create to quickly assign the columns then.  See example attached, note you need to remove the additional rows 1 and 2 when importing in AT create, they contain explanation of the variable names. 
![](Pasted%20image%2020231217104843.png)

![](Pasted%20image%2020231217105156.png)

![](observations_fileT_example.csv)


Potential Errors

![](Pasted%20image%2020231219112606.png)

![](Pasted%20image%2020231219112806.png)