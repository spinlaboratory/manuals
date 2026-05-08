---
title:        "ACODE"
linkTitle:    "ACODE"
type:         docs
weight:       40
draft:        false
description:  ""
---
### ACODE generation ###

When the OpenVnmrJ "go" command is executed, the parameter seqfil is used toselect the pulse sequence to execute. For example, if seqfil='s2pul', then a binary file named s2pul is looked for in ~/vnmrsys/seqlib and /vnnmr/seqlib. If it is found, it is started and the parameters from the "joined" experiment, along with the global parameters are sent to the s2pul binary. The s2pul program then generates a set of acodes, based on the parameters and the details of the pulsesequence function. The acodes are keyword - value pairs. For example, running s2pul with just a single transient (nt=1) may generate a set of acodes such as

{{<highlight Shell>}}
DEBUG 0
BOARD_NUMBER 0
BLANK_BIT 2
BYPASS_FIR 1
ADC_FREQUENCY 75
FILE /home/vnmr1/vnmrsys/exp2/acqfil
ARRAYDIM 1
MPS ext
PULSEPROG_START 1
SPECTROMETER_FREQUENCY 14.0005
NUMBER_POINTS 32768
NUMBER_OF_SCANS 1
SPECTRAL_WIDTH 8012.82
POWERS 1 1000 -1 -1 -1
PULSE_ELEMENTS START
PHASE_RESET 1
DELAY 1
PULSE 4.9e-06 0 1e-05
DELAY 3.4875e-05
ACQUIRE 0
PULSEPROG_DONE 1
{{</highlight>}}

The values following each keyword are determined from the parameters that were sent to the pulse sequence program (s2pul). The acodes are reproduced below with the operative parameters noted.

{{<highlight Shell>}}
DEBUG 0                               "debug flag set by whether go or go('debug') is called"
BOARD_NUMBER 0                        "global B12_BoardNum parameter"
BLANK_BIT 2                           "global B12_BlankBit parameter"
BYPASS_FIR 1                          "global B12_BypassFIR parameter"
ADC_FREQUENCY 75                      "global B12_ADC parameter"
FILE /home/vnmr1/vnmrsys/exp2/acqfil  "exppath parameter"
ARRAYDIM 1                            "arraydim parameter"
MPS ext                               "mps parameter"
PULSEPROG_START 1                     "keyword indicating start of experiment."
                                      "Index indicates which array element is being collected"
                                      "It would range from 1 to ARRAYDIM."

SPECTROMETER_FREQUENCY 14.0005        "sfrq parameter"
NUMBER_POINTS 32768                   "np parameter"
NUMBER_OF_SCANS 1                     "nt parameter"
SPECTRAL_WIDTH 8012.82                "sw parameter"
POWERS 1 1000 -1 -1 -1                "values of the shaped pulse amplitudes"
PULSE_ELEMENTS START                  "Keyword indicating start of pulsesequence"
PHASE_RESET 1                         "Keyword to reset phases. Called once for each element in array."

DELAY 1                               "d1 parameter"
PULSE 4.9e-06 0 1e-05                 "pw parameter, first element of oph phase table, rof1 parameter"
DELAY 3.4875e-05                      "sum of parameters rof2 and alfa"
ACQUIRE 0                             "Keyword to trigger data acquisition. 0 argument is the"
                                      "current transient (ct). It ranges from 0 to NUMBER_OF_SCANS-1"
                                      "It is there to simplify acode parsing"

PULSEPROG_DONE 1                      "Keyword to indicate acodes for FID 1 is done."
                                      "It also is an instruction to get the data from the"
                                      "SpinCore system and save it to FILE"
{{</highlight>}}

Phase cycling is handled by incrementing the index used when accessing the phase tables. Note that the actual phase tables are not included in the acodes. Only the values of the indexed phase tables are in theacodes. To avoid multiple copies of the acodes where the only differences are the phase values, the PSG first scans the pulse sequence to determine the longest phase cycle used, and then uses the SpinCore looping mechanism to loop over the pulse elements the proper number of times.

To illustrate, the following are the acodes for s2pul with nt=10. The longest phase cycle used by s2pul is 4 for the receiver (oph) phase cycle. The acodes loop twice over four transients and then the remaining two transients follow. Acodes with no comments are the same as for the seqfil='s2pul' and  nt=1 case.

{{<highlight Shell>}}
DEBUG 0
BOARD_NUMBER 0
BLANK_BIT 2
BYPASS_FIR 1
ADC_FREQUENCY 75
FILE /home/vnmr1/vnmrsys/exp2/acqfil
ARRAYDIM 1
MPS ext
PULSEPROG_START 1
SPECTROMETER_FREQUENCY 14.0005
NUMBER_POINTS 32768
NUMBER_OF_SCANS 10                    "nt parameter"
SPECTRAL_WIDTH 8012.82
POWERS 1 1000 -1 -1 -1
PULSE_ELEMENTS START
PHASE_RESET 1
NSC_LOOP 2                            "keyword to loop over the following acodes 2 times"
                                      "the end of the looping section is denoted"
                                      "by the NSC_ENDLOOP keyword"
