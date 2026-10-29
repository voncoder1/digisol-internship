# Lab 01: Network Connectivity and DNS Troubleshooting

## Objective
Test IP connectivity, DNS resolution, and the route to an external destination.

## Environment
- OS: Ubuntu 24.04 LTS on WSL 2
- Network interface: eth0
- WSL IPv4 address: 172.24.22.22/20

## Test 1: IP Connectivity
Command: `ping -c 4 8.8.8.8`

Results:
- Packets transmitted: 4
- Packets received: 4
- Packet loss: 0%
- Average round-trip time: approximately 32.5 ms

Conclusion: IP connectivity to 8.8.8.8 was successful.

## Test 2: DNS Resolution
Command: `dig google.com`

Results:
- DNS status: NOERROR
- Returned IPv4 address: 142.251.216.110
- DNS server: 10.255.255.254
- Query time: 47 ms

Conclusion: DNS resolution succeeded.

## Test 3: Route Tracing
Command: `traceroute -m 12 google.com`

Observations:
- The route showed local and upstream network hops.
- Some routers did not respond to traceroute probes.
- The destination resolved to 142.251.29.138 during this test.

Conclusion: The trace reached a Google destination. Non-responsive hops do not necessarily indicate a fault.

## Skills Practiced
- Inspecting network interfaces with `ip addr`
- Testing IP connectivity with `ping`
- Querying DNS with `dig`
- Tracing network paths with `traceroute`

## Summary
All three tests completed successfully. This lab established a baseline for connectivity and DNS troubleshooting.
