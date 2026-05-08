---
title:        "Creating a Study in OVJ"
linkTitle:    "Creating a Study"
type:         docs
weight:       40
draft:        false
description:  "Creating a Study in OVJ"
---
If the user wants to run a series of experiments a *Study* should be created in OVJ by the user. The study can be started using the ```go``` command and each experiment is automatically saved.

To create a study in OVJ follow these steps:

1.  Click 'New study' in the 'Study Queue' tab.
2.  Enter a Sample name in the 'Start' tab.

    <center>
    {{< figure_b12t src="/images/software/OVJ/newStudy_600px.png">}}
    </center>

3. Drag an experiment (e.g. PROTON) from the Experimentor Selector Tree into the Study Queue.

    <center>
    {{< figure_b12t src="/images/software/OVJ/studyProton_600px.png">}}
    </center>

    when the the PROTON_001 sequence is selected (double click) one can adjust all settings for the sequence ([Array](#arrayPRM) parameters, change MPS settings, etc..) and when pressing the save button the settings are saved.

    These settings will be the default settings for all experiments in this study. To save the data automatically go to the 'Acquire' tab and select 'Future Actions'.

4.  In the 'When experiment finished' line enter procsaveplot (select process/plot/save from the dropdown menu) or save to save the data after each 'go'. Alternatively this can be set with the commandline

    {{<highlight shell>}}
    wexp='procsaveplot'
    {{</highlight>}}

5.  To start the acquisition of experiments in the study, press the *Submit* button to start the acquisition.

    <center>
    {{< figure_b12t src="/images/software/OVJ/studyForeground_400px.png">}}
    </center>
