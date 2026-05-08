---
title:        "External Trigger"
linkTitle:    "External Trigger"
type:         docs
weight:       30
draft:        false
description:  "Using an External Trigger"
---
The acquisition of an NMR spectrum by the Bridge12 SCN system can be triggered using an external trigger. The external trigger is connected to the *TRIG/STAT* connector located on the back panel. The pinout for the connector is given in the section describing the [Back Panel Connectors](../../20_hardware#backPanelPinOut).

The trigger is *active low* on the falling edge. This means, pulling pin 7 on the *TRIG/STAT* connector to GND will start the acquisition of an NMR spectrum. By default every acquisition needs to be triggered. If you require a different behavior (e.g. trigger 4 acquisitions to complete a phase cycle) the pulse program need to be changed accordingly. For further information please contact Bridge12 at support@bridge12.com.

The system also has a hardware reset, accessible through pin 9 on the *TRIG/STAT* back panel connector. When this pin is pulled to GND, the pulse program will reset.
As long as the hardware reset of the SCN (pin 9) is pulled to GND no RF pulses are generated and send to the amplifier. Acquisition of an NMR spectrum is not possible.

### Enabling the External Trigger ###
The external trigger needs to be enabled in OVJ for the user to be used. This is done either:

1. from the OVJ command line:

    {{<highlight shell>}}
    B12HWTriggerFlag=1
    {{</highlight>}}

2.  by setting the value in the *Enable HW Trigger* (in the Acquisition tab) to 1

<center>
    {{< figure_b12t src="/images/software/OVJ/quick_h1_trigger_600px.png">}}
</center>

3. or by activating the *HW Trigger* checkbox in the 1H tab

<center>
    {{< figure_b12t src="/images/software/OVJ/Acquistion_HWTrigger_s2pul_600px.png">}}
</center>


### Disabling the External Trigger ###

To disable the external trigger use the command

{{<highlight shell>}}
B12HWTriggerFlag=0
{{</highlight>}}

or set the value in the *Enable HW Trigger* box to 0 (Acquisition tab) or disable the checkbox in the Default 1H tab.
