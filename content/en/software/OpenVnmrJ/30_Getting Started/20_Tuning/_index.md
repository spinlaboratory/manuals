---
title:        "Tuning the Probe"
linkTitle:    "Probe Tuning"
type:         docs
weight:       20
draft:        false
description:  "How to tune the NMR probe using the nanoVNA."
---
{{% pageinfo color="info" %}}
### Warning ###
The following section describes how to tune the NMR probe to the correct spectrometer frequency. This requires disconnecting the NMR probe from the spectrometer.

Make sure all experiments have been finished and no pulses are transmitted anymore before disconnecting the NMR probe from the spectrometer.
{{% /pageinfo %}}

### Tuning the NMR Probe {#tuneProbe} ###

To tune the NMR probe to the spectrometer frequency follow these steps:

1. Note down the spectrometer frequency. This does not have to be an exact value, but should be close (within 0.1 MHz of the operating frequency).
2. Switch on the [nanoVNA](10_nanovna/) and set the center frequency to the spectrometer frequency (set it to the frequency of the nucleus you want to observe, not the <sup>2</sup>H lock frequency).  Set the span to a value of 1-2 MHz.

{{% pageinfo color="primary" %}}
### Note ###

See the page [Setting up the Display](10_nanovna/#setUp) to configure the nanoVNA for S<sub>11</sub> measurements.

For instructions on how to setup the center frequency, span, marker position, etc. see the page with the [setup instructions for the nanoVNA](10_nanovna/#setFreq).

If this is the first time using the nanoVNA you should [calibrate the device](10_nanovna/#nanovna_calibrations). This calibration needs to be repeated every time you change the center frequency or span.
{{% /pageinfo %}}

3. Disconnect the NMR probe from the Bridge12 SCN spectrometer and connect it to channel 0 (CH0) of the nanoVNA.
4. You should see a 'Tuning Dip' on the nanoVNA. If you do not see a tuning dip try one of the following things:
    + Increase the span of the VNA to scan a broader frequency range
    + Change the *matching* on your probe
5. Use the slider at the top of the nanoVNA to move the marker to the spectrometer frequency (within +/- 0.1MHz). The marker will tell you the absolute value of the S11 parameter at the spectrometer frequency (see image below, S<sub>11</sub> = -7.8 dB).

<center>
{{< figure_b12t src="/images/software/OVJ/NanoVNA_tuning0_600px.png">}}
</center>

7. Turn the *tune* and *match* capacitor of your probe to achieve a minimum reflection. In general, the *tune* capacitor will shift the dip up in down with frequency, while changing the *match* capacitor value will increase the depth of the dip. Optimize both capacitor values for a minimum in reflected power. The probe is tuned once you achieve the lowest value for S<sub>11</sub> (see image below, S<sub>11</sub> = -40.9 dB)

<center>
{{< figure_b12t src="/images/software/OVJ/NanoVNA_tuning1_600px.png">}}
</center>

Next, you are ready to [Acquire an NMR Spectrum](../30_acquiring_spectrum/).