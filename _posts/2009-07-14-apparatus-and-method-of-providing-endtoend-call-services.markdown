---

title: Apparatus and method of providing end-to-end call services
abstract: An apparatus and a method are provided. The provided solution includes an apparatus including a transceiver to be in wireless connection with one or more sets of user equipment and a controller configured to connect to the Internet, set up a virtual point-to-point connection to a second apparatus, set up and provide end-to-end call services using the virtual point-to-point connection between user equipment which are connected to and served by the apparatuses.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09319865&OS=09319865&RS=09319865
owner: Nokia Solutions and Networks Oy
number: 09319865
owner_city: Espoo
owner_country: FI
publication_date: 20090714
---
The embodiments of the invention relate generally to communication networks and more particularly to an apparatus and a method in communication networks.

Communication systems have been under extensive development in recent years. Several new services have been developed. Different data and multimedia services are attractive to users and communication systems should provide a sufficient quality of service.

The popularity of Internet based services has increased. One of such services is Internet based voice calls Voice over IP where a speech or video phone call is realized with an Internet Protocol IP connection between personal computers.

The developed wireless communicating systems are utilizing IP based connections and provide browsing and other IP based services to customers. The users expect to have similar service using wireless user equipment as personal computers.

The following presents a simplified summary of the invention in order to provide a basic understanding of some aspects of the invention. This summary is not an extensive overview of the invention. It is not intended to identify key critical elements of the invention or to delineate the scope of the invention. Its sole purpose is to present some concepts of the invention in a simplified form as a prelude to a more detailed description that is presented later.

According to an aspect of the present invention there is provided an apparatus comprising a transceiver to be in wireless connection with one or more sets of user equipment a controller configured to connect to the Internet set up a virtual point to point connection to a second apparatus set up and provide end to end call services using the virtual point to point connection between user equipment which are connected to and served by the apparatuses.

The controller of the apparatus may be configured to set up a virtual point to point connection to the second apparatus utilizing an Internet Protocol tunneling mechanism within the network of an operator.

According to an aspect of the present invention there is provided an apparatus comprising a transceiver to be in wireless connection with a first network element a controller configured to control the transceiver to send a message to the first network element the message comprising a request to establish an end to end call service with a second apparatus utilizing a virtual point to point connection to a second network element to which the second apparatus is connected.

The controller of the apparatus may be configured to control the transmitter to receive from the first network element information on apparatuses currently connected to the first network element and the second network element.

According to another aspect of the present invention there is provided a method comprising maintaining a wireless connection between a first network element and one or more sets of user equipment connecting the first network element to the Internet setting up a point to point connection to a second network element setting up and providing end to end call services using the virtual point to point connection between user equipment which are connected to and served by the network elements.

According to another aspect of the present invention there is provided a method comprising maintaining a wireless connection with a first network element sending a message to the first network element the message comprising a request to establish an end to end call service to a second apparatus utilizing a virtual point to point connection to a second network element to which the second apparatus is connected.

According to another aspect of the present invention there is provided a system comprising one or more sets of user equipment one or more apparatuses configured to be in wireless connection with one or more sets of user equipment and to connect to the Internet set up a virtual point to point connection to another apparatus set up and provide end to end call services using the virtual point to point connection between user equipment which are connected to and served by the apparatuses.

According to another aspect of the present invention there is provided a computer program comprising program code means adapted to perform the methods discussed above.

According to another aspect of the present invention there is provided an article of manufacture comprising a computer readable medium and embodying program instructions thereon executable by a computer operably coupled to a memory which when executed by the computer perform methods discussed above.

According to another aspect of the present invention there is provided an apparatus comprising means for being in wireless connection with one or more sets of user equipment means for connecting to the Internet means for setting up a virtual point to point connection to a second apparatus and means for setting up and providing end to end call services using the virtual point to point connection between user equipment which are connected to and served by the apparatuses.

