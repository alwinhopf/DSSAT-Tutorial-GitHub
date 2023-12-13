DSSAT output files are in proprietary format and text files. They can be manually imported in .csv or .xlsx but using the spaces between rows to separate values. DSSAT also offers a .csv output option in the simulation setting: FMOPT = “A” → ASCII text files, = “C” → .csv files. Not supported for all output files yet, but the most common one.
![](Pasted%20image%2020231213182021.png)

DSSAT R package could be one way of importing data and plotting graphs: [https://cran.r-project.org/web/packages/DSSAT/index.html](https://cran.r-project.org/web/packages/DSSAT/index.html)


### Example R Code

#### Setup

library(DSSAT)

options(DSSAT.CSM="C:/DSSAT48/DSCSM048.exe")

library(dplyr)

library(ggpubr)

library(ggplot2)

#### 1. Simple Run - Run simulation for all treatments of one specific experiment

Soybean Experiment UFGA8401 (from 1984), part of standard DSSAT installation

run_dssat(run_mode = "A", file_name = 'UFGA8401.SBX', suppress_output = FALSE)

#### 2. Simple Run with specifying one specific treatment of one experiment

Recommended because plotting multiple treatments at same time required additional steps

filename <- "UFGA8401.SBX"

batch_file_path <- paste0(getwd(),'/DSSBatch.V48')

write_dssbatch(x=(filename), trtno=1:1, file_name = batch_file_path)

run_dssat()

#### 2.1. Simple graph with simulated values

plantgro <- read_output('PlantGro.OUT')

LAI <- ggplot(data=plantgro,aes(x=DAP,y=LAID)) +

  geom_line() +

  ylab(expression(Leaf~Area~Index~"("*m^2~m^{-2}*")")) +

  xlab("Days After Planting") +

  theme_bw() +

  theme(legend.position='bottom')

LAI

#### 3. Batch Run - Run simulations for specific treatments of a specific experiment

setwd("C:/DSSAT48/Soybean")

filename <- "UFGA8401"

batch_file_path <- paste0(getwd(),'/DSSBatch.V48')

write_dssbatch(x=paste0(filename,'.SBX'), trtno=1:2, file_name = batch_file_path)

run_dssat()

  

#### 3.1. Merge output files and label treatments, for plotting

adjust the labels for treatments as needed

plantgro <- read_output('PlantGro.OUT') %>%

  mutate('Treatment'=factor(TRNO,labels=c('Irrigated','Rainfed')))

Optional: Merge additional output files if combining different output files in same set of graphs

plantn <- read_output('PlantN.OUT') %>%

  mutate('Treatment'=factor(TRNO,labels=c('Irrigated','Rainfed')))

etphot <- read_output('ETPhot.OUT') %>%

  mutate('Treatment'=factor(TRNO,labels=c('Irrigated','Rainfed')))

treatment_variable <- plantgro$Treatment

Example below if you want to have unit in treatment header

treatment_variable <- plantgro$'Planting Density (plants m-2)'

#### 3.2. Plot LAI -Different line type for each of the treatments

LAI <- ggplot(data=plantgro,aes(x=DAP,y=LAID,linetype=treatment_variable)) +

  geom_line() +

  ylab(expression(Leaf~Area~Index~"("*m^2~m^{-2}*")")) +

  xlab("Days After Planting") +

  theme_bw() +

  theme(axis.title.x=element_blank(),

        axis.text.x=element_blank(),

        legend.position="none")

LAI

#### 3.3. Plot Leaf Weight

leaf_weight <- ggplot(data=plantgro,aes(x=DAP,y=LWAD,linetype=treatment_variable)) +

  geom_line() +

  ylab(expression(Leaf~Weight~"("*kg~dm~ha^{-1}*")")) +

  xlab("Days After Planting") +

  theme_bw() +

  theme(legend.position='bottom')

leaf_weight

#### 3.4. Plot Canopy Height

height <- ggplot(data=plantgro,aes(x=DAP,y=CHTD,linetype=treatment_variable)) +

  geom_line() +

  ylab(expression(Canopy~Height~"(m)")) +

  xlab("Days After Planting") +

  theme_bw() +

  theme(axis.title.x=element_blank(),

        axis.text.x=element_blank(),

        legend.position="none")

height

#### 3.5. Combine multiple graphs into one

Note that legend was specified accordingly to layout (top grpah does not have a legend etc)

simulation <- ggarrange(height, LAI, leaf_weight,

                                 labels = "auto", label.x=0.875, font.label =  list(size = 20, face = "bold", color ="black"),

                                 ncol = 1, nrow = 3)

simulation