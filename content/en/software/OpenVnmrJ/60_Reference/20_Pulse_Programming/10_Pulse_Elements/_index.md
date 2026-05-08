---
title:        "Pulse Elements"
linkTitle:    "Pulse Elements"
type:         docs
weight:       10
draft:        false
description:  "Pulse Elements for Pulse Programming"
---
Pulse sequences are constructed from pulse elements, which specify controls for the NMR hardware. The "C-style" signature for these elements is defined below.

### Delay ###
{{<highlight C>}}
void delay(double time)
   # Delay for "time" seconds. If 0.0 is passed, the delay is ignored.
   # The minimum delay time is about 67 ns.
{{</highlight>}}

Examples:
{{<highlight C>}}
delay(0.1);
delay(d1);
delay(d2/2.0);
{{</highlight>}}

### Pulse ###
{{<highlight C>}}
void pulse(double time, int phase)
   # Turn on the RF for duration of "time" seconds with the RF phase set to the
   # value of the "phase" argument. A delay of "rof1" is done prior to turning
   # on the RF pulse to allow the amplifier to switch on. A delay of "rof2" is
   # done following the pulse to allow for probe ring-down.
{{</highlight>}}
Examples:
{{<highlight C>}}
pulse(p1,zero);
pulse(pw,oph);
pulse(pw,PH90);
pulse(pw,t1);
{{</highlight>}}


### Rgpulse ###
{{<highlight C>}}
void rgpulse(double time, int phase, double rg1, double rg2)
   # Turn on the RF for duration of "time" seconds with the RF phase set to the
   # value of the "phase" argument. A delay of rg1 is done prior to turning
   # on the RF pulse to allow the amplifier to switch on. A delay of rg2 is
   # done following the pulse to allow for probe ring-down.
   # rgpulse(p1,zero,rof1,rof2) is equivalent to pulse(p1,zero).
{{</highlight>}}
Examples:
{{<highlight C>}}
rgpulse(pw,oph,rof1,rof2);
rgpulse(p1,zero,rof1,0.0);
rgpulse(pw,PH90,1e-6,0.0);
rgpulse(pw,t1,1e-6,rof2);
{{</highlight>}}


### Offset ###
{{<highlight C>}}
void offset(double frequency)  // Not yet implemented
  # Offset the RF frequency to the supplied value.
{{</highlight>}}


### Acquire ###
{{<highlight C>}}
void acquire(double datapnts, double dwell)
   # Start acquiring data points. The number of data points is defined
   # by the np parameter. The dwell period to acquire one complex pair is 1/sw.
   # A delay of alfa is done prior to the acquire to account for filter
   # delays. If a pulse sequence does not include an acquire pulse element,
   # one will be automatically added at the end of the sequence.
{{</highlight>}}
Examples:
{{<highlight C>}}
acquire(np, 1.0/sw);
{{</highlight>}}


### Power ###
{{<highlight C>}}
void power(double amp)
  # Control the power of the amplifier during an RF pulse. The supplied
  # amp can be in the range of 0.0 (no power) to 100.0 (full power).
  # The power adjustment uses the pulse shaping capability of the SpinCore
  # board. The power controls the amplitude of a rectangular shaped pulse.
  # Only four power levels can be used, one of which is the full power
  # pulse.
{{</highlight>}}


### Settable ###
{{<highlight C>}}
void settable(int table, int cnt, int phases[])
  # The "table" argument is one of the phase table names t1-t10.
  # The "cnt" argument is the number of phase elements to be assigned
  # to the phase table. It is the number of elements in the array specified
  # by the third argument.  The phases[] arguemnt is a pre-defined array
  # of phase elements. For an example, see the "Phase cycling" section.
{{</highlight>}}


### Status ###
{{<highlight C>}}
void status(int state)
  # Controls the on/off state of the microwave source. The microwave source
  # is selected by the systemglobal bnc, which can be set with the config
  # program to BNC0 or BNC1. The parameter xm controls the on/off state.
  # It can have multiple states: status(A) sets the status described by
  # the first letter of the xm parameter, status(B) uses the second letter,
  # etc. If a pulse sequence has more status statements than there are
  # letters in the xm parameter, control reverts back to the last letter
  # of the parameter value. For example, xm='nyn' will turn the microwave
  # source off during status A, on during status B, and off during
  # status C. Any status higher than C (D-Z) will select the final character
  # of the xm string (n) and turn the microwave source off.

  # The states do to need to increase monotonically during a pulse
  # sequence. One can write a pulse sequence that starts with status(A),
  # goes later to status(B), returns to status(A) and then goes to status(C).
{{</highlight>}}
Example:
{{<highlight C>}}
status(A);
delay(d1);
status(B);
{{</highlight>}}
will turn the microwave source on during the d1 delay if xm='yn', It will turn the microwave source off during the d1 delay if xm='nn'


### Getstr ###
{{<highlight C>}}
void getstr(const char *variable, char buf[])
void getstrnwarn(const char *variable, char buf[])
  # Get the value of a string parameter. The first argument is the name
  # of the string parameter and the second argument is a character array
  # of length MAXSTR. If the parameter does not exist, a null
  # string is returned. The getstr() element will give a warning if the
  # parameter does not exist. The getstrnwarn() will not give a
  # warning if the parameter does not exist.
{{</highlight>}}
Example:
{{<highlight C>}}
char myFlag[MAXSTR];
getstr("flag", myFlag);
{{</highlight>}}


### Getval ###
{{<highlight C>}}
double getval(const char *variable)
double getvalnwarn(const char *variable)
  # Get the value of a real valued parameter. The argument is the name
  # of the parameter.  If the parameter does not exist, a 0.0
  # is returned. The getval() element will give a warning if the
  # parameter does not exist. The getvalnwarn() will not give a
  # warning if the parameter does not exist.
{{</highlight>}}
Example:
{{<highlight C>}}
double myVal = getval("val");
{{</highlight>}}