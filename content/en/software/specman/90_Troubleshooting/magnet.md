---
title:          "Magnet"
linkTitle:      "Magnet"
type:           docs
weight:         30
draft:          True
description:    "Troubleshooting magnet issues"
---
## Magnet Control ##
[Recovering after Magnet Quench](/software/specman/90_troubleshooting/specman4epr/#re-installing-specman4epr-on-new-hardware)

___

### Recovering after Magnet Quench
A magnet quench can occur for several reasons, such as sudden loss of electricity, or the cooling water supply shuts down. If the helium compressor shuts off while the magnet coils are charged, or are in persisten mode, the user has about 8 minutes left until the magnet coils have reached about 8 K and the magnet will quench. However, in contrast to a wet magnet, this is rather uneventful. The temperatures of all sensors will suddenly increase. Once electricity (or cooling water) is back, the helium compressor will restart automatically and the magnet will be cooled. If the compressor doesn't restart automatically, it has to be done manually.

Once the magnet has reached its base temperature it is again safe to operate the system. The temperatures can be observed either directly on the temperature monitor or through the systems logger. Typical temperatures are:

| Sensor Name | Typical Temperature (K) |
| ----------- | ----------------------- |
| Cryo Head (1st Stage) | ~ 37 K |
| Cryo Head (2nd Stage) | ~ 3 K |
| Magnet Coil (LHS, RHS) | ~ 3 K |
| Heater Switch | ~ 5.5 K |

To energize the magnet again follow these steps:

1. Make sure the helium compressor is running and that the magnet has reached its base temperatures (see table above).
2. The power supply may show the message *HEATER switched off at XX.XXX Amps*. This indicates, the magnet was in persistent mode when the quench occurred. However, the user can safely ignore this message. To clear this message:
    1. If the power supply is in remote control mode, take the power supply back into local front panel operation mode by pressing the button labeled *REMOTE*.
    2. Press the *HEATER* button to activate the switch (the LED light will come on). Wait for a few seconds.
    3. Press the *HEATER* button again to switch the heater off.

Alternatively, the user can just restart SpecMan4EPR and start using the magnet.
