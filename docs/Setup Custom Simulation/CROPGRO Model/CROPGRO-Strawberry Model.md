**FreshWt.OUT (everything related to fruit growth)**

Strawberry is harvested repeatedly, hence some new variables that might not exist in other DSSAT models. Model internally uses dry weight. Fresh weight is calculated through %dry weight coefficient

F at end indicates fresh weight, D at end indicates dry weight. C at beginning is cumulative

HRVD = dry weight of harvested fruit, individual harvest (kg[DM]/ha)

HRVF = harvest fresh weight of mature fruit, individual harvest (kg[FM]/ha)

CHRVD = Cumulative dry weight of harvested fruit (kg[DM]/ha)

CHRVF = Cumulative fresh weight of harvested fruit (kg[FM]/ha)

**Yield Interpretation and Conversion**

kg/ha → g/ha →  g/m2 →  g/plant: (*1000/10000/4.3)
- g/plant as one common metric (used in publications, variety comparison)
- planting density of 4.3 plants/m2 → division by 4.3 to get form m2 to individual plant
- Dry to fresh weight ratio is 1g fresh = 0.16g dry. Empirically determined
- E.g. CHRVD = 5030.59 kg[dm]/ha at end of season → 726.74 g[FW]/plant  
(=5030.59 *1000/10000/4.3/0.16)

A typical yield per season can be 500-1000g/plant based on fresh weight and marketable fruit (not including non-marketable, i.e., deformed or otherwise “bad” fruit, which is often not harvested or not weighed)