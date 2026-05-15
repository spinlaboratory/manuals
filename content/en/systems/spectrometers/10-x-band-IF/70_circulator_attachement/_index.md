---
title:          "Circulator Attachment"
linkTitle:      "Circulator"
type:           docs
weight:         70
draft:          false
description:    "Connecting the circulator attachment to the the X-Band IF system."
---
The Bridge12 X-Band IF does not have an integrated circulator/pre-amplifier, instead an attachment is connected to the side panel of the X-IF system. This attachment will look slightly different for different frequency bands (X-Band, Q-Band, etc.). For some other frequency bands such as S-Band, or W-Band, the circulator is integrated into the frequency extension.

## X-Band Circulator
<center>
{{< figure_manuals src="/images/systems/xif/X-Band IF with Circulator_800px.png">}}
</center>

The X-Band circulator attachment is directly connected to the side panel of the X-IF system (see figure above) and is held by two SMA connections. A schematic of the circulator attachment is shown in the figure below.

<center>
{{< figure_manuals src="/images/systems/xif/X-Band Circulator Extension.png">}}
</center>

The circulator attachment has three connectors:

1. **Input:** This connector needs to be connected either to the output of the high-power microwave amplifier for pulsed experiments, or to the ```TX``` or the ```LO1``` (```LO2```) output of the X-IF (back panel connector).
2. **Probe:** The EPR probe is connected to this connector.
3. **SIG:** This is the signal output which is connected to the side panel of the X-IF system. The SMA connector below is only for support and is internally terminated with 50 &ohm;. 


