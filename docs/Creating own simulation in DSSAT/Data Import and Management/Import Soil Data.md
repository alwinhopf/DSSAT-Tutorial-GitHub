
Two approaches: 
a) detailed soil profile (measures for %sand, clay, loam, different depths etc.) or 
b) use a pre-defined soil type from the soil database that most closely fits your assumed soil type. 

If the objective of your modeling is strongly soil type dependent (e.g. nitrogen leaching, water-limited production, drought or flooding) is strongly soil type dependent, it is strongly recommended to have detailed soil profile information available. 

  
DSSAT: Soil Data --> Profile --> New. 
Enter country, location, code --> Next

![[DSSAT-Tutorial-GitHub/src/site/img/user/Pasted image 20231114235627.png]]

![[Pasted image 20231114235627.png]

![[Pasted image 20231114235631.png]]

Click “Add Layer” for each layer you have, specify depth, % etc. “More Inputs” for further parameters. Leave empty is parameter is not measured/known à “Next”, insert further values if known or “Calculate missing values” à Finish

Profile à Save as à Specify name (e.g. UFLO220001) à OK

à Profile->Close à File->Save à File->Exit

Back in DSSAT Menu: à Update LST Files

Edit Simulation File à Environment à Fields. Soil Type should appear at top of list (right side), select and save. Test if you can run the experiment

When editing the text based files (instead of using XBUILD / Crop Management Data), you will see the entry under *Fields à ID_SOIL