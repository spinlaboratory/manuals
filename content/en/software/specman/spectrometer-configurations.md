---
title:          "Spectrometer Configuration"
linkTitle:      "Spectrometer Configuration"
type:           docs
weight:         40
draft:          False
description:    "How to configure your spectrometer"
---
SpecMan4EPR supports a wide range of hardware configurations. The spectrometer configuration defines which devices are connected to the system, how they communicate, and what their roles are in the experiment. A configuration is saved as a set of device configuration files in the SpecMan4EPR configuration directory (`C:\SpecMan4EPR\cfg`).

{{% pageinfo color="primary" %}}
### Note
Your EPR spectrometer was delivered with a pre-configured version of SpecMan4EPR matched to your specific hardware. You should not need to create a configuration from scratch. This page describes the configuration structure for reference and for situations where a reconfiguration is required (for example, after a hardware change or software reinstallation).
{{% /pageinfo %}}

## Overview of the Configuration Structure

A SpecMan4EPR configuration consists of the following device entries:

| Device | SpecMan4EPR Name | Description |
|--------|-----------------|-------------|
| EPR Bridge (X-IF + LabJack) | `BRIDGE` | Controls the X-Band IF microwave bridge, including synthesizer, PFU, and receiver gain settings |
| Microwave Synthesizer | `SRC` | The Windfreak SynthHD dual-channel microwave synthesizer |
| Digitizer | `DAQ` | The data acquisition digitizer (model depends on configuration) |
| Arbitrary Waveform Generator | `AWG` | The AWG used to generate pulse shapes (model depends on configuration) |
| Pulse Programmer | (integrated) | The pulse programmer for rectangular pulses (integrated in the X-IF system via the LabJack) |
| Magnet Controller | `FLD` | The superconducting magnet power supply (for systems with a superconducting magnet) |

## Accessing the Device Configuration

To open the Device Configuration window in SpecMan4EPR:

1. Click the **Configuration of devices** button in the main toolbar (indicated by a red box in the SpecMan4EPR documentation figures).
2. The Device Configuration window opens in **Basic Access** mode. In this mode all parameters are visible but cannot be edited.
3. To edit parameters, click **Expert Access** in the upper right of the window and confirm the password prompt by pressing **OK**.

For a detailed description of the individual device parameters, see the [Configuration](/software/specman/20_configuration/) page.

## Saving and Loading Configurations

In Expert Access mode, use the **Save** button to save the current device configuration to a file, and the **Load** button to restore a previously saved configuration. Bruker recommends keeping a backup copy of a working configuration file before making any changes.

## Common Configuration Tasks

### Changing the COM Port

If a hardware component (synthesizer, bridge controller, etc.) is assigned to a different COM port after a reinstallation or hardware change:

1. Open Device Manager in Windows to identify the new COM port number.
2. Open SpecMan4EPR and switch to Expert Access mode in the Device Configuration window.
3. Locate the affected device (e.g., `BRIDGE` or `SRC`).
4. Update the `Resource` or `Resource1` parameter with the new COM port number (e.g., `COM5`).
5. Save the configuration.
6. Restart SpecMan4EPR to apply the changes.

### Adding a New Device

Contact epr-applications@bruker.com if you need to add a new hardware device to an existing SpecMan4EPR configuration. Adding new devices requires knowledge of the specific SpecMan4EPR driver for that device.
