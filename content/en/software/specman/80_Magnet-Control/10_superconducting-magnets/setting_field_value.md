---
title:        "Operating the Magnet"
linkTitle:    "Operating the Magnet"
type:         docs
weight:       30
draft:        false
---
Depending on the type of experiment the magnet field is either:

1. **Moving** For example in a echo-detected field-sweep experiment. Here, the field is swept while recording the echo intensity.   
2. **Static** For example in a DEER/PELDOR experiment. These type of experiments are performed at a static magnetic field value. If the user does not change the field for a long time (e.g. an overnight experiment), it is recommended to put the magnet in persistent mode.

Typically, when switching on the spectrometer, the user would set a field value close the start value. This is not strictly required but will speed up operations when the field is moved a lot during an experiment session.

Once an initial value is set the field is entirely controled by SpecMan4EPR.

### Setting an Initial Field Value
To prepare for an experiment:

1. Open the SpecMan4EPR Magnetic Field GUI.
2. Click on the heater control icon.
3. Activate the superconducting heater switch. After you clicked the icon to activate the switch wait for about 10 - 20 s for the switch to completely open.
4. Click the icon to control the magnetic field.
5. Enter the desired value for the magnetic field and press the ENTER key.
6. Wait for the magnet power supply to reach the desired magnetic field value.
7. (Optional) If the EPR experiments are performed at a static magnetic field, close the superconducting magnet switch to put the magnet in persistent mode. Enter a value of 0 T for the magnetic field to ramp down the current in the magnet leads.

### Ramping Down the Magnet
It is completely fine to leave the magnet at field, if the spectrometer is not used for a short time. However, if the spectrometer is not used for a while, the magnetic field should be discharged. To ramp down the magnet:

1. (Optional) If the magnet is in persistent mode:
    1. Enter the field value, matching the magnetic field value of the magnet and hit the ENTER key.
    2. Wait for the power supply to reach the value.
    3. Open the superconducting magnet switch. After you clicked the icon to activate the switch wait for about 10 - 20 s for the switch to completely open.
2. Enter a value of 0 T for the magnetic field strength and hit the ENTER key.
3. Wait for the magnet to reach a field of 0 T.
4. Once the magnet reached 0 T, close the superconducting magnet switch.

{{% pageinfo color="primary" %}}
### Information ###
Unless the spectrometer is not used for several days, the Helium compressor will be constantly running and is not turned off, when the spectrometer is switched off. Keep in mind, it takes about 24 hrs to cool down the magnet from room temperature.
{{% /pageinfo %}}

### Changing the Ramp Rate
When sweeping or changing the magnetic field, the rate, at which the magnetic field is changed, can not exceed a specific value. This value for the sweep rate is given by the magnet manufacturer. It is common for superconducting magnets to have different sweep rates for different field value regimes.