According to another aspect of the present invention there is provided an apparatus comprising means for being in wireless connection with a first network element and means for sending a message to the first network element the message comprising a request to establish an end to end call service to a second apparatus utilizing a virtual point to point connection to a second network element to which the second apparatus is connected.

Although the various aspects embodiments and features of the invention are recited independently it should be appreciated that all combinations of the various aspects embodiments and features of the invention are possible and within the scope of the present invention as claimed.

Exemplary embodiments of the present invention will now be de scribed more fully hereinafter with reference to the accompanying drawings in which some but not all embodiments of the invention are shown. Indeed the invention may be embodied in many different forms and should not be construed as limited to the embodiments set forth herein rather these embodiments are provided so that this disclosure will satisfy applicable legal requirements. Although the specification may refer to an one or some embodiment s in several locations this does not necessarily mean that each such reference is to the same embodiment s or that the feature only applies to a single embodiment. Single features of different embodiments may also be combined to provide other embodiments. Like reference numerals refer to like elements throughout.

Embodiments are applicable to any base station user equipment server corresponding component and or to any communication system or any combination of different communication systems that support required functionalities.

The protocols used the specifications of communication systems servers and user terminals especially in wireless communication develop rapidly. Such development may require extra changes to an embodiment. Therefore all words and expressions should be interpreted broadly and they are intended to illustrate not to restrict the embodiments.

Modern communications systems under development provide a possibility to install local area LA base stations in the network. These base stations may be installed within buildings to provide additional coverage and capacity in homes and offices. These base stations may utilize so called plug and play operation with a self organizing network SON and flexible spectrum use FSU techniques.

Main targets of these techniques are to minimize the need for network configuration and enable new types of communications networks such as decentralized ad hoc networks. The techniques enable self tuning and reconfiguration of network parameters of the LA base stations. In addition the techniques provide some solutions for utilizing and sharing spectrum resources among communication systems of the same or different operators serving in an overlapping or even common spectrum and or geographical area.

In the following different embodiments will be described using as an example of a system architecture whereto the embodiments may be applied an architecture based on Evolved UMTS Terrestrial Radio Access E UTRA UMTS Universal Mobile Telecommunications System without restricting the embodiment to such an architecture however.

Many different radio protocols to be used in communications systems exist. Some examples of different communication systems are the universal mobile telecommunications system UMTS radio access network UTRAN or E UTRAN long term evolution LTE also known as E UTRA long term evolution advanced LTE A Wireless Local Area Network WLAN worldwide interoperability for microwave access WiMAX Bluetooth personal communications services PCS and systems using ultra wideband UWB technology.

In an E UTRA network the base stations may be called Enhanced Node Bs eNB . These base stations may be called Wide Area WA base stations.

In the E UTRA network the local area LA base stations may be called home node Bs HNB or local node Bs LNB . A home node B may be a wireless access point that may be purchased and or installed by a private user for example in the user s home.

In the example of the radio system is based on LTE SAE Long Term Evolution System Architecture Evolution network elements. However the invention described in these examples is not limited to the LTE SAE radio systems but can also be implemented in other radio systems such as HSDPA high speed downlink packet access HSUPA high speed uplink packet access or in other suitable radio systems.

The exemplary radio system of comprises a service core of an operator including the following elements a service management IMS IP multimedia subsystem a MME Mobility Management Entity and a SAE GW SAE Gateway .

Traffic between mobile terminals and the service core network is carried out via a national IP backbone network a regional transport network and a local area aggregation network . eNBs Enhanced node Bs to of the radio system host the functions for Radio Resource Management Radio Bearer Control Radio Admission Control Connection Mobility Control Dynamic Resource Allocation scheduling . The MME is responsible for distributing paging messages to the eNBs to .

The example of comprises a local area base station HNB forming a cell . The HNB may be privately purchased and owned. The owner of the HNB may form a user group of the UEs which are allowed to access the HNB. Such a group may be called a closed subscriber group CSG. Typically only the members of the CSG of a HNB are allowed to contact the HNB. In an embodiment more than one HNB form a CSG Network. For example one home may be covered by more than one HNB sharing the same CSG.

