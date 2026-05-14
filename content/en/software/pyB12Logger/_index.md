---
title:          "System Monitor - pyB12Logger"
linkTitle:      "pyB12Logger"
type:           docs
weight:         30
draft:          false
description:    "System monitor and logger for Bridge12 spectrometers"
---
The pyB12Logger is a general purpose logging software to log the status of different devices that are connected to the spectrometer (e.g. cryo-compressor, temperature controllers, ...). The software is distributed as a Python package.

When the software is started for the first time, it will automatically create some configuration files and directories on the hard disc to store the log files.

The log files are written as a comma separated value (csv) file.

The Python package has two components:

1. **pyB12logger** This is he logger software, which will run in the background. Typically, it is automatically started when the computer starts up.
2. **pyB12monitor** This is a program to plot the logged data. The monitor can be used to plot real-time data or historical data from the log files.

#### Requirements

* Operating System: Windows 10 (or higher)
* Python, version > 3.6

## Using the Logger
### Starting the Logger
Typically, the logger is started automatically for example, after the computer re-boots. To start the logger manually follow these steps:

1. Open a command prompt window by typing ```cmd``` into the window search bar.
2. At the command prompt type ```pyB12Logger``` and hit the return key.

After hitting the return key a status message will inform the user whether the logger is already running, or if it has been started (see screen shot below).

<center>
{{< figure_b12t src="/images/software/pyB12Logger/Terminal_ScreenShot_800px.png">}}
</center>

The general format it the command is:

```pyB12logger [-h] [-desktop {True,False}] [-startup {True,False}] [-debug {True,False}] [{start,stop}]```

| Arguments/Options | Description |
| --- | --- |
| {start,stop} | Start or stop the pyB12logger. If no argument is given, the command will start the logger |
| -h, --help | Show help message |
| -desktop {True,False} | Create a desktop icon for the software |
| -startup {True,False} | Enable or disable the starting the pyB12logger when the computer boots |
| -debug {True,False} | Start the pyB12logger with console window |

### Starting the Monitor

The pyB12monitor is used to either plot historical data or the real-time data. To type start the monitor:

1. Open a command prompt window by typing ```cmd``` into the window search bar.
2. At the command prompt type ```pyB12monitor``` and hit the return key.

The pyB12monitor will start.

<center>
{{< figure_b12t src="/images/software/pyB12Logger/Monitor_ScreenShot_800px.png">}}
</center>

| Name | Description |
| --- | --- |
| Status | Status of the devices |
| Warnings | Warning messages are shown here. Warnings are based on the ```min```, ```max```, ```static``` values given in the configuration file |
| Window Length | Number of data points shown in the graph |
| Hidden | List of variables that are logged |
| Shown | List of variable that are shown in the plot |
| Arrows | Move variables from Hidden to Shown and vice versa |
| Start Time & End Time | Optional parameters. These values can be used to select a certain time range to be plotted. Click ```OK``` to confirm the time range. Click ```Reset``` to return to the real-time view |

All settings are automatically saved.

## Configuring the Logger

* Data logs are located at C://Users/Public/B12TLOG
* The typical file size is 100 kB. This value can be adjusted by the user in the configuration file.
* The configuration file is located at C://User/Public/B12TLOG_Config/config.cfg

The first section of the config file is the [SETTINGS] section. It contains information about the logging interval (given in s), the location of the log files, and the maximum file size.

```
[SETTINGS]
log_interval = 10
log_folder_location   = C:/Users/Public/
save_file_size_kb   = 100
```

This section is followed by individual sections for different instruments that are connected to the logger.

```
[F70]
device_status = True
address = ASRL11::INSTR
termination = CR
id_command = $ID1D629
index = 1
helium_discharge_temperature  = $TE140B8, alias = He discharge
water_outlet_temperature      = $TE241F8, alias = H2O outlet, min = 10, max = 35
water_inlet_temperature       = $TE38139, alias = H2O inlet, min = 10, max = 35
compressor_pressure           = $PR171F6, alias = He pressure
status                        = $STA3504, alias = Status, static = 301
```

For more information about how to configure the pyB12logger, please contact Bridge12 at support@bridge12.com.


## Installation
The software comes installed and pre-configured with the spectrometer. If you need to re-install the software please contact us at support@bridge12.com.
