---
title:        "Heater Control"
linkTitle:    "Heater Control"
type:         docs
weight:       20
draft:        True
---
To change the magnetic field first the superconducting heater needs to be activated. This will connect the magnet power supply to the main coil and will allow the user to increase or decrease the current in the main coil and therefore moving the magnetic field.

<center>
{{< figure_manuals src="/images/software/SpecMan/magnet_control/heater_control_800px.png" alt="SpecMan4EPR Heater Control">}}
</center>

The value of the magnetic field is shown in two different colors, depending if the heater switch is activated or not:

* **Yellow :** The heater switch is off. If the field is at a value of 0 T, the main coil is completely discharged. If the value is not 0 T it means the magnet is in persistent mode, and the field is "parked" at that value. Before activating the switch, the current in the magnet leads not to ramped back to the persistent mode value (see figure above, left).
* **Green :** The heater switch is activated (on) and the field can be moved (see figure above right).

{{% pageinfo color="info" %}}
### Warning ###
The switch in the superconducting magnet is thermally activated. When activating the heater (switching the heater on) the user should wait for 10-20 seconds until the switch is fully opened. To be sure the switch is fully openend, the user can check the heater switch temperature in the logging GUI.
{{% /pageinfo %}}


### Operating the Switch

#### Opening the Switch at 0 T
To open the superconducting switch:

1. If the magnetic field is at a value of 0 T, click the icon to open the switch in the magnet GUI (see figure above, left).
2. Confirm that you want to open the switch by clicking *Yes* in the dialog box.
3. Wait for 10 - 20 seconds for the switch to fully open.

#### Opening the Switch when Magnetic Field is not at 0 T
To open the superconducting switch:

1. Enter the value of the persistent field to charge the current in the leads to match the current when the switch was closed.
2. Wait for the power supply to reach the field.
3. Click the icon to open the switch in the magnet GUI (see figure above, left).
2. Confirm that you want to open the switch by clicking *Yes* in the dialog box.
3. Wait for 10 - 20 seconds for the switch to fully open.

#### Closing the Switch
To close the superconducting switch:

1. Click the icon to close the switch in the magnet GUI (see figure above, right).
2. Wait about 10 - 20 seconds for the switch to close