---
title:          "Modulation Breakout Box"
linkTitle:      "Modulation Breakout Box"
weight:         99
type:           docs
date:           2023-03-28
description:    ""
draft:          False
---
If your EPR probe has an integrated modulation coil for cw EPR spectroscopy the probe also comes with a breakout box to connect the modulation coil to the spectrometer (see figure below).

<center>
{{< figure src="/images/probes/modulation-breakout-box/modulation_breakout_box_600px.png" caption="Modulation breakout box for EPR probes" >}}
</center>

The modulation breakout box is connected to the 6-pin connector of the EPR probe. The cable connecting the probe and the temperature controller is then connected to the breakout box. The modulation coil output of the spectrometer (or lock-in amplifier) is connected to the 3-pin connector of the breakout box.

### Modulation Coil Pinout ###

<center>
{{< figure src="/images/probes/modulation-breakout-box/mod_coil_connector_pinout_400px.png" caption="Modulation coil pinout" >}}
</center>

The modulation coil connector is a female LEMO connector. The figure above shows the front view of the connector. The same direction a user would look at the connector when holding the breakout box in their hands. The pinout numbering follows the default numbering scheme for this type of connector:

* 1 - Mod - : Modulation coil.
* 2 - GND : Probe ground.
* 3 - Mod + : Modulation coil.

Note: The modulation coil is not internally grounded (floating).

**Probe connector (female):** [LEMO, model: EGG.0B.303.CLL](https://www.digikey.com/en/products/detail/lemo/EGG-0B-303-CLL/2835140)  
**Mating connector (male):** [LEMO, model: FGG.0B.303.CLAD52](https://www.digikey.com/en/products/detail/lemo/FGG-0B-303-CLAD52/3797583)

Please contact Bridge12 at support@bridge12.com if you have further questions how to connect the modulation output of your spectrometer or lock-in amplifier to the modulation breakout box.

The pinout for the temperature connector can be found [here](/probes/temperature_sensor/#electrical-connector).