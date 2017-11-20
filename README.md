## Synopsis

This provides an SNMP Trap server compatible with ARM architecture on Raspberry Pi. Configuration is passed in from a local directory, which should be indicated by docker options "-v /path/to/config:/etc/snmp"

Port forwarding is enabled for port 162

## Code Example

docker run -d --name rpi-snmp -p 162:162 -v /home/pi/docker/snmp/conf:/etc/snmp fatalglitch/rpi-snmptrap

## Tests
You can test the functionality by running the below (replacing host with your server IP) from a system which has snmp installed:
snmptrap -v 2c -c public "" UCD-NOTIFICATION-TEST-MIB::demoNotif SNMPv2-MIB::sysLocation.0 s "Just here"

## License

MIT Licensed
