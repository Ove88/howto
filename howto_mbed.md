# Howto: ARM mbed

The most configurable and useful way to export (and build) the mbed library is to use the [mbed CLI](https://docs.mbed.com/docs/mbed-os-handbook/en/5.1/dev_tools/cli/). This tool makes it very easy to export and build the mbed library for any of the supported targets. It also support several different IDE's, or just standard arm gcc make.

Requirements:

* Python
* Git
* mbed CLI: _pip install mbed-cli_

Make sure Python and Git are added to PATH.
To get started, clone the mbed OS git repository:

In a terminal window:

* git clone https://github.com/ARMmbed/mbed-os.git
* In the parent directory (where mbed-os resides), execute the _mbed new ._ (including the dot)


## Create new Project

First of all, to be able to create a project, the target MCU(board) must be supported by ARM mbed. The currently supported boards should be listed [here](https://developer.mbed.org/platforms/). The supported boards can also be found in /mbed-os/targets/targets.json, where all of the different properties and supported features are also listed. 

The mbed CLI allows to either _export_ a project, or to _compile_. The export function allows you to "export" to the desired IDE using the _-i_ keyword. To list the available IDE's, simply type _mbed export -i x_. The export function itself does not export any source files, it rather creates the project files needed to run the project in the chosen IDE. 

To export the project files to a new project folder: _mbed export -m {MCU/TARGET BOARD} -i {SUPPORTED IDE} --source={YOUR NEW PROJECT FOLDER} --source=mbed-os_
Then simply copy the mbed-os folder into the new project folder. This includes a lot of unnecessary files, which can be removed.

In addition, one can also pre-compile the source files, as well as make a static library. Use the _mbed compile_ command to do this, and add the static library to you project.

More information and examples on the mbed CLI can be found [here](https://github.com/ARMmbed/mbed-cli).
