---

title: Microkernel gateway server
abstract: A gateway server includes a first subsystem including a media level, a communication level and a control level; a microkernel; an IPC controller configured to manage communication between the server resources allocated to the first subsystem a second subsystem including a second media level, a second communication level and a second control level such that the microkernel and the IPC controller also manage communication between the server resources allocated to the second subsystem; and a memory with shared reading and writing, established under the control of the microkernel and the IPC controller, between the control level of the first subsystem and the control level of the second subsystem.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09282079&OS=09282079&RS=09282079
owner: EADS SECURE NETWORKS
number: 09282079
owner_city: Elancourt
owner_country: FR
publication_date: 20091223
---
This application is the U.S. National Stage of PCT FR2009 052687 filed Dec. 23 2009 which in turn claims priority to French Patent Application No. 0859143 filed Dec. 30 2008 the entire contents of all applications are incorporated herein by reference in their entireties.

The present invention relates to a gateway server provided with a microkernel. It also relates to a method for transmitting data between networks via a gateway server.

Conventional operating systems such as Microsoft Windows or GNU Linux have not been designed to have strong security constraints. The result is a poorly secure design in the form of an operating system which uses operative layers which can be represented in accordance with different models such as the OSI open systems interconnection model.

Within the scope of a gateway server also known as a proxy this representation can be carried out simply in three levels 

A monolithic kernel of this type includes low level software such as the scheduler process manager memory manager and device drivers as well as some high level services such as file systems cryptographic algorithm systems or filtering systems.

In a protocol stack each layer solves a specific number of problems regarding data transmission and provides well defined services to the upper layers of the first level . These top layers are closer to the user and manage more abstract data by using the services of the lower layers which edit these data so they can be sent over a physical medium.

A gateway server of this type can have a filtering function intended to ensure the transmission of data received for example from an unsecured network such as the Internet network to a sensitive network . In this case these data are processed 

The present invention is based on the fact that such a server and the method required for its implementation have drawbacks. In particular they have weaknesses in terms of the complexity of a monolithic kernel and the architecture of a computer system which does not allow formal verification of the vulnerability of a gateway server.

More specifically no mechanism makes it possible to prove that the data from subsequently pass through all the filtering steps performed by the levels and . A voluntary or accidental dysfunction may thus occur over one of these levels or and may lead to a bypassing of the control level .

By way of example such a dysfunction is demonstrated at the communication level for example within the layer specific to the TCP IP stack. In this case this dysfunction transmits data coming from the network to the network without the prior transmission of said data to the control level .

It is thus possible to access the network independently of the rules of transmission which must be applied by the control level which constitutes an unacceptable flaw of the server .

In order to solve this problem the present invention relates to a gateway server provided with a first subsystem including a media level a communication level and a control level said server also including a microkernel and an IPC controller managing communication between the server resources allocated to the first subsystem characterised in that said server includes 

A gateway server of this type solves the problem of the absence of transmission control functions caused by provoked or accidental dysfunctions at the media level and or communication level of a gateway server.

In fact such a dysfunction cannot result in the transmission of data between networks in a server according to the invention since only the control level can transmit data between these networks via the shared memory.

Such a server therefore affords numerous advantages. On the one hand it makes it possible to respond to a lack of clearly established security rules in the sensitive network since these rules can be implemented by its control level.

It also makes it possible to prevent an attack emanating from a non sensitive network with the aim of bypassing the security level of a gateway server by bypassing the control level thereof.

A server according to the invention thus makes it possible to protect a network which is sensitive to voluntary or involuntary external attacks. In this manner it makes it possible to ensure a security policy between networks of different sensitivity for example between an unsecured network and a sensitive network.

In one embodiment each subsystem comprises means for encoding information which has been received in a request which conforms to a network communications protocol into a binary structure which conforms to a communications protocol for communication between the control level of the first subsystem and the control level of the second subsystem.

In this case each sub system may comprise means for encoding the information into a binary structure after processing of said information in the communication level and then in the control level of said subsystem.

In accordance with one embodiment the server comprises means for identifying as a function of the nature of the request data which are characteristic of the request and have to be encoded in the binary structure.

In one embodiment the server comprises means for associating the request received with a request which has been predefined in a limited list of authorised requests.

In accordance with one embodiment the microkernel comprises means for associating each application implemented by a subsystem with the control of a server resource.

In one embodiment the server comprises means for limiting communication in such a way that neither the media level nor the communication level of a subsystem can communicate directly with the media level or the communication level of the other subsystem without the intermediary of the control levels of the subsystems.

In accordance with one embodiment the server comprises means for analysing the syntax and validity of the protocols filtered by each layer used in the server.

The invention also relates to a method for controlling a gateway server provided with a first subsystem including a media level a communication level and a control level said server also including a microkernel and an IPC controller managing communication between the server resources allocated to the first subsystem characterised in that since the server is also provided with a second subsystem including a second media level a second communication level and a second control level such that the microkernel and the IPC controller also manage communication between the server resources allocated to said second subsystem a memory with shared reading and writing established under the control of the microkernel is used to send requests between the control level of the first subsystem and the control level of the second subsystem with the aid of a server according to any one of the above embodiments.

Lastly the invention also relates to a computer program product including program code instructions recorded on a support which can be read by a computer to implement a method according to the invention when said program runs on a computer.

With reference to a gateway server according to the invention comprises two media levels and two communication levels and and two control levels and .

However a single microkernel is used to carry out some basic functions including the management of communication between the server resources in particular by IPC inter process communication message transfer.

