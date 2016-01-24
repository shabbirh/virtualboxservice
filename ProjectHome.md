## VirtualBoxService ##
A Windows-Service to control Startup and Shutdown of Virtualbox VMs.

![http://wiki.virtualboxservice.googlecode.com/git/screenshot.png](http://wiki.virtualboxservice.googlecode.com/git/screenshot.png)

Download [latest release](http://virtualboxservice.googlecode.com/files/VirtualBoxService-v0.1.zip) (beta, expect bugs or crashes)


### Features ###
  * Starts and stops virtual machines of [Oracle VirtualBox](http://www.virtualbox.org)
  * Supports three different shutdown-methods
  * Runs as Windows-Service
  * Uses the Virtualbox-Configuration of the user account under which the Service runs
  * Delays shutdown of Windows until all machines have properly shutdown (only on Vista SP1 and higher)
  * Configurable from within Virtualbox GUI or phpvirtualbox
  * Starts and Stops Virtualbox-Webservice (vboxwebsrv)


### Usage Instructions ###
  1. Download and extract to a folder of your choice
  1. Run _virtualboxservice.exe_ and install using the GUI
  1. Open Virtualbox and add the following template to the description of the machines you wish to be controlled by VirtualBoxService:`<!VirtualboxService--{"Autostart":"true", "ShutdownType":"ACPIShutdown", "ACPIShutdownTimeout": "300000"}--/VirtualboxService>`
  1. Customize the parameters:
    * **Autostart**: "true" or "false", defines, if the machine should be controlled
    * **ShutdownType**: "ACPIShutdown", "SaveState" or "HardOff"
    * **ACPIShutdownTimeout**: Milliseconds to wait for machine to shutdown once the ACPI-Command has been sent
  1. If you want the Service to start at Windows startup, go to services control panel and change the startup type

**Hint:** To control your Virtual Machines while the service is running, you can use [phpvirtualbox](http://code.google.com/p/phpvirtualbox). You have to enable vboxwebsrv-hosting in the service-configuration GUI for this to work.


### Current Limitations ###
  * Only tested with Windows 7 x64 (but should work on Vista SP1 (or higher) and various server editions, too. Unsure about Windows XP.)
  * Service has to run as user, which has local admin-privileges
  * Due to unstable virtualbox-api only compatible to VirtualBox v4.0.x and v4.1.x
  * ~~Not tested in productive environment or over long term~~

### Short Update (June 8, 2012) ###
  * Running for about 9 months now in my environment without problems
  * Tested successfully with Virtualbox 4.1.16.


<br />
<br />
[![](https://www.paypalobjects.com/en_US/i/btn/btn_donate_SM.gif)](https://www.paypal.com/cgi-bin/webscr?cmd=_s-xclick&hosted_button_id=DQF89XW768Z84)


_Note: VirtualBox, Oracle, Windows, Vista and all other trademarks are the property of their respective owners_