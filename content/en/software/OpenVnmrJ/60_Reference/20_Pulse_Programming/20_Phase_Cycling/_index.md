---
title:        "Phase Cycling"
linkTitle:    "Phase Cycling"
type:         docs
weight:       20
draft:        false
description:  ""
---
There are several phase variables that control the phase of RF pulses and the phase of the receiver. These are:

* zero, one, two, three
* t1, t2, t3, t4, t5, t6, t7, t8, t9, and t10
* oph

The constants PH0, PH90, PH160, PH270 are used to select the 0, 90, 180,and 270 degree phase. The constants ZERO, ONE, TWO, and THREE similarly represent the 0, 90, 180, and 270 degree phase. These are present for compatibility with Varian/Agilent pulse sequences.

There are also phase tables t1-t10 and oph. These tables may contain any number of phase elements. The particular element used is determined by the current transient (CT) being acquired. The tranisients increment from 0 to (nt-1) where nt is the total number of transients.

The zero, one, two, and three phase variables are initialized to ZERO, ONE, TWO, and THREE, respectively. The oph phase table controls the phase of the receiver. It is initialized to the four values {ZERO,ONE,TWO,THREE}, which represents the "cyclops" phase cycle. The t1-t10 tables are only used if they are defined by the pulse sequence.

The cp parameter (cycle phase) is typically set to 'y'. If it is set to 'n', the cycling of the receiver phase (oph) is turned off. That is, only the first element of the oph table is used. This is usually only used during FID shimming and wobble.

The second argument to the pulse element is the phase. For example:

{{<highlight Shell>}}
pulse(pw, zero);
{{</highlight>}}

That second argument can to zero, one, two, or three. Equivalently, it can be PH0, PH90, PH180, or PH270. It can also be oph, in which case the phase of the pulse tracks the receiver phase. Phase tables t1-t10 can also be used. For example:

{{<highlight Shell>}}
static int ph1 = {PH0, PH180, PH90, PH270};
{{</highlight>}}

{{<highlight Shell>}}
void pulsesequence()
{
   ...

   settable(t1,4,ph1);

   pulse(pw,t1);

}
{{</highlight>}}

By setting oph to a table, one can alter the receiver phase.

{{<highlight Shell>}}
settable(oph,4,ph1);
{{</highlight>}}
