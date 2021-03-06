---

title: Self-configuration of a forwarding table in an access node
abstract: The present invention also relates to a method for self-configuring a forwarding table () in an access node ().
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08396010&OS=08396010&RS=08396010
owner: Alcatel Lucent
number: 08396010
owner_city: Paris
owner_country: FR
publication_date: 20091019
---
Local Area Networks LAN were originally made up of stations or hosts connected to each other via a shared transmission medium. Data are encapsulated into frames next frames are encoded into physical signals for transmission over the transmission medium possibly via multiple physical paths . One station at most can be transmitting at a given time while the other stations are listening. Each station is provided with Medium Access Control MAC and in particular with signal collision detection frame delineation unicast or multicast addressing and protection against signal corruption.

A repeater or hub is a device used to interconnect segments of a transmission medium thereby extending the range of a LAN when its physical specifications would otherwise be exceeded.

A bridge or switch is a device used to interconnect two or more LANs. A bridged LAN can provide for the following 

An example of a bridged LAN with different MAC types and network topology is given in 6.3.2.6 of the document entitled ref. 802 published by the Institute of Electrical and Electronics Engineers IEEE on Mar. 8 2002.

The Request For Comment RFC entitled ref. 826 published in November 1982 by the Internet Engineering Task Force IETF discloses a method that allows stations exchanging data over a LAN or a bridged LAN to learn each other s hardware or physical address such as a MAC address based on their network or logical address such as an IP address. An hardware address uniquely identifies a particular destination or a particular source over a LAN or a bridged LAN. A sending station that wishes to send data to a particular target station which is assigned a particular network address broadcasts a request to resolve that particular network address into a hardware address. The station that is assigned that particular network address answers the request with its hardware address. The request further comprises the sending station s network and hardware addresses thereby allowing the listening stations to learn this association. Once each other s hardware addresses are known peer to peer communication is possible.

The present invention primarily relates to Metropolitan Area Networks MAN and further to access or aggregation networks that span a geographical area and provide users with an access towards network service providers and further towards application service providers for a wide variety of end user applications or services such as file transfer electronic mail web browsing voice and video communication multimedia applications database access transaction processing remote process control etc.

The present invention more specifically relates to an access node which is a network unit at the edge of the aggregation network that couples subscribers to the aggregation network and further to the core network. An example of an access node is a Digital Subscriber Line Access Multiplexer DSLAM an Optical Network Unit ONU a wireless base station etc.

In a Layer 2 L2 aggregation network such as an Ethernet MAN EMAN the access node accommodates or emulates a bridge. A bridge makes use of the self learning forwarding paradigm to forward traffic to the right destination the forwarding table is populated on the fly by decoding the source MAC addresses of incoming frames and by configuring these MAC addresses as being bound to or associated with the respective ports or interfaces being of physical or logical nature through which the incoming frames were received. The association is deleted after some ageing timer expires.

Upon receipt of an incoming frame the bridge determines the egress port by means of a table lookup with the destination MAC address of that frame. If no match is found meaning if the destination MAC address has not yet been learned as being bound to a particular port then the frame is either discarded or flooded towards all the egress ports depending on the configured policy.

For security issues downstream frames bound to an unknown hardware address are typically discarded in an access node meaning that no session setup is possible from the network if the subscriber s hardware address has not been learnt first from an upstream frame or if the subscriber s hardware address ages out and no upstream traffic has been received since.

Large ageing timers partially solve the problem. Another option is to configure a small ARP ageing timer on the edge router such that it periodically ARPs the subscriber devices the ARP reply will trigger the MAC address learning. However configurable ARP timers are generally not available and short timers causes too much broadcast traffic in large aggregation networks.

It is an object of the present invention to allow incoming connections to be established from the network side as well as to enhance the security standards while remaining as easy to configure as the self learning forwarding paradigm is.

The objectives of the present invention are achieved and the aforementioned shortcomings of the prior art are overcome by an access node comprising 

Examples of auto configuration messages are Dynamic Host configuration Protocol DHCP messages and an example of an auto configuration server is a DHCP server.

By synchronizing the bounding of a particular hardware address to a particular subscriber port with the lease of a particular network address to the corresponding subscriber device holding that particular hardware address and coupled to that particular port and by making sure that such a bounding is in force throughout the course of the lease one prevents ageing out an hardware addresses while the corresponding subscriber is still logically attached to the network thereby allowing incoming connections from the network to be established at whatever time e.g. for remote management of the subscriber device.

A further embodiment of an access node according to the invention is characterized in that said forwarding configuration means is further adapted to pause respectively to resume a particular ageing timer related to said particular forwarding entry upon the assignment respectively the release of said particular network address to said particular subscriber device.

This embodiment is particularly advantageous as it comes on top of the self learning forwarding paradigm. The very first message exchanged between the auto configuration server and the subscriber device causes a new forwarding entry to be added into the forwarding table and a corresponding ageing timer to be started. Upon assignment of a network address to that subscriber device the ageing timer is frozen. Upon release of that network address being the expiry of the lease timer or an explicit release from either the subscriber device or the auto configuration server the ageing timer resumes. The forwarding entry is removed from the forwarding table when the ageing timer expires.

