---

title: Commissioning incoming packet switched connections
abstract: A node () for communication within a communication system (), wherein the node () comprises a network signaling stack (), the node () is adapted for serving as a first radio access platform which supports incoming packet switched connections, the node () is adapted for interconnecting to a second radio access platform which supports outgoing packet switched connections, and the node () is adapted for commissioning of an incoming packet switched connection.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08711744&OS=08711744&RS=08711744
owner: Telefonaktiebolaget LM Ericsson
number: 08711744
owner_city: Stockholm
owner_country: SE
publication_date: 20090908
---
This application claims the benefit of the filing date of U.S. Provisional Patent Application No. 61 101 209 filed Sep. 30 2008 the disclosure of which is hereby incorporated herein by reference.

The invention relates to communication especially to a node for communication within a communication system a communication arrangement for communication within a communication system a method executed by a node which supports incoming packet switched connections a computer program adapted to perform such a method and a computer readable medium product comprising such a computer program.

Existing Universal Mobile Telecommunications System UMTS platforms already integrate several radio access technologies such as the so called General Packet Radio Service GPRS Enhanced Data rates for GSM Evolution EDGE Wideband Code Division Multiple Access WCDMA and Evolved HSPA eHSPA in one platform. Concerning packet switched services a UMTS mobile is independently of the current radio access technology RAT always connected to the same domain for packet services the GPRS core network packet domain. Thus the User Equipment UE always uses the same principles for Internet Protocol IP bearer connection management and allocation between the UE and the network.

The IP bearer connection management and allocation in the GPRS packet domain is based on Primary Packet Data Protocol PDP contexts and Secondary PDP contexts and comprises functions for activation deactivation and modification of them as being described in the specification document issued by the Generation Partnership Project named 3GPP TS 24.008 Mobile Radio Interface Layer 3 specification Core Network Protocols Stage 3 which is herewith included by reference thereby especially including the description of handling of Traffic Flow Templates TFTs and Quality of Service QoS profiles being specified per Secondary PDP contexts.

In existing mobile phone platforms the IP bearer connection management and allocation as specified by 3GPP for the GPRS packet domain is also the basis for the IP bearer connection management and allocation functionality provided towards applications.

This functionality might be provided through any application programming interface API . For internal applications this functionality may be provided through the OPA Open Platform API interface which is the name a mobile phone platform being developed by Telefonaktlebolaget L. M. Ericsson. Alternatively e.g. for external applications this functionality may be provided through the so called AT command interface as described in the document 3GPP TS 27.007 AT command set for User Equipment UE hereby incorporated by reference. To simplify the description in the following exemplarily only the AT command interface is considered which in addition is an interface that is not only used by Ericsson mobile phone platforms but probably by all wireless 3GPP based modems as it is part of the 3GPP standard.

Instead of using Primary PDP Contexts and Secondary PDP Contexts as in the GPRS packet domain the Evolved Packet System EPS which is the packed switched domain used for the so called Long Term Evolution LTE radio technology being specified by the above mentioned 3GPP defining Default Bearers Dedicated Bearers and Service Data Flows SDFs in the so called Non Access Stratum NAS protocol e.g. being specified in the documents 3GPP TS 23.401 GPRS Enhancements for E UTRAN access and 3GPP TS 24.301 Non Access Stratum NAS protocol for Evolved Packet System EPS Core Network Protocols Stage 3 . With regard to the SDFs it should be mentioned that meanwhile the standard defined a further term i.e. the Traffic Flow Aggregate refer to TS 23.401 e.g. section 4.7.1 and the figure in section 4.7.2.2.

An SDF is always based on a Bearer. This also holds for a Traffic Flow Aggregate. Whenever statements regarding the term SDF are made in this document such statements may also apply to the term Traffic Flow Aggregate. Several SDFs or Traffic Flow Aggregate with the same QoS may build an aggregated SDF or Traffic Flow Aggregate and may be mapped to the same Bearer. Contrary to the existing GPRS packet domain where the decision of how to map SDFs denoted as Traffic Flow Template in existing GPRS packet domains and secondary PDP Contexts is done in the UE in EPS the network decides how the mapping shall be done. This means an LTE Resource Allocation Request for an SDF or a Traffic Flow Aggregate issued by the application via NAS signaling can either return a new Dedicated Bearer with an SDF or a Traffic Flow Aggregate or return an already existing bearer with an additional SDF or Traffic Flow Aggregate. For the existing GPRS packet domain the corresponding Secondary PDP Context Activate Request always returns a new secondary PDP Context. In both latter cases a so called outgoing packet switched PS connection is issued.