DELAY 1
PULSE 4.9e-06 0 1e-05                 "pulse with phase 0"
DELAY 3.4875e-05
ACQUIRE 0                             "end of transient 0"
DELAY 1
PULSE 4.9e-06 1 1e-05                 "pulse with phase 1"
DELAY 3.4875e-05
ACQUIRE 1                             "end of transient 1"
DELAY 1
PULSE 4.9e-06 2 1e-05                 "pulse with phase 2"
DELAY 3.4875e-05
ACQUIRE 2                             "end of transient 2"
DELAY 1
PULSE 4.9e-06 3 1e-05                 "pulse with phase 3"
DELAY 3.4875e-05
NSC_ENDLOOP 10                        "Because of the way SpinCore programming works,"
                                      "the NSC_ENDLOOP is specified prior to the final"
                                      "acode in the loop." 
ACQUIRE 3                             "end of transient 3"
DELAY 1                               "Program the remaining two transients"
PULSE 4.9e-06 0 1e-05                 "pulse with phase 0"
DELAY 3.4875e-05
ACQUIRE 0
DELAY 1
PULSE 4.9e-06 1 1e-05                 "pulse with phase 1"
DELAY 3.4875e-05
ACQUIRE 1
PULSEPROG_DONE 1
{{</highlight>}}

Acquiring arrayed data sets involves multiple acode sets. This is illustrated in the following acode set for seqfil='s2pul' and nt=1,4

{{<highlight Shell>}}
DEBUG 0
BOARD_NUMBER 0
BLANK_BIT 2
BYPASS_FIR 1
ADC_FREQUENCY 75
FILE /home/vnmr1/vnmrsys/exp2/acqfil
ARRAYDIM 2                            "acquire 2 FIDs"
MPS ext
PULSEPROG_START 1                     "Start acodes for FID 1" 
SPECTROMETER_FREQUENCY 14.0005
NUMBER_POINTS 32768
NUMBER_OF_SCANS 1
SPECTRAL_WIDTH 8012.82
POWERS 1 1000 -1 -1 -1
PULSE_ELEMENTS START
PHASE_RESET 1
DELAY 1
PULSE 4.9e-06 0 1e-05
DELAY 3.4875e-05
ACQUIRE 0
PULSEPROG_DONE 1                      "Finish acodes for FID 1"
PULSEPROG_START 2                     "Start acodes for FID 2" 
SPECTROMETER_FREQUENCY 14.0005
NUMBER_POINTS 32768
NUMBER_OF_SCANS 4
SPECTRAL_WIDTH 8012.82
POWERS 1 1000 -1 -1 -1
PULSE_ELEMENTS START
PHASE_RESET 1                        "No need for NSC looping elements"
                                     "since nt=4 is the same as the maximum"
                                     "phase cycle"
DELAY 1
PULSE 4.9e-06 0 1e-05
DELAY 3.4875e-05
ACQUIRE 0
DELAY 1
PULSE 4.9e-06 1 1e-05
DELAY 3.4875e-05
ACQUIRE 1
DELAY 1
PULSE 4.9e-06 2 1e-05
DELAY 3.4875e-05
ACQUIRE 2
DELAY 1
PULSE 4.9e-06 3 1e-05
DELAY 3.4875e-05
ACQUIRE 3
PULSEPROG_DONE 2                      "Finish acodes for FID 2"
{{</highlight>}}

### ACODE interpretation ###

When the go command is executed, it generates the acode file as described above and a second file used by "the procs" to handle experiment queueing and monitoring. When the controlling Expproc determines that it is time to start an experiment, it checks its queue and starts B12proc, passing the name of the acode file to use.

The B12proc program reads the acode file line by line. Each keyword causes some action. Some keywords, such as BOARD_NUMBER, BLANK_BIT, BYPASS_FIR, ADC_FREQUENCY, FILE, NUMBER_POINTS, NUMBER_OF_SCANS, SPECTRAL_WIDTH, and POWER just set parameters. Other keywords cause SpinCore elements to be executed.

The PULSEPROG_START acode causes the SpinCore initialization functions to be called. It also initializes the internal current transient (ct) counter. The PULSE_ELEMENTS acode calls the pb_start_programming(PULSE_PROGRAM) SpinCore function.

The PULSEPROG_DONE acode calls the pb_stop_programming() function and also uses the pb_get_data() function to collect the data from the SpinCore board and save it to a file defined by the FILE keyword.

Other keywords, such as DELAY, PULSE, and ACQUIRE cause appropriate pb_inst_radio_shape() functions to be called .
