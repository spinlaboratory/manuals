---
title:        "Overview"
linkTitle:    "Overview"
type:         docs
weight:       10
draft:        false
description:  "Brief Introduction to Open VnmrJ"
---
## Open VnmrJ (OVJ) ##
[Open VnmrJ](https://openvnmrj.org/) (OVJ) is an open-source software package designed for the acquisition, analysis, and processing of nuclear magnetic resonance (NMR) spectral data. It is an extension of the popular VnmrJ software, which was originally developed by Varian (later Agilent) for NMR data processing and acquisition. [OVJ](https://openvnmrj.org/) provides a flexible and customizable platform for researchers to acquire, perform advanced data analysis, and visualize NMR experiments.

<center>
{{< figure_b12t src="/images/software/OVJ/OVJ_SplashScreen.gif">}}
</center>

[OVJ](https://openvnmrj.org/) offers a wide range of features and tools to facilitate NMR data processing. It includes functionalities for Fourier transformation, baseline correction, peak picking, spectral fitting, and data manipulation. [OVJ](https://openvnmrj.org/) supports various 1D or multi-dimensional NMR experiment types, for solution- and solid-state NMR spectroscopy.

[OVJ](https://openvnmrj.org/) is entirely open source. The software's source code is freely available and can be modified and customized by the user community. This allows researchers to adapt the software to their specific needs, add new functionalities, or contribute to the development and improvement of the software itself.

The software provides a user-friendly interface, making it easily accessible to both novice and experienced users. It offers a range of visualization tools, such as 1D and 2D spectral displays, contour plots, and integration windows, to aid in data interpretation. Additionally, the software supports automation and scripting capabilities, enabling users to streamline their workflows and automate repetitive tasks.

### OVJ Resources ###

* Further information is available on the [Open VnmrJ](https://openvnmrj.org/) webpage.
* To contribute to the project check out the [How to join this project](https://openvnmrj.org/How%20to%20Join/) webpage for more information.
* The source code for OVJ is hosted on [GitHub](https://github.com/OpenVnmrJ/OpenVnmrJ).
* Please report issues on the [Issues Page of the GitHub Repository](https://github.com/OpenVnmrJ/OpenVnmrJ/issues)

## Bridge12 Version of Open VnmrJ ##
<center>
{{< figure_b12t src="/images/software/OVJ/OVJ_SplashScreen_B12.png">}}
</center>

Bridge12 uses a customized version of OVJ to control:

* The [Bridge12 Single Channel NMR (SCN)](https://www.bridge12.com/products/single-channel-nmr-spectrometer-for-odnp/) spectrometer
* The Bridge12 Shim Power Supply (Bridge12 SPS)
* The [Bridge12 Microwave Power Source (MPS)](https://www.bridge12.com/products/microwave-power-source-for-odnp-spectroscopy/) for Overhauser-DNP spectroscopy.

All functionality of [OVJ](https://openvnmrj.org/) is available in the Bridge12 version of OVJ, but new functionality is added to communicate with the Bridge12 instruments.

## Syntax Highlighting ##
Syntax highlighting is used throughout this documentation. Below are some examples for reference:

##### Shell Command #####
{{<highlight Shell>}}
echo "Hello World"
{{</highlight>}}

##### Python Script #####
{{<highlight python>}}
import dnplab as dnp

data = dnp.load("MySpectrum)
dnp.plt.figure()
dnp.plot(data)
dnp.plt.show()
{{</highlight>}}
