---
title:          "Specifications"
linkTitle:      "Specifications"
weight:         20
type:           docs
date:           2022-09-23
description:    ""
draft:          True
---
The Bridge12 Active Electric Shims (AES) are a 5 channel shim system for electromagnet with a horizontal field. These magnets are typically used in Electron Paramagnetic Resonance (EPR) spectroscopy. The five channels or the shims are: Z0 (or B0), Z1, Z2, X, and Y. Each channel can operate at a current of up to 1.5 A.

| Parameter               | Value | 
|-------------------------|-------|
| Number of channels      | 5     |
| Maximum current/channel | 1.5 A |
| Spacing                 | 53 mm |

{{% pageinfo color="warning" %}}
### Warning

Do not exceed a current of (+/-) 1.5 A per channel to avoid permanent damage to the shims.
{{% /pageinfo %}}

### Shim Interface Pinout

| Pin# (sub-D) | Shim Connection | Pin# (sub-D) | Shim Connection |
|--------------|-----------------|--------------|-----------------|
| 1            | Z(B)0 (s)       | 2            | Z(B)0 (r)       |
| 3            | Z1 (s)          | 4            | Z2 (r)          |
| 5            | Z2 (s)          | 6            | Z2 (r)          |
| 7            | X (s)           | 8            | X (r)           |
| 9            | Y (s)           | 10           | Y (r)           |
| 15           | GND             | Shield       | GND             |
(GND - Ground, s - supply, r - return)

If you need help at any step of the installation please contact Bridge12 at support@bridge12.com.