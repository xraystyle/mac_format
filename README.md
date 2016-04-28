MAC Address Formatter
------------------------

Output a MAC address in the formats used by various vendors on their router/switch hardware.

Requires the Docopt gem.

	Usage:
	  mac_format <mac>
	  mac_format -h | --help
	  mac_format <mac> [-c|--convert <format>]

Recognized vendor MAC formats: Linux, Juniper ScreenOS and Junos, MRV, Brocade, HP and Dell Switches.

mac_format will take a MAC address in any of the vendor formats listed above and translate it to any other, or when used without a -c argument will output all known formats.

Sample output:

	mac_format 00:11:22:aa:bb:cc

	Linux/JunOS/MRV/Dell:  00:11:22:aa:bb:cc
	ScreenOS:              001122aabbcc
	HP:                    001122-aabbcc
	Brocade:               0011.22aa.bbcc