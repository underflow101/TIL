# TIL 2020.11.06
---

### Port-Forwarding
- In computer networking, port forwarding or port mapping is an application of network address translation (NAT) that redirects a communication request from one address and port number combination to another while the packets are traversing a network gateway, such as a router or firewall. This technique is most commonly used to make services on a host residing on a protected or masqueraded (internal) network available to hosts on the opposite side of the gateway (external network), by remapping the destination IP address and port number of the communication to an internal host.

### Why do you need port-forwarding?
- You need port-forwarding when other people from different locations could reach to your private server.

### Things to be considered
- External port number and internal port number could be different
- You must designate IP address for port to be connected internally
- One port could only be forwarded to one IP address
- You can only forward port to IP address that router has designated