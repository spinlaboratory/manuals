---
title:          "Cooling Down the Magnet"
linkTitle:      "Magnet Cooldown"
type:           docs
weight:         20
draft:          True
description:    "How to cool down the magnet"
---
{{% pageinfo color="warning" %}}
### Warning ###
Please make sure to read the instructions for cooling down the magnet carefully. Make sure you don't have any questions and all required equipment is in place.

These instructions are not to be used for initial cooling down of the magnet. For these instructions it is assumed that the magnet was properly decommissioned by [Bridge12](mailto:info@bridge12.com) or [CRYOGENIC](mailto:sales@cryogenic.co.uk).

If you have additional questions please do not hesitate to reach out to [Bridge12](mailto:info@bridge12.com) or [CRYOGENIC](mailto:sales@cryogenic.co.uk).
{{% /pageinfo %}}

## Required Equipment ##
For cooling down the magnet or recharging the helium reservoir of the integrated VTI (iVTI) the following additional equipment is required:

* Vacuum pump, preferable a turbomolecular pump with a capacity of 12 m<sup>3</sup>/hr.
* Various vacuum hoses, matching center rings and clamps
* High grade helium gas (grade 5). This is only required for recharging the helium compressor or the helium reservoir of the iVTI. For changing the sample regular grade helium gas is sufficient.
* Hoses, fittings, pressure regulator, etc. to connect the helium cylinder to the iVTI.

## 1. Evacuation of the Magnet Cryostat ##

The magnet cryostat has a single vacuum space which is evacuated via the bellows sealed valve fitted to the cryostat top plate. As a guide, this space should be evacuated using a pump with a capacity of at least 12 m3/hr and a base pressure of <10-4 mbar. Outgassing of the superinsulation occurs whenever the cryostat is allowed to warm up to room temperature. Also, after a magnet quench it is sometimes necessary to evacuate the magnet cryostat, especially if you can't reach the normal base temperature of the magnet after a quench.

To evacuate the magnet cryostat, connect a vacuum pump to the vale located at the top of the cryostat. Start the vacuum pump and once the pump has reached its base pressure open the valve to the magnet cryostat. The cryostat should be pumped down to a pressure of <10-3 mbar before attempting to cool down. If the pressure decrease is slow, this may be an indication of moisture in the superinsulation which will require more extended pumping of the interspace.

Under normal circumstances there is no need to vent the vacuum space to atmospheric pressure. It is strongly recommended to not vent the vacuum space to decrease the time it takes for the magnet to come up to room temperature. If you have to vent the magnet cryostat please consult the instructions in the magnet manual or contact [CRYOGENIC](mailto:sales@cryogenic.co.uk).

## 2. Prior Checks Before Cooling Down the Magnet ##

Before cooling down the magnet, please observe the following operational checks:

* **Magnet**
    1. The cryostat vacuum space is adequately evacuated to a base pressure of <10e-3 mbar
    2. The compressor is connected to the electrical mains according to the supply information on the compressor housing. Please refer to the compressor manual for further information regarding power requirements.
    3. Adequate water cooling is provided for the compressor (water-cooled versions only). Please refer to the compressor manual for the correct specification for the water circuit.
    4. Both ends of the flexible hoses connecting the compressor to the cold head are properly tightened. Make sure the charcoal trap is installed. Please use the supplied tools to tighten all connections. 
    5. The electrical lead from the compressor to the cold head is connected.
    6. The current leads running from the magnet power supply are securely attached to the magnet terminals.
    7. The magnet coil is electrically isolated from the cryostat. To check this, measure the resistance between a magnet current terminal and one of the cryostat top plate outer fixing bolts. A value of &#8805; 500 k&#8486; is typical.
    8. The temperature monitors/controllers are installed properly and the lead(s) are connected.
    9. The static helium pressure in the compressor is correct to ensure it is at the recommended value. Please refer to the compressor manual for the correct specification of the helium pressure. If the pressure is lower than expected please follow the instructions in the compressor manual before starting the compressor.
    10. The system is properly positioned such that there are no significant ferromagnetic objects (e.g.; steel beams, pumping stations etc) close to the cryostat. It should be noted that structural supports on the floor must also be considered when positioning the cryostat. Please contact [CRYOGENIC](mailto:sales@cryogenic.co.uk) if you are unsure about the possible influence of magnetic objects adjacent to the system. 
