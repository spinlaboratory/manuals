---
title:          "Probe Specifications"
linkTitle:      "Specifications"
weight:         50
type:           docs
date:           2023-03-27
description:    "XLP Probe Description"
draft:          False
---
## Bridge12 XLP ##

The Bridge12 XLP is a Loop-Gap Resonator (LGR) for pulsed EPR spectroscopy at X-band frequencies (~ 9.6 GHz). 

Pulsed Electron Paramagnetic Resonance (EPR) spectroscopy using high-power microwave pulses or arbitrary waveform generated (AWG) broadband pulses require a large resonator bandwidth (low resonator Q) to avoid distortion of the pulse shape.

However, a large resonator bandwidth often comes at the cost of a reduced microwave conversion factor. Loop-Gap Resonators (LGR) are the preferred choice for pulsed EPR experiments since they have large microwave conversion factors and excellent field homogeneity across the length of the sample. This is especially important when using AWG generated broadband pulses.

### Resonator Specifications (Bridge12 XLP-3.0)
| Parameter                                        | Value                             |
| ------------------------------------------------ | --------------------------------- |
| Resonator Frequency (empty)                      | 9.6 GHz                           |
| Resonator Frequency (with sample capillary)      | 9.5 GHz                           |
| Microwave Conversion Factor (critically coupled) | > 3.5 G/sqrt(W)                   |
| Bandwidth (critically coupled)                   | Q ~ 700 <br> (15 MHz)             |
| Microwave Conversion Factor (overcoupled)        | > 1 G/sqrt(W)                     |
| Bandwidth (critically coupled)                   | Q < 100 <br> (> 100 MHz)          |
| Maximum Sample Diameter                          | 3.0 mm                            |
| Resonator Height                                 | 10 mm                             |
| Operating Temperature                            | 4 K to RT                         |


### Bridge12 XLO ###

The Bridge12 XLO probe is based largely on the design of the XLP probe but has an integrated NMR coil for solution-state Overhauser Dynamic Nuclear Polarization (ODNP) experiments. The XLO probe has similar specifications as the XLP probe (frequency, conversion factor, etc.) but due to the NMR coil the sample access is limited to 1.2 mmm.

## What's next?
* [Resonator Description](/probes/bridge12-xlp/description/).
