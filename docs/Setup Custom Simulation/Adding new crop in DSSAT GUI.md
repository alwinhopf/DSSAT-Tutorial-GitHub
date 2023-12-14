
DSSAT → Crops → ‘‘Add New Crop’’

![](Pasted%20image%2020231213182314.png)

Example for Hemp
Crop Name: Hemp
Crop Code: HM (check in crop_codes.csv in DSSAT main directory)
Module Name: CRGRO
Description: CRGRO-Hemp (will auto populate)
DSSAT Tree Node: Fiber (group of crops it belongs to)

→ click save → should appear in DSSAT GUI. Note that you still need to copy the respective files of the new crop into the new “Crop Name” directory, including new genetic, weather and soil files as needed. 

![](Pasted%20image%2020231213191921.png)

![](Pasted%20image%2020231213192045.png) 

Use “Refresh” option if new crop does not appear in list of available crops in XBUILD (e.g. Hemp)
![](Pasted%20image%2020231213192510.png)

Files that might need addition of crop code (HM for Hemp, SR for Strawberry etc.) if not already present in DSSAT
- Simulation.CDE
- Detail.CDE
- DSSATPRO.v48

To make changes to the naming and file structure of existing crops: Switch to “Models” Tab --> Select Model, for example “Strawberry” 

![](Pasted%20image%2020231213192400.png)