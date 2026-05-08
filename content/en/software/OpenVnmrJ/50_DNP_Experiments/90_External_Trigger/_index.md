---
title:        "Using the External MPS Trigger"
linkTitle:    "External Trigger"
type:         docs
weight:       90
draft:        false
description:  "Using the external MPS trigger in DNP experiments"
---
The Bridge12 MPS microwave source can be controlled by an external trigger to enable and disable the microwave power programmatically through the NMR pulse sequence.

To be able to use the external trigger, connect the *MPS TRIG* output from the SCN backpanel to the MPS *Ext. Trig* input of the MPS backpanel, using a BNC cable.

To enable the external trigger:

1. Select a pulse sequence.
2. In the MPS panel select the *Ext* mode from the dropdown menu.
3. Select the checkmark *Ext* under *RF*

Now, the MPS is set to accept an external trigger signal. In this mode the RF output set by the *status()* command during the pulsesequence. In OVJ, every pulse sequence is divided into three different sections, labeled *A*, *B*, and *C*. This label is shown in the bottom row when displaying a pulse sequency in OVJ using the ```dsp``` command.

The microwave status (on or off) for these sections is controlled by the ```xm``` variable in the pulse program.

{{<highlight shell>}}
xm
{{</highlight>}}

To enable the microwave power during Status(A) in the pulse program, but disable the power during Status(B), and Status(C) the *xm* variable has to be set to

{{<highlight shell>}}
xm='ynn'
{{</highlight>}}

When only a single character is given the status() is set for A,B,C to the same value.

When the *xm* variable is set, the status can be seen in the display of the pulsesequence by typing

{{<highlight shell>}}
dps
{{</highlight>}}

An additional line labeled *MW* appears, indicating the status of the microwave output during each segment of the pulse sequency. In this example, the microwave power is enabled (*ON*) during Status(A) but disabled during Status(B), and Status(C).

<center>
{{< figure_b12t src="/images/software/OVJ/image-sources/dps_yes_mps.png" width="70%">}}
</center>

Note that the position of the status() statement in the pulsesequence determines where a state starts and ends. As an example the following modified 's2pul' includes *p1* in status A and *pw* in status B

{{<highlight C>}}
// Copyright (C) 2022 Bridge12Technologies
// You may distribute under the terms of either the GNU General Public

/*  s2pul - standard two-pulse sequence with modified status */

#include <standard.h>

void pulsesequence()
{
   /* equilibrium period */
   status(A);
   hsdelay(d1);

   /* --- tau delay --- */
   pulse(p1, zero);
   status(B);
   hsdelay(d2);

   /* --- observe period --- */
   pulse(pw,oph);
   status(C);
}
{{</highlight>}}
