---
title:          "Record a Field Sweep Spectrum"
linkTitle:      "Record Field Sweep Spectrum"
type:           docs
weight:         30
draft:          True
description:    "How to record an echo-detected field sweep spectrum"
---
In this section we will provide general instructions on how to record an echo-detected field sweep spectrum.

1. First, load a new experiment. From the ``File`` menu, select ``New Experiment``. Scroll to the ``Field Sweep Echo in Set Mode`` experiment and click on it to load the experiment.
2. When you load the experiment SpecMan4EPR will set all experimental parameters to the default values loaded from the template. Adjust the parameters to the values determined in the previous experiments, such as pulse length, pulse amplitude, ...
3. Under X-axis set the field range and number of points for the experiment. To get started use the field sweep range, that is calculated by the Python script. In this example we will sweep the field from 1.212 T to 1.232 T. enter the phrase "1.212. to 1.232" under ``Field``. The step size is automatically calculated.
4. Hit the run button to start the experiment.

<center>
{{< figure_manuals src="/images/software/SpecMan/specman-8.png" alt="SpecMan4EPR field sweep spectrum">}}
</center>

Once the experiment is finished, data will be saved automatically by SpecMan4EPR. In this particular experiment the software will set a magnetic field and will wait for the field to be settled (SetMode: SetAndWait). While this is the slowest mode to record a spectrum, it will give the most accurate results. At the end of the experiment SpecMan4EPR will return the field to the start value.

Note down the value of the magnetic field for the maximum echo amplitude. You can enable the cursor by enabling the ``Hint`` mode:

1. Click the right button in the top right corner of the spectrum (see figure below)
2. From the drop-down menu select Show Hint.

<center>
{{< figure_manuals src="/images/software/SpecMan/specman-9.png" alt="SpecMan4EPR hint mode">}}
</center>

In this particular experiment the field position for the maximum echo amplitude is 1.21865 T.

For nitroxide spin-labels at Q-Band frequencies the separation between the pump and the observe pulse is typically set to 90 MHz, corresponding to 90 MHz / 2.804 = 3.2097 mT.

The field position for the observe pulse is therefore 1.21865 T + 3.2097 mT = 1.221859 T.

### What's next? ###
* [Run a B1 Nutation Experiment](/systems/spectrometers/81-q-band-spectrometer/20_getting_started/40-run-nutation-experiment/).
