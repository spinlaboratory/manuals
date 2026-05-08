---
title:          "Built-In Temperature Sensor"
linkTitle:      "Temperature Sensor"
weight:         80
type:           docs
date:           2023-03-28
description:    ""
draft:          False
---
Most Bridge12 EPR probes have an integrated, calibrated [Cernox](https://www.lakeshore.com/products/categories/overview/temperature-products/cryogenic-temperature-sensors/cernox) temperature sensor. This allows the user to get an accurate reading of the sample temperature even when using a liquid cryogen-free (dry) cryostat with an exchange gas. The temperature sensor is compatible with all temperature controllers commonly used to regulate the cryostat temperature. 

## Temperature Sensor Calibration File ##

A calibration file for the temperature controller is available for [download from LakeShore](https://cal.lakeshore.com/). If you can't find the serial number for the temperature sensor please contact Bridge12 at info@bridge12.com with the probe serial number.

## Electrical Connector ##
<center>
{{< figure src="/images/probes/bridge12-qlp/qlp-connector-pinout.png" caption="Bridge12 QLP Pinout" width="400px">}}
</center>

A 6-pin electrical connector is located on the top of the probe to connect the internal temperature sensor of the probe to a temperature controller. Two more pins are available to the user for auxillary connections. Upon request a connector with more pins (up to 9) can be installed. For reference, these are the connectors for the default configuration:

**Probe connector (female):** [LEMO, model: HGG.1B.306.CLLPV](https://www.digikey.com/en/products/detail/lemo/HGG-1B-306-CLLPV/3690677)  
**Mating connector (male):** [LEMO, model: FGG.1B.306.CLAD52Z](https://www.digikey.com/en/products/detail/lemo/FGG-1B-306-CLAD52Z/2786165)

#### Temperature Sensor
The Bridge12 QLP probe is equipped with an an integrated [Cernox Temperature Sensor](https://www.lakeshore.com/products/categories/temperature-products/cryogenic-temperature-sensors) to measure the temperature close to the sample/resonator. This is especially helpful when using a liquid cryogen-free (dry) cryostat that uses an exchange gas. The temperature senor is located close to the actual sample position for an accurate reading.

Typically, the QLP probe will be shipped with a cable to connect the probe to a temperature controller. Please make sure you inform Bridge12 about the temperature controller you intend to use. For reference the pinout for two of the most commonly used temperature controllers is given in the next section.

#### Temperature Controller: Oxford Instruments, ITC
**Manufacturer:** [Oxford Instruments](https://www.oxinst.com)  
**Model:** [Mecury ITC](https://nanoscience.oxinst.com/accessories/mercuryitc)

<center>
{{< figure src="/images/probes/bridge12-qlp/itc-pinout.png" caption="Oxford Instruments ITC Pinout" width="200px">}}
</center>

#### Temperature Controller: Stanford Research Systems, CTC100
**Manufacturer:** [Stanford Research Systems (SRS)](https://www.thinksrs.com/index.html)  
**Model:** [CTC100](https://www.thinksrs.com/products/ctc100.html)  
**Manual:** [PDF](https://www.thinksrs.com/downloads/pdfs/manuals/CTC100m.pdf)

<center>
{{< figure src="/images/probes/bridge12-qlp/srs-pinout.png" caption="SRS CTC100 Connector Pinout" width="200px">}}
</center>

##### Using a Custom Calibration Table with the CTC100 #####
For the most accurate temperature measurements a custom calibration table has to be used with the SRS CTC100 temperature controller. This file is typically provided with the probe. If you don't have the calibration file please contact us as support@bridge12.com and provide the serial number of the probe and the model and make of the temperature controller you are using.

To use a custom calibration table you will need a USB stick (note, the file size of the calibration file is only a few kB).

To use the custom calibration table follow these steps:

1. Create a directory named *cal* within the top-level directory of a USB storage device.
2. Rename the CTC100 calibration file (this is a .txt file). The name of the file should be the name of the channel, with any spaces removed, plus .txt extension. If you don't have a .txt file with the sensor calibration data contact us at support@bridge12.com.
3. Copy the file into the *cal* directory.

The calibration files are automatically loaded when the storage device is plugged into the instrument.

For more information see page 24 of the [CTC100 User Manual](https://www.thinksrs.com/downloads/pdfs/manuals/CTC100m.pdf).
