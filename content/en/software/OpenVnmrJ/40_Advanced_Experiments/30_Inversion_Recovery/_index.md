---
title:        "Inversion Recovery Experiments in OVJ"
linkTitle:    "Inversion Recovery"
type:         docs
weight:       30
draft:        false
description:  "Performing an Inversion Recovery Experiment in OVJ"
---
The longitudinal relaxation time T<sub>1</sub> can be determined from an inversion-recovery experiment. This is another good example to demonstrate the arrying capabilities in OVJ. If you haven't read the section about [how to array parameters in OVJ](../10_arrying_parameters/), we would suggest doing this first before you start to follow this example.

The following pre-requisites are assumed:

1.  A sample is inserted in the probe. 
2.  The 90 degree pulse length is know. To determine the correct pulse length please follow the steps outlined in the section [Calibrating a 90º Pulse](../20_calibration_90_pulse_length/).

#### Acquire the Inversion Recovery Data ####

To perform the inversion-recovery experiment follow these steps:

1.  Select the PROTON experiment (```seqfile='s2pul'```).
2.  Enter the pulse for the 90 degree pulse (pw) and the 180 degree inversion pulse (d1).
3.  Enter a value for d1. This is the repetition time of the experiment and it should typically be set to a value of 5 times the T<sub>1</sub> relaxation time of the nucleus. For example, if the relaxation time of the water protons is about 1 s, the value for d1 should be set to 5 s. This ratio can be reduced to speed up the experiment, however, if the repetition time is too short, the measured value for T<sub>1</sub> will be incorrect.
4.  For the inversion-recovery experiment we will array the d2 parameter

    {{<highlight shell>}}
    array('d2',30,0.05,0.05)
    {{</highlight>}}

5.  Press 'Go' to start the acquisition or type ```go``` and press enter in the OVJ command line.
6.  Once the aquisition is finished save the data.

#### Determining T<sub>1</sub> in OVJ ####

To determine T<sub>1</sub> in OVJ follow these steps:

1.  Select the last spectrum of the array using the ```ds``` command. Here, we use spectrum number *15*. Alternatively, you can select any spectrum with sufficient signal-to-noise.

    {{<highlight shell>}}
    ds(15)
    {{</highlight>}}

2.  Phase the spectrum using the autophase function ```aph```:

    {{<highlight shell>}}
    aph
    {{</highlight>}}

    Once all spectra are phased, you can display all spectra horizontally using the ```dssh``` command:

    {{<highlight shell>}}
    dssh
    {{</highlight>}}

    The result should like like the example below

    <center>
    {{< figure_b12t src="/images/software/OVJ/t1_dssh_phased_600px.png">}}
    </center>

    If the spectra look like the data shown in the image proceed to the next step.

3.  Select the last spectrum using the ```ds(15)``` command.
4.  Next, we need to set a threshold for the peak picking algorithm. The threshold is set using the ```th``` parameter. In this example, we will set a threshold of 10.

    {{<highlight shell>}}
    th=10
    {{</highlight>}}

    You can also use the horizontal line marker to adjust a threshold. Set the threshold to a value that only one peak is above the threshold.

5.  In the next step the peak amplitudes for each spectrum are determined using the ```dll``` and ```fp``` (find peak) command. Only peaks are considered that are above the threshold value.

    {{<highlight shell>}}
    dll
    fp
    {{</highlight>}}

6.  To get the T<sub>1</sub> relaxation time, the *t1* OVJ macro can be used. To run the macro, enter *t1* in the OVJ command line and press enter.

    {{<highlight shell>}}
    t1
    {{</highlight>}}

7.  Display the fitting results using these OVJ command line commands:

    {{<highlight shell>}}
    center
    expl
    {{</highlight>}}

    You should see a result similar to the one shown below.

    <center>
    {{< figure_b12t src="/images/software/OVJ/t1_expl_600px.png">}}
    </center>

    The fit values returned by the *t1* macro can be seen in the *Process* tab under *Text output*.

    <center>
    {{< figure_b12t src="/images/software/OVJ/output_screenshot_t1_analysis_600px.png">}}
    </center>

The *t1* macro will create an output file located in the current experiment folder. The path the folder is (N corresponds to the experiment number). The number of the current experiment can be seen in the top left part of the display tab or using the ```curexp?``` command in the OVJ command line.

{{<highlight shell>}}
~/vnmrsys/expN/analyze.list
{{</highlight>}}

#### Evaluation with dnplab ####
The inversion-recovery experiment can also be analyzed using [DNPLab](http://dnplab.net/). First, make sure DNPLab is installed:

{{<highlight shell>}}
pip3 install dnplab
{{</highlight>}}

A typical processing script is given below:

{{<highlight python>}}
import dnplab as dnp

data=dnp.load('path/to/FID/folder')

data=dnp.fourier_transform(data)
data=dnp.autophase(data,dim='t1')

fig,ax=dnp.plt.subplots(1,2)
dnp.plt.sca(ax[0])
dnp.fancy_plot(data)

noise_start_ppm=-1000 #change this according to your spectrum
noise_end_ppm=-500 #change this according to your spectrum
signal_start_ppm=-50 #change this according to your spectrum
signal_end_ppm=50 #change this according to your spectrum

data=dnp.processing.offset.remove_background(data,dim='f2',regions=[(noise_start_ppm,noise_end_ppm)])
data=dnp.processing.integration.integrate(data,regions=[(signal_start_ppm,signal_end_ppm)])

data.attrs['experiment_type']='inversion_recovery'
dnp.plt.sca(ax[1])
dnp.fancy_plot(data)
dnp.show()
{{</highlight>}}

The first subfigure can be used to determine the noise and signal region.
The second figure shows the T1 recovery curve. An example for the second figure is shown below.

<center>
{{< figure_b12t src="/images/software/OVJ/T1_recovery_600px.png">}}
</center>
