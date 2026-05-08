---
title:        "Pulse Sequence Parameters"
linkTitle:    "Pulse Sequence Parameters"
type:         docs
weight:       30
draft:        false
description:  ""
---
The following parameters are used by all pulse sequences. The global parameters do not exist and the defaults are the
normal values. 

| Parameter Name | Description |
| -------------- | ----------- |
| B12_BoardNum   | global parameter specifying the SpinCore board number. <br> default is 0
| B12_BypassFIR  | global parameter specifying whether to bypass the SpinCore FIR filter. <br> default is 1
| B12_ADC        | global parameter specifying the SpinCore ADC frequency in MHz. <br> default is 75.0
| mps            | set the state of the MPS when the experiment starts. At the end of the experiment, the state of the MPS will be returned to its original state. The mps parameter can be set to one of four values. <br> manual - leave the MPS in the state it has been manually set to. <br>off - turn the MPS off (rfstatus=0) <br> on - turn the MPS on (wgstatus=1 rfstatus=1) <br> ext - turn the MPS to ext state (wgstatus=1 rfstatus=2) <br> <br> If mps='manual' and the MPS is set in the "EXT" state or if mps='ext', then pulse sequences will be able to control the MPS with the status() pulse element. Also, the mpspower parameter will be active. <br> The default value for mps is 'ext'.|

Experiment parameters used by all pulse sequences include:

| Parameter Name | Description |
| -------------- | ----------- |
| exppath        | the path name of the experiment where data will be stored. This is normally set when one does a "jexp" or join experiment.|
| arraydim       | The total number of FIDs to be acquired for this experiment. This parameter is automatically set when one arrays a parameter.|
| sfrq           | base frequency of the RF channel. This is normally a calculated value based on the selected nucleus (tn), the lockfreq, and any additional offset (tof).|
| np             | the number of points in an acquired FID (total points, sum of reals and imaginaries). Number of complex pairs is np/2.|
| mpspower       | the power of the MPS. Range is 0-60. If mpspower=-1, the MPS will be set to the "OFF" state. The mpspower parameter is only active if mps='ext' or if mps='manual' and the MPS unit has been manually set to the "EXT" state.|
| nt             | number of transients.|
| sw             | spectral width, in Hz.|
| tpwrf          | amplitude of an RF pulse. Values range from 100.0 (full power) to 0.0 (no power). If tpwrf does not exist, or if it is set to "Not used" (tpwrf='n'), full power hard pulses are used. If tpwrf is set to a number between 0 and 100, the "shaped pulse" feature of the SpinCore board is used. The shape is a rectangular shape and tpwrf controls the amplitude of this shape. This allows for less than full power pulses.|
| rattn          | controls the additional "Receiver attenuator" hardware. If rattn does not exist or is set to "Not used" (rattn='n'), then no instructions are sent to the additional attenuator. If rattn is a value between 0 and 120, then that value is sent to the attenuator. Setting rattn=0 means no attenuation of the incoming signal. Setting rattn=120 means adding 120 dBm of attenuation to the incoming signal.|
| rof1           | time prior to an RF pulse to allow for the amplifier turnon time.|
| rof2           | time following an RF pulse. Often reflects probe ringdown time.|
| alfa           | delay prior to acquiring data. Often used to account for filter group delay.|
| cp             | cycle phase, controls the behavior of the oph phase table. For cp='y', the oph phase table uses all elements of the table. If cp='n', only the first element of the table is used.|
| array          | used to determine what parameters, if any, are arrayed.|
| ni             | number of increments in the first indirect dimension. This identifies a 2D experiment.|
| ix             | current increment. It's values will range from 1 to arraydim. It can be used to select alternate sequences for an arrayed experiment. For example, to acquire data where every other FID has the microwave source turned on, one could do something like the following:

{{<highlight C>}}
if (ix % 2)
        status(A);
else
        status(B);|
{{</highlight>}}


Other parameter associated with a pulse sequence are used within the pulse sequence itself. For example, the s2pul.c pulse sequence uses

| Parameter Name | Description |
| -------------- | ----------- |
| d1             | relaxation delay prior to the first pulse.|
| p1             | pulse width of the first pulse.|
| d2             | delay between the first and second pulse.|
| pw             | pulse width of the second pulse.|

If custom parameters are defined for a pulse sequence, their values may be obtained with the getval() and getstr() pulse elements.

Processing parameters:

| Parameter Name | Description |
| -------------- | ----------- |
| wexp           | specify action to take at the completion of the data acquisition.|
| werr           | specify action to take if an error occurs during data acquisition.|


