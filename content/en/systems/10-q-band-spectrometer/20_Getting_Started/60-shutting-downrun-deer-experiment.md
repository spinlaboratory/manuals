---
title:          "Shutting Down the Spectrometer"
linkTitle:      "Shutting Down"
type:           docs
weight:         60
draft:          False
description:    "How to shut down the spectrometer once the experiment is finished"
---
Once all experiments have finished you can shut down the spectrometer.

Shutting down the spectrometer means:

* Closing SpecMan4EPR (if desired)
* Switching of the microwave amplifier and Q-Band extension
* Ramping down the magnetic field to 0 T

Shutting down the spectrometer **DOES NOT MEAN**:

* Switching off the helium compressor

The helium compressor should only be switched off for maintenance or if the spectrometer is not used for a longer time.

### Removing the Sample ###
Follow these steps to remove the sample:

1. Critically couple the resonator. This will make it easier to find the resonator the next time. Turn the micrometer screw to 0 mm.
2. Open the resonator tune window (``RESONATOR plugin``) from the plugins window
3. Start the tune sweep by clicking the ``run`` button (green arrow on bottom left)

You should see a clean tuning picture (see figure below)

<center>
{{< figure_b12t src="/images/software/SpecMan/specman-4.png" alt="SpecMan4EPR tune mode">}}
</center>

To remove the sample:

1. Make sure you have the blind plug within reach.
2. Make sure the helium gas pressure inside the cryostat is slightly above atmospheric pressure (> 0.1 bar). Note, the pressure gauge shows a value of 0 bar, when the pressure inside the cryostat is close to atmospheric pressure.
3. Once the pressure in the cryostat is slightly above atmospheric pressure, it is safe to remove the sample stick. For this loosen the nut and slowly pull out sample stick. While raising the sample stick, observe the tuning picture of the resonator. Once the sample is pulled out of the resonator, the tuning dip of the resonator will disappear (shifted to higher frequency).
4. Slowly keep raising the sample stick. The sample stick has venting holes at the top and bottom of the G10 section to release helium gas from the cryostat and to purge the sample stick and to prevent air and moisture to enter the sample space.
5. Once the sample stick is removed from the cryostat secure the sample and either insert a new sample or close the cryostat using the blind plug and tighten the nut. This nut should just be hand-tight. Do not use any tools (e.g. pliers) to close the nut.
6. Once the cryostat is closed, close the valve to the helium supply.
7. Start the pump and open the valve to the pump to lower the pressure inside the cryostat to about -0.5 bar. The exact pressure is not important.
8. Close the valve to the pump.


### Ramping Down the Magnetic Field ###
Once the sample is removed the magnetic field can be ramped down.

1. Open the window to control the field. From the ``DDI menu`` select ``Set Field form, FLD``.

<center>
{{< figure_b12t src="/images/software/SpecMan/specman-13.png" alt="SpecMan4EPR magnetic field control">}}
</center>

2. Enter 0 in the field for the magnetic field and hit return.
3. Under Sweep rate, select the highest sweep rate.
4. Click the ``Set Field`` button to ramp down the magnetic field.
5. Wait for the field to reach 0 T.


### Switching the Spectrometer to Standby Mode ###
To switch the spectrometer into operate mode:

1. Select the ``mode`` tab from the Experiment Panel.
2. Click the ``Standby`` button. This will disable all synthesizers.


The spectrometer is in standby mode. It is safe to switch off the amplifier and the Q-Band extension.