An alternative embodiment of an access node according to the invention is characterized in that said forwarding configuration means is further adapted to add respectively to delete said particular forwarding entry upon the assignment respectively the release of said particular network address to said particular subscriber device.

Once a network address is validly assigned to a subscriber a forwarding entry is added for the corresponding hardware address and traffic from to that subscriber starts flowing through the bridge. Once the network address is released the corresponding forwarding entry is removed causing any traffic except DHCP traffic to be discarded DHCP traffic is typically forwarded by means of DHCP contextual information . In this embodiment the self learning paradigm is superseded by the addition and removal of quasi static forwarding entries or semi permanent forwarding entries i.e. that do not age out during the lease time in synchronization with respectively the assignment and the release of network addresses.

The present invention also relates to a method for configuring a forwarding table of an access node and comprising the steps of 

Embodiments of a method according to the invention correspond with the embodiments of an access node according to the invention.

It is to be noticed that the term comprising also used in the claims should not be interpreted as being restricted to the means listed thereafter. Thus the scope of the expression a device comprising means A and B should not be limited to devices consisting only of components A and B. It means that with respect to the present invention the relevant components of the device are A and B.

Finally it is to be noticed that the term coupled also used in the claims should not be interpreted as being restricted to direct connections only. Thus the scope of the expression a device A coupled to a device B should not be limited to devices or systems wherein an output of device A is directly connected to an input of device B and or vice versa. It means that there exists a path between an output of A and an input of B and or vice versa which may be a path including other devices or means.

There is seen in a data communication system comprising a subscriber device CPE an access node an Ethernet based aggregation network EMAN a DHCP server an edge router and the Internet .

The subscriber device is coupled to the access node . The access node the DHCP server the edge router are coupled to the aggregation network . The edge router is further coupled to the Internet .

The DHCP server is adapted to allocate network addresses and to deliver configuration parameters to dynamically configured client hosts. The DHCP server assigns an IP address to a client for a limited period of time or until the client explicitly relinquishes the address . Dynamic allocation allows automatic reuse of an address that is no longer needed by the client to which it was assigned. Thus dynamic allocation is particularly useful for assigning an address to a client that will be connected to the network only temporarily or for sharing a limited pool of IP addresses among a group of clients that do not need permanent IP addresses.

There is seen in an access node according to the invention comprising the following functional blocks 

The Ethernet switch is coupled to the subscriber ports to to the network ports and to the forwarding configuration unit and to the DHCP relay agent . The forwarding configuration unit is further coupled to the DHCP relay agent .

The Ethernet switch is adapted to switch any incoming Ethernet frame from any ingress port towards any egress port. Upon receipt of a new incoming frame the Ethernet switch determines the egress port by means of a table lookup with the destination MAC address of that frame. If no match is found then the frame is discarded downstream or flooded upstream .

The Ethernet switch is further adapted to trigger see new incoming frame S port id message the forwarding configuration unit whenever a new incoming Ethernet frame has a source MAC address that is not associated yet with the ingress port that is to say the port through which the frame has been received . The trigger includes both the source MAC addresses S and a logical identifier of the ingress port port id .

The Ethernet switch is further adapted to redirect DHCP traffic towards the DHCP relay agent for further handling through e.g. an Application Programming Interface API . Once the captured DHCP traffic is processed according to the invention it is returned to the Ethernet switch for further forwarding possibly through a specified egress port.

The forwarding table maintains one to one relationships between learned source MAC addresses and respective port identifiers.

The forwarding configuration unit is adapted to configure the forwarding table based on the triggers received from both the Ethernet switch and the DHCP relay agent .

More specifically the forwarding configuration unit either writes a new forwarding entry see add entry S port id message between the forwarding configuration unit and the Ethernet switch associating a particular source MAC address S with a particular port identifier port id or delete an existing forwarding entry see delete entry S port id message or update an existing forwarding entry see update entry S port id message by re associating a learned MAC address to another port identifier.

The forwarding configuration unit is further adapted to start an ageing timer whenever a new entry is added or an existing entry is updated and to delete the corresponding association once this timer expires.

The forwarding configuration unit is further adapted to pause respectively to resume the ageing timer corresponding to a particular forwarding entry which associates a particular hardware address with a particular port identifier in synchronization with the assignment respectively the release of a network address to the particular subscriber device that holds that particular hardware address and that is coupled to that particular port. The synchronization triggers are issued by the DHCP relay agent .

The DHCP relay agent is adapted to relay any DHCP message from a client device towards the DHCP server and vice versa see DHCP traffic in . The DHCP relay agent implements a BOOTP relay agent as described in RFC 951 entitled BOOTSTRAP PROTOCOL BOOTP published in September 1985 by the IETF.

The DHCP relay agent is further adapted to trigger the forwarding configuration unit upon capture of a DHCPACK message whereby a particular subscriber device is validly assigned an IP address see IP  assignment S message wherein S denotes the MAC address of the corresponding subscriber device as read from chaddr field in DHCPACK message .

