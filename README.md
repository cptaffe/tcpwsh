tcpwsh
======

simple bash script that starts wireshark with a real-time analysis of tcpdump.

Basically runs tcpdump as root with flags for eth0 and packet length of 65535 (no truncation), writing binary data to stdout. This is piped into wireshark running with standard priveledges, and it then gets a real-time influx of packet data with no need to give wireshark root priveledges.
