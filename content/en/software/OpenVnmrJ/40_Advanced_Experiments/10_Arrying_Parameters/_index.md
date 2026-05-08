---
title:        "Arraying Parameters"
linkTitle:    "Arraying Parameters"
type:         docs
weight:       10
draft:        false
description:  "Arraying Parameters in OVJ"
---
For many experiments a parameter needs to be varied (e.g. the delay (recovery) time in an inversion-recovery experiment to measure the <sup>1</sup>H longitudinal relaxation time T<sub>1</sub>. 

In OVJ, this can be done specifying an array of parameters. An array can be either specified through an OVJ GUI or the command line.

It is helpful to first take a look at the pulse sequence to decide, which parameter needs to be arrayed. Either click the 'Sequence diagram' button in OVJ or type ```dps``` in the OVJ command line. A typical, two pulse experiment is shown in the figure below.

<center>
{{< figure_b12t src="/images/software/OVJ/pulseDiagram_800px.png">}}
</center>

+ **d1**: Repetition time.
+ **p1**: Pulse length of the first pulse. For an inversion recovery experiment, this is the pulse length of the first 180 degree pulse.
+ **d2**: Recovery delay.
+ **pw**: Pulse length of the detection pulse.

### Arraying Parameters using the GUI ###
To use the GUI to define an array of parameters to vary follow these steps:

1.  In the *Acquire Tab* click the *array* button or select *Parameter Arrays* from the *Acquisition* menu

    <center>
    {{< figure_b12t src="/images/software/OVJ/Water_T1_SelectArray_600px.png">}}
    </center>

2.  In the window, enter the parameter name to array in the field *Param Name*. In this example we will vary the parameter ```d2```. The description will be automatically filled in.

    <center>
    {{< figure_b12t src="/images/software/OVJ/Water_T1_make_array_600px.png">}}
    </center>

3.  Enter three of the four parameters (*Array Size*, *First Value*, *Increment*, *Last Value*). The fourth parameter will be calculated once three values are entered.

    The values of the array is shown in the box to the right. Use the scroll bar see all values of the array.

4.  Click the *Close* button.

    The window will close. The value of the parameter (here ```d2```) will now be displayed as "Array" to indicate an array of values instead of a single value.

### Arraying Parameter using the OVJ Command Line ###

From the OVJ command line, an array can be defined using the ```array``` command.

{{<highlight shell>}}
array(parameter,number_of_steps,start,step)
{{</highlight>}}

For example, to array the parameter ```d2```, starting at 0.05 s, with steps of 0.05 s for a total of 30 points enter the following command:

{{<highlight shell>}}
array('d2',30,0.05,0.05)
{{</highlight>}}

another possibility to create arrays with arbitrary values is using the syntax *$value=val1,val2,...*

{{<highlight shell>}}
d2=1,4,42
{{</highlight>}}
