---
title:          "40 W Q-Band Amplifier"
linkTitle:      "40 W Q-Band Amplifier"
type:           docs
weight:         20
draft:          False
description:    40 W Q-Band Solid-State Microwave Amplifier
---
The Bridge12 AMP-Q40 is a 40 W solid-state microwave amplifier for Q-Band (35 GHz) pulsed EPR spectroscopy. The amplifier can fully replace a TWT amplifier and in combination with the [Bridge12 QLP-1.6 probe ](https://www.bridge12.com/products/q-band-pulsed-epr-resonator/) is a great combination for pulsed dipolar EPR spectroscopy.

{{% pageinfo %}}
### Note ###
The expected pulse length for a 180º-pulse, using a maximally overcoupled [Bridge12 QLP-1.6 resonator](https://www.bridge12.com/products/q-band-pulsed-epr-resonator/) is 16 ns.
{{% /pageinfo %}}

<center>
{{< figure_b12t src="/images/systems/amplifiers/Q40/Q-Band 40 W Amplifier Schematic_600px.png">}}
</center>

A schematic of the amplifier is shown in the figure above. The amplifier has an integrated gate, isolator, and coupler. The input connector for the amplifier is a 2.92 mm connector, while the output is a WR-28 waveguide output.

## Back Panel Connections
The Bridge12 AMP-Q40 can fully replace a TWT amplifier. The following connection to the spectrometer need to be made:

1. **Microwave Input (TX IN):** Input connection of the amplifier. This needs to be connected to the output of the EPR bridge. 2.92 mm connector.
2. **Microwave Output (OUT):** Output connection of the amplifier. This either needs to be connected to the circulator extension (Bridge12 Q-Band spectrometer) or to the input of the EPR bridge. If you are unsure please contact Bridge12 at support@bridge12.com. If your EPR bridge requires a 2.92 mm input connection, we recommend installing a [waveguide to coax adapter](https://www.eravant.com/wr-28-waveguide-to-v-f-coax-adapter-right-angle-5g). 
3. **Gate:** Amplifier blanking. This gate is active HIGH and needs a trigger pulse from the EPR bridge.
4. **Microwave Monitor (TX MON):** Monitor output of the amplifier. This is the same signal that is sent to the probe but attenuated by 40 dB. The signal can be used to monitor the microwave pulses or to characterize the amplifier performance.
5. **15 Pin D-Sub Connector:** Control and monitor signals of the amplifier. For a detailed pin out see [tabel below.](/systems/spectrometers/30-amplifiers/20-q-band-amplifier/#15-pin-d-sub-back-panel-connector)

## Operating Instructions
{{% pageinfo color="warning" %}}
### Warning ###
Do not obstruct the airflow of the cooling air. This can lead to overheating of the amplifier and possible permanent damages.
{{% /pageinfo %}}

### Power Up Procedure

* Make sure that no microwave pulses are sent out by the EPR bridge.
* Turn on the amplifier.
* Wait  a few minutes for the amplifier to warm up. For optimum, stable performance we recommend to leave the amplifier for about 20 minutes for the internal temperature to stabilize. The amplifier has an internal delay of 5 s. You need to wait at least for this time before sending the first microwave pulses.
* Apply gate and microwave pulses.

### Power Down Procedure
* Make sure that no microwave pulses are sent out by the EPR bridge.
* Turn off the amplifier.

### Pulse Timing
{{% pageinfo color="warning" %}}
### Warning ###
Do not Hot Switch the amplifier. Hot Switching occurs, when the blanking gate is disabled while sending a microwave pulse. This can lead to permanent damage of the internal protection circuit of the amplifier. Please see the timing diagram below.
{{% /pageinfo %}}

Please refer to the timing diagram and the values below for recommended pulse timing.

<center>
{{< figure_b12t src="/images/systems/amplifiers/Q40/Q-Band 40 W Amplifier Timing Diagram_600px.png">}}
</center>

* Gate lead, t<sub>g,lead</sub> > 100 ns (200 ns recommended)
* Gate tail, t<sub>g,tail</sub> > 20 ns (50 ns recommended)
* Maximum duty cycle: 20%
* Maximum pulse length: 10 µs
* **ATTENTION: DO NOT HOT SWITCH AMPLIFIER**

## 15 Pin D-Sub Back Panel Connector
| Pin Number | Name | Function | Initial State | Description |
| --- | --- | --- | --- | --- |
| 1 | Reset | Control | - | Resets PA when logic LOW is applied and released |
| 2 | Gate Disable | Control | LOW | Applying a HIGH signal disables gate of amplifier |
| 3 | Drain Disable | Control | LOW | Applying a HIGH signal disables drain of amplifier |
| 4 | RF IN Over | Indicator | LOW | Pin will be latched to HIGH when input signal is to high |
| 5 | Temp Over | Indicator |  LOW | Pin will be latched to HIGH when maximum amplifier temperature is exceeded |
| 6 | Current Over | Indicator |  LOW | Pin will be latched to HIGH when drain current limit is reached |
| 7 | ID Imbalance | Indicator |  LOW | Pin will be latched to HIGH when an imbalance in the drain current of the combining branches occurs |
| 8 | PA Off Alarm | Indicator |  LOW | Pin will be latched to HIGH when any of the protection limits are reached |
| 9 | - | not connected | - | |
| 10 | - | not connected | - | |
| 11 | - | not connected | - | |
| 12 | - | not connected | - | |
| 13 | - | not connected | - | |
| 14 | +5 V | Power Supply | +5 V | +5 V DC power supply for reference. Mac. 400 mA available |
| 15 | GND | Ground | GND | Electrical ground |


<!-- ### Specifications
* Frequency Range: 32-38 GHz
* Small Signal Gain: 55 dB
* P<sub>sat</sub>: 45 dB
* P<sub>1dB</sub>: 39 dBm
* Power Requirements: 48V, 2 Amp (typ.), 6 A (max) -->
