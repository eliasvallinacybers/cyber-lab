A host uses its IP address, subnet mask, and the destination IP to decide whether the destination is in the same subnet or a different one. If it is in the same subnet, the traffic is sent directly: PC1 → Switch → PC2. If it is in a different subnet, the host sends the traffic to its default gateway: PC1 → Switch → Router → Switch → PC2. The key point is that the destination IP identifies the final host, while the destination MAC identifies the next device on the local link. If the destination is local, the sender needs the MAC address of the other host; if the destination is remote, it needs the MAC address of the router. ARP is used only on the local network to discover that MAC address.  
  
A switch connects devices in the same local network and forwards frames using MAC addresses. A router connects different networks and forwards packets assigning IP addresses to the devices, and its routing table. Each router interface belongs to a different network and has its own IP address, such as 192.168.1.1 on one side and 192.168.2.1 on the other. When a router forwards traffic, the IP destination usually stays the same, but the MAC addresses change at each hop.  
  
In home networks, the router, switch, and Wi-Fi access point are often built into the same physical device. 
- The access point is the part that lets wireless devices join the local network through Wi-Fi. 
- The **LAN** is the local network inside the home, while the **WAN**, or Wide Area Network, is the outside network that connects the home to the provider. The **ISP**, or Internet Service Provider, is the company that gives Internet access (like Vodafone)

So to get to internet, it's this way: 

**devices → home router → ISP/provider network → Internet**. 

The LAN ports usually belong to the internal switch, while the router connects the home LAN to the WAN. 

- LAN VS SUBNET: A LAN is the local network environment, while a subnet is the IP range used within it. In simple home networks, one LAN often uses one subnet, so they can seem the same.