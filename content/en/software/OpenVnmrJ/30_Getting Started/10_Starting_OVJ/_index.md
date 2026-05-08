---
title:        "Launching OVJ"
linkTitle:    "Launching OVJ"
type:         docs
weight:       10
draft:        false
description:  "Launching OVJ and setting the spectrometer frequency."
---
### Launching OVJ ###

OVJ can be launched in two different ways: 1) by double-clicking the vnmrj icon on the desktop or, 2) by opening a terminal window and launching it from the command line by typing:

{{<highlight Shell>}}
vnmr
{{</highlight>}}

### Setting the Spectrometer Frequency ###

If this is the first time you are using OVJ, the spectrometer frequency has to be set to the correct value.

{{% pageinfo color="primary" %}}
### Note ###
The first time you launch OVJ the spectrometer frequency has to be set. Once the spectrometer frequency has been set the value will be stored by OVJ and does not have to be entered every time the user starts OVJ.
{{% /pageinfo %}}

In OVJ, the spectrometer is historically set by setting the frequency of the deuterium (<sup>2</sup>H) lock frequency.

The ratio between the (<sup>1</sup>H) and (<sup>2</sup>H) frequency is approximately 6.51. For example, to set the spectrometer to a <sup>1</sup>H frequency of **14.5 MHz** the user has to set the spectrometer frequency to 14.5/6.51 = **2.227 MHz**. To set the spectrometer frequency:

1. In OVJ go to Edit -> System Settings

    <center>
    {{< figure_b12t src="/images/software/OVJ/System_settings_1_600px.png" width="70%">}}
    </center>

2.  In the window that appears enter the deuterium (<sup>2</sup>H) lock frequency in MHz.

    <center>
    {{< figure_b12t src="/images/software/OVJ/SystemSetting_set_reference_400px.png">}}
    </center>

Alternatively, the spectrometer frequency can be set from the OVJ command line using the ```lockfrequency``` parameter:

{{<highlight shell>}}
lockfreq = 2.27
{{</highlight>}}

Next, you are ready to [Tune the Probe](../20_tuning/).