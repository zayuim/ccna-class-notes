# CCNA Class Notes
Some notes that might came in handy with the 'Cisco Certified Network Associate' or CCNA course.

**Packets**

# IPv4 Basic's
**IP Address**

This address is assigned to hosts. A host in computer network theory is simply an end device, something like a computer or phone. All IPv4 addresses are split up into 4 sections called "octets" these contain 8 bits which can range from (0 - 255). This is sort of like an ID, so that packets can find their way to you.

```
11000000.10101000.01100100.00011001
192     .168     .100     .25
```

**NAT or Network Address Translation**

**Subnet Mask**

This mask is what we use to devide different networks
```
11111111.11111111.11111111.11110000
255     .255     .255     .240
```

**Network Address**

The first address in the network, not assigned to anything, just used to describe the subnetwork as a whole in topologies/network documentation.
```
11000000.10101000.01100100.00010000
192     .168     .100     .16
```

**Broadcast Address**

The final address in a subnetwork, It is reserved and cannot be assigned to a host/device.
```
11000000.10101000.01100100.00011001
00000000.00000000.00000000.00001111
11000000.10101000.01100100.00011111
192.168.100.31
```

**Default Gateway**

The IP address of the first router interface your computer goes to (never a switch). Basically if your computer goes to a switch and then into router interface g0/1, which the IP is set to 192.168.1.1. That IP is your default gateway, since it's the first router you reach.

**"CIDR notation" or "What does the slash mean?**
The network portion from the left in other words the amount of ones from left to right e.g.
192.168.0.0 /29 =
11111111.11111111.11111111.11111000

Various Subnet Mask Endings:
128 - 192 - 224 - 240 - 248 - 252 - 254 - 255

Reserved IPs:
The first address (the network address) cannot be assigned to a host/end point.
the last address (the broadcast address) cannot be assigned to host/end point.

How to work out hosts:
Host bits are zeros to the right of the subnet mask.
2^(number of host bits) -2 = Number of hosts.

# Commands
enable > config > hostname  -  add hostname

config > line console 0 > password ... > login > exit  -  add access to console line

config > enable password > exit  -  set/change a static enable password

config > enable secret > exit - add password to secure access

config > interface g0/0 or fe0/0 or vlan1 > ip address ... ... > no shut > exit  -  config IP to interface

config > banner motd  -  setup message of the day

service password-encryption

show run  /  show ip int brief

int [whatever] > ipv6 address fe80::2 link-local  -  set link local



---Default Route used when there is no known network to forward to---
(config)# ip route 0.0.0.0 0.0.0.0 ip add [IP address of where it is going or the exit interface]


---Static Route uses its own exit interface---
(config)# ip route [destination address] [destination subnet mask] [exit interface of current device]

# Resources
http://networkengineering.stackexchange.com/questions/7106/how-do-you-calculate-the-prefix-network-subnet-and-host-numbers

http://www.cisco.com/c/en/us/td/docs/ios/12_2/security/configuration/guide/fsecur_c/scfpass.pdf
