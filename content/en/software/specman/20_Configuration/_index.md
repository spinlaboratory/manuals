---
title:          "Configuration"
linkTitle:      "Configuration"
type:           docs
weight:         20
draft:          False
description:    "Sample Configuration for SpecMan"
---
Typically, your EPR spectrometer will be delivered with a pre-configure version of SpecMan4EPR. Below, we provide a sample configuration. However, the exact values for certain parameters (e.g. COM port) may differ from system to system.

## Device Configuration ##
To configure the different hardware component in SpecMan4EPR, open the Device Panel by clicking on the button labeled *Configuration of devices* (see button indicated by red box in figure below).

<center>
{{< figure_b12t src="/images/software/SpecMan/SM_Device_Config_800px.png">}}
</center>

Once you click the button the Device Configuration window will open.

<center>
{{< figure_b12t src="/images/software/SpecMan/SM-Device-Configuration-Basic-Access_600px.png">}}
</center>

When you first open the Device Configuration window, you will be in *Basic Access* mode. In this mode, you can only view the parameters but you won't be able to change any parameters or safe a new configuration. For this you need to access the *Expert Mode*. In the *Basic Access* mode, the safe and load buttons are greyed out.

To access the *Expert Mode* click Expert Access button to the top right of the window. You will be prompted with a password window. Simply acknowledge the password in the window by pressing the *OK* button. The Device Configuration window will change to *Expert Mode* (see figure below).

<center>
{{< figure_b12t src="/images/software/SpecMan/SM-Device-Configuration-Expert-Mode_600px.png">}}
</center>

### EPR Bridge
Bridge12 B12TXIF bridge controller and LabJackT7 (B12TXIF)  
Driver version: 3.5

Interface 0: LabJack  
Interface 1: Pixel controller

Name: BRIDGE  

| Key | Value | Comment |
| --- | --- | --- |
| Band | X-Band | Frequency band of the EPR bridge. |
| CGain1 | -27.142, 0.5714, 0, 0, 0, 0 | Polynomial coefficients (6th order) to adjust video amplifier gain. |
| CGain2 |  -27.142, 0.5714,0 , 0, 0, 0 | Polynomial coeficients (6th order) to adjust video amplifier gain. |
| COMOptions1 | B115200M500| Baud rate and timeout for DAQ device.  Here the baud rate is set to 115200 and the timeout is set to 500 ms. These are default parameters for the Bridge12 X-IF and should not be changed.|
| CRvrLOAttn | -10, 0.667, 0, 0, 0, 0 | Polynomial coeficients (6th order) to adjust RCVR LO amplifier gain. |
| CVCA | -10, 4, 0, 0, 0, 0 | Polynomial coeeficients (6th order) to adjust RCVR amplifier gain. |
| DeviceID | CNIGM0114 | ID of DAQ device. Typically this is the Bridge12 project number. |
| Multithreaded1 | false | true or (false) Allows using of GPIB in multiple threads. Bridge12 typically does not use any GPIB devices. |
| Options1 | | Leave blank |
| ReadTime1 | 0 ms | none |
| Resource1 | COM3 | COM port of pixel controller. Use the Microsoft Device Manager (devmgr) to determine the correct port number. |
| TextReadProc1 | &#95;A,A&#95;,LFCR | Comma-separated: aA,Aa,&#95;A,A&#95;,LFCR |
| RextWriteProc1 | LF | none |
| WriteTime1 | 0 ms | none |

A sample configuration is shown below.

<center>
{{< figure_b12t src="/images/software/SpecMan/SM-Device-Configuration-Bridge_600px.png">}}
</center>


### Microwave Source
Synth HD ver. 2.0  (SYNTHHD)
Driver ver. 2.0

Name: SRC

| Key | Value | Comment |
| --- | --- | --- |
| COMOptions | | Leave blank |
| Multithreaded1 | false | true or (false) Allows using of GPIB in multiple threads. Bridge12 typically does not use any GPIB devices. |
| Options | | Leave blank |
| ReadTime | 0 ms | Do not change. |
| Reference | R0F10 | Reference for microwave synthesizer. R(0/1/2) for External, Internal 27MHz, or Internal 10 MHz Reference. When using an external reference the frequency (in MHz) must be given. |
| Resource | COM4 | COM port of synthesizer. Use the Microsoft Device Manager (dvmgr) to determine the correct port number.|
| SourceOutputPow | 30 | Do not change. |
| TextReadProc1 | &#95;A,A&#95;,LFCR | Comma-separated: aA,Aa,&#95;A,A&#95;,LFCR |
| TextWriteProc | | Leave blank |
| WriteTime1 | 0 ms | none |

A sample configuration is shown below.

<center>
{{< figure_b12t src="/images/software/SpecMan/SM-Device-Configuration-SRC_600px.png">}}
</center>

### Digitizer
The configuration of the digitizer depends on the model and make you are using. Please contact support@bridge12.com for more information.


### Arbitrary Waveform Generator (AWG)
The configuration of the arbitrary waveform generator (AWG) depends on the model and make you are using. Please contact support@bridge12.com for more information.


## SpecMan4EPR Options
Please use the default SpecMan4EPR parameters for *Directories and files*. To access this go to Configuration and Select Options and expand the Directories and files menu.

| Parameter | Value |
| --- | --- |
| Configuration directory | C:\SpecMan4EPR\cfg |
| Template directory | C:\SpecMan4EPR\tpl |
| Data root directory | C:\SpecManDAta |
| Database root directory | C:\SpecManData |
| AWG pattern directory | C:\SpecMan\cfg\pattern |
| Directory with calibrations | \clb |
| Data buffer directory | C:\SpecManData\buffer |
| Data path format | &lt;data root&gt;\YY\YYMMDD |
| Station name | HOMEST |
| DLL paths | *empty* |