Current radio networks are based on a single switch model. This is implemented in the LTE SAE network by the SAE GW SAE Gateway . All calls are long distance because the user traffic is forced to pass via the SAE GW . For example a connection from a mobile terminal connected to the eNodeB to an external IP network such as to the Internet is typically guided via a route indicated with a dashed line . Likewise a speech call from the mobile terminal to another mobile terminal of the system is routed through the SAE GW .

Recently cellular operators have started to offer local IP Internet Protocol connectivity within a certain area local IP breakout . The user equipment may connect to the Internet using a local gateway via a eNodeB instead of the SAE GW . Thus all data is not required to traverse via the centralized SAE GW . The local gateway may be implemented as a separate IP Gateway server or access router .

In an embodiment the server functionality is implemented in the eNodeB. For example a HNB may be implemented to connect to the Internet through a high speed DSL Internet connection available in the location of the HNB. Thus the user equipment may connect to the Internet through the HNB which acts as a gateway to the Internet.

Conventional phone call between the CGS networks is a long distance call. A conventional Voice over IP call via Internet are realized by 3party software and they do not use wireless cellular access. Therefore many Voice over IP implementations are not supported by the cellular operators.

In the regular cellular access end to end call operation an eNodeB or an HNB provides a radio access link to user equipment and an end to end call between two UEs is set up through one or more operators networks which are interconnected via transport networks such as the Internet or public telephone networks etc. In this operation the eNodeB or HNB is not visible on a transport layer for end to end data forwarding between the UEs. That is point to point or peer to peer transport between the eNBs or HNBs which provide radio links to the UEs is not applied.

In an embodiment virtual IP connectivity between the CGS networks is created. The connectivity creates a tunneled connection through cellular operator s s network s and or the Internet between the CGS networks. The connection may be called a Virtual Breakout VBO connection. The VBO may be realized for example by utilizing an Internet Protocol tunneling mechanism within the network of an operator or between the networks of more than one operator. In an embodiment the VBO is realized by utilizing an IP connectivity service control mechanism such as registering at a common server and advertising about reachability over the Internet. The server may belong to a 3party.

In an embodiment the common server may identify requesting acquainted HNBs and distribute keys and configurations to them to set up a secure VBO connection.

In an embodiment a first HNB may register itself to a 3rd party server and check whether an acquainted HNB is also on line. Then the first HNB may select and connect to the acquainted HNB via the 3rd party server.

As a result of the VBO the HNBs and UEs of the CGS networks are aware of each other s on line reachability and end to end connections between devices of different CGS networks can be fast and easily set up and utilized.

The UE of a CGS network may utilize the VBO connectivity and request a Voice over IP call to a UE camped on the other CGS Network .

In an embodiment the VBO connection of the HNBs is targeted to IP call services. Other Internet connections of the user equipment connected to an HNB are not utilizing the VBO connections. When the user equipment wishes to utilize Internet services it is required to connect to Internet before accessing the services. However when user equipment wishes to place a call utilizing the VBO there is no need to set up an Internet connection. The user equipment may merely send a call set up request to the HNB over the air interface using a normal call set up control channels.

In an embodiment the network element comprises a second controller for acting as a gateway between the network element and the Internet. The second controller may be connected to the controller and to the interface . In an embodiment the tasks of the second controller are performed by the controller . In another embodiment the network element is connected to the Internet via a separate gateway.

In step of a first network element maintains a connection with one or more sets of user equipment. The network element may be an HNB serving a femto cell in a cellular system. The connection may be maintained by the transceiver . In an embodiment the network element is configured to assign or map an identifier to the user equipment allowed to be in wireless connection with the apparatus. The identifier may be a customized nickname or user ID that may be used in end to end calls instead of regular phone numbers. In an embodiment the identifier is generated by the UE which registers the identifier to the HNB.

