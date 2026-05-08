---
title:          "Probe Description"
linkTitle:      "Description"
weight:         10
type:           docs
date:           2023-03-27
description:    "Bridge12 XLP(O) Probe Description"
draft:          False
---
## Overview ##
The Bridge12 XLP(O) probe is an EPR probe designed for pulsed X-Band (~ 9.5 GHz) EPR spectroscopy based on a loop gap resonator. The probe is optimized for pulsed EPR experiments, which require a large resonator bandwidth and high microwave conversion factors.

This X-Band probe is available in two different configurations:

1. **Pulsed EPR Spectroscopy**: Resonator model: Bridge12 XLP-3.0
2. **(Pulsed) ODNP Spectroscopy**: Resonator model: Bridge12 XLO

Both configurations are based on a Loop-Gap Resonator (LGR). When completely overcoupled, the resonator has a large bandwidth, and the high microwave conversion factor guaranties large B<sub>1e</sub> fields. This makes the XLP resonator the ideal choice for pulsed EPR experiments that require a large excitation bandwidths.

<center>
{{< figure src="/images/probes/bridge12-xlp/xlp-overview.png" caption="Bridge12 XLP Overview" width="500px">}}
</center>

An overview of the Bridge12 XLP probe is shown in the figure shown above. For low-temperature measurements, the probe can be operated inside a cryostat. The Bridge12 XLP is compatible with commonly used cyrostats, such as the [Oxford Instruments](https://www.oxinst.com/) cryostat model CF935.

The main features of the probe are:
* The resonator
* Integrated temperature sensor
* Baffles along the length of the probe
* Electrical connector to connect the temperature sensor to a controller
* SMA connector
* Sample turret with sample stick
* Iris adjustment

### Optical Access ###

Optical access to the sample location for e.g. light/laser irradiation is possible in several different ways:

1. Through the sample holder/stick (for fiber access only).
2. Free-space access perpendicular to the sample axis (please inquire with Bridge12 about this option).

If you like to use an optical fiber to irradiate the sample using the sample holder/stick (option 1), please contact Bridge12 at info@bridge12.com for further information.

### Temperature Sensor ###

The Bridge12 XLP probe has a built-in, calibrated [Cernox](https://www.lakeshore.com/products/categories/overview/temperature-products/cryogenic-temperature-sensors/cernox) temperature sensor. The connector is located at the back of the probe. Please use the cable that came with the probe to connect the probe to the temperature controller.

More information about the pin-out can be found in the section [Temperature Sensor](/probes/temperature_sensor/).

### What's next? ###
* Learn about [Connecting the Probe](/probes/bridge12-xlp/02_connecting_the_probe/).
