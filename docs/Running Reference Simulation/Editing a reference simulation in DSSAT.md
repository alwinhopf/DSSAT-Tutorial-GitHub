
Start with UFGA8201 as example (corn grown in Gainesville). Copy the files, adjust the file to refer to your year (2022?), weather file, soil file, observation file. Find current files in “DSSAT Files” folder, upload your new/edited files there too so I can review

- Adjust name: UFGA = University of Florida, Gainesville à e.g. UFLO for Live Oak
- Adjust year: 82xx means 1982 à change to e.g. 22xx
- xx01 means experiment 1 for that location and year  
	- if you have multiple experiments/sites at that location/year you can use xx02, xx03 and so on 
	- the corresponding weather and observation files need to match that format
	- UFLO2201: UFHA2201 also in file name of weather and observation


### Add Planting and Harvest Dates

Edit Simulation settings à Management à Planting. Select tab “Sowing”, unless you worked with transplants. Add planting and emergence date (if known), define planting density, depth and row spacing. Add 2nd level if you have a sub-field or so with a different planting date in the same or different year

![](Pasted%20image%2020231213181814.png)

### Add Irrigation

Note: This is only for additional irrigation. Rainfall comes from weather file

Edit simulation settings à Management à Irrigation

Define date and amount of each irrigation application, as well as type

Add more dates via “Add Application”

![](Pasted%20image%2020231213181822.png)

### Add Fertilization

Edit simulation settings à Management à Fertilizers. Define date, source materials, application type, depth and quantity of NPK etc.

Add additional applications via “Add Application”. If experiments are fertilized in different way, add new level

![](Pasted%20image%2020231213181829.png)

You can double-check the dates in the text file again

![](Pasted%20image%2020231213181833.png)