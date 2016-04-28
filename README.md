MAC Address Formatter
------------------------

Output a MAC address in the formats used by various vendors on their router/switch hardware.

`Usage:
  #{File.basename(__FILE__)} <mac>
  #{File.basename(__FILE__)} -h | --help
  #{File.basename(__FILE__)} <mac> [-c|--convert <format>] 

Options:
  none          Convert to standard Linux format.
  -h --help     Show this screen.
  -c --convert  Specify a MAC address format. (Linux|Brocade|ScreenOS|JunOS|MRV|HP|Dell)`