An incoming PS connection is characterized by the fact that from the UE perspective no application has triggered the establishment of such a PS connection. The initiation is perceived as unsolicited. This type of PS connection is not supported by e.g. pre release 7 3 GPP networks or by other cellular network e.g. CDMA Code Division Multiple Access .

In case of an outgoing PS connection the application is the initiator e.g. in LTE when the application issues a BEARER RESOURCE ALLOCATION REQUEST in network signaling NS the network responds with an activation i.e. ACTIVATE DEDICATED EPS BEARER CONTEXT REQUEST or modification i.e. MODIFY EPS BEARER CONTEXT REQUEST of an EPS bearer.

In case of an incoming PS connection the ACTIVATE DEDICATED EPS BEARER CONTEXT REQUEST or MODIFY EPS BEARER CONTEXT REQUEST would be received by the UE without an explicit trigger by the application. In the latter case the modification of an existing EPS bearer may be sent to establish a new service flow.

There are may be several possibilities to implement the handling of incoming PS connections. One conventional concept is described in the following.

The incoming PS connection is commissioned by the connection manager as soon as the application initiates the connection setup.

An ACTIVATE DEDICATED EPS BEARER CONTEXT REQUEST is received by the LTE NS stack of the UE . LTE NS stack forwards a connection setup request to the connection manager which in turn may send an accept reply to the LTS NS stack . Next an ACTIVATE DEDICATED EPS BEARER CONTEXT ACCEPT is sent from the LTS NS stack to the network .

Application may send a connection setup request to the connection manager which in turn commissions the PS connection and may send back a response to the application .

Application sends a connection setup request to connection manager which forwards the connection setup request to LTE NS stack . LTE NS stack then sends a BEARER RESOURCE ALLOCATION REQUEST to the network responding in turn to the LTE NS stack with an ACTIVATE DEDICATED EPS BEARER CONTEXT REQUEST . Then a connection setup response is sent from the LTE NS stack to the connection manager which in turn sends a response to the application and an accept message to the LTE NS stack . An ACTIVATE DEDICATED EPS BEARER CONTEXT ACCEPT is then sent from the LTE NS stack to the network .

Hence the instance which manages the outgoing PS connections i.e. the connection manager has to handle also the incoming PS connection.

As shown in a problem with the conventional implementation depicted in and arises when two radio platforms e.g. the LTE platform which supports also the incoming PS connections is acting as modem and is connected to an existing legacy radio access platform e.g. WCDMA which only supports outgoing PS connections .

Hence and referring to in a conventional system application uses connection manager to trigger PS data connections into network. Triggered by application with the connection setup request the connection manager configures the network signaling NS stack with parameters for the Bearer like QoS TFT and protocol type. The NS stack uses the NAS protocol to signal this connection setup request towards the network . If a Resource Allocation was requested see message the network provides either a Dedicated EPS Bearer or modifies an existing EPS Bearer. This mechanism shown in is suitable for handling so called outgoing connections. Further messages in this context ACTIVATE DEDICATED EPS BEARER EVENT ACTIVATE DEDICATED EPS BEARER CONTEXT ACCEPT BEARER RESOURCE ALLOCATION RESPONSE and CONNECTION STATUS INFORMATION message are shown as well.

This concept works fine for e.g. existing legacy WCDMA radio access platforms where only this type of connections had to be supported. However it is no longer sufficient for future systems as PS data connections can also be triggered by the network 

The messages used in and are based on NAS signaling between NS stack and Network . All other communications are for illustration only but not based on any specific protocol.

It is an object of the invention to enable a flexible interconnection between different radio access platforms.

In order to achieve the object defined above a node for communication within a communication system a communication arrangement for communication within a communication system a method executed by a node which supports incoming packet switched connections a computer program adapted to perform such a method and a computer readable medium product comprising such computer programs according to the independent claims are provided.

According to an exemplary embodiment of the invention a node for communication within a communication system is provided. The node comprises a network signaling stack and is adapted for serving as a first radio access platform which supports incoming packet switched connections. The node is further adapted for interconnecting to a second radio access platform which in an embodiment may host the application which supports outgoing packet switched connections particularly supports only outgoing packet switched connections but in an embodiment does not support incoming packet switched connections and for commissioning incoming packet switched connections. The second radio access platform may be located on a further node.

