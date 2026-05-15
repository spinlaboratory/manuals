---
title:        "Example: Pulsed Q-Band Operation"
linkTitle:    "Pulsed Q-Band Operation"
type:         docs
weight:       81
draft:        true
description:  "Example configuration for pulsed Q-Band EPR spectroscopy."
---
A typical configuration of the X-Band IF system for pulsed Q-Band spectroscopy is shown in the figure below. Connections that are not required are greyed out.

<!-- <center>
{{< figure_manuals src="/images/software/X_Band_IF/X_Band_Config_BackPanelLabels.png">}}
</center>

| Connector | Description |
| :--------:| ----------- |
| RCVR I <br> RCVR Q | Connect the RCVR I and RCVR Q channel to the digitizer or oscilloscope. The EPR signal will appear here. |
| AWG I <br> AWG Q | Connect the AWG I and AWG Q connectors to the arbitrary waveform generator. Alternatively, these channels can also be conencted directly to the output of a pulse programmer to generate rectangular pulses at the LO1 frequency. If you have questions about these mode, please contact Bridge12 at support@bridge12.com. |
| PFU TX | This is the output of the X-Band IF system. Connect this connector to the input of the high-power pulse amplifier. Depending on the type of the amplifier an additional pulse blanking gate is required as a channel of the pulse programmer.|
| PFU <br> BLNK | Blanking gate of the PFU. This is not the amplifier blanking gate. This gate is active high and needs to be high to be able to transmit microwave pulses. |
| 10 MHz <br> CLK | Connect the system clock to each, the digitizer and the AWG. That way, the X-Band IF system provides the master clock to synchronize all other instruments. The X-Band IF master clock runs at 10 MHz. In cases when the AWG clock is higher, the user may want to synchronize the system to the AWG clock to minimize pulse jitter. |
 -->
