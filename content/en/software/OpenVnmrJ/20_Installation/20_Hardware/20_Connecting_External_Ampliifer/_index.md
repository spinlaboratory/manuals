---
title:        "Connecting an External Amplifier"
linkTitle:    "External Amplifier"
type:         docs
weight:       20
draft:        false
description:  "Connecting an External Amplifier to the Bridge12 SCN Hardware"
---
The Bridge12 SCN has an internal RF power delivering up to 2 W output power. For many (low frequency) experiments this power is sufficient.

If the available power from the internal amplifier is not sufficient, an external high-power RF amplifier can be connected to the system.

To connect an external amplifier the input of the external device must be connected to the **AMP OUT** connection on the back panel of the SCN. The output of the external amplifier must be connected to the **AMP IN** connection located on the back panel.

To blank the external amplifier, connect the blanking gate to the **AMP BLNK** output of the SCN. The blanking gate is *active low*.

### Specifying the Amplifier pre-Blanking Time rof1 ###
To use an external amplifier with blanking, the amplifier needs to be unblanked before sending the RF pulse. Amplifiers typically require a short time unblank. This time can be specified using the OVJ parameter *rof1*. The value is typically given by the manufacturer in the data sheet of the amplifier.

The value can be set from the OVJ command line:

{{<highlight shell>}}
rof1=1000
{{</highlight>}}

If the required value is larger than the default value, for *rof1* can be changed using the ```setlimit``` command as shown below.

{{<highlight shell>}}
setlimit('rof1',MAX_VALUE,MIN_VALUE,STEP)
{{</highlight>}}

### Enabling the External Amplifier and Setting the Drive Level ###

OVJ needs to be connected to use the external amplifier. This is done from the OVJ command line:

{{<highlight shell>}}
B12SCNControl('extamp 1')
{{</highlight>}}

The ```B12SCNControl('state?)``` command can be used to query the state of the amplifier. If the system returns "extamp" the external amplifier is enabled.

{{<highlight shell>}}
B12SCNControl('state?')
{{</highlight>}}

The drive level (input power) of the external amplifier can be set using the OVJ command line by specifying the value stored by ```tpwrf```.

{{<highlight shell>}}
tpwrf=1
{{</highlight>}}

To disable the internal amplifier from the OVJ command line enter this command:

{{<highlight shell>}}
B12SCNControl('extamp 0')
B12SCNControl('state?')
{{</highlight>}}

If the command ```B12SCNControl('state?)``` returns "intamp", the internal amplifier is used. The ```tpwrf``` value is automatically set to 100 (the maximum).

{{% pageinfo color="warning" %}}
### Warning ###

The drive level for the external amplifier is by default set to 3 dBm (2 mW - corresponding to ```tpwrf=3.25```). This value can be changed using the ```tpwrf``` command from the OVJ command line. Please consult the data sheet of the external amplifier to find out the correct drive level for you amplifier model. The value in ```tpwrf``` is a linear scaling factor.
{{% /pageinfo %}}
