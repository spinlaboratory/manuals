---
title:          "Troubleshooting iVTI Operation"
linkTitle:      "iVTI Troubleshooting"
type:           docs
weight:         40
draft:          True
description:    "How to Operate the iVTI"
---
{{% pageinfo color="info" %}}
### Important ###
Before operating the iVTI please familiarize yourself with the principle of operations described in the section [iVTI Overview](/systems/spectrometers/70_magnets/10-superconducting-magnets/30-vti-overview/). 

The following section provides information about day-to-day operation of the cryostat. If you need assistance troubleshooting iVTI operations, please first consult the manual or contact [Bridge12](mailto:info@bridge12.com) or [CRYOGENIC](mailto:sales@cryogenic.co.uk).
{{% /pageinfo %}}

### Blockage in the iVTI Circuit ###

The most likely cause of abnormal iVTI performance is a blockage in the iVTI circuit due to ingress of air.

Symptoms of a iVTI partial blockage before the helium pot can include:

* Reduced flow at a given needle valve setting.
* Reduced pressure at the iVTI pumping side for a given needle valve aperture.
* Increased pressure at the external helium reservoir.
* Decreased temperature of the 2nd stage and helium pot.

The pressure in the helium reservoir increases as the partial blockage limits the flow of helium through the inlet heat exchangers. The 2<sup>nd</sup> stage and helium pot temperatures may fall as the cryocooler heat load is reduced due to the lower helium flow rate at the 2<sup>nd</sup> stage.

Symptoms of a blockage after the helium pot are similar; however, in this case, the helium reservoir pressure may fall as the helium charge is condensed into the system with a reduced flow returning to the reservoir.

If a blockage is suspected the following actions are recommended:

* Heat the iVTI to room temperature. In some cases, this may clear the blockage.

If the blockage persists, please follow these steps:

1. Once the iVTI is at room temperature, disconnect the helium reservoir hose at the face-sealing connector on the cryostat.
2. Connect an external pump to the face-sealing connector of the cryostat using the fitting that was provided with the system. This connection provides the most efficient pumping of the inlet circuit which is the most likely location for any blockage to occur.
3. Close the valve at the head of the iVTI (V11) to the dry pump and open the needle valve fully.
4. Pump the iVTI via the external pump and switch off the compressor.
5. Heat the charcoal trap using the temperature controller and maintain it at 300 K.
6. Wait for the 2<sup>nd</sup> stage to rise in temperature above 90 K.
7. Turn off the charcoal heater, isolate the external pump and restart normal flow through the iVTI circuit.

If the blockage persists, continue to warm the system to room temperature and replace the helium of the iVTI circuit as outlined below.

### Replacing the Helium in the iVTI Circuit ###

If contamination or loss of helium in the iVTI circuit is suspected please follow these instructions to replace the helium charge:

1. Make sure the system is at room temperature and the dry pump is not running.
2. Connect a T-connector to the plug valve on the exhaust side of the dry pump. One arm of the T should be connected to a clean helium source with an in-line valve, and the other to a pump via a valve. The helium source should be either a bottle of high purity gas (99.95%, grade 5) or the boil-off gas from a helium storage vessel. Do not use standard (balloon) grade bottled helium  for this purpose as this can have a high moisture content.
3. Open the connection to the external pump and pump out the helium reservoir. Once the pressure is low enough (< 1e-3 mbar>) activate the dry pump and use it to purge the internal iVTI circuit.
4. Close the valve to the external pump and fill the reservoir to a pressure of +1psi above atmospheric pressure with pure helium gas.

The system is now ready for cooldown and operation.