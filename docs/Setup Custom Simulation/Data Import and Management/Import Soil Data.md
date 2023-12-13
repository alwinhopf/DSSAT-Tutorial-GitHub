
Two approaches: 
a) detailed soil profile (measures for %sand, clay, loam, different depths etc.) or 
b) use a pre-defined soil type from the soil database that most closely fits your assumed soil type. 

If the objective of your modeling is strongly soil type dependent (e.g. nitrogen leaching, water-limited production, drought or flooding) is strongly soil type dependent, it is strongly recommended to have detailed soil profile information available. 

  
DSSAT: Soil Data → Profile → New
Enter country, location, code → Next

![[DSSAT-Tutorial-GitHub/src/site/img/user/Pasted image 20231114235627.png]]


![[Pasted image 20231114235631.png]]

Click “Add Layer” for each layer you have, specify depth, % etc. “More Inputs” for further parameters. Leave empty is parameter is not measured/known → “Next”, insert further values if known or “Calculate missing values” → Finish

![](Pasted%20image%2020231119005710.png)
![](Pasted%20image%2020231119005716.png)

Profile → Save as →  Specify name (e.g. UFLO220001) → OK
 → Profile → Close → File → Save File → Exit

![](Pasted%20image%2020231119005721.png)

Back in DSSAT Menu → Update LST Files

![](Pasted%20image%2020231119005726.png)

Edit Simulation File → Environment → Fields. Soil Type should appear at top of list (right side), select and save. Test if you can run the experiment

![](Pasted%20image%2020231119005731.png)

When editing the text based files (instead of using XBUILD / Crop Management Data), you will see the entry under *Fields à ID_SOIL

![](Pasted%20image%2020231119005753.png)