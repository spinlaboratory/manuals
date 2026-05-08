---
title:          "Connecting the Probe to the EPR Bridge"
linkTitle:      "Connecting the Probe"
weight:         20
type:           docs
date:           2023-03-27
description:    "Connecting the Bridge12 XLP to the EPR bridge"
---
### Connection to the EPR Bridge ###

{{% pageinfo color="primary" %}}
### Important

Please make yourself familiar with the instructions below before attempting to install the probe. At no point should you use any force during the installation process. In general, all threads, screws, etc. are imperial size, not metric. Please use the appropriate tools to fasten screws.

{{% /pageinfo %}}

<center>
{{< figure src="/images/probes/bridge12-xlp/probe-top-SMA-connector.png" caption="Bridge12 XLP Overview" width="500px">}}
</center>

The Bridge12 XLP has a single SMA port to connect the probe to the spectrometer (see figure above). The SMA port is located at the top of the probe. Since the iris coupling is adjusting by moving the coupling loop inside the resonator up and down, we suggest using a flexible SMA cable between the bridge and the probe.

To connect the probe to the spectrometer follow these steps:

1. Remove plastic cover from SMA connector (typically used for shipping or long-term storage of the probe).
2. Place probe inside cryostat. If you don't use a cryostat, place probe in the appropriate support structure.
3. Turn/orient the probe so the SMA connector and translation stage is pointing to the back and the Bridge12 logo is facing the front. Typically, the EPR bridge is located on the left.
4. Connect a flexible SMA cable between the EPR bridge and the probe. If your EPR bridge was a WR-90 waveguide port (this will be the case with most older bridges) you first need to connect a WR-90 to SMA adapter.
5. Tighten the SMA connections with your fingers. Ideally, you should use an SMA torque wrench. Do not use pliers to tighten the connection.
6. Connect the temperature sensor to the temperature controller.

{{% pageinfo color="warning" %}}
### Warning

Do not use force to tighten the SMA connector. **Do not use pliers or regular wrenches to tighten the SMA connection**. We recommend using a torque wrench when tightening SMA connections. Torque wrenches for SMA connections are available from [DigiKey](https://www.digikey.com/en/products/detail/huber-suhner-inc/22543130/15203105) or [Mouser](https://www.mouser.com/ProductDetail/HUBER+SUHNER/74_Z-0-0-21?qs=Cv1v43EOJppZn2LnbueqCA%3D%3D). If you don't have a torque wrench available please just use your fingers to tighten the connection. Using the wrong tools can lead to permanent damages of the probe.

{{% /pageinfo %}}

### What's next? ###
* Learn about [Inserting the Sample](/probes/bridge12-xlp/03_inserting_sample/).