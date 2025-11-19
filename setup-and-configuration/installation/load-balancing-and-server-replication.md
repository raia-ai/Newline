---
title: "Load Balancing And Server Replication"
source: "Load Balancing and Server Replication.doc"
tags: [Setup and Installation]
version: "1.0"
last_updated: "2025-11-17"
short_description: "Load Balancing and Server Replication"
long_description: "Load Balancing and Server Replication."
---


Load Balancing and Server Replication.


What do we mean by load balancing and server replication?

Servers by definition provide services to your computer network. It may be
possible that more than one server on any network can be configured to
provide the same service, such as DHCP or DNS.  Most of our existing single
terminal server setups are configured with Active Directory, DHCP, DNS,
File Servers, Terminal Services and Terminal Service Licenses. These
services are required for our current server setup. In the event of failure
to our single server we would have a disaster on our hands. To get around
this we can configure multiple servers to provide these services. This is
known as load balancing.

Server replication is different as it is the process of copying data from
one server to another server. Your first priority on what data needs to be
replicated is NLData and Mysql data. This can data can be replicated behind
the scenes as data is amended. There are two different services that can
provide this functionality FRS or File Replication Services and DFS
Replication or Distributed File System Replication. FRS is a service which
replicates data from one server to another server (Or multiple other
servers.) FRS would be used primarily on any server running Windows Server
prior to Windows 2003 R2. Whilst the technology works well it has one
performance flaw whereby if you make a single word change to a 10MB file
FRS will replicate the whole 10MB file to the other server/servers, this
data is compressed but it is still a significant amount of data for such a
small change. Since the release of Windows 2003 R2 FRS has been replaced by
DFS Replication, this replicates data between 2 or more servers but only
replicates the data that has changed. It also provides a much user-friendly
 configuration page.

In addition to our newline data we also need to consider our active
directory data as this contains users and there attributes, DNS, group
policy and Server Services configuration. This is done behind the scene to
all domain controllers. To allow for this we need to make all backup
servers domain controllers. If we didn’t do this when a user goes to login
to the backup server in the event of failure to the primary server
potentially none of the users would not be able to logon (I say potentially
as they might be able to with cached credentials but this is not something
you would want to put to chance.)


Why and what do we need to configure Network Load Balancing?

As Mentioned above our servers provide multiple services below is a simple
scenario of one of our current single server networks. Listed on the left
is a list of services that the server provides to the network.

[pic]



Imagine the server failed midway through the sale all network objects were
connected to the server at the time and all had received IP addresses at
9am that morning. Based on this type of failure DHCP should not be a
problem as the network objects would have received IP address that morning
and would not need to renew them for as long as the DHCP lease (Usually 8
days depending on the configuration.) However the rest of the services will
obviously fail as they are all run from that one server. This would leave
the users without a server to dial into and would also leave them without
DNS which would mean changes would have to be made for the users to easily
access the internet.

Imagine now we have the same server failure but with the following network
layout.

[pic]

With this sort of network layout we will be able to configure both servers
to offer all the services the main server is providing. I will go through
each of these services and try to explain why we need them on both servers
and how best to configure them, at this point I will not discuss what
issues this could cause us. That will be covered later in the guide.


DHCP

DHCP as you are likely aware configures network adapters with the settings
needed for the network object to function on the network. You can have more
than one DHCP server on any network providing they are configured to allow
for each other and they are both set to give out the same settings (If
required). A DHCP server can give IP addresses from a pool of addresses we
assign when we set them up. What I mean by allowing for each other is to
not allow DHCP servers to have over-lapping pools else it would be possible
for two machines to get given the same IP address by two different DHCP
servers. I would suggest what we do here is the first server we assign a
pool of 198.162.10.1 – 198.162.10.99 and the second to have a pool of
198.162.10.100 – 198.162.10.199, I will demonstrate how this actually works
in DHCP.

Most DHCP Servers will be set to provide the IP address, Subnet Mask,
Default Gateway and DNS server.  In the event of server failures any
disconnected device that was powered on and connected after the first
server failure the clients would only receive an IP address if a second
DHCP Server was configured and available on the network.





Below is a list of network settings retrieved from a DHCP Server

Wireless LAN adapter Wireless Network Connection:

 Connection-specific DNS Suffix  . :    newlineasp.local
 Description . . . . . . . . . . . :         Atheros AR5007EG Wireless
Network Adapter
 Physical Address. . . . . . . . . :          00-21-63-15-14-0A
DHCP Enabled. . . . . . . . . . . :          Yes
 Autoconfiguration Enabled . . . . :    Yes
IPv4 Address. . . . . . . . . . . :          198.162.10.112
Subnet Mask . . . . . . . . . . . :          255.255.255.0
Lease Obtained. . . . . . . . . . :          26 November 2008 09:38:05
Lease Expires . . . . . . . . . . :          04 December 2008 09:38:05
Default Gateway . . . . . . . . . :          198.162.10.19
DHCP Server . . . . . . . . . . . :          198.162.10.69
DNS Servers . . . . . . . . . . . :          198.162.10.69
NetBIOS over Tcpip. . . . . . . . :          Enabled

Providing the above settings were correct the client would be able to
access the internet through the Default Gateway and DNS requests would be
resolved through the IP address given out by the DHCP server (In this case
the IP address is 198.162.10.69) however in the event of server failure to
198.162.10.69 none of the machines on this DHCP scope would be able to
resolve names. To get around this we simply need to configure DNS on both
servers and have records for both servers within DHCP options. In our case
we would look like:

DNS Servers . . . . . . . . . . . :          198.162.10.69
                             198.162.10.68

In the event of failure to 198.162.10.69 DNS queries would timeout and the
client would switch over to the next DNS server in the list in this case
198.162.10.68.


DNS













