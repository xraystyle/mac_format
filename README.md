MAC Address Formatter And OUI Lookup Tool
------------------------

Mac Address Formatter is a Mac OS X app that will reformat MAC addresses to different vendor formats and perform OUI vendor lookups on MAC addresses in most any format.

It has two components, the CLI utility and the OS X contextual menu services.

To install MAC Formatter, paste the following command into a terminal window:
	
	/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/xraystyle/mac_format/master/install)"

If you've previously installed and want to update to the newest version, just re-run the above script again.

Installing this app requires typing your admin password to install the required Ruby Gem, `Docopt`.

To use the contextual menu services, highlight a MAC address anywhere and right-click. Under the `Services` submenu, click on the format you'd like to convert to. You'll see a notification that it's completed and the converted MAC address will be copied to your clipboard. If you select the Vendor Lookup service option, you'll receive a notification with the name of the vendor.

![Right-Click Screenshot](https://raw.githubusercontent.com/xraystyle/mac_format/master/right-click.png)

CLI Tool instructions:

The command name is `mac_format` and it's installed to `/usr/local/bin`.

	Usage:
	  mac_format <mac>
	  mac_format -l <mac>
	  mac_format -h | --help
	  mac_format <mac> [-c|--convert <format>] 

	Options:
	  none          Show MAC in all known formats.
	  -h --help     Show this screen.
	  -c --convert  Specify a MAC address format. (Linux|Brocade|Cisco|ScreenOS|JunOS|MRV|HP|Dell|Windows)
	  -l            Perform a vendor lookup on the given MAC address.

Recognized vendor MAC formats: Linux, Windows, Juniper ScreenOS and Junos, Cisco, MRV, Brocade, HP and Dell Switches.

mac_format will take a MAC address in any of the vendor formats listed above and translate it to any other, or when used without a `-c` argument will output all known formats.

Sample output:

	~$ localhost: mac_format 00:11:22:aa:bb:cc

	Linux/JunOS/MRV/Dell:  00:11:22:aa:bb:cc
	Windows:	       00-11-22-aa-bb-cc
	ScreenOS:              001122aabbcc
	HP:                    001122-aabbcc
	Brocade/Cisco:         0011.22aa.bbcc

	~$ localhost: mac_format -l d4:f4:be:49:03:00
	Palo Alto Networks


To uninstall, paste the following command into a terminal window:

	/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/xraystyle/mac_format/master/uninstall)"


Updates
--------------

2/22/2019

Tested working on Mojave!
Updated to support latest version of the vendor lookup API. The API was updated which broke everything. It's all functional again.

11/29/2017

Added support for dropped leading zeros in MAC address octets, such as found with the `arp -a` command on OS X.

Fixed High Sierra compatibility. High Sierra breaks Automator services in some very subtle and stupid ways, which means notifications sent from automator don't always work. Fixed the Automator services to work properly again.

If you've upgraded to High Sierra, probably best to run the uninstall script to remove everything, then reinstall. 

5/4/2016

Added vendor OUI lookup functionality! You can now lookup a vendor with either the CLI tool or with the new OS X contextual menu service!


5/3/2016

Converted from just a CLI tool to integrated OS X contextual menu services app. 