In addition to this management a second generation microkernel includes a clock driver and a scheduler such that a microkernel of this type includes less than 20 000 code lines.

By contrast a monolithic microkernel includes millions of code lines with a proportional risk of bugs and security flaws. It can hardly be verified as conforming to the specifications of code verifiers and current formal proof systems.

Moreover monolithic kernels have poor isolation properties. In fact user processes can break the different types of isolation thanks to pipelines files the shared memory etc. The management of interprocess communication is not trusted.

In fact as previously mentioned within a monolithic kernel there is no isolation between kernel subsystems such as between the drivers and network stacks. A driver of a bugged or corrupted hardware component may therefore put the entire system at risk.

The use of second generation microkernels solves the problem linked to a flaw within the control level. These microkernels are of such a size that they can be serviced easily and evaluated formally so as for example to certify them at a higher level such as level of the EAL evaluation assurance level international standard.

For example the most commonly known second generation microkernels which are currently used in different variations are supported on an L4 API application programming interface which was designed by Jochen Liedtke.

A gateway server provided with such a microkernel thus makes it possible to respond to the complexity and vulnerability of monolithic kernels. In terms of security such a system benefits from the security of the microkernel.

However the security of servers also depends on the security of the IPC communication since this represents a possible means of transmitting dangerous data. For reasons of efficacy the management of the security of communications is traditionally left to the servers the microkernel being satisfied with transmitting the messages.

This is why in this embodiment the microkernel includes an IPC controller offering a mechanism of communication rights such that two applications can only communicate with one another if the controller recognises that these applications have the appropriate rights.

In fact the microkernel considers each application for example of services or drivers as the subject of security criteria which are provided to it beforehand.

From these criteria the microkernel can allocate system resources to the applications that it manages in accordance with a rule established upon its start up whilst its IPC controller allocates or refuses rights for communication between these applications.

In other words the microkernel identifies the resources to be allocated such as the memory inputs and outputs and privileges for the management levels as well as any communication waiting for the authorisation of the IPC controller .

When an application requires IPC communication between different elements the IPC controller thus determines from this list whether the requesting application has a right to communicate with the recipient application.

The IPC controller thus performs the function of an IPC controller for for example issuing communication rights to specific applications on request. Said IPC controller can likewise detect attempts to violate security criteria and supply an audit on the violation potential.

In this embodiment the microkernel also maintains previously authorised communications for each application.

Such a structure makes it possible to accurately control the use of the resources whilst each application is simultaneously connected to the control of a resource that is to say of a hardware component or mechanism which reinforces the control to block the spread of an attack or bug.

In fact each subsystem manages a flow of data for example at its network interface or its protocol stack by using its own physical resources which are isolated from the other subsystem apart from between their control levels as will be described below.

The microkernel and its IPC controller thus only authorise communications between the respective media level or and the respective communication level or said communication level only being able to communicate with the respective control level or .

Supposing that an attack or bug originating from the network were to succeed in infiltrating through a flaw in one of the layers of the media level and or communication level for example in the application of a driver and or of the protocol stack data cannot therefore be transmitted to the sensitive network without being processed by the control levels and .

Furthermore the architecture of the server makes it possible to carry out a deep filtering process of the network this filtering process using an analysis of the syntax and of the validity of the protocols filtered by each layer of the server for example Ethernet IP TOP application level.

For this reason a request received by the unsecured subsystem is transformed during the progressive processing thereof by the communication level and then by the control level from a request into a simple clearly defined binary structure.

Such a transformation is shown in which illustrates the decomposition of an HTTP protocol request into binary data encoding the information transmitted by said HTTP instruction.

More specifically these data include a get instruction a URL address the version of the HTTP protocol used and the file formats taken into account by a browsing or navigation software.

These binary data shown in a table for reasons of clarity are then sent to the control level of the secured subsystem via the intermediary of a memory which is shared between the two subsystems.

To this end an exhaustively defined protocol is used. Such a protocol defines all requests which can be emitted by the control level of the unsecured network in such a way that the data fields required for these requests can on the one hand be predetermined and on the other be filled in by binary data encoding the information identified in the received request.

The requests sent by the unsecured network via the gateway server are thus processed by the unsecured subsystem in order to extract therefrom any data which are characteristic of said requests these characteristic data being sent to the secured subsystem via the control level of said unsecured subsystem.

The secured subsystem then rewrites the request in accordance with its communication level for example in accordance with an HTTP protocol on the basis of previously extracted characteristic data. This request is then sent via the communication level to the recipient server which can then be validly and securely forced.

In return the response of the recipient server is received by the media level then by the communication level so as to reach the control level .

Said control level can then transmit the binary data obtained from the response through the shared memory such that said memory transmits it to the requester via the levels and then of the unsecured subsystem.

It would appear that a gateway server according to the invention does not aim to block bugs and or attacks but to limit their effect on the sensitive network since all requests emitted within the sensitive network by said server are requests validated by their rewriting said validated requests not corresponding exactly to the initial request. The security of the gateway is thus ensured by the architecture of the server.

To summarise each subsystem acts as a trap which can only communicate with the other subsystem via the intermediary of a memory in which binary data are recorded which encode the information identified in a request received at the input of one of the subsystems in predefined fields.

In this way the subsystems only communicate via the intermediary of their control level which is particularly trusted owing to the presence of a microkernel and by means of data of which the scope is limited to the predefined field.

The present invention may encompass numerous variations. In particular the description given above of the invention provides a microkernel including the IPC controller although depending on the variations and criteria used to define a microkernel said IPC controller may be located outside the microkernel .