In step the first network element is connected to the Internet. An HNB may comprise software instructing the controller of the HNB to connect the HNB to the Internet automatically when powered up. Alternatively the HNB may be commanded to connect to the Internet by the user or owner of the device. The connection may be established through a local gateway or the HNB itself may be configured to act as a gateway under control of the home domain operator s network. The UEs using the network element or HNB form a closed subscriber group. In an embodiment the HNB and femto cell of the HNB are a part of the operator s cellular system. Thus the HNB activation or power up and cell configuration is controlled by the network.

In step a virtual point to point or peer to peer P2P connection to a second network element is established. The HNBs of acquainted closed subscriber groups may comprise software instructing the controller of the HNBs to connect the HNBs to each other when reactivated and connected to the Internet. In other words a secure virtual P2P connection may be established between such HNBs either manually at a certain point in time or semi autonomously whenever the HNBs are reactivated and visible reachable on line.

In step end to end call services between the sets of user equipment which are connected to and served by the apparatuses using the virtual P2P connection are set up and maintained utilizing the virtual P2P connection.

In step information on user equipment allowed to be in wireless connection with the network element and on user equipment currently connected to the network element is maintained in a memory in the HNB. The information may comprise the identifier nickname or used ID assigned to each set of the user equipment. The HNB keeps a list of the user equipment belonging to the closed subscriber groups of the HNB. In addition the HNB naturally keeps track of user equipment currently connected to the HNB. The connection may be either idle or active. In active mode the user equipment is communicating on a traffic channel. In idle mode there is a control channel connection between the user equipment and the network element.

In step information on user equipment allowed to be in wireless connection with the network element and on user equipment currently connected to the network element is transmitted to the second network element or the HNB.

In step information on user equipment allowed to be in wireless connection with the second HNB and on user equipment currently connected to the second HNB is received from the second HNB. The HNB may store this information.

In step the received information is sent to the user equipment connected to the network element. The information may comprise the identifiers of the user equipment connected to other HNBs. The information may be sent to the user equipment using common control signaling via a broadcast channel or using dedicated signaling. The HNB may page the user equipment camping on the cell for initiating the information transfer.

In step the first network element is connected to the Internet. In addition the network element contacts a server in the Internet. The server may be a 3party server i.e. it may be maintained by a party not related to the cellular operator. The server is configured to establish and assist in maintaining a virtual P2P connection between network elements of cellular operators.

In step the network element authenticates and registers itself at the server. The authentication may be performed using methods known in the art. To set up a secure P2P connection the server must be sure of that the participating network elements are valid participants. By registering itself at the server the network element enables another network element to detect that the network element is online and may be reached. The second network element authenticates and registers itself as well.

After authentication and registration the network element may check whether other network elements are online. The first network element may detect that the second network element with which it is configured to set up a connection is online. In such a case the process may continue.

In step the network element receives virtual private network VPN encryption keys from the server. In an embodiment the virtual P2P connection between the network elements is realized as a secure VPN connection. The connection may be established using encryption requiring keys.

In step the encrypted connection between the network elements via the server is established. The virtual end to end connection between the network elements may be realized in many ways as one skilled in the art is well aware. The above method is merely an example.

In step a first HNB receives a message from user equipment wirelessly connected to the HNB the message comprising a request to set up an end to end call to user equipment connected to a second HNB. The first HNB has a virtual end to end connection to the second HNB. The message comprises a request to establish the call using the virtual P2P connection between the HNBs. The message may comprise the identification nickname or user ID of the user equipment to which the connection is to be established.

In step the first HNB determines the target HNB on the basis of the identification information. This step may be required if the first HNB has virtual P2P connections with several HNBs. The first HNB may determine the 3party server which is used in the realization of the P2P connection.

In step the first HNB sends an end to end IP call set up request to the second HNB. The second HNB may page the target user equipment to establish the radio connection needed for the call.

