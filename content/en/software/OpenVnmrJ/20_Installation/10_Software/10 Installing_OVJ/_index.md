---
title:        "Installing OVJ-B12"
linkTitle:    "Installing OVJ-B12"
type:         docs
weight:       10
draft:        false
description:  "Installing the Bridge12 version of Open VnmrJ (OVJ-B12)"
---

{{% pageinfo color="primary" %}}
### Note ###
[Open VnmrJ](https://openvnmrj.org/) is automatically installed when installing OVJ-B12, the Bridge12 version of OVJ. OVJ does not have to be installed separately.
{{% /pageinfo %}}

Bridge12 does not offer a pre-compiled version of OVJ-B12. Instead, the package has to be build on the computer that is used to operate the spectrometer. However, the installation process is streamlined and does not require any specific programming skills besides navigating through some terminal windows.

## Preparing the System ##

1.  Start by opening a terminal window and update all installed packages to the latest version:

    {{<highlight Shell>}}
    sudo apt-get update
    sudo apt upgrade
    {{</highlight>}}

    The best way to install OVJ-B12 is by using the [GitHub repository](https://github.com/Bridge12Technologies/OpenVnmrJ_B12T). Updates are pushed to the GitHub repository and can be installed by the user from there.

2.  Install *git* and *python3-pip*

    {{<highlight Shell>}}
    sudo apt install python3-pip
    sudo apt install git
    {{</highlight>}}

    To communicate with the NMR spectrometer and the [Bridge12 MPS](https://www.bridge12.com/products/microwave-power-source-for-odnp-spectroscopy/) a serial connection to the periphery is required. OVJ-B12 uses Python and the *pyserial* Python package for this purpose, which can be installed through *pip*.

    {{<highlight Shell>}}
    sudo pip3 install pyserial==3.5
    {{</highlight>}}

## Cloning the Repository ##

3.  To clone the GitHub repository, open a terminal window

    {{<highlight Shell>}}
    git clone git@github.com:Bridge12Technologies/OpenVnmrJ_B12T
    {{</highlight>}}

    Once the repository is downloaded change into the directory .....

## Building the OVJ-B12 Package ##

4.  Build the package. As a first step in the installation, the OpenVnmrJ and ovjTools repositories will be automatically downloaded. The complete build processes takes about 10 minutes.

    {{<highlight Shell>}}
    sudo ./buildb12
    {{</highlight>}}

    We recommend opening a new console tab in the terminal window to monitor the build process. To do this copy and paste the command (*tail -f*) with the corresponding file shown in the console after starting the build process into the new console tab of the terminal window.

    <center>
    {{< figure_b12t src="/images/software/OVJ/Monitor_b12Build_600px.png">}}
    </center>

5.  Once the build is finished check the build process with

    {{<highlight Shell>}}
    ./whatsin
    {{</highlight>}}

    The output should report **0 Errors and 0 Build Terminations** for a successful build.

    <center>
    {{< figure_b12t src="/images/software/OVJ/Whatsin_b12Build_600px.png">}}
    </center>

    If the build succeeded the folder ~/ovjbuild/dvdimageB12 is created.

## Install OVJ-B12 ##

6.  To install OVJ-B12 change to the dvdimageB12 directory and execute ./load.nmr

    {{<highlight Shell>}}
    cd ~/ovjbuild/dvdimageB12
    ./load.nmr
    {{</highlight>}}

    A popup window will appear, press *install* to continue with the installation.

    <center>
    {{< figure_b12t src="/images/software/OVJ/InstallB12_ovnmrj_popup_600px.png">}}
    </center>

7.  When asked to update users start the *vnmrjAdmin* program located on the Desktop. The program should start automatically. In *vnmrjAdmin* go to
    Configure -> Users -> Update users ...

    <center>
    {{< figure_b12t src="/images/software/OVJ/UsersTab_Screen1_600px.png">}}
    </center>
    
    and add all users (vnmr1, service and walkup if they were created) to the right side. Then press "update users"
    
    <center>
    {{< figure_b12t src="/images/software/OVJ/UpdateUsersPanel-2_600px.png">}}
    </center>
    
    Once all users are updated, the bottom status line in OpenVnmrJAdmin will show "Update User Completed All Requested Users". Once you see this message, close OpenVnmrJAdmin.
 
8.  After this, the system will open a new terminal window and the user has to answer a few questions. Please answer both questions with y(yes).

    {{<highlight Shell>}}
    Standard configurations include the walkup and service accounts.
    Would you like to make them now? (y/n)
    {{</highlight>}}


    {{<highlight Shell>}}
    Shall this system be configured as a spectrometer (see image below).
    Would you like to configure it now? (y/n)
    {{</highlight>}}

    <center>
    {{< figure_b12t src="/images/software/OVJ/InstallSpectrometer_600px.png">}}
    </center>

9.  Installing NMRPipe is optional and can be answered with n(no).

10. We recommend to install the OVJ manuals. When asked to install the manuals please answer the question with y(yes).

    <center>
    {{< figure_b12t src="/images/software/OVJ/InstallManuals_600px.png">}}
    </center>

### Finish Installation ###

11. Once the *load.nmr* script has finished the *upgrade.nmr* script should be executed

    {{<highlight Shell>}}
    ./upgrade.nmr
    {{</highlight>}}

12. The installation scripts places two icons to the Desktop: *vnmrj* and *vnmrjAdmin*. *vnmrj* can either be launched by double-clicking on the desktop icon or from the command line:

    {{<highlight Shell>}}
    vnmrj
    {{</highlight>}}

    It is convenient to add Open VnmrJ to the quicklaunch menu. This can be done by by searching for "openvnmr" and then dragging the program icon to the quicklaunch bar.

    <center>
    {{< figure_b12t src="/images/software/OVJ/OpenVNMR_Searchbar_600px.png">}}
    </center>

OVJ-B12 is now installed and ready for its first experiment.