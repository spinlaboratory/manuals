---
title:        "Pulse Programming"
linkTitle:    "Pulse Programming"
type:         docs
weight:       20
draft:        false
description:  "Pulse Programming in OVJ"
---
## General Concept ##

Pulse sequences are written in C, a high-level programming language that allows considerable sophistication in the way pulse sequences are created and executed.

A new pulse sequence is written as a C function called pulsesequence. The file containing this function is compiled and linked with an object library that contains the definitions for all pulse-sequence statements, the PSG. A compiled C sequence is executed on the Linux workstation at the start of acquisition, so-called run-time. At run-time, the sequence reads values from a parameter table and constructs a second real-time program of acodes, whose purpose will be to run the SpinCore controller board.

The PSG library contains C code to run the pulsesequence function and to run spectra corresponding to arrays of parameter values. The user need not program these loops explicitly. At the start of the acquisition, all of the variables and statements of the compiled C program, including the C loops and conditionals, are resolved and fixed into acodes, without the possibility of further input or calculation. A complex program with many choices, using the C if-else-endifstatement, may resolve into a very few acodes, because the acodes in the non-selected branches are never created. A pulse program with multidimensional looping and/or parameter arrays will produce a separate set of acodes for every increment.

The real-time acode program is automatically looped over the number of scans for each multidimensional increment or array element. Special real-time integer tables, t1 to t10, are used to increment phases and other values that might change scan-to-scan. These tables and variables are initialized and manipulated by special pulse-sequence statements, the real-time math statements. 

### Writing pulse sequences ###

Pulse sequence text files are stored in a directory named psglib in either the system directory (/vnmr/psglib) or in a user directory (/home/vnmr1/vnmrsys/psglib for the user vnmr1). A pulse sequence file has the extension .c to indicate that it contains C language source code. Pulse sequences may also be saved in the psglib directory of an applications directory, which may have any name and path. An applications directory is made accessible through the Edit Applications tool of the Files pull down menu. A pulse sequence text file can be modified using the Linux tool vi, the standard Linux editor gedit, or by an available text editor or development package. 

The template for all pulse sequences is:

{{<highlight C>}}
#include "standard.h"

void pulsesequence()
{
  // Pulse elements

}
{{</highlight>}}

Since it is a C function, any C construction may be used. The available pulse elements are described below. For examples, see the pulse sequences in /vnmr/psglib

### Compiling pulse sequences ###

After writing a pulse sequence, the source code is compiled by one of the following methods:

* By entering ``seqgen(filename<.c>)`` on the OpenVnmrJ command line.
* By entering ``seqgen`` on the OpenVnmrJ command line, with seqfil='filename'
* By entering ``seqgen filename<.c>`` from a Linux shell

For example, enter ``seqgen('s2pul')`` to compile the s2pul.c sequence in OpenVnmrJ. A full path is not necessary from the command line. Alternatively, you can enter

{{<highlight Shell>}}
seqgen s2pul
{{</highlight>}}

in a Linux shell. The ```seqgen``` command will first search the user, then the available applications directories, and then the system for a file with a .c extension. 

During compilation, the system performs the following steps:

1. Extensions are added to the pulse sequence to allow a graphical display of the sequence, using the dps command. 
2. The source code is checked for syntax, variable consistency, and the correct usage of functions.
3. The source code is converted into compiled object code.
4. If the conversion is successful, the object code is combined with the necessary system PSG object libraries (libparam.so and libpsglib.so), to be linked at run-time. If the compilation of the pulse sequence with the dps extensions fails, the pulse sequence is recompiled without the dps extensions. 

The executable code is stored in the user seqlib directory (e.g. /home/vnmr1/vnmrsys/seqlib). If the user does not have a seqlib directory, it is automatically created. A copy of the source code is also saved in vnmrsys/seqlib of the user directory. If desired, you can copy the compiled sequence to /vnmr/seqlib or to the seqlib directory in an applications directory. 

Standard compiled sequences are supplied in /vnmr/seqlib and the source code for each of these sequences is found in /vnmr/psglib. To recompile one of these sequences or to modify it, first copy the sequence into the user psglib, make the required modifications, and then recompile the sequence using seqgen. Sequences can only be compiled from a user directory. If you attempt to compile a system sequence, a local copy will be created. The seqgenupdate command performs a seqgen as the first step, and will then attempt to move the resulting seqlib entries back to the application directory from which they were taken.

The source files that are used to create the PSG object library are contained in the system directory /vnmr/psg. In principle, a user can customize and recompile the PSG source files, but most users do not do so. It is easier to add the user source code in a separate file using the standard C #include statement. User #include files should be stored in the ~/vnmrsys/psg directory of a user or an applications directory. 