According to another exemplary embodiment of the invention a communication arrangement for communication within a communication system is provided the communication arrangement comprising a node having the above mentioned features. The communication arrangement further comprises a further node adapted for performing connection management the further node being adapted for being interconnected to the first radio access platform which supports incoming packet switched connections and which commissions an incoming packet switched connection. The further node is also adapted for serving as the second radio access platform which supports particularly only outgoing packet switched connections.

According to yet another exemplary embodiment of the invention a method executed by a node comprising a network signaling stack and serving as a first radio access platform which supports incoming packet switched connections is provided. The node is adapted for interconnecting to a second radio access platform which supports particularly only outgoing packet switched connections. The method comprises commissioning of an incoming packet switched connection by the node.

According to still another exemplary embodiment of the invention a computer program is provided comprising code adapted to perform the step of the above method having the above mentioned features when loaded into a processing unit of a node.

According to yet another exemplary embodiment of the invention a computer readable medium product is provided which comprises at least one computer program having the above mentioned features.

Embodiments of the present invention also concern computer programs comprising portions of software codes in order to implement the method as described above when operated at a respective device. A computer program can be stored on a computer readable medium. A computer readable medium can be a permanent or rewritable memory within a respective device or located externally. A computer program can be also transferred to a respective device for example via a cable or a wireless link as a sequence of signals.

Data processing which may be performed according to embodiments of the invention can be realized by a computer program that is by software or by using one or more special electronic optimization circuits that is in hardware or in hybrid form that is by means of software components and hardware components.

The term node may particularly denote any communication device for instance a transmitter receiver device transceiver which allows for an exchange of communication messages with a communication partner over a communication system or network. Such a node may particularly be a wireless communication device i.e. a communication device which communicates without the necessity of wires. However wire based communication may be also possible. A node may have processing resources storage resources and message transmitting receiving resources.

The term network signaling stack may be denoted as a functional entity allowing the node to communicate with a communicatively connected network such as a telecommunications network. It may include a protocol stack such as a layered set of protocols which work together to provide a set of network functions.

The term radio access platform may particularly denote a platform scheme or entity allowing for a communication in accordance with a dedicated radio access technology for instance GPRS EDGE WCDMA eHSPA CDMA . Radio access technology may indicate a type of radio technology to access a core network. In the context of exemplary embodiments the first radio access platform may be different from the second radio access platform i.e. different radio access platforms may be combined in one communication arrangement.

The term packet switching may be denoted as a network communications method that groups all transmitted data irrespective of content type or structure and to suitably sized blocks called packets. A network over which packets are transmitted may be denoted as a shared network which routes each packet independently from all others and allocates transmission resources as needed. When traversing network adapters switches and other network nodes packets may be buffered and queued.

The term incoming packet switched connection may particularly denote that from a perspective of a user equipment no application has triggered the establishment of a packet switched connection. In other words a corresponding request can be received by the user equipment without an explicit trigger by the application i.e. from an external entity.

Accordingly the term outgoing packet switched connections may particularly denote that from a perspective of a user equipment an application is the initiator of the establishment of a packet switched connection.

The term commissioning may particularly denote managing a packet switched PS connection which may also include accomplishing and or accepting the establishment of such a PS connection from a network. In other words commissioning a PS connection may include handling the establishment of such a PS connection.

In order to overcome at least some of the above mentioned problems an embodiment of the present invention interconnects a radio access platform acting as modem and supporting incoming PS connections outgoing PS connections may or may not be supported by this radio access platform with another radio access platform that supports only outgoing PS connections but not incoming PS connections . In the context of this interconnection the radio access platform acting as modem and supporting incoming PS connections may commission incoming PS connections. According to embodiments of the invention a system is provided to perform a commission of the incoming PS connection not in the functional instance that performs the connection management which typically resides on the platform that hosts an application but to implement the commission of the incoming PS connections on the platform that supports the incoming PS connections e.g. a LTE modem. Such an embodiment may have the advantage of providing a common interface towards applications for IP bearer and management independent of an active RAT GPRS EDGE WCDMA HSPA LTE or other RATs . Furthermore it may enable the reuse e.g. for LTE of existing legacy applications that currently are working e.g. for pre release 7 WCDMA.

In the following further exemplary embodiments of the node will be explained. However these embodiments also apply to the communication arrangement to the method to the computer program and to the computer readable medium product.

