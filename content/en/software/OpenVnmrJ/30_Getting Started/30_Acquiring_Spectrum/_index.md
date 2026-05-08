---
title:        "Acquiring a Proton Spectrum"
linkTitle:    "Acquisition"
type:         docs
weight:       30
draft:        false
description:  "How to acquire a 1D <sup>1</sup>H NMR spectrum."
---
This section provides a brief overview how to acquire a 1D <sug>1</sup>H NMR spectrum. For this we assume that:

1. OVJ-B12 is [installed](../../20_installation/10_software/) on the computer
2. The [hardware is set up](../../20_installation/20_hardware/) properly
3. A sample is inserted into the probe
4. The NMR [probe is tuned](../20_tuning/) to the spectrometer frequency.

## Acquiring a <sup>1</sup>H NMR {#NMR} ##

1. From the protocols tab drag the PROTON experiment into the plotting window, or double click on the PROTON protocol.

    <center>
    {{< figure_b12t src="/images/software/OVJ/Experiment_selector_tree_400px.png">}}
    </center>

    Alternatively, the pulse sequence can be set using the OVJ command line:

    {{<highlight C>}}
    seqfil='s2pul'
    {{</highlight>}}

    The PROTON sequence calls a pulse program *s2pul*. This is a general, two-pulse sequence used to run variety of different experiments such as a single pulse NMR experiment or an inversion-recover sequence.
    
2. Next, the user has to set the length and power of the RF pulse to properly acquire a 1D <sup>1</sup>H spectrum. In OVJ the pulse parameters can be changed from the OVJ command line or from the acquisition panel.

{{% pageinfo color="primary" %}}
### Note ###
Make sure that the spectrometer frequency is set correctly. The spectrometer frequency is set by adjusting the [*lockfreq*](../10_starting_ovj/). For experiments at 14.79 MHz, this parameter has a value 2.271 MHz (<sup>2</sup>H frequency corresponding to a <sup>1</sup>H frequency of 14.78 MHz). This value should be ideally set to a precision of three to four significant digits.

See the [Launching OVJ](../10_starting_ovj/) section in the Getting Started section for more details.
{{% /pageinfo %}}

The length of the observe pulse is given by the parameter ```pw```. From the OVJ command line set the pulse length:

{{<highlight C>}}
pw=3
{{</highlight>}}

corresponding to a pulse length of 3 &micro;s.

{{% pageinfo color="primary" %}}
### Note ###

If the pulse length corresponding to a 90 degree pulse is unknown, it can be determined by performing a [nutation experiment](../../40_advanced_experiments/20_calibration_90_pulse_length/) to calibrate the correct pulse length. Typically, the probehead manufacturer will provide the length and power level for the 90 degree pulse.
{{% /pageinfo %}}

3. Next some of the acquisition parameters need to be set. Go to the **Acquire** tab and click on **Acquisition**. Here, basic acquisition parameters can be adjusted. Alternatively, the values can be entered in the OVJ command line.

    + **Spectral Width**: Parameter *sw*
    + **Acquisition Time**: Parameter *at*
    + **Complex Points**: Parameter *np*

    For example

    {{<highlight C>}}
    sw=50000
    np=4096
    {{</highlight>}}

    will set the spectral width to 50000 Hz (50 kHz) and the number of points acquired in the time domain to 4096.

{{% pageinfo color="primary" %}}
### Note ###

In OVJ the number of points corresponds to the total number of real and imaginary points. To acquire a total of 2048 (complex) points, ```np``` has to be set to 4096 (twice the number of complex points).
{{% /pageinfo %}}

4. Set the number of transients (```nt```) to 4. In general, OVJ will add a CYCLOPS phase cycle to each sequence automatically to remove DC offsets and correct for phase imbalances. Therefore, the parameter ```nt``` should always be set as a multiple of 4.

    {{<highlight C>}}
    nt=4
    {{</highlight>}}

5. On the Acquire tab click *Channels* to set the transmitter offset ```tof``` parameter. To get started, set this value to 0

    {{<highlight C>}}
    tof=0
    {{</highlight>}}

    With the transmitter offset set to 0, the spectrum, if excited on resonance, appears in the center of the window. To center the spectrum adjust the ```tof``` value. Alternatively, you can click with the mouse on the peak (single red line cursor) and enter the command ```movetof``` in the OVJ command line. OVJ will automatically adjust ```tof``` so that the NMR spectrum in the next acquisition is at the center of the window.

6. Start the acquisition by either pressing the *GO* button or by typing

    {{<highlight C>}}
    go
    {{</highlight>}}

    in the OVJ command line. The acquisition will start and the data is displayed and processed on the screen.

{{% pageinfo color="primary" %}}
### Note ###

In OVJ the acquisition of the NMR spectrum can be started using the ```go``` or ```ga``` command. In this version of OVJ the two commands are identical. This may be different on other (older) NMR spectrometers running vnmrj.
{{% /pageinfo %}}

### Phasing a spectrum {#phasingSignals} ###

Once the acquisition is finished, the spectrum most likely needs to be phased to show just the real part of the complex spectrum (see figure below). This can be done automatically using the autophase command ```aph``` or manually.

<center>
{{< figure_b12t src="/images/software/OVJ/image-sources/t1_wft.png">}}
</center>

#### Using the Autophase Routine ####

To autophase the spectrum type the following command in the OVJ command line and press enter:

{{<highlight shell>}}
aph
{{</highlight>}}

to autophase the spectrum.

#### Manually Phasing the Spectrum ####

Sometimes, the autophase routine fails and the spectrum needs to be phased manually. To manually phase an NMR spectrum:

1. Click the *Phase* button in the toolbar to the left

    <center>
    {{< figure_b12t src="/images/software/OVJ/phasing_0_50px.png">}}
    </center>

2. Click the spectrum with the left mouse button and keep the button pressed. Two red cursors appear to the left and right of the peak. Phase the peak by moving the mouse up and down. This will adjust the 0<sup>th</sup> order phase correction (frequency-independent phase correction). Alternatively, the phase can be adjusted from the OVJ command line by typing:

    {{<highlight shell>}}
    rp=11.5
    {{</highlight>}}

3. To adjust the 1<sup>st</sup> order phase correction (frequency-dependent phase correction) click the *Phase* button in the toolbar to the left. Next, select the peak by moving the mouse cursor to the NMR peak and click the right mouse button. The point selected is the *pivot* point used to adjust the 1<sup>st</sup> order phase correction. By moving the mouse up and down the phase of the rest of the spectrum can be adjusted. To adjust the 1<sup>st</sup> order phase correction ```lp``` from the OVJ command line type:

    {{<highlight shell>}}
    lp=157
    {{</highlight>}}

The proper phased spectrum is shown below.

<center>
{{< figure_b12t src="/images/software/OVJ/image-sources/t1_aph.png">}}
</center>

{{% pageinfo color="primary" %}}
### Note ###

Start phasing the spectrum with ```rp``` and ```lp``` set to 0. First, adjust the 0<sup>th</sup> order phase and then the 1<sup>st</sup> order phase correction. Note that ```rp=360``` is equivalent to ```rp=0```. This is also true for ```lp```.
{{% /pageinfo %}}

Next, proceed to the next section to [Save the NMR Spectrum](../40_saving_data/).