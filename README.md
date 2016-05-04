MAC Address Formatter
------------------------

Mac Address Formatter is a Mac OS X app that will reformat MAC addresses to different vendor formats.

It has two components, the CLI utility and the OS X contextual menu services.

To install MAC Formatter, paste the following command into a terminal window:
	
	/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/xraystyle/mac_format/master/install)"

Installing this app requires typing your admin password to install the required Ruby Gem, Docopt.

To use the contextual menu services, highlight a MAC address anywhere and right-click. Under the 'Services' submenu, click on the format you'd like to convert to. You'll see a notification that it's completed and the converted MAC address will be copied to your clipboard.

![Right-Click Screenshot](https://raw.githubusercontent.com/xraystyle/mac_format/master/right-click.png)

CLI Tool instructions:

The command name is 'mac_format' and it's installed to /usr/local/bin.

	Usage:
	  mac_format <mac>
	  mac_format -h | --help
	  mac_format <mac> [-c|--convert <format>]

Recognized vendor MAC formats: Linux, Windows, Juniper ScreenOS and Junos, Cisco, MRV, Brocade, HP and Dell Switches.

mac_format will take a MAC address in any of the vendor formats listed above and translate it to any other, or when used without a -c argument will output all known formats.

Sample output:

	mac_format 00:11:22:aa:bb:cc

	Linux/JunOS/MRV/Dell:  00:11:22:aa:bb:cc
	Windows:			   00-11-22-aa-bb-cc
	ScreenOS:              001122aabbcc
	HP:                    001122-aabbcc
	Brocade/Cisco:         0011.22aa.bbcc



To uninstall, paste the following command into a terminal window:

	/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/xraystyle/mac_format/master/uninstall)"


Updates
--------------

5/3/2016

Converted from just a CLI tool to integrated OS X contextual menu services app. 