The DHCP relay agent is further adapted to start a timer the value of which matches the IP lease time as encoded in the DHCP option field of DHCPACK message. Upon timer expiry the DHCP relay agent informs the forwarding configuration unit about the release of the corresponding IP address see IP  release S message . So does the DHCP relay agent upon capture of a DHCPRELEASE message whereby a subscriber device releases its previously assigned IP address or upon capture of a DHCPFORCERENEW message whereby the DHCP server forces a subscriber device to release its previously assigned IP address.

An operation of this embodiment follows with reference to the subscriber device which is assumed to be coupled to the subscriber port of the access node

Initially the subscriber device more specifically a DHCP client housed by the subscriber device initiates a DHCP session to obtain network configuration parameters from a DHCP server. The network configuration parameters includes an IP address primary and secondary Domain Name Server s DNS IP addresses a gateway s IP address a subnet mask etc.

The DHCP session is initiated by broadcasting a DHCPDISCOVER message presently DHCPDISCOVER with the MAC address of the subscriber device as source MAC address presently MAC and with the broadcast MAC address FF FF FF FF FF FF as destination MAC address.

The Ethernet switch identifies DHCPDISCOVER message as a DHCP message e.g. by examination of UDP client server port number and thus delivers DHCPDISCOVER message to the DHCP relay agent .

The DHCP relay agent writes its one IP address into giaddr field of DHCPDISCOVER message and requests the Ethernet switch to forward DHCPDISCOVER message through a specified network port towards the DHCP server .

Concurrently the Ethernet switch triggers the forwarding configuration unit as the source MAC address of DHCPDISCOVER message presently MAC address MAC is not yet associated with the port through which DHCPDISCOVER message has been received presently the subscriber port .

The forwarding configuration unit writes a new forwarding entry in the forwarding table whereby MAC address MAC is bound to port see add entry S port id with presently S MAC and port id 11 and starts a new ageing timer T1.

The DHCP session goes on by exchanging further DHCP messages DHCPOFFER DHCPREQUEST not shown and terminates with the DHCP server returning a DHCPACK message presently DHCPACK to the DHCP client. DHCPACK message contains an IP address IP assigned to the subscriber device as well as an IP lease time and is received by the access node through the network port.

The Ethernet switch delivers DHCPACK message to the DHCP relay agent . The DHCP relay agent reads IP and MAC from ciaddr and chaddr fields of DHCPACK message respectively and notifies the forwarding configuration unit about the network address assignment see IP  assignment S message with presently S MAC .

Concurrently the DHCP relay agent starts a lease timer T2 the value of which matches the value as read from the DHCP option field lease time of DHCPACK message.

Thereupon the forwarding configuration unit identifies the ageing timer T1 as being running for the forwarding entry related to MAC and pauses this timer.

Eventually the DHCP relay agent substitutes the MAC address of the subscriber device for the destination MAC address and requests the Ethernet switch to forward DHCPACK message towards the subscriber device .

upon expiry of timer T2 or upon receipt of either DHCPFORCERENEW or DHCPRELEASE message from the DHCP server or the subscriber device respectively the DHCP relay agent notifies the forwarding configuration unit about the IP address release see IP  release S message with presently S MAC .

Thereupon the forwarding configuration unit identifies the ageing timer T1 as being paused for the forwarding entry related to MAC and resumes this timer. Upon expiry of timer T1 the forwarding entry related to MAC ages out and is removed from the forwarding table see delete entry S port id with presently S MAC and port id 11 .

Alternatively the forwarding configuration unit may stop the ageing timer T1 upon IP address assignment and starts a new ageing timer T1 upon IP address release. Upon expiry of timer T1 the forwarding entry related to MAC is removed from the forwarding table. This embodiment is rather advantageous in that no timer context need to be maintained.

Still alternatively a DHCP snooper function may substitute for the DHCP relay agent . The DHCP snooper only gets a duplicate of the DHCP messages exchanged between the DHCP server and the subscriber devices. The duplicates are not returned to the Ethernet switch for further forwarding.

There is seen in an alternative embodiment of an access node according to the invention wherein the forwarding configuration unit does not implement the self learning forwarding paradigm at least for the subscriber ports and only relies on IP address assignment and release messages from the DHCP relay agent for adding or deleting quasi static forwarding entries to the forwarding table . The lease timer T2 is still started upon receipt of a DHCPACK message and the forwarding entry is removed upon expiry of this timer or upon release of the IP address by the DHCP server or the DHCP client.

A final remark is that embodiments of the present invention are described above in terms of functional blocks. From the functional description of these blocks given above it will be apparent for a person skilled in the art of designing electronic devices how embodiments of these blocks can be manufactured with well known electronic components. A detailed architecture of the contents of the functional blocks hence is not given.

While the principles of the invention have been described above in connection with specific apparatus it is to be clearly understood that this description is made only by way of example and not as a limitation on the scope of the invention as defined in the appended claims.