In an embodiment the node serving as a first radio access platform which supports incoming packet switched connections may be free of hosting an application i.e. does not host an application. In contrast to this a further node serving as a second radio access platform which supports only outgoing packet switched connections may host such an application.

In an embodiment the first radio access platform may be a Long Term Evolution LTE platform. LTE is standardized in 3GPP. By providing the node compatible with LTE it is possible to operate this node in combination with another node lacking LTE capability but having for instance pre release 7 WCDMA capability so that such a WCDMA compatible node can be reused without changes.

According to an exemplary embodiment the second radio access platform may be a legacy platform. The term legacy platform in particularly denotes any NS stack or radio access technology platform that deploys outgoing packet switched connections only. Thus it can be considered as an already existing technology that continues to be used for instance because it still functions for users needs even though newer technology particularly LTE technology is available.

However the further node using the second radio access technology may support General Packet Radio Service GPRS Enhanced Data rates for Global Evolution EDGE High Speed Packet Access HSPA evolved High Speed Packet Access eHSPA etc. Also platforms related to applications provided by a personal computer may be such legacy applications.

In an embodiment the node may be adapted for completely commissioning of an incoming packet switched connection. In other words the node alone may include the entire functionality required for providing the commissioning of the incoming package switched connection. The node may serve as the controlling entity which provides other entities with commands with regard to the commissioning. Therefore in such an embodiment no further entity is required to provide capability or resources for such commissioning tasks. Thus all the commissioning services may be centered at the described node.

In an embodiment the node may be adapted for commissioning of an incoming packet switched connection s without simultaneously performing an association towards an application hosted by the second radio access platform. Performing an association towards an application may particularly denote taking an action which is related to commissioning of packet switched connection s and which involves the application in this procedure. In other words the application is not linked to any communication relating to the commissioning in an introductory phase. In a later phase the application may be involved in the communication. In an embodiment such an application may be located not at the node performing the commissioning but at a further node which may also comprise a connection manager. It may be possible to preserve incoming connections in the node particularly but not necessarily in a network signaling stack thereof until a request from the connection manager for this specific connection is received.

The node may further be adapted for performing an association towards an application hosted by the second radio access platform in response to a receipt of a connection setup request from the application. In other words although initiation of the commissioning does not require that the node involves a further node providing the application receipt of a connection setup request from the application may be a trigger for the node to respond to such a received message. When the connection manager of the further node has received such a response from the node it may confirm acceptance to the node and may send the response also to the application of the further node.

However still referring to the previously described embodiment the node may be adapted for performing the association in response to the receipt of the connection setup request only after a successful previous check of all known network connections. Such a check may determine whether requested connection parameters match to an existing network connection. Thus when a connection request is received the node may first check all known network connections i.e. EPS bearers whether the requested connection parameters for instance IP address port number quality of service etc. match to an existing network connection. If so it may link the application connection request to the corresponding modem network connection.

Still referring to the previously described embodiment the node may further be adapted for after a non successful check of all known network connections with regard to the question whether requested connection parameters match to an existing network connection requesting a new connection to a communicatively connected network and establishing an outgoing packet switched connection. Thus if the analysis yields the result that the requested connection parameters do not match to an existing network connection the modem may request a new connection for instance EPS bearer towards the network. An outgoing packet switching connection may be established in such a case.

The node may be adapted for acting as a modem. The term modem may be denoted as an entity used to modulate digital information so that it can be carried via an analog carrier. The signal may be then demodulated at a receiver end to extract the original digital data. The term modem originates from modulator and demodulator.

The node may be or may be part of a mobile communication device a portable communication device a mobile terminal a mobile phone a data card a Personal Digital Assistant a personal computer a laptop etc. The term mobile communication terminal may particularly denote any user equipment UE . Hence portable or stationary communication devices can be operated in accordance with the disclosed architecture of exemplary embodiments.

For instance the node may be implemented for use in the context of telecommunications particularly as a mobile phone or a part thereof.

Next further exemplary embodiments of the communication arrangement will be explained. However these embodiments also apply to the node to the method to the computer program and to the computer readable medium product.

The further node may be adapted for hosting an application. An application may denote any instance which uses a service e.g. connection setup connection teardown etc. of a connection manager.

Moreover the further node may comprise a connection manager. Such a connection management utility may be a piece of software or hardware that manages the activities and features of a network connection.

An application block and a connection manager block may form part of a user equipment for instance a pre release 7 WCDMA user equipment or any other legacy user equipment. Every platform that supports outgoing connections may be such a legacy user equipment.

