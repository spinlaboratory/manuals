---
title:          "Run a B1 Nutation Experiment"
linkTitle:      "Run a Nutation Experiment"
type:           docs
weight:         40
draft:          True
description:    "How to run a B1 nutation experiment"
---
In this section we will provide general instructions on how to run a nutation experiment to determine the optimum length of the inversion pulse.

The nutation is a three pulse experiment. The sequence starts with a nutation pulse followed by a long delay and a two-pulse echo detection sequence. During the experiment the pulse length of the nutation pulse is increased to observe the Rabi oscillation.

To perform the nutation experiment follow these steps:

1. Start by loading the experiment. From the ``File`` menu, select ``New Experiment``. Scroll to the ``Two Pulse Echo Nutation `` experiment and click on it to load the experiment.
2. Make sure the magnetic field is still set to a value corresponding to the maximum echo amplitude (here 1.21865 T).
3. In the experimental parameter section set the parameter ``amp_Nut`` to 1. This is the amplitude for the nutation pulse and we will just use maximum power.
4. Set pulse length to p_90 = 16 ns and p_180 = 32 ns, set the amplitude for the detection pulses to 0.08 (this is the value that was previously determined).
5. Hit the tune button and adjust the integration interval in the scope window (vertical orange lines). 
6. To start the experiment, hit the ``run`` button.

The result of the experiment is shown in the figure below.

<center>
{{< figure_manuals src="/images/software/SpecMan/specman-10.png" alt="SpecMan4EPR Rabi oscillations">}}
</center>

Use the cursor and *Hint Mode* to determine the pulse length of the inversion pulse. In this case it is 10 ns for an pulse amplitude of 1. 

{{% pageinfo color="primary" %}}
### Note ###
The Bridge12 QLP resonator has a bandwidth of > 400 MHz. Therefore, you don't have to repeat the nutation experiment at the observe field position.

{{% /pageinfo %}}


### What's next? ###
* [Run the PELDOR/DEER Experiment](/systems/spectrometers/81-q-band-spectrometer/20_getting_started/50-run-deer-experiment/).
