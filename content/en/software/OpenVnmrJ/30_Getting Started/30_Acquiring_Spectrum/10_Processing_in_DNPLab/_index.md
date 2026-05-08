---
title:        "Processing 1D Spectra in DNPLab"
linkTitle:    "Processing in DNPLab"
type:         docs
weight:       10
draft:        false
description:  "How to process 1D OVJ Data in DNPLab"
---
[DNPLab](http://dnplab.net/) is a Python package to process NMR data. The software was developed by Bridge12 and is open-source, free to use. DNPLab can be used for offline processing of OVJ data.

Below, a brief example is shown how to load and process a 1D NMR spectrum. For a complete reference and many more processing examples visit the [DNPLab Online Documentation](http://dnplab.net/).

### Installling DNPLab ###

DNPLab requires a working Python installation and can be simply installed using pip:

{{<highlight shell>}}
pip3 install dnplab
{{</highlight>}}

All requirements are automatically installed.

### Processing 1D Spectra ###

A typical processing and plotting script is shown below:

{{<highlight python>}}
import dnplab as dnp

data=dnp.load('path/to/folder/PROTON_XY.fid')
data.attrs['experiment_type']='nmr_spectrum'

data=dnp.fourier_transform(data)
data=dnp.autophase(data)
data=dnp.processing.offset.remove_background(data,dim='f2',regions=[(200,320)])

dnp.fancy_plot(data)
dnp.show()
{{</highlight>}}

The general structure of the script is:

+ Line 1: Import the DNPLab package.
+ Line 3: Load the NMR spectrum. DNPLab can import many different spectrometer formats. The format is automatically detected and a *dnpdata object* is created. 
+ Line 4: The attribute of the spectrum needs to be changed to *nmr_spectrum* to ensure that the plot function ```fancy_plot``` works properly (this line will not be required in the future).
+ Line 6-7: Fourier transform the spectrum and apply an autophase routine.
+ Line 8: Remove DC offset from spectrum.
+ Line 10-11: Plot the NMR spectrum

The result is shown below.

<center>
{{< figure_b12t src="/images/software/OVJ/image-sources/nmr_water_signal.png">}}
</center>

[DNPLab](http://dnplab.net/) has many more features for processing and analyzing NMR data. It can also be used to process EPR data. For more information check out the [Online Documentation](http://dnplab.net/).