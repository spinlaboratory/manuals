---
title:          "SpecMan4EPR"
linkTitle:      "SpecMan4EPR"
type:           docs
weight:         10
draft:          True
description:    "Troubleshooting SpecMan4EPR issues"
---

## Software Installation ##
[Re-Installing SpecMan4EPR](/software/specman/90_troubleshooting/specman4epr/#re-installing-specman4epr-on-new-hardware)

## Debugging ##
[Debugging the LabJack Interface](/software/specman/90_troubleshooting/specman4epr/#labjack-daq-interface)
___

## Software Installation ##
### Re-Installing SpecMan4EPR on new Hardware ###

In case have to re-install SpecMan4EPR on a new computer, follow these steps (assuming you saved a previous copy of SpecMan4EPR):

1. Start by creating two folders in the main directory (C:).
    1. C:\SpecMan4EPR
    2. C:\SpecManData
2. Copy the SpecMan4EPR application (SpecMan4EPR.exe) into the application directory (C:\SpecMan4EPR)
3. Inside the SpecMan4EPR folder create three subfolders:
    1. cfg - to store configuration files
    2. pattern - to store pattern files
    3. tpl - to store pulse program templates
4. Double click the SpecMan4EPR icon to start the application. Since no license is installed, SpecMan4EPR will create a *LIF File*. To obtain a license please send this file to support@bridge12.com and include any additional information about your spectrometer (e.g. serial number)
5. You will receive a license file (Specman4EPR.nlic). Move this file into the SpecMan4EPR directory. This will activate your software license and you will be able to use SpecMan4EPR.


## Debugging ##
### Serial Communication
Serial communication in SpecMan4EPR is most conveniently debugged in the built-in script editor. 

#### LabJack DAQ Interface
To debug communication with the LabJack interface and to enable the verbose mode for the LabJack interface follow these steps:

1. In SpecMan4EPR to the the *Script* tab
2. Select the *LABJACK* interface from the dropdown menu
3. Select *S00*
4. From the *command* dropdown menu select *.echo*
5. Enter *1* in the empty text box
6. Hit *ENTER*.

Once the verbose mode is enabled, open the *Log Window* by clicking the *View log window* in the toolbar to the right. For clarity, you can clear the log by right clicking with the mouse into the window and click *Clean Log*. This will clear all old messages. 
