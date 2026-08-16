---
title:          "QLP EPR Probe"
linkTitle:      "QLP EPR Probe"
weight:         10
type:           docs
date:           2026-05-15
description:    "Online Documentation of the QLP Probe Head for Pulse EPR Spectroscopy"
draft:          False
---

The QLP EPR probe head is a Q-Band EPR probe head, optimized for pulsed EPR experiments that require strong microwave pulses with a large excitation bandwidth. 

<center>
{{< figure_manuals src="/manuals/images/probes/QLP/QLP_horizontal.png" caption="The QLP-1.6 EPR Probe for Pulsed EPR Spectroscopy (Manual Iris Control)" width="600px" >}}
</center>

## Overview ##
The QLP EPR probe head comes in two different flavors. The QLP-1.6 optimized for absolute sensitivity while the QLP-2.5 is ideal for experiments that require optimum concentration sensitivity. The probe heads are operating at Q-Band (34 - 36 GHz) frequencies. The probe heads are particularly useful for pulsed dipolar spectroscopy (PDS) such as [Double Electron-Electron Resonance (PELDOR/DEER)](/resources/literature-references/#peldordeer) spectroscopy, [Double Quantum Coherence (DQC)](/resources/literature-references/#double-quantum-coherence-dqc-spectroscopy) spectroscopy, or [Relaxation Induced Dipolar Modulation Enhancement (RIDME)](/resources/literature-references/#ridme) experiments. However, any pulsed EPR experiment that requires strong microwave pulses and large excitation bandwidths will benefit from the use of the QLP probe head.

Pulsed Electron Paramagnetic Resonance (EPR) spectroscopy using high-power microwave pulses or arbitrary waveform generated (AWG) broadband pulses require a large resonator bandwidth (low resonator Q) to ensure efficient excitation and to avoid distortion of the pulse shape. However, a large resonator bandwidth often comes at the cost of a reduced microwave conversion factor. Loop-Gap Resonators (LGR) combine all these desired features together with an excellent field homogeneity across the sample. This is especially important when using AWG generated broadband pulses.

At the heart of the QLP probe head is a Loop-Gap Resonator (LGR), with a large conversion factor, and a large homogenous B<sub>1e</sub> microwave field across the entire sample volume to improve the performance of pulsed EPR experiments.

<center>
{{< figure src="/manuals/images/probes/QLP/qlp-overview.png" caption="Schematic Overview of the QLP EPR Probe Head (Manual Iris Control)" width="500px">}}
</center>

An overview of the QLP probe is given in the figure above. For low-temperature measurements, the probe can be operated inside a cryostat. The QLP probe head is compatible with commonly used cryostats, such as the [Oxford Instruments](https://www.oxinst.com/) cryostat model CF935 or the integrated VTI of the Compact-Q spectrometer.

The main features of the probe are:
1. The loop-gap resonator
2. Integrated temperature sensor close to the sample space for accurate temperature determination
3. Direct WR-28 waveguide connection
4. Iris adjustment. The QLP probe head is available either with a remote controlled or manually controlled iris <sup>(1)</sup>

### Optical Access

Optical access to the sample location for e.g. light/laser irradiation is possible in several different ways:

1. Through the sample holder/stick (for fiber access only).
2. Free-space access through the bottom of the resonator.
3. Free-space perpendicular to the sample axis. The probe has a small window (1.5 mm diameter) for direct light access. The location of the window is compatible with the location of the window of the cryostat.

### Temperature Sensor ###

The QLP probe head is equipped with a built-in, calibrated [Cernox](https://www.lakeshore.com/products/categories/overview/temperature-products/cryogenic-temperature-sensors/cernox) temperature sensor. The connector for the temperature controller is located at the top of the probe. A cable is provided together with the probe to connect the probe to a temperature controller.  The pin-out for the connector can be found in the section [Temperature Sensor](/probes/temperature_sensor/).

<sup>(1)</sup>. By default the probe is delivered with remote control of the iris, which is compatible with the [Compact-Q](https://www.bruker.com/en/products-and-solutions/mr/epr-instruments/compact-q-deer-spectrometer.html) or the [Elexsys E580](https://www.bruker.com/en/products-and-solutions/mr/epr-instruments/epr-research-instruments/elexsys-ii-e580.html) series pulsed EPR spectrometers.