In the following further exemplary embodiments of the method will be explained. However these embodiments also apply to the node to the communication arrangement to the computer program and to the computer readable medium product.

The method may further comprise receiving a request from a communicatively coupled network to activate a dedicated packet switched domain. In an embodiment such a request may be denoted as an ACTIVATE DEDICATED EPS BEARER CONTEXT REQUEST. Furthermore in response to the received request the method may comprise sending by the node a response to the communicatively coupled network to activate the dedicated packet switched domain. In an embodiment such a response may also be denoted as an ACTIVATE DEDICATED EPS BEARER CONTEXT ACCEPT. Participation of an application in the communication process may be initiated later. The network may allow for a communicative connection to any communication party such as a base station a further user equipment a computer etc.

Furthermore in an embodiment the method may comprise particularly succeeding the previously mentioned method steps receiving a request from the second radio access platform to setup a connection and in response to the received request sending a response to the second radio access platform to setup the connection. The received request may also be denoted as a connection setup request whereas the sent response may also be denoted as a connection setup response.

The aspects defined above and further aspects of the invention are apparent from the examples of embodiment to be described hereinafter and are explained with reference to these examples of embodiment.

The illustration in the drawing is schematically. In different drawings similar or identical elements may be provided with the same reference signs.

To simplify the description exemplarily the LTE network signaling stack will be mentioned in the following as representative for a radio access technology that supports an incoming packet switched connection. The scope of exemplary embodiments of the invention applies for all radio access technologies which are supporting incoming packet switched connection. In the following the handling of incoming LTE Network connections i.e. incoming EPS Bearer will be described exemplarily.

In the following referring to a communication system according to an exemplary embodiment of the invention will be explained.

The communication system comprises a network such as a telecommunication network. This network is communicatively coupled with a communication arrangement for communicating within the communication system and comprising a first node and a second node . Nodes and may be physically separate nodes or may be combined to one common physical structure.

The first node acts as a modem and serves as a Long Term Evolution platform LTE supporting incoming packet switched connections. An LTE NS stack of the first node serves as a control entity of the first node within the communication system . The first node may or may not support outgoing packet switched connections.

The first node is communicatively interconnected to the second node which includes an application block and a connection manager block . The second node supports only outgoing packet switched connections not incoming packet switched connections. In the described embodiment the second node performs connection management and handles the application . The second node is a WCDMA UE user equipment but can also be any other legacy radio access node which only supports outgoing packet switched connections not incoming packet switched connections.

In the embodiment of the first node performs alone commissioning of an incoming packet switched connection whereas the second node does not contribute anything to this commissioning task.

The first node alone performs commissioning of an incoming packet switched connection see reference numeral in .

The application hosted by the second node may send a connection setup request to the connection manager which in turn may forward the connection setup request to the first node . In response to the connection setup request the first node will communicate a connection setup response to the connection manager . The connection manager in turn may forward the response to the application and may send an access communication message to the first node .

Hence depicts an embodiment of the present invention in which the commissioning of an incoming PS connection is completely done at the radio access platform which acts as modem e.g. a LTE modem i.e. at the first node . The incoming PS connection is not exported to other platforms e.g. the WCDMA platform of node or a PC . The modem of the first node accomplishes accepts the establishment of the incoming PS connection from the network without simultaneously performing an association towards the application . The association towards the application is not done until a connection setup request from the application is received. When such a connection request is received the modem of the first node first checks all known network connections i.e. EPS bearers to determine whether the requested connection parameters e.g. IP Address Port Number QoS etc. match an existing network connection. If so the modem of the first node links the application connection request to the corresponding modem network connection. If not the modem of the first node requests a new connection e.g. EPS bearer towards the network not shown in . But in the latter case a so called outgoing PS connection is established.

In a block a dedicated EPS bearer is activated. In a subsequent block a connection setup request is received by the first node . Subsequently an incoming PC connection is commissioned by the first node alone compare reference numeral . Then a connection setup response message is sent from the first node to the second node . The incoming packet connection is highlighted in .

Node may comprise a receiving unit R capable of receiving communication messages a transmission unit T capable of transmitting communication messages a processing unit P providing processing resources and a storage unit C providing storage resources. Although not shown explicitly other nodes mentioned in this description or shown in the figures may have a similar constitution as the node i.e. may also have corresponding blocks R T P and C.

In the following several use cases will be explained in which exemplary embodiments of the invention may be implemented. The following impacted use cases UC can be derived from the above explanations particularly the explanations referring to and 

