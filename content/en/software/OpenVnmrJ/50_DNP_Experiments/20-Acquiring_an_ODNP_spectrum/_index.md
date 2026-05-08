---
title:        "1H ODNP Spectroscopy"
linkTitle:    "1H ODNP Spectroscopy"
type:         docs
weight:       20
description:  "Acquiring an ODNP-enhanced NMR Spectrum with OVJ"
---

In this first example we demonstrate how to record an NMR spectrum with and without microwave power. Here, it is assumed that the microwave resonator is properly connected to the MPS, and that the resonator is properly tuned and matched.

{{% pageinfo color="info" %}}
### Warning ###
Before enabling the microwave power on the MPS, make sure the microwave resonator is properly coupled to the MPS. While the MPS has a safety feature to disable the microwave power if the reflected power exceeds a safe value, exceeding this value can cause permanent damage to the MPS.

{{% /pageinfo %}}

The NMR signal recorded without microwave power is often referred to as the *Off Signal*, or the thermal equilibrium (TE) signal, while the signal recorded with microwave power is often referred to as the *On Signal*. In most cases, optimizing the spectral parameters using the *On Signal* is simpler due to the increased signal-to-noise of the spectrum.

**Sample:** For this example we use a sample of 10 mM TEMPO dissolved in water. The sample is loaded in the appropriate sample tube and inserted into the resonator.

Prior to recording a DNP spectrum the user has to:
* Adjust the microwave coupling to minimize the reflected microwave power.
* If necessary, record an EPR spectrum of the sample
* Adjust the magnetic field strength so the microwave radiation is on-resonance with an EPR transition

### Recording the On Signal

To record the *On Signal*:

1. Select the PROTON experiment (seqfile='s2pul') and set the NMR acquisition parameters ((*nt*, *sw*, *tof*, *np*, *d1*, *pw*, etc.) to some common values.
2. Go to the Start tab and select the MPS panel.
3. Select the *DNP* checkmark (under *WG*) in the MPS tab. This will set the waveguide switch to select the microwave path for DNP. A waveguide switch is commonly installed in systems that are based on an EPR spectrometer. Your system configuration may differ.
4. In the MPS panel, enter the microwave frequency. This is the same frequency that the EPR resonator is tuned to.
5. Enter the microwave power ([see this table for conversion of mW to dBm](http://mps.bridge12.com/Appendix.html)). The power requirement for a DNP experiment strongly depends on the nature of the sample. A good starting value is 23 dBm (200 mW).
6. Make sure the *MPS mode* is set to *Manual*.
7. To enable the microwave power, click on the *On* check box under *RF*.
8. Acquire an NMR spectrum by clicking the *go* button or by typing the ```go``` command in the OVJ terminal.
9. Phase the spectrum. Note: Typically, the *off-signal* is phased so the NMR signal has a positive amplitude. In an ODNP experiment, the enhanced peak will be inverted.

The ODNP-enhanced spectrum is shown in the figure below.

<center>
    {{< figure_b12t src="/images/software/OVJ/display_ds_mps_on_800px.png" >}}
</center>

Next, optimize the acquisition parameters of the NMR experiment.

### Recording the Off Signal ###

Once the acquisition parameters are optimized you can record the *off-signal*, the NMR signal without microwave power. Typically, the signal-to-noise ratio will be much lower and often more averaging is required. To record the *off-signal*:

1. Turn off the microwave power by clicking the *Off* check box under *RF*.
2. Acquire an NMR spectrum by clicking the *go* button or by typing the ```go``` command in the OVJ terminal.

<center>
    {{< figure_b12t src="/images/software/OVJ/ds_mps_off_800px.png" >}}
</center>

If the signal-to-noise ratio is not sufficient, increase the number of acquisitions (OVJ parameter ```nt```).

Keep in mind, to calculate the DNP enhancement, either both, the on and the off spectrum have to be recorded with the same number of transients, or the signals have to be properly normalized.
