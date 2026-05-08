---
title:        "Saving the NMR Spectrum"
linkTitle:    "Saving OVJ Data"
type:         docs
weight:       40
draft:        false
description:  "Saving the NMR Spectrum in OVJ"
---
OVJ provides two different options to save the NMR data:

1. by using the OVJ GUI
2. by using the OVJ command line.


#### Saving Data using the OVJ GUI{#saveEXP} ####

To save the NMR experiment using the GUI:

1. Go to the *Acquire Tab* and select *Future Actions*
2. Click on *save FID* (see image below)

<center>
{{< figure_b12t src="/images/software/OVJ/save_fid_800px.png">}}
</center>

#### Saving Data from the OVJ Command Line ####

To save the NMR experiment from the OVJ command line:

1. Type the command ```save```
2. Enter a name (e.g. mydata). Do not add an extension to the file name
3. Press return

The data will be saved and a [study](#saveSTUDY) is created automatically.

#### Location of Saved Data ####

Assuming a default installation of OVJ, the data can be found in the 'mydata' subfolder in the vnmrsys/data folder:

{{<highlight shell>}}
~/vnmrsys/data/
{{</highlight>}}
