---
title:        "Superconducting Magnets"
linkTitle:    "Superconducting Magnets"
type:         docs
weight:       10
draft:        false
---
{{% pageinfo color="primary" %}}
### Important ###
The following instructions are specific to how the magnetic field is controlled through SpecMan4EPR. Instructions for cooling down the magnet can be found in the [Magnet Section](/systems/spectrometers/70_magnets/) of the [Systems Menu](/systems/).

{{% /pageinfo %}}

{{% pageinfo color="warning" %}}
### Warning ###
Superconducting magnets can produce extremely high magnetic fields. Avoid any metal objects around the magnet. Always operate around the magnet with care.

Please check with your local facility manager about safety procedures when working with superconducting magnets.
{{% /pageinfo %}}

## Overview ##
Superconducting magnets used in Bridge12 EPR spectrometers come with an integrated heater switch so the magnet can be operated in a *driven-mode* or in *persistent mode*. If the magnet switch is closed, the magnet is in persistent mode, similar to superconducting magnets. While the magnet will have the lowest drift rate in persistent mode, generating a very stable field, the field can not be swept/changed. To sweep the magnetic field, the heater has to be activated to open the switch.

A typical scenario to put the magnet in persisten mode at e.g. 5 T would look like this:

1. Assuming the magnet is at 0 T activate the heater to open the (superconducting) switch. Wait until the heater reaches its target temperature (about 11 K).
2. Ramp the field to the desired value, here 5 T. During ramping the field the magnet voltage will increase.
3. Wait for the field to settle. This is indicated by the lowest voltage read by the power supply. When the magnet is at field, the voltage will never be 0 V, since this voltage also includes the voltage drop across the magnet leads.
4. Deactivate the heater to close the switch. Wait for the heater to return to its base temperature.
5. Ramp down the current in the magnet leads.

{{% pageinfo color="warning" %}}
### Warning ###
Contrary to what is done in NMR spectroscopy, do not disconnect the power supply from the magnet, once the magnet is set to persistent mode.
{{% /pageinfo %}}

At the end of this procedure this the magnet is in a 5 T persistent field state and the drift will be very low. To change the field, first the magnet leads need to be ramped up to match the current in the magnet.

{{% pageinfo color="warning" %}}
### Warning ###
If the magnet is "parked" at a non-zero field and is in persistent mode, the current in the leads has to be ramped up to match the current in the magnet coil to avoid quenching or possible damage to the magnet.

The superconducting magnet power supply will not allow the user to activate the heater if the current in the leads does not match the current of the magnet coil.

If you encounter any problems please contact Bridge12 at support@bridge12.com.
{{% /pageinfo %}}