Use Case UC 1 Initial PDN connectivity request that is combined with the attach request to establish the initial Default EPS Bearer.

Use Case UC 2 Inter Radio Access Technology IRAT Handover to a LTE cell i.e. the LTE cell is the handover target . This addresses all cases comprising the IRAT cases.

Use Case UC 3 Incoming PS connection by means of dedicated EPS bearers triggered by a Mobility Management Entity MME .

The following concept description of the incoming PS data connection handling illustrates only principles of operation between NS and upper layers connection manager and application . The description does not consider the different platform architectures i.e. all combinations of the LTE Platform with other radio access technologies ORATs . It describes only the pure concept that is independent from the architecture. The description does not elaborate map the concept onto the impacted use cases UC 1 to UC 3 which are specified above. However the skilled person will understand that the concept is of course applicable for all use cases.

A gist of the concept is to preserve incoming connections in the NS stack or in another instance that is located in this node until a request from the connection manager for this specific connection is requested i.e. the NS stack comprises a dedicated module for this purpose.

Each connection which is preserved by the NS Stack is preferably stored with the following settings for instance 

Bearer ID may be required to identify each connection and provide the correct connection to the connection manager when requested later on.

For the Use Cases UC 1 to UC 3 different procedures for connecting the incoming PS data connection to the right application have to be applied.

In UC 1 the Default Bearer is not used by any application first. Some time later a user may start an application which requires network connection. The application may trigger the connection manager with a setup connection request as shown in . The connection manager forwards this request to the NS stack with an unspecified Bearer ID i.e. the Bearer ID is not chosen by the connection manager as it shall be assigned by network. The NS stack returns the Default Bearer received with the attach procedure.

In UC 2 one or several Default Bearers or Dedicated Bearersare preserved by the NS stack until an application requests them with a PDN Connectivity Request Resource Allocation using the right Bearer ID and the right Packet Filter ID. If the Bearer IDs will change during handover HO network has to provide a Bearer Mapping Table. This table is forwarded to a handover module HOM which translates this mapping table into separate setup connection requests towards the connection manager. Additionally the HOM informs the NS stack about all Bearer IDs which will be received from network during HO. In each setup connection request towards the connection manager a specific Bearer ID and a specific Packet Filter ID is passed by HOM. Also the information if a Default Bearer Dedicated Bearer or an SDF is requested should be contained in the request. The connection manager forwards this request to the NS stack. As the NS has been informed about the Bearer IDs that will arrive due to HO it can match the Bearer ID provided with the connect request message of the connection manager. If the Bearer SDF was already setup by network it can immediately passed to the connection manager. If not yet established the connection manager has to wait until the connection was prepared from network.

To do the final connect of a Bearer to the right application data received from a Bearer has to be put in a specific channel which terminates in the desired application. To associate the correct channel with a bearer HOM has to receive a mapping table between Bearer IDs in the destination RAT and channel IDs.

LTE platform comprises LTE NS stack and additionally a connection manager and handover module . ORAT platform comprises application IP stack connection manager and additionally ORAT NS stack .

In a step 5 a setup connection request is transmitted from the handover module to the connection manager .

In a step 6 the connection manager sends a PDN connectivity request resource allocation to the LTE NS stack .

The data path before handover is indicated by a broken bold line and after handover by a continuous bold line. Arrows indicate control signaling. It should be noted that the Figure shows merely one implementation example and selected items e.g. a connection manager could be omitted depending on the embodiment.

In UC 3 a Default Bearer is received without being requested by an application. For example an IP Multimedia Subsystem IMS server in the network can decide to setup a VoIP connection. As the IMS server signals this also via Session Control to the UE IMS terminal it can trigger the connection manager to fetch the Dedicated Bearer which has been preserved by the NS Stack.

The above described concept for UC 2 HO assumes that when changing from ORAT into LTE RAT the LTE Bearer establishment is e.g. triggered by the network. In this case the NS Stack has to process the NAS container instead of reacting on several Bearer Activation Context Modify messages.

Modifications and other embodiments of the disclosed invention will come to mind to one skilled in the art having the benefit of the teachings presented in the foregoing descriptions and the associated drawings. Therefore it is to be understood that the invention is not to be limited to the specific embodiments disclosed and that modifications and other embodiments are intended to be included within the scope of this disclosure. Although specific terms may be employed herein they are used in a generic and descriptive sense only and not for purposes of limitation.

