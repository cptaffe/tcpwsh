tcpwsh
======

simple bash script that starts wireshark with a real-time analysis of tcpdump.

## Advantages

### Security
Basically runs tcpdump as root with flags for eth0 and packet length of 65535 (no truncation), writing binary data to stdout. This is piped into wireshark running with standard priveledges, and it then gets a real-time influx of packet data with no need to give wireshark root priveledges.

### Efficiency
All given arguments (to the script) will be passed to tcpdump which will serve as a filter. This filter will execute in kernel-space, which is faster/better. bpf (and tcpdump) explained here: https://idea.popcount.org/2014-05-21-bpf-the-forgotten-bytecode/
