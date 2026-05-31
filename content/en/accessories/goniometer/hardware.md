---
title:          "Using the Goniometer"
linkTitle:      "Using the Goniometer"
weight:         10
type:           docs
date:           2024-07-11
draft:          False
description:    "How to assemble and use the goniometer"
---
The goniometer accessory attaches to the top of an EPR probe and allows rotation of the sample stick around its axis. This enables angle-dependent EPR measurements, for example to study the orientation dependence of EPR spectra in single crystals, oriented films, or mechanically aligned samples.

## Parts of the Goniometer

The goniometer assembly consists of the following components:

| Part | Description |
|------|-------------|
| Goniometer housing | The main body of the goniometer that attaches to the top of the EPR probe |
| Stepper motor | A compact stepper motor that drives the rotation of the sample stick |
| Stepper motor controller | A BIGTREETECH SKR MINI E3 V3.0 controller board that translates software commands into motor steps |
| Sample stick adapter | Connects the sample stick to the goniometer rotation axis |
| USB cable | For serial communication between the PC and the stepper motor controller |
| Power supply | Powers the stepper motor controller |

## Sample Stick

The goniometer requires a dedicated sample stick that is compatible with the rotation adapter. The sample stick fits into the sample stick adapter on the goniometer and rotates with it. The sample tube (capillary) is mounted at the end of the sample stick as usual.

{{% pageinfo color="primary" %}}
### Important
Make sure the sample stick is fully seated in the goniometer adapter before starting a rotation experiment. An improperly seated sample stick may slip during rotation and produce incorrect angle-dependent data.
{{% /pageinfo %}}

## Attaching the Goniometer to the Probe

To attach the goniometer to the EPR probe:

1. Make sure the EPR probe is installed in the spectrometer and the sample stick is removed.
2. Slide the goniometer housing over the top of the probe until it seats on the probe flange.
3. Secure the goniometer to the probe using the provided locking screws. Tighten finger-tight — do not overtighten.
4. Insert the sample stick through the goniometer adapter and lower it into the probe until it reaches the resonator position.
5. Connect the stepper motor controller to the PC via the USB cable.
6. Connect the power supply to the stepper motor controller.

The goniometer is now ready for use. For instructions on how to control the goniometer from a computer, see the [Remote Control](/accessories/goniometer/software/) section.

## Removing the Goniometer

To remove the goniometer:

1. Remove the sample stick from the probe.
2. Loosen the locking screws and lift the goniometer housing off the probe.
3. Disconnect the USB cable and power supply.
