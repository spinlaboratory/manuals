---
title:        "Using the nanoVNA"
linkTitle:    "Using the nanoVNA"
type:         docs
weight:       10
draft:        false
description:  "Introduction on how to use the nanoVNA"
---
The Bridge12 SCN is delivered with the [nanoVNA](https://nanovna.com/), a pocket-size vector network analyzer (VNA) to tune the probe to the transmitter frequency of the spectrometer.

The nanoVNA has two channel and has many different ways to display the (complex) S parameters. However, in the following we provide a brief set of instructions to setup the nanoVNA display to:

* Only show the reflected power from the probe (S<sub>11</sub>)
* How to calibrate the nanoVNA.

The nanoVNA will store these settings, so you only have to go once through these instructions.

For a complete reference please visit the [nanoVNA Webpage](https://nanovna.com/).

{{% pageinfo color="primary" %}}
### Note ###

To navigate through the different menus of the nanoVNA you can either use the wheel located at the top of the device or using the touch screen. The touch screen is best used with a stylus pen. 
{{% /pageinfo %}}

## Setting up the Display  {#setUp} ##

To setup the display:

1. Tap the touchscreen to show the menu
2. Tap the *Display* button (top right corner)

<center>
{{< figure_b12t src="/images/software/OVJ/NanoVNA_menu0_300px.png">}}
</center>

3. Tap the *Trace* button on the display

<center>
{{< figure_b12t src="/images/software/OVJ/NanoVNA_menu1_300px.png">}}
</center>

4. For convenience, select only Trace 0 by tapping on it. The selected trace is highlighted with a colored background (yellow for Trace 0). Unselect any other traces by tapping on the button.

<center>
{{< figure_b12t src="/images/software/OVJ/NanoVNA_menu2_300px.png">}}
</center>

5. To leave the menu tap somewhere on the touchscreen.

## Setting the Frequency Range {#setFreq} ##

1. Tap on the touchscreen to show the menu
2. Tap on the *Stimulus* button

<center>
{{< figure_b12t src="/images/software/OVJ/NanoVNA_menu0_Stimulus_300px.png">}}
</center>

3. Next, tap the *Center* button
4. On the next screen, enter the spectrometer frequency using the number pad and press the *M* button to indicate that the entered frequency is given in MHz.

<center>
{{< figure_b12t src="/images/software/OVJ/NanoVNA_enter0_300px.png">}}
</center>

5. Next, tap the *Span* button and enter the frequency range to observe the resonator tuning dip. Typically 1-2 MHz is a good range to start with.

## Calibrating the nanoVNA {#nanovna_calibration} ##

{{% pageinfo color="info" %}}
### Important ###

The nanoVNA should be calibrated frequently. The calibration is only valid for a given set of parameters (e.g. span, center frequency, number of points ....). If one of these parameters is changed, the device needs to be recalibrated.

The device will still work even with a calibration that is "slightly off". For example, the spectrometer frequency will not change drastically on a day to day basis and using the same configuration is ok. However, if you require accurate values for S<sub>11</sub> we recommend calibrating the device before taking the measurement.

We recommend calibrating the device once and then not changing the measurement parameters. This should be good for a day-to-day operation.
{{% /pageinfo %}}

The nanoVNA is calibrated using a basic OPEN-SHORT-LOAD protocol. Three SMA connectors are included with the nanoVNA, used for calibrating the device (see image below).

<center>
{{< figure_b12t src="/images/software/OVJ/Short-Open-Load_400px.png">}}
</center>

* **SHORT** - Left, used to shorten the input of the VNA. This connector is all metal on the inside.
* **OPEN** - Middle, used to create an open port. This connector does not have a middle pin.
* **LOAD** - Right, used to simulate a 50 &ohm; load. This connector has a middle pin and a white teflon ring around it.

To calibrate the nanoVNA:

1. Set the center frequency and span to the desired range by [following the instructions above](#setFreq).
2. Tab the *Cal* button on the display

<center>
{{< figure_b12t src="/images/software/OVJ/NanoVNA_menu0_Cal_300px.png">}}
</center>

3. Connect the OPEN standard to the CH0 port and press 'Open'
    + The open entry is now black underlined

<center>
{{< figure_b12t src="/images/software/OVJ/NanoVNA_calib0_300px.png">}}
</center>

4. Connect the SHORT standard to the CH0 port and press 'Short'
5. Connect the LOAD standard to the CH0 port and press 'Load'
9. Press 'Done'

The nanoVNA is now calibrated.

## Charging the Battery of the nanoVNA ##
From time to time the nanoVNA battery needs to be recharged.

To recharge the battery connect an USB-C cable to the nanoVNA and plug the cable either into a USB charger or a computer.




