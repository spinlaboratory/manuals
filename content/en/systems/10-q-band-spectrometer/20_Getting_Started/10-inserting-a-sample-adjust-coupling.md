---
title:          "Inserting a Sample and Adjust the Resonator Coupling"
linkTitle:      "Inserting a Sample"
type:           docs
weight:         10
draft:          True
description:    "How to insert the sample into the spectrometer"
---
The following section provides a step-by-step procedure how to insert the sample into the EPR probe and adjust the iris coupling of the resonator.

To confirm that the sample is inserted into the microwave resonator correctly, we will observe the microwave tune dip of the resonator.

### Inserting the Sample ###
Make sure SpecMan4EPR is running.

To insert the sample follow these steps:

1. Switch the spectrometer into operate mode
    1. From the Experiment Panel select the ``mode`` tab
    2. Click the Operate button. This will enable all synthesizers

<center>
{{< figure_manuals src="/images/software/SpecMan/specman-1.png" alt="SpecMan4EPR mode panel">}}
</center>

2. Open the resonator tune window (``RESONATOR plugin``) from the plugins window
3. Start the tune sweep by clicking the ``run`` button (green arrow on bottom left)

<center>
{{< figure_manuals src="/images/software/SpecMan/specman-3.png" alt="SpecMan4EPR tune mode">}}
</center>

4. Make sure the resonator is critically coupled. For this, the resonator iris is completely inserted into the resonator. This corresponds to a micrometer reading of 0 mm.

To insert the sample:

5. Make sure the helium gas pressure inside the cryostat is slightly above atmospheric pressure (> 0.1 bar). Note, the pressure gauge shows a value of 0 bar, when the pressure inside the cryostat is close to atmospheric pressure.
6. Once the pressure in the cryostat is slightly above atmospheric pressure, it is safe to remove the bling plug. For this loosen the nut and pull out the plug. You will feel a stream of cold helium gas exciting the cryostat. This will prevent air and moisture entering the sample space.
7. Slowly insert the the sample stick and lower it into the resonator. The sample stick has holes at the top and the bottom to release the helium gas coming from the probe. While lowering the sample stick, observe the tuning picture of the resonator. Once the sample enters the resonator, the tuning dip of the resonator will be visible (see figure below).

<center>
{{< figure_manuals src="/images/software/SpecMan/specman-3a.png" alt="Resonator tuning with and without sample">}}
</center>


8. Once the sample is fully inserted into the resonator, tighten the nut at the top of the probe that holds the sample stick. This nut should just be hand-tight. Do not use any tools (e.g. pliers) to close the nut.
9. Close the valve to the helium gas supply.
10. Start the pump and open the valve to the pump to lower the pressure inside the cryostat to about -0.5 bar. The exact pressure is not important.
11. Close the valve to the pump and wait for a couple minutes until the temperature inside the cryostat stabilizes.

In side the tune window you can zoom into the tune picture by clicking the up and down buttons.

<center>
{{< figure_manuals src="/images/software/SpecMan/specman-4.png" alt="SpecMan4EPR tune mode">}}
</center>


### Overcoupling the Resonator ###
For pulsed EPR experiments the resonator must be overcoupled to reach the maximum resonator bandwidth.

1. Before you adjust the resonator iris to overcouple the resonator, make sure the microwave frequency (red vertical line) is set to the tuning dip. The microwave frequency is adjusted in the Control Panel (see figure above).
2. Slowly turn the micrometer screw to overcouple the resonator. This will raise the iris and the tuning dip will get broader. The tune dip will also shift ub by about 90 MHz. For maximum overcoupling set the height of the iris to 7 mm.
3. For DEER experiments on nitroxide-based spin labels you don't have to adjust the microwave frequency. The shift of the dip is about 90 MHz, which corresponds to the frequency separation of the pump and observe pulse. When using different paramagnetic species the frequency may have to be adjusted. However, keep in mind, the resonator bandwidth is > 400 MHz for the Bridge12 QLP probe.
4. To exit the tune mode, click the ``stop`` button (click the square icon, bottom left) and click the ``OK`` button to close the window.

The spectrometer is ready for the first experiment.

### What's next? ###
* [Optimizing Pulse Parameters](/systems/spectrometers/81-q-band-spectrometer/20_getting_started/20-optimize-pulse-parameters/).