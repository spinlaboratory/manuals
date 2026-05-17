---
title:          "Optimizing the Microwave Pulse Parameters"
linkTitle:      "Optimizing Pulse Parameters"
type:           docs
weight:         20
draft:          True
description:    "How to optimize the microwave pulse parameters for PELDOR/DEER experiments"
---

In this section we provide the general procedure how to optimize the microwave pulse parameters for the PELDOR/DEER experiment.

### Set the Magnetic Field ###

1. Use the microwave frequency that was set in the microwave bridge ``Control Panel`` to calculate the maximum field for a nitroxide radical. This can be done using the provided Python script.
    * In this example the microwave frequency is 34.032 GHz and the script returns a field value of 1.21896 T.
2. Next, open the window to control the field. From the ``DDI menu`` select ``Set Field form, FLD``.
3. Enter the field value and click the ``Set Field`` button.

<center>
{{< figure_manuals src="/images/software/SpecMan/specman-5.png" alt="SpecMan4EPR magnetic field control">}}
</center>

4. Wait until the desired field value is reached. When the magnetic field is sweeping, the temperature of the Magnet Switch will typically rise from about 5.9 K to about 8 K. Once the desired field is reached, the temperature returns to its base temperature of about 5.9 K.
5. Close the magnet control window.

### Optimizing the Pulse Parameters ###
To optimize the pulse parameters follow these steps:

1. Load a new experiment. From the ``File`` menu, select ``New Experiment``. Scroll to the ``Two-Pulse Echo`` experiment and click on it to load the experiment. This will load some default pulse parameters, which will be a good start for the optimization.
2. Next, start the pulse sequence by hitting the ``Tune`` button. Once the experiment starts, you should see an echo in the ``Scope`` window to the left.

In the next step we will adjust the video amplifier gain and the microwave phase. This is an iterative process and you have to adjust both parameters. Make sure the ``Modulation Frequency`` parameter is set to 500 MHz.

3. In the microwave bridge ``Control Panel`` adjust the video amplifier gain. Observe the echo amplitude and set the video amplifier gain to a value so the echo amplitude is not clipped.
4. In the same window adjust the microwave phase to maximize the echo amplitude (real part of the complex signal, green trace).

The video amplifier gain should be adjusted to a value that the echo amplitude is about 75 % of the maximum (horizontal red line). For small echo amplitudes, you can also adjust the scale in the same window. This will adjust the input scale of the digitizer.

In the next step, we will find the optimum value for the microwave power. SpecMan4EPR allows the user to make almost every variable of the experiment an axis of the experiment. We will use this feature of the software to find the correct pulse amplitude. 

1. Right click on the ``amp`` variable in the Parameter section and select ``Y axis`` to assign the parameter to the y axis.
2. In the section for the y axis, set the ``size`` of the axis to 101 points.
3. In the line below, set the sweep range to ``"0 step 0.01"``. This will you to step the ``amp`` parameter from 0 to 1 in steps of 0.01 using the slider.
4. To start the experiment, click the ``tune`` button.

5. Move the slider with the mouse to maximize the echo amplitude.
    1. Find the optimum pulse amplitude for a two-pulse echo using 8 and 16 ns for the pi/2 and pi pulse, respectively.  In this example the optimum value is at 0.2 (21st step).
    2. Change the pulse length the for 90º and 180º pulse to 16 and 32 ns, respectively, and repeat the optimization. In this example the optimum value for the 16/32 echo is at 0.08. This value should be approximately half of the value determined for the 8/16 ns echo.

    While the tune mode is running, SpecMan4EPR will integrate the area of the echo and record the value in the display. Observe the value (red trace in figure below) and optimize for the maximum echo amplitude.

6. Once you found the optimum values stop the tune mode by clicking the ``tune`` button.

<center>
{{< figure_manuals src="/images/software/SpecMan/specman-6.png" alt="SpecMan4EPR optimizing pulse parameters">}}
</center>

### Record reference T2 decay ###

In the next step, we will record a two-pulse echo decay as a reference spectrum. This will give you and idea of the setting for the maximum dipolar evolution time. To record the T2 decay follow these steps:

1. Reload the experiment. From the ``File`` menu, select ``New Experiment``. Scroll to the ``Two-Pulse Echo`` experiment and click on it to load the experiment.
2. Set the ``amp`` parameter (pulse amplitude) to the value determined above. In this example we use the parameters for the 8/16 ns echo.
3. Hit the ``run`` button to start the experiment.

It will take about 15 s to compile the pulse sequency and upload it to the AWG. Once the sequence is uploaded the experiment will start and the results are shown once the experiment finishes (see figure below). Overall duration for this experiment is about 26 s.

<center>
{{< figure_manuals src="/images/software/SpecMan/specman-7.png" alt="SpecMan4EPR two-pulse echo decay">}}
</center>

For this particular sample we pick a maximum dipolar evolution time of about 2 &micro;s.

### What's next? ###
* [Record a Field Sweep Experiment](/systems/spectrometers/81-q-band-spectrometer/20_getting_started/30-record-field-sweep-experiment/).
