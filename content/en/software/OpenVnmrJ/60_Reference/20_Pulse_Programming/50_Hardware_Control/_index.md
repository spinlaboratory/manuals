---
title:        "Hardware Control"
linkTitle:    "Hardware Control"
type:         docs
weight:       50
draft:        false
description:  ""
---

### Triggers of the SpinCore Board ###

The SpinCore board has four TTL lines, named Flag0 to Flag3. They have been assigned the following functions.

| Name  | Usage |
| ----- | ----- |
| Flag0 | Trigger line to the MPS if the "mps" parameter is set to "ext" It is triggered by the status pulse element when the xm parameter for that status period is 'y'.|
| Flag1 | This controls the receiver unblanking. It goes high after the alfa delay when the SpinCore board is triggered to start data acquisition.|
| Flag2 | This controls the amplifier unblanking. It goes high at the beginning of the rof1 delay prior to turning on the RF. It goes low after the RF is turned off.|
| Flag3 | The controls setting the system into tune mode for RF turning. It goes high at the beginning of the "mtune" process and goes low when "mtune" completes. There is a delay of d1 duration prior to the start of the RF tuning process where Flag3 is also high. This gives the system time to switch into tune mode.|

### Receiver Attenuator ###
The "receiver attenuator" is a USB device controlled by the ``/vnmr/bin/mcl_RUDAT`` command. The range of values is 0 to 120 (in dB) in 0.25 steps. One can set the attenuator directly from a terminal with the command ``/vnmr/bin/mcl_RUDAT <value>``.

The attenuator is controlled from a pulse sequence with the rattn parameter.