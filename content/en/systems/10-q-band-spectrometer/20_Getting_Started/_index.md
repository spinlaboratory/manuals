---
title:          "Getting Started"
linkTitle:      "Getting Started"
type:           docs
weight:         20
draft:          False
description:    "Getting started with the Q-Band spectrometer SpecMan4EPR"
---
In this section we give a general overview how to operate the Bridge12 Q-Band pulsed EPR spectrometer, which will include the following steps:

* Loading the sample into the spectrometer
* Optimizing the microwave pulse parameters
* Record an echo-detected field sweep EPR experiment
* Perform a PELDOR/DEER experiment

All experiments were performed on our in-house spectrometer, using a sample of a ruler molecule with a concentration of 100 &micro;M in polystyrene. Experiments were performed at a temperature of 50 K.

{{% pageinfo color="primary" %}}
### Important ###
These are sample instructions recorded on equipment in our lab. Actual parameters may vary depending on your specific system configuration, sample, or sample temperature.

{{% /pageinfo %}}

This documentation was prepared using SpecMan4EPR version 3.6.4. If you use a different version some features are maybe named differently or the layout of some windows has changed.

### Preparing SpecMan4EPR ###

When you first start SpecMan4EPR, the software will make sure it can connect to all devices. Once the initialization routine finishes you will see a window very similar to the one shown in the figure below.

<center>
{{< figure_manuals src="/images/software/SpecMan/specman-1a.png" alt="SpecMan4EPR">}}
</center>

We recommend to open the following windows to operate the spectrometer:

1. Open the ``Scope Window`` and activate the digitizer trace. This will be helpful to see the integration limits for the digitizier.
2. Open the ``Pulse Programmer`` window to show the pulse sequence.
3. Open the top ``User Panel``, this will give you convenient access to bridge parameters such as the microwave frequency, video amplifier gain, or the microwave phase.
4. Optionally, open the ``Log Window``. This is helpful to see messages from the SpecMan4EPR software.

Once you opened all these additional panels, the SpecMan4EPR window should look similar to the one shown below.

<center>
{{< figure_manuals src="/images/software/SpecMan/specman-1b.png" alt="SpecMan4EPR with additional panels">}}
</center>


### What's next? ###
* [Inserting a Sample](/systems/spectrometers/81-q-band-spectrometer/20_getting_started/10-inserting-a-sample-adjust-coupling/).