If the reply was negative the first HNB informs the user equipment that requested the connection information that the connection failed. A negative reply occurs if the target user equipment refuses the call for example.

Thus a new mode of service network access points referred to as VBO mode is introduced to enable user equipment which are camping on or connected to HNBs having a P2P connection between them to utilize the P2P connection for calling each other. In other words HNBs and UEs are facilitated with necessary access stratum and non access stratum functions including application programming interfaces API and IP call server controller functionality to support the VBO mode.

The virtual P2Pd connection between the HSB and the HSB is set up utilizing the server . The closed subscriber group information CSG INFO of the HNBs is updated between the HNBs. The information may comprise data on the UEs belonging to the CSG of each HNB and data on the currently camped UEs. In this case only the UE is camping on the HNB.

The HNB sends an update of the closed subscriber group information to the UE. In addition the HNB informs the UE about availability of the P2P connection to the HNB and the VBO mode support.

Thus the UE becomes visible to the UE. The UE is aware that the UE is camping on the HNB with which the HNB has a virtual P2P connection.

The UE transmits a call set up request to the HNB the request indicating the identification of the UE and information that the call should utilize the P2P connection between the HNB and the HNB that is using the VBO mode.

The connection for the call between the HNBs is established and finally the end to end call between the user equipment via the virtual P2P connection between the HNBs is established .

It should be understood that the apparatuses of are depicted herein as an example illustrating some embodiments. It is apparent to a person skilled in the art that the apparatuses may also comprise other functions and or structures. Although the apparatuses are depicted as single entities different modules and memory may be implemented in one or more physical or logical entities.

An apparatus may be any server node host or corresponding component providing a required functionality. The apparatus may also be a user device which is a piece of equipment or a device that associates or is arranged to associate the user device and its user with a subscription and allows a user to interact with a communications system. The user device presents information to the user and allows the user to input information. In other words the user device may be any terminal capable of receiving information from and or transmitting information to the network connectable to the network wirelessly or via a fixed connection. Examples of the user devices include a personal computer game console laptop notebook personal digital assistant PDA pager mobile television mobile station and line telephone.

The apparatuses of may be implemented as an electronic digital computer which may comprise a working memory RAM a central processing unit CPU and a system clock. The CPU may comprise a set of registers an arithmetic logic unit and a control unit. The control unit is controlled by a sequence of program instructions transferred to the CPU from the RAM. The control unit may contain a number of microinstructions for basic operations. The implementation of microinstructions may vary depending on the CPU design. The program instructions may be coded by a programming language which may be a high level programming language such as C Java etc. or a low level programming language such as a machine language or an assembler. The electronic digital computer may also have an operating system which may provide system services to a computer program written with the program instructions.

The apparatuses of may be implemented using at least one chipset or integrated circuit such as ASICs application specific integrated circuit .

Embodiments of the invention may be implemented as computer software executable by a processor or as a combination of software and hardware.

An embodiment provides a computer program embodied on a distribution medium comprising program instructions which when loaded into an electronic apparatus perform the actions of the controller transmitter receiver and other units of the apparatuses described earlier.

The computer program may be in source code form object code form or in some intermediate form and it may be stored in some sort of carrier which may be any entity or device capable of carrying the program. Such carriers include a record medium computer memory read only memory and software distribution package for example. Depending on the processing power needed the computer program may be executed in a single electronic digital computer or it may be distributed amongst a number of computers.

The steps signaling messages and related functions described above are in no absolute chronological order and some of the steps may be performed simultaneously or in an order differing from the given one. Other functions can also be executed between the steps or within the steps and other signaling messages sent between the illustrated messages. Some of the steps or part of the steps can also be left out or replaced by a corresponding step or part of the step.

It will be obvious to a person skilled in the art that as technology advances the inventive concept can be implemented in various ways. The invention and its embodiments are not limited to the examples described above but may vary within the scope of the claims.

