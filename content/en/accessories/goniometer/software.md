---
title:          "Remote Control the Goniometer"
linkTitle:      "Remote Control"
weight:         20
type:           docs
date:           2024-07-11
description:    "How to remote control the goniometer from a computer"
draft:          True
---
## Getting Started
### Installing the pyB12SMC Python Package

#### Requirments
The pyB12SMC Python package requires:
* [Python](https://www.python.org/) (>= 3.10)
* [Numpy](https://numpy.org/) (>= 1.26)
* [Pyserial](https://pypi.org/project/pyserial/) (>= 3.5)

The pyB12SMC Python package to remote control the goniometer is available on [GitHub (pyB12SMC)](https://github.com/Bridge12Technologies/pyB12SMC). To install the Python package follow these steps:

1. Clone the Python package from the GitHub repository.
2. Open a terminal window and navigate to the folder to which the Python package was downloaded. For example, if you cloned the repository to C:\Documents\Repositories\pyB12SMC navigate to the folder C:\Documents\Repositories
3. In the terminal window type the following command and hit the return key:

    ```pip install -e pyB12SMC ```

Then the Python package will be built and installed locally. Once it is installed you can verify using the ```pip show``` command that the package is properly installed:

```
    B12TManuals % pip show pyB12SMC

    Name: pyB12SMC
    Version: 0.0.1
    Summary: A Python package for interfacing with Stepper Motor Controller (BIGTREETECH SKR MINI E3 V3.0) used in Bridge 12 Technologies products.
    Home-page: http://www.bridge12.com/
    Author: Bridge12 Technologies, Inc
    Author-email: yhuang@bridge12.com
    License: 
    Location: /Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages
    Editable project location: .../Documents/Repositories/pyB12SMC
    Requires: numpy, pyserial
    Required-by: 
```

The Python package is properly installed and the goniometer can be controlled using the methods in pyB12SMC.

### Quickstart - Using the pyB12SMC Python Package
{{% pageinfo color="primary" %}}
### Important
The goniometer rotation is controlled using a stepper motor and the motor is connected to the X axis of the stepper motor controller. Therefore, all commands used to control the goniometer need to reference the X axis..
{{% /pageinfo %}}

Once the package is installed open a terminal and start Python. To use the goniometer follow these steps:

1. Import the Python package

    ```import pyB12SMC```

2. Initialize the class

    ```smc = pyB12SMC.SMC()```

3. Try the following commands:

    Go to the home position (X-axis), corresponding to 0º

    ```smc.home('X')```

    Set the position of the goniometer to 15º

    ```smc.theta('X', 15)```

    Nothing will happen if the command is repeated since the angle theta is an absolute value. To return to the home position either use one of these two commands:

    ```smc.home('X')```

    or

    ```smc.theta('X', 0)```

4. To change the behavior from absolute angle to relative angle use the following command:

    ```smc.relative(True)```

    Now, each time the smc.theta command is issued the goniometer rotates by the given angle. For example:

    ```smc.theta('X', 15)```
    
    ```smc.theta('X', 15)```

    Will result in a total rotation of 30º.

    Sending the following command:

    ```smc.theta('X', -15)```

    will rotate the goniometer 15º in the opposite direction.

5. To print an overview of the available methods send the following command:

    ```smc.help()```

## Troubleshooting
### No Serial Communication
If the communication with the controller fails or the device cannot be found, it is possible that the Python package cannot find the device on the COM port. In this case, a COM port can be specified manually. To set the COM port manually (here COM13) send the following command:

```smc = pyB12SMC.SMC('COM13')```

## Method Overview
When starting the Python package an object is created. The methods included in the class are described below.

{{% pageinfo color="primary" %}}
### Important
Valid values for the parameter *axis* are "X", "Y", or "Z" (capital letters) 
{{% /pageinfo %}}

| Method | Returns | Description |
| --- | --- | --- |
| move(axis, position) | None | Move axis linearly. Position given in mm.|
| theta(axis, theta) | None | Move axis rotationally. The angle is given in degrees. |
| feedrate(axis, feedrate) | None or value (dictionary) | Query the information of federate if no arguments, or set axis feedrate in units/s |
| position(axis, position) | None or value (dictionary) | Query the information of positions if no arguments, or set axis position in unit |
| current(axis, current) | None or value (dictionary)  | Query the current settings if no arguments, or set axis current in mA |
| steps_per_unit(axis, step) | None or value | Query the resolutions of all axis if no arguments, or set axis resolution in steps/unit |
| home(axis) | None | Home all axis if no argument, or home specified axis |
| set_home(axis) | None | Set current positions as home for all axis if no argument, or set current position as home for an axis |
| relative(enable) | None or boolean | Query the movement type if no arguments, set movement relative or absolute |
| save() | None | Save settings to EEPROM |
| restore() | None | Restore settings from EEPROM |
| reset() | None | Reset configuration to factory defaults |
| send_command(command, receive) | None or string | Send command to a device and receive information from a device |
