---
title:          "EPR Bridge"
linkTitle:      "EPR Bridge"
type:           docs
weight:         20
draft:          False
description:    "Troubleshooting issues of the EPR bridge"
---
This page covers common issues with the EPR bridge (X-Band IF system) and how to resolve them.

## No Communication with the Bridge

If SpecMan4EPR cannot connect to the EPR bridge at startup, check the following:

1. **USB connection** — Make sure the USB cable between the PC and the X-Band IF system is properly connected. Try unplugging and reconnecting the cable.
2. **COM port** — Open the Windows Device Manager and verify that the LabJack interface appears under *Ports (COM & LPT)*. Note the COM port number and compare it with the setting in the SpecMan4EPR device configuration. Update the COM port in the configuration if they do not match. See the [Configuration](/software/specman/20_configuration/) section for instructions.
3. **LabJack driver** — If the LabJack device does not appear in the Device Manager, the driver may not be installed. Download and install the latest LabJack driver from the [LabJack website](https://labjack.com/support/software/installers).
4. **Power** — Confirm that the X-Band IF system is powered on (the front panel LED should be illuminated).

## Microwave Not Detected / No Tune Dip Visible

If no resonator tune dip is visible in the SpecMan4EPR resonator plugin:

1. Confirm the spectrometer is in **Operate** mode (not Standby).
2. Check that the synthesizer (SRC) is connected and its COM port is correctly configured.
3. Verify all waveguide and coaxial connections between the X-Band IF system, the frequency extension (if used), the amplifier, and the probe are properly tightened.
4. If using a Q-Band extension, confirm the Q-Band extension is powered and all WR-28 flange connections are properly fastened.

## Noisy or Unstable Signal

1. Check that all SMA connectors are properly tightened (recommended torque: 10 Nm using a torque wrench).
2. Ensure the 10 MHz reference clock output of the X-Band IF is connected to both the AWG and the digitizer clock inputs to synchronize all instruments.
3. Verify that the PFU blanking gate (BLNK) timing is correct. The gate should open at least 100–200 ns before each microwave pulse and close at least 20–50 ns after the pulse ends. See the [Amplifier Timing](/systems/spectrometers/30-amplifiers/20-q-band-amplifier/#pulse-timing) section for details.

## Contact

If the issue cannot be resolved, contact epr-applications@bruker.com with the system serial number and a detailed description of the problem.
