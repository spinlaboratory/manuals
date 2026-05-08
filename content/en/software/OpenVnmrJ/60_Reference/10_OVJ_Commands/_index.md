---
title:        "OVJ Commands"
linkTitle:    "OVJ Commands"
type:         docs
weight:       10
draft:        false
description:  "Commonly Used OVJ Commands"
---
### General Command Structure ###

* OVJ commands are entered at the command line. Some commands require arguments or parameters, which can enclosed in parentheses.
* To change a parameter value, the parameter is entered followed by an equal sign (=), followed by the value of the parameter (real, integer, or string).
* String values are always enclosed in parentheses and surrounded by single quotes.
* Multiple command and parameter settings can be entered consecutively, separated by spaces. 

Command Examples:
{{<highlight Shell>}}
aph
wft
wft aph dc vsadj
{{</highlight>}}

Example of Setting a Parameter Value:
{{<highlight Shell>}}
lb = 0.2
sampe = 'MySample'
{{</highlight>}}

### Commonly Used OVJ Parameters ###
The following sections provide a list of commonly OVJ commands and parameters. For a complete list of commands see the [VnmrJ Command and Parameter Reference]().

#### Commands ####
##### Spectrometer Control and Data Acquisition Parameters #####

| Command                   | Description/Example |
| ------------------------- | ------------------- |
| **aa**                    | abort current running experiment immediately. Recommended to use in most occasions over sa except when some experiments are queued |
| **cexp(n)**               | create new experiment from current one <br> Example: **cexp(2)** copy current parameters and create experiment number 2 (#2 must not exist) |
| **dg**                    | display group of acquisition/processing parameters in Process→Text Output window |
| **dps**                   | display pulse sequence |
| **ga**                    | start experiment and autoprocess the data when data are available |
| **go**                    | start experiment using acquisition parameters |
| **jexp(n)**               | join (or go to) specified experiment <br> Example: **jexp(2)** join exp#2. exp#2 must exist |
| **movesw**                | move new spectral window (sw) to the area enclosed by the two red cursors |
| **movetof**               | move transmitter offset freqeuency (tof) to the cursor position |
| **su**                    | setup experiment. Force hardware to changes according to current parameter settings <br> Example: **load='MySpectrum' su** - change shims to current values in parameter file <br> Example: **tn='C13' su** - change direct detection to C13 |
| **time**                  | displays total experiment time with current parameters |
| **time(hours,minutes)**   | displays number of scans (nt) required for a given time of experiment <br> Example: **time(1,10)** - displays number of scans needed for a one hour 10 mins experiment |
| **unlock(exp_number)**    | remove interactive lock and join an experiment. Useful to remove lockup of an experiment, sometimes due to user failure to exit vnmrJ before logging out Linux |

##### Data Processing and Display Commands #####
| Command                       | Description/Example |
| ----------------------------- | ------------------- |
| **aph**                       | automatic phasing of both zero (constant) and first-order (linear with frequency) terms |
| **aph0**                      | automatic phasing with zero-order term only to achieve absorptive mode spectrum. Zero-order phase value (rp) is the same across the spectrum |
| **array**                     | Enter this command to set an arrayed experiment where a parameter is varied and an experiment is collected with each parameter. Enter parameter name, initial value, number of steps, and stepsize. All other parameters are kept constant |
| **bc**                        | 1D or 2D baseline correction with a spline or 2nd to 20th order polynomial function. Needs to define baseline regions (regions in between the integral areas covering peaks) |
| **centersw**                  | With full spectrum displayed and in single cursor mode, centers moves the cursor to the center (transmitter) of the spectrum |
| **cz**                        | clear integral reset points |
| **da**                        | display acquisition parameter array in Plot→Text Output window |
| **dc**                        | Apply a simple drift correction (with a straight line function) so that the spectrum baseline is close to zero. Level (lvl) and tilt (tlt) parameters are adjusted |
| **df**                        | display a single FID (default index is 1) <br>  Example: **df** displays the 1st FID or df(10) displays #10 FID in the array |
| **dli**                       | display list of integrals |
| **dll**                       | displays line frequency and intensities (peaks have to picked) |
| **dpir**                      | display integral values below spectrum |
| **dpf**                       | adjust threshold and display peaks so that a maximum 20 highest peaks are found and the minimum height cutoff is 5 times above noise level |
| **dres**                      | calculates peak resolution/linewidth |
| **ds**                        | display processed spectrum without preprocessing |
| **dssa**                      | display arrayed spectra in a stack plot <br> Example: **wft dssa** |
| **dssh**                      | display arrayed spectra horizontally <br> Example: **wft dssh** |
| **dssl**                      | Label displayed arrayed spectra with index number <br> Example: **wft dssh dssl** |
| **dsn**                       | measure and display signal-to-noise ratio in region enclosed by two cursor lines |
| **f**                         | display the full spectrum |
| **fbc**                       | apply baseline correction for each spectrum in an spectrum array |
| **full**                      | display spectrum with full window size. The range of the spectrum is not changed <br> Example: **f full** - display the full spectrum with full window size |
| **fp**                        | find peaks in arrayed dataset according to the refrence peaks found by dll |
| **isadj**                     | automatic adjustment of integral vertical display height to fit page |
| **mf**                        | move FID file from one experiment to another <br> Example: **mf(1,2)** move fid from exp #1 to #2 |
| **mp**                        | Move all parameters from one experiment to another <br> Example: **mp(1,2)** |
| **nl**                        | move cursor line to nearest peak/line position |
| **th**                        | set a threshold for peaks in dll command |
| **thadj(maxpks,noise_mult)**  | Adjust the threshold th so that no more than maxpks number of peaks are found with a minimum of noise_mult factor above noise level. <br>  Example: **thadj(20,5)** |
| **peak**                      | Find tallest peak in current display region <br> Example: **peak** - display tallest peak position and height in current displayed spectrum region <br> Example: **peak:$height,$freq** - find tallest peak in current displayed region and save height and frequency in the variables $height and $freq. $heigt? or $freq? shows the values |
| **vsadj**                     | automatic vertical scale adjustment so that the highest peak fits the window height |
| **setref**                    | set reference ppm of any nucleus by the chemical shift of the deuterium signal from the solvent, according to IUPAC standard indirect referencing to TMS 1H signal |
| **wft**                       | Weighted Fourier transform (FT). Weighting is applying a window function to the profile of the FID to enhance resolution or signal-to-noise and to reduce truncation artifacts from finite data collection |

#### Plotting Commands ####
| Command       | Description/Example |
| ------------- | ------------------- |
| **page**      | submit plot to printer and change plotter page. Usually last command in printing command chain |
| **pap**       | plot "all" parameters in table format |
| **pir**       | plot integrals below spectrum |
| **pl**        | plot spectrum |
| **pll**       | plot frequency line list in a table format |
| **pltext**    | plot user comment/notes. Not necessary if ppa command is used |
| **ppa**       | plot basic parameters in plain english format |
| **pps**       | plot pulse sequence |
| **ppf**       | plot peak frequencies over the spectrum |

### Parameters ###
#### Acquisition parameters ####
| Parameter     | Description/Example |
| ------------- | ------------------- |
| **at**        | acquisition time in seconds |
| **bs**        | block size of data (number of transients) periodically read and stored on disk <br> Example: **bs=4** stores data every 4 scans |
| **ct**        | current transient (or scan) number. ct is displayed at the bottom of vnmrJ screen during a running experiment. If the experiment is stopped before all transients are done, ct (stored in the parameter file procpar) is the number of scans completed |
| **d1**        | 1st delay period in pulse sequence. Typically this is the recycle time (in seconds) between scans |
| **dn**        | 1st decoupler nucleus |
| **gain**      | receiver gain. If gain='n', auto-gain adjustment is set before data acquisition. Autogain cannot be used for arrayed experiment. Gain values go from 0 to 60. Too high a gain setting causes receiver overflow, leading to severe artifacts in the spectrum <br> Example: **gain=36** sets gain to 36 |
| **nt**        | number of transients or scans |
| **pad**       | preacquisition delay (in seconds). pad is the additional delay time set before the 1st recycle delay (d1) before the start of an experiment. If pad=60, the experiment will start after 60 secs |
| **rattn**     | receiver attenuation, the attenuation can be set from 0 to 95, a too high value will attenuate all signals. A too small value will increase noise without increasing the signal strength. |
| **ss**        | number of steady-state transients or dummy scans before start of experiment. It's used to establish a steady-state for the spins before data collection |
| **sw**        | spectral width of direct detection dimension, in Hz be default <br> Example: **sw=6000** or **sw=15p** to specify 15ppm width |
| **sw1**       | spectral width of 1st indirect detection dimension, in Hz be default |
| **solvent**   | name of solvent <br> Example: **solvent='cdcl3'** or **solvent='c6d6'** |
| **tn**        | observe transmitter nucleus |
| **tof**       | observe transmitter offset (center of spectrum) |

#### Processing and display parameters ####
| Parameter     | Description/Example |
| ------------- | ------------------- |
| **axis**      | axis label in display and plots. Values include 'h' for Hz, 'p' for ppm <br> Example: **axis='p'** or **axis='ppm'** set axis to ppm display |
| **cr**        | cursor position in direct detected dimension <br> Example: **cr=8.0p** set cursor position to 8ppm |
| **date**      | date of experiment |
| **delta**     | In two-cursor (box cursor) mode, delta stores the width in Hz between the two cursors <br> Example: **delta=1000** sets the separation between two cursors to 1000 Hz, or delta? to see the cursor separation value |
| **ho**        | horizontal offset (in mm) between a set of spectra in stacked display mode for arrayed spectra |
| **intmod**    | integral display mode. Value is 'off', 'full', or 'partial' <br> Example: **intmod='off'** |
| **lb**        | line broadening amount for exponential weighting function (Hz) <br> Example: **lb=0.2** |
| **lp**        | 1st order (or linear) phase in directly detected dimension, adjusted during phasing process <br> Example: **lp=0** sets linear phase correction to zero, useful to reset linear phase to zero to correct accidental introduction of large lp value during manual phasing |
| **rp**        | zero order phase correction in degree, adjusted during phasing process <br> Examples: **rp=45** set zero-order phase to 45 degree or rp=rp+45 to change phase by 45 degree |
| **vo**        | vertical offset (in mm) between a set of spectra in stacked display mode for arrayed spectra |
| **vp**        | vertical position of spectrum, in mm <br> Example: **vp=60** sets spectrum baseline roughly in the middle of the display along Y-axis <br> Example: **vp=vp+20** moves the spectrum up by 20 mm |
| **vs**        | vertical scale of spectrum <br> Example: **vs=vs*2** - set vertical scale to double peak height <br> Example: **vs=vs*0.5** - set vertical scale to halve peak height |