* **integrated VTI (iVTI)**
    1. The dry pump for the iVTI is connected to an outlet. At this time, the dry pump is not powered on.
    2. The external gas reservoir must be charged to the correct pressure with clean helium gas and connected to the cryostat (see system specification). The reservoir is connected to the iVTI gas circuit via a face-sealing connector.
    3. It is recommended that the flow through the iVTI is checked at room temperature prior to cooling down the magnet.
        1. Make sure the dry pump bypass valve (V16) is closed and th helium reservoir valve (V12) is opened.
        2. Make sure the iVTI butterfly valve is open
        3. Switch on the dry pump and pumping for a short time on the iVTI head with the needle valve fully open and circulating gas through the external dump as in normal operation at cold temperatures. The expected flow should be in the range of 5-15 mbar.
        4. Having checked the room temperature flow, switch oof the dry pump
        5. Open the bypass valve (V16). This allows gas to circulate via natural convection throughout the gas circuit during the cooldown of the magnet. The convective flow helps to cool the internal components of the gas circuit whilst minimizing the wear of the pump. 
    4. Charge the static column, the space where the resonator is located, to 1 atmosphere of clean helium gas from an external source of helium. The gas is necessary to conduct heat from the wall of the static column and maintain a small temperature differential between the helium flowing in the annular space around static column and the sample probe. It is recommended to charge the static column prior to cooldown as once the system is cold it is more difficult to judge the quantity of helium being added due to condensation of the gas as it enters the column. The approximate volume of the static column is .05 litres.

## Cooling Down the Magnet ##

Once all prior checks have been completed ([see instructions above](/systems/spectrometers/70_magnets/10-superconducting-magnets/20-cooldown/#2-prior-checks-before-colling-down-the-magnet)) the magnet cooldown can be started. It is recommended, that the system monitor is started to log all temperatures during the cooldown process. 

Cooling the magnet is simply a matter of starting the helium compressor:
1. Turn the switch located on the back of the compressor into the ON position.
2. Press the ON button to start the compressor.

Typically the 1<sup>st</sup> stage of the cryocooler will cool fastest followed by the 2<sup>nd</sup> stage and then the magnet. For this magnet, the cooldown time is typically about 22 hrs. It should be noted that initially, the operating pressure at the compressor will be high and then reduce (typically by 20 %) as the magnet temperature drops and the cryocooler is required to do less work to remove heat from the system. Once the base temperature of the magnet is achieved the magnet may be energized.

<center>
{{< figure_manuals src="/images/systems/q-band-magnet/Q-Band_Magnet_Cooldown_600px.png" caption="Temperatures of a Typical Magnet Cooldown">}}
</center>

Temperatures for a typical cooldown of the magnet are shown in the figure above. The following table has shows some typical temperatures once the magnet is at its base temperature.

**Q-Band Magnet with iVTI Base Temperatures**
| Parameter | Value | Parameter | Value |
| ----------| ----- | --------- | ----- |
| Cryocooler 1st stage | 36.2 K | Persistence Switch | 3.0 |
| Cryocooler 2nd stage | 3.0 K | Helium pot (Not heated) | 3.0 K |
| Magnet LHS winding | 3.0 K | Helium pot (heated) | 3.2 K |
| Magnet RHS winding | 3.0 K | Charcoal trap (not circulating) | 46.6 K |

## Checking the iVTI Operation ##

Once the magnet has avhieved base temperature:

1. Close the bypass valve (V16) across the dry pump.
2. Make sure the cryostat heater is switched off.
2. Start the dry pump.
3. Adjust the needle valve to a pressure of approximately 6 mbar at the iVTI pump port. Please note the needle valve may require several further adjustments as the temperature profile within the flow circuit varies whilst steady-state flow conditions are established in the circuit.

For further information/instructions on how to operate the iVTI please see the section about [operating the iVTI](/systems/spectrometers/70_magnets/10-superconducting-magnets/30-integrated-vti/30-vti-operation/).
