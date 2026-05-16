---
title:          "Overview of the iVTI Operation"
linkTitle:      "iVTI Overview"
type:           docs
weight:         10
draft:          True
description:    "How the Integrated VTI (iVTI) Works"
---
## iVTI - How it Works ##

The integrated Variable Temperature Insert (iVTI) is a liquid cryogen-free (dry) cryostat built into the superconducting magnet of the EPR spectrometer. It operates by circulating helium gas around a closed-loop circuit cooled by the same cryocooler that is used to cool the superconducting magnet coil. The iVTI can operate continuously and in conjunction with the magnet.

<center>
{{< figure_manuals src="/images/systems/q-band-magnet/iVTI Schematics_600px.png" caption="Schematic of the iVTI">}}
</center>

A schematic of the iVTI is shown above. High quality helium gas (grade 5) is stored at room temperature in the helium reservoir and a dry (oil-free) pump drives drives the circulation of the helium gas through a closed cycle circuit. Under normal operations, the bypass valve (V16) is closed and the helium reservoir valve (V12) and iVTI outlet valve (V11) is open. The helium gas passes from the helium reservoir and into the iVTI circuit via the self-sealing helium gas inlet.

Once the helium gas enters the magnet space, it first passes through a charcoal filter to remove any impurities within the gas. It then flows through the first stage heat exchanger which cools the gas to ~40K. The gas then passes to the second stage heat exchanger 
where it is cooled further to below 4.2K and condenses in the helium pot. The helium pot has an integrated heater to keep the pot at a recommended temperature of 3.1 K.

To cool the cryostat space, the liquid helium then flows across the needle valve, at which point it expands and cools further to approximately 1.6K. The cooled gas/liquid mixture then passes through the iVTI heat exchanger where the helium is heated to the required temperature. The helium gas flows upwards in an annular space surrounding the static column (containing the EPR probe) to the top of the iVTI where it exits and is circulated through the pump and exhausts back to the dump vessel.

The probe is cooled using an exchange gas, which is cooled at the wall of the static column.

The temperature inside the cryostat is regulated using the iVTI heater located at the bottom of the static column, and the heating power is regulated by the temperature controller. To achieve the most accurate temperature at the position of the sample, all Bridge12 EPR probes are equipped with a calibrated Cernox temperature sensor. This sensor is located as close to the sample as possible for accurate temperature readings and this temperature is used to control the heater power in a feedback loop.

If the probe is removed from the cryostat, the temperature can be regulated using the internal iVTI temperature sensor. Note, that the iVTI temperature is not necessarily equal to the sample temperature.

### Integrated Heaters 
The magnet system with integrated VTI has in total three internal heaters that are all connected to the temperature controller (typically a LakeShore Model 350). The following table summarizes the function of the heater and gives some default operation parameters.

| Heater | Description |
| --- | --- |
| Heater 1 (VTI) | The VTI heater is used to regulate the cryostat temperature. Typically, the heater control loop is connected to one of the temperature sensors (this is done in the settings for the temperature controller). For the Q-Band spectrometer the user has the option to control the cryostat temperature using the temperature sensor of the VTI or the one integrated into the EPR probe. Bridge12 recommends using the temperature sensor of the EPR probe for accurate temperature readings.|
| Heater 2 | Not used |
| Heater 3 (Helium Pot) | During operation some the helium of the VTI used for cooling is condensed inside the helium pot and the flow of helium is controlled by the needle valve (see figure above). Under normal conditions, the temperature of the helium pot should be kept at around 3.3 K. To achieve this temperature the heater output power should be set to a value of about 5 to 10 % (open loop) to maintain that temperature. This value only needs to be changed if the user wants to go to very low temperatures (e.g. < 5 K) and the user should first read the instructions in the manual to set the temperature of the helium pot. |
| Heater 4 (Charcoal Trap) | During normal VTI operations the helium passes through an activated charcoal filter to remove any residues (oxygen, nitrogen, etc.) from the helium gas used for cooling. After a while this charcoal filter needs to be degassed (cleaned) using the charcoal heater. This is a low power heater and the heater can be ramped up to 100%. While ramping up the  heater, please monitor the temperature of the charcoal trap in the logging system. During normal operations, the charcoal heater is off. | 
