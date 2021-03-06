---

title: Subscription-based services
abstract: The present invention provides a virtual network, sitting “above” the physical connectivity and thereby providing the administrative controls necessary to link various communication devices via an Access-Method-Independent Exchange. In this sense, the Access-Method-Independent Exchange can be viewed as providing the logical connectivity required. In accordance with the present invention, connectivity is provided by a series of communication primitives designed to work with each of the specific communication devices in use. As new communication devices are developed, primitives can be added to the Access-Method-Independent Exchange to support these new devices without changing the application source code. A Thread Communication Service is provided, along with a Binding Service to link Communication Points. A Thread Directory Service is available, as well as a Broker Service and a Thread Communication Switching Service. Intraprocess, as well as Interprocess, services are available. Dynamic Configuration Management and a Configurable Application Program Service provide software which can be commoditized, as well as upgraded while in operation.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08285669&OS=08285669&RS=08285669
owner: Cappelle Networking DE, LLC
number: 08285669
owner_city: Wilmington
owner_country: US
publication_date: 20090430
---
This application is a continuation of U.S. patent application Ser. No. 11 062 256 filed on Feb. 18 2005 now U.S. Pat. No. 7 535 927 by NORTHRUP Charles J. entitled SUBSCRIPTION BASED SERVICES which is a continuation of U.S. patent application Ser. No. 09 211 202 filed on Dec. 14 1998 by NORTHRUP Charles J. entitled ACCESS METHOD INDEPENDENT EXCHANGE WITH COMMUNICATION REQUEST now U.S. Pat. No. 6 922 705 issued on Jul. 26 2005 which is also a continuation of U.S. patent application Ser. No. 08 353 905 filed on Dec. 12 1994 by NORTHRUP Charles J. entitled ACCESS METHOD INDEPENDENT EXCHANGE now U.S. Pat. No. 5 850 518 issued on Dec. 15 1998 the entire contents of each is hereby incorporated by reference and from which priority is claimed under Title 35 U.S.C. 120.

A portion of the disclosure of this patent document contains material which is subject to copyright protection. The copyright owner has no objection to the facsimile reproduction by anyone of the patent disclosure as it appears in the PTO patent file or records but otherwise reserves all copyright rights whatsoever.

This invention relates to computer networks and communication management and to the establishment of communication between various users and or software applications.

The term The Information Superhighway is commonly thought of as an extension of the Internet a network linking hundreds of thousands of computer systems together and communicating via a standard protocol. A computer network is simply a collection of autonomous computers connected together to permit sharing of hardware and software resources and to increase overall reliability. The qualifying term local area is usually applied to computer networks in which the computers are located in a single building or in nearby buildings such as on a college campus or at a single corporate site. When the computers are further apart the term wide area network may be used.

As computer networks have developed various approaches have been used in the choice of communication medium network topology message format protocols for channel access and so forth. Some of these approaches have emerged as de facto standards but there is still no single standard for network communication. The Internet is a continually evolving collection of networks including Arpanet NSFnet regional networks such as NYsernet local networks at a number of university and research institutions a number of military networks and increasing various commercial networks. The protocols generally referred to as TCP IP were originally developed for use through Arpanet and have subsequently become widely used in the industry. The protocols provide a set of services that permit users to communicate with each other across the entire Internet.

A model for network architectures has been proposed and widely accepted. It is known as the International Standards Organization ISO Open Systems Interconnection OSI reference model. See . The OSI reference model is not itself a network architecture. Rather it specifies a hierarchy of protocol layers and defines the function of each layer in the network. Each layer in one computer of the network carries on a conversation with the corresponding layer in another computer with which communication is taking place in accordance with a protocol defining the rules of this communication. In reality information is transferred down from layer to layer in one computer then through the channel medium and back up the successive layers of the other computer. However for purposes of design of the various layers and understanding their functions it is easier to consider each of the layers as communicating with its counterpart at the same level in a horizontal direction. See e.g. The TCP IP Companion by Martin R. Arick Boston QED Publishing Group 1993 and U.S. Pat. No. 5 159 592. These and all patents and publications referenced herein are hereby incorporated by reference. 

As shown in the lowest layer defined by the OSI model is called the physical layer and is concerned with transmitting raw data bits over the communication channel. Design of the physical layer involves issues of electrical mechanical or optical engineering depending on the medium used for the communication channel. The second layer next above the physical layer is called the data link layer. The main task of the data link layer is to transform the physical layer which interfaces directly with the channel medium into a communication link that appears error free to the next layer above known as the network layer. The data link layer performs such functions as structuring data into packets or frames and attaching control information to the packets or frames such as checksums for error detection and packet numbers.

The Internet Protocol IP is implemented in the third layer of the OSI reference model the network layer and provides a basic service to TCP delivering datagrams to their destinations. TCP simply hands IP a datagram with an intended destination IP is unaware of any relationship between successive datagrams and merely handles routing of each datagram to its destination. If the destination is a station connected to a different LAN the IP makes use of routers to forward the message.

The basic function of the Transmission Control Protocol TCP is to make sure that commands and messages from an application protocol such as computer mail are sent to their desired destinations. TCP keeps track of what is sent and retransmits anything that does not get to its destination correctly. If any message is too long to be sent as one datagram TCP will split it into multiple datagrams and makes sure that they all arrive correctly and are reassembled for the application program at the receiving end. Since these functions are needed for many applications they are collected into a separate protocol TCP rather than being part of each application. TCP is implemented in the transport layer namely the fourth layer of the OSI reference model.

Except as otherwise is evident from the context the various functions of the present invention reside above the transport layer of the OSI model. The present invention may be used in conjunction with TCP IP at the transport and network layers as well as with any other protocol that may be selected.

As shown in the OSI model provides for three layers above the transport layer namely a session layer a presentation layer and an application layer but in the Internet these theoretical layers are undifferentiated and generally are all handled by application software. The present invention provides for session control and for communicating with applications programs. Thus the present invention may be described in accordance with the OSI theoretical model as operating at the session layer and application layers.

 Connectivity and convergence have been used to describe two aspects of the communications and computing revolution taking place. In 1994 technology provides to communicate by telephone pager fax email cellular phone and broadcast audio and video. However to use these communication services you have to employ a telephone number beeper number pager number fax number cellular number and each of many email IDs radio stations and television channels. The user is confronted with an overabundance of methods providing such physical connectivity one which will only grow in the future.

The types of physical connections are provided by various systems including the Regional Bell Operating Companies the Long Distance Carriers the Cellular Networks and others providing signal based or wireless communications. The Cable Television Industry provides connectivity for video signals and increasingly other services.

The present invention provides a virtual network sitting above the physical connectivity and thereby providing the administrative controls necessary to link various communication devices via an Access Method Independent Exchange. In this sense the Access Method Independent Exchange can be viewed as providing the logical connectivity required. In accordance with the present invention connectivity is provided by a series of communication primitives designed to work with each of the specific communication devices in use. As new communication devices are developed primitives can be added to the Access Method Independent Exchange to support these new devices without changing the application source code. When viewed in accordance with the OSI model the communication primitives operate at the level of the transport layer and to the extent appropriate at the network layer and in some instances down to the data link layer and occasionally as needed the physical layer.

Using the Access Method Independent Exchange of the present invention anybody can provide a service. Similarly anybody can be a client of a service. A service can even be a client of another service. This is because every user and every service is identified by a unique communication identifier. In accordance with the present invention various communication points are connected together to form a communication link.

The aforesaid identifiers are assigned to the user or service provider during their subscription process. For service providers additional information must be provided and added to the Thread Directory Service. This information includes the required physical connectivity to reach the service.

When users want to access the Access Method Independent Exchange they simply supply Exchange with their unique identifiers. The Binding Service validates each user and permits access to the Exchange. The user may then connect to any registered service by simply calling the service s communication identifier. Of course if they are unfamiliar with the service providers communication identifier they can request assistance through the Thread Directory Service. The Thread Directory Service provides a listing of available services grouped by relationship. The user can search for keywords titles or other information such as service fees. Ultimately the user can request to gain access to the service.

The Access Method Independent Exchange is not limited to servicing a particular geographic area and hence can easily work with foreign countries. The Access Method Independent Exchange includes the ability to provide voice or data message processing.

At the core of the technology is the Thread Communication Service TCS a software utility used to administer the dynamic communications between computer processes executing on a local computer or on a remote system. Two versions of the TCS have been implemented one for intraprocess communications and a second for interprocess communications. The intraprocess version of the TCS is used for a single application process with multiple threads of control. The interprocess version of the TCS provides the administration of communications between processes executing in disjoint address spaces on a local or remote computer system.

In the TCS everything is viewed as either being a communication primitive or a communication point. The communication primitives are the low level mechanisms used to provide the physical communication between various processes. The processes participating in the communication are referred to as communication points. Two or more communication points are connected by a communication link using the communication primitives.

The communication primitives are built using the underlying computer operating system intraprocess and interprocess communication facilities and thus are operating system specific. On one operating system there may be for example five communication primitives supported while another operating system may support twenty. A communication primitive generally must provide for several operations to be applied such as 

Communication primitives are registered with the Thread Communication Service for the specific operating system the TCS is executing on. The name the location and certain characteristics describing the communication primitive are retained by the TCS for subsequent use. In this context the communication primitives become a reusable asset needing to be developed and tested only one time.

Each communication primitive has a shared object referred to as the communication primitive object describing the location of the various operations to be applied when using this primitive type. All primitives have the same communication primitive object structure. The TCS will load the communication primitive object at runtime only when requested for use by a communication point.

In a sense the communication primitive can be thought of as analogous to the physical connection of a telephone on a phone network. A twisted pair telephone would use one primitive while a cellular telephone would use a different primitive.

A process can register zero or more communication points with the TCS. Each point is said to describe a service. Note however that a service can be a client of a different service or a client of itself. The registration process notifies the TCS as to the name and location of the service the default primitive to use for communicating to the service and the default primitive to use when receiving messages from the service.

The registration process also identifies certain characteristics of the communication point. These characteristics include system dependent information implementation dependent information and usage dependent information. The characteristics include 

The registered communication points are then retained by the TCS for subsequent use. When a communication point has been registered a process can request to be connected to the service.

Using the telephone model example a communication point is the equivalent of a destination telephone. That is you can call an individual only by knowing the attributes describing that individual such as a telephone number. The registered characteristics would be similar to your name and address being entered into the phone book. The TCS calls the TDS if requested to record the registered communication point in the TDS.

When a process is executing it may request the TCS to connect it to a communication point. For the intraprocess communication version of the TCS the service executes as a separate thread of control. In the interprocess communication version of the TCS the service executes as a separate process.

There are several modifications permitted. First when a communication point is registered the registering process can identify the communication point as a public point. As such only one instance of the service needs to be executing at any time. All processes requesting to use this point will share the same primitive. Alternatively a service can be registered as a private service in which case each process requesting communication to the service will be connected to their own instance of the service. Finally when a service is initially registered a maximum number of connection points can be preset. When this limit is reached then all new processes requesting access to the service will be denied until such time as the number of current instantiations of the service falls below the threshold.

A single process can be connected to multiple services simultaneously. This can be accomplished through a single connection or though multiple connections established by the process with the various services. In the former case each time the process sends data the data is actually sent to all services using the communication link. In the latter instance only a single destination is connected to the communication link.

Again using the telephone model as an example this is equivalent to your calling a business associate on your telephone system. While connected you can put the call on hold and dial another associate or you can conference the associate in on the same call.

On systems supporting multiple threads of control within a single process address space the TCS uses a special communication point called the intra.sub. p communication point to execute commands on behalf of the TCS within that address space. That is to say when the application process makes its initial request to the TCS the intra.sub. p communication point will bootstrap itself as a communication point within the application process address space. The TCS then issues specific commands to the intra.sub. p communication point who executes these commands on behalf of the TCS. The use of the intra.sub. p communication point is essential to permit intraprocess communication points while supporting interprocess communication points at the same time.

When an application makes a request to connect with a registered communication point and that point must execute as a separate thread of control within the address space of the requesting process then the TCS must have a method to satisfy the request. Since the TCS itself is executing in a different address space it needs a worker thread executing within the requesting process s address space to spawn the requested communication point thread on its behalf.

The TCS also provides a method for a intraprocess communication point to be treated as an interprocess communication point. When an application process makes a request to use an intraprocess communication point as an interprocess communication point the TCS will execute a generic front end loader to initialize the address space of the new process and then invokes the specific thread requested in that address space.

Once connected a process can send messages to a service. The primitive to send this message must accept the message the size of the message and the destination. Similarly a process can request to receive a message from a service. In receiving the message the process must identify the service it is to receive the message from the maximum length of a message it can consume and the actual size of the message returned.

Note that from the point of view of the application process there is no need to be aware of the underlying physical primitive in use. Instead the application sees that a Thread Communication Link is provided and need not deal with how it is provided.

A process can request the TCS to disconnect it from a particular service. When this happens the service can be terminate by the TCS if this was the only process connected to it. Otherwise the service remains executing.

In the TCS model a special communication point can be created to monitor a communication device available to the computer system. This communication point acts as the conduit to send messages to and receive messages from the communication device. The primitive used for this communication point wraps the identifier of the sending process along with the identifier of the receiving process around the message prior to sending the data out on the communication device. Similarly when this communication point receives a message from the communication device it unwraps the message to determine the process that the message is to be sent to. In this sense the communication point is the conduit for communications with external systems.

When a communication point is registered the communication point may have a specific communication primitive required to either send or receive message. This poses a challenge for another communication point to connect if the requesting communication point requires a different communication primitive. When this happens the TCS will search for a broker communication point which can convert the messages from the first primitive type to the second primitive type. The broker service if necessary will be inserted between the requesting communication point and the requested service communication point.

In the TCS model processes are nothing more than communication points. Application programs residing on a disk are also viewed as communication points albeit the application program must be started for execution by the TCS . This powerful model enables application software development which may effectively commoditize software.

The Thread Directory Service is an extension of the Thread Communication Service offering persistence to the registered communication primitives and registered communication points. When a communication point is registered with the TDS it is assigned a unique communication identifier. Numerous additional characteristics of the service can be registered within the TDS such as 

A process can request information from the Thread Directory Service specifying the desired search criteria. This is similar to dialing 411 and requesting a telephone number for an individual based on their name and street address. Each TDS has its own unique identifier. The registered communication points are assigned unique communication identifiers based on the TDS s identifier. Thus communication points are fixed in the universe in this sense.

When the Thread Communication Service works in conjunction with the Thread Directory Service all communication points to be connected are located via their communication identifiers.

When a connection is requested to a particular communication point the requesting process specifies the unique communication identifier of the desired service. The TCS causes the identifier to be looked up in the TDS to determine how to connect to the service and then provides the actual connections.

To minimize the message flow a Thread Communication Switching Service is provided as a special instance of a communication point. It accepts multiple communication links redirecting the communications from one communication point to the appropriate destination communication point. As shown in a TCSS can communicate with communication points or to another TCSS.

Dynamic Configuration Management is a rule based system for specifying components of software to use in constructing a Dynamically Configured Application Program. The components of software are loaded according to the specified rules and are subsequently executed.

The Application Process constructs the Dynamically Configured Application Program in the Dynamic Configuration Management DCM by specifying zero or more RULES identifying the components of the Dynamically Configured Application Program the interactions between these components the policy for evaluating these components the order of evaluation of these components and a method for satisfying the RULE. The Application Process can specify zero or more data files referred to as Virtual Program Rules Files containing RULES for the Dynamically Configured Application Program. In this sense the Application Process provides the blueprint for constructing the Dynamically Configured Application Program.

The specification of a RULE includes the following information although additional information may be incorporated by the implementation 

There are two classifications of RULES supported by the DCM given as Reserved Rules and Universal Rules. The Reserved Rules have special meaning to the DCM. The Universal Rules are specified by the Application Process. In either case however the Rules contain the minimum information described above.

A series of Reserved Rules referred to as the Flow Rules provide the framework for executing the Dynamically Configured Application Program. Whenever a Dynamically Configured Application Program is to be executed the DCM begins by evaluating the Flow Rules. All other actions are derived as a result thereof. The Flow RULES include 

A Dynamically Configured Application Program is therefore constructed by specifying Universal Rules as Prerequisites Rules of the Flow Rules. In evaluating a Flow Rule the DCM will ensure that all Prerequisite Rules of the Flow Rule are evaluated first.

In evaluating a RULE the DCM views the RULE name as the current rule. The evaluation process is such that the DCM will first evaluate all Prerequisite Rules of the current rule. Thus a Prerequisite Rule becomes the current rule and the evaluation continues with its Prerequisite Rules.

When the current rule has no Prerequisite Rules listed and the current rule has never been evaluated then the DCM will execute the method for this rule. After executing the method for the current rule the DCM attaches a time stamp value denoting when the current rule was evaluated.

When the current rule has one or more Prerequisite Rules then the DCM compares the time stamp value of the current rule with that of its Prerequisite Rules. If the time stamp value of the current rule is older than the time stamp value of its Prerequisite Rules then the current rule s method is executed to satisfy the rule and the time stamp value of the current rule is updated to denote when the current rule was evaluated. Otherwise the current rule s time stamp value remains unchanged and the method is not executed.

After evaluating the last Flow Rule of the Dynamically Configured Application Program the DCM considers the application as having completed and returns control back to the initial Application Process.

Initially when a RULE is specified the DCM makes no assumptions as to what the RULE name represents. During the evaluation of the RULE the DCM associates the RULE name with an entity understood by the DCM. This is called the binding process. The list of entities understood by the DCM and their corresponding interpretation by the DCM are provided during the initialization of the DCM. In this sense the list of entities can be modified and updated over time based on market demand for new entities and their interpretations.

The binding of the RULE name to an entity understood by the DCM is determined by the RULE s attributes. In this sense the Application Process can specify how the RULE is to be interpreted by the DCM.

Through the use of this method Minor Services for an Application Service can be designed implemented tested and distributed independently of the corresponding Application Program. The end user can therefore purchase and install only those Minor Services of interest. When the Application Program is to be executed the resulting Application Process will dynamically configure itself to provide the available Minor Services.

The advantage to the computer industry is that the Minor Services for example can be designed after the Application Program and sold individually to the end user. The implications are that 

The Configurable Application Program Service provides a method to dynamically reconfigure an application process. Through the CAPS a communication point can be dynamically replaced by another communication point. This is important for real time systems in which you would not want to terminate the application process to replace a defective module.

The Application Process uses the Configuration Administrator Minor Service to administer zero or more components of software from shared libraries. Each component is said to offer a Minor Service. The specifications for the administration of the Minor Services can be provided directly by the Application Service or indirectly through a data store monitored by the Configuration Administrator. These specifications can instruct the Configuration Administrator Minor Service to perform the desired operation immediately at a predefined time which may be an interval or as a result of some event which is later communicated to the Configuration Administrator Minor Service.

Note that the Configuration Administrator Minor Service operations can be specified to occur at set time intervals at predefined time periods as a result of external events or as a result of internal events. Events in this context are registered with the Configuration Administrator Minor Service to denote their occurrence.

The various aspects of the present invention can be implemented on a digital computer running an operating system that supports runtime loadable software modules such as Unix SVR4.2 MP TLP 5 Unix System Laboratories a subsidiary of Novell Corporation . Such a computer may for example be a Gateway 2000 computer having an Intel 486 microprocessor or any other hardware compatible with that operating system. Many other operating systems may alternatively be used including SunSoft Solaris 2.X Microsoft Windows 95 Microsoft Windows NT IBM s AZ and Hewlett Packard HP UX on any hardware compatible therewith. See e.g. Solaris 2.2 SunOS 5.2 Reference Manual Section 3 Library Routines A M and N Z SunSoft Part No. 801 3954 10 Revision A May 1993 .

The term Application Program is used to describe a software application residing on a medium accessible to the computer system.

An Application Process is said to provide some well known service e.g. wordprocessing spreadsheet graphics etc. The Application Program may be devised to provide a series of one or more Minor Services and a Primary Service which collectively constitute the Application Service.

The term Application Process as used in this document refers to the overall computer representation of the Application Program s execution. In this definition the term Application Process is defined to incorporate all processes of various weight including but not limited to heavy weight medium weight and light weight processes relating to the Application Service. A heavy weight process executes in its own address space whereas medium weight and light weight processes may execute within the same address space. The Application Process may constitute one or more of these processes. Each of these processes is said to have a Thread of execution.

A Thread in this context represents an execution stream of the Application Process. The notion of a Thread can be provided by the underlying operating system referred to as kernel supported threads or can be provided at the application level referred to as user level threads or can be a mixture of the two. For the purposes of this description these will collectively be referred to as Threads. Note that in a distributed environment one or more of these Threads may be executing on a remote computer system.

The Application Process may be confined locally to the computer system on which the Application Process was initially started or may have its execution threads distributed among various computer systems accessible to the computer system on which the Application Process was initially started.

When a user of the computer system requests to execute an Application Program the Application Program is loaded into the computer s memory having a single Thread of execution. This initial Thread may then create additional Threads on the local computer system or possibly on a remote computer system.

The creation of a new Thread requires the Application Process to specify the starting point of the new Thread. In procedural computer languages for example this would require the requesting Thread to specify the address of the procedure to begin as a new Thread. On some implementations the new Thread must be identified by its Application Program name. The implication herein is that the Application Program is created i.e. compiled with this information present.

The Application Program is therefore a static representation of a well known functionality and is not easily able to dynamically load additional Threads unknown at the time the Application Program was developed. There are however certain Applications Programs which provide a listing of installed computer Application Programs either through a textual display or through a graphical representation referred to as an icon. Additionally certain Application Processes search specific directories for available Application Programs to execute as Application Co Processes but again the criteria for their representation is static and unalterable by the end user.

In the textual representation the name of the Application Program is provided with zero or more additional information components such as the owner the size and or execution privileges. This listing is shown to the user who may then enter the name of the application to execute.

Alternatively when using a graphical user interface with an Icon the name of the Application Program its specific location on the computer system and other information is required to execute the Thread. A further limitation of the Icon is that one Application Process can be started by selecting the Icon but that Application Process cannot select a new Icon to execute as an Application Co Process. That is to say the Icon is a graphical representation for the end user to select.

A limitation of both the textual and graphical representation of the available Application Programs is that the information displayed to the user is dependent on the underlying operating system implementation. Certain operating systems will display the name the size in bytes the owner the date created and execution mode while others will display a subset of this information and possibly other system dependent information. Regardless however the user cannot easily associate additional information with the installed application in a useful manner. Finally many users have manually created what has become known as README files to describe this information.

There are many instances in which an Application Process will select different Minor Services depending on installed features additional software available to the computer system or due to other factors external to the Application Process itself. Currently the only provisions to support such run time changes to the Application Process are to design the Application Program with the appropriate logic.

This disadvantage to this approach however is that it limits the ability of the Application Process to dynamically configure itself based on available Minor Services or due to other factors external to the Application Process itself. Additionally the Application Process cannot appropriately handle cases in which an available Minor Service may conflict with another Minor Service. Once the incompatibility is detected the Application Process will simply print an error message and terminate its processing.

Finally an Application Process which locates available Minor Services has no simple provision for executing these Minor Services communicating with these Minor Services nor ensuring a proper ordering of the execution of these Minor Services.

The prior art therefore does not provide the necessary mechanisms for an Application Process to dynamically alter its execution based on Minor Services available either locally or remotely to the computer system. Additionally the prior art does not provide the necessary mechanisms for the same Application Program to behave differently on two separate computer system offering two very different sets of Minor Services without this logic being introduced into the Application Program from the onset.

The prior art also does not provide the mechanisms for resolving feature conflicts in which there are two or more installed Minor Services available to the Application Process but whose use are mutually exclusive. The Application Program will typically be designed to execute the first feature Feature A and then the second Feature B . If Feature B conflicts with the use of Feature A there are no simple remedies to support a resolution. Consider for example that the Application Process performs various initialization sequences required for Feature A. The Application Process may then also execute various initialization sequences for Feature B. During the initialization sequences for Feature A certain values may be set in the Application Process which are inappropriate in the case of Feature B being present.

Within the prior art there are various approaches for configuration of Application Programs. Typically referred to as Software Construction Utilities these approaches provide a rule based system describing how an Application Program should be constructed from its corresponding application programming language source code. Examples of Software Construction Utilities include 

Here the source code provides the necessary algorithm logic and instructions in a human readable form. This source code must then be compiled into an Application Program which the computer can then load and execute. The process of determining the necessary actions to create the Application Program are typically controlled by a software construction Application Program a make utility which reads specifications from a data file known as a makefile . This process is well known and well understood in the computer programming profession. The makefile contains specification of the form 

to denote that a target is dependent on prerequisites. If one or more of the prerequisites is newer than the target then the ACTION is performed to construct the target. Each prerequisite can be listed as a target of another rule. As an example consider 

In this example the rule to construct the target A shows it has a dependency on prerequisites B and C . Note however that B is dependent on b according to the second rule and that C is dependent on c based on rule 3. If c has changed since the last time C was constructed then the ACTION for rule 3 would be performed to reconstruct C. Similarly if b has changed since the last time B was constructed then the ACTION for rule 2 would be performed to reconstruct B. Note that the ACTION for rule 2 and the ACTION for rule 3 could in fact occur simultaneously since there are no other dependencies on these rules. After rule 2 and rule 3 has completed then rule 1 can continue. Here if B or C has changed since the last time A has been constructed then the ACTION for rule 1 will be performed to reconstruct A.

The issue of software configuration has historically been addressed by one of the following mechanisms 

Application Programs are typically designed and distributed following the Non featuring Software model. Consider for example that when purchasing a Word Processing Application you receive all of the latest features available. This has the disadvantage that you are paying for features which you may not need.

With Run Time Featuring the Application Program consists of the monolithic representation of the application. Thus you receive a potentially large Application Program with certain portions of the Application Program inaccessible to you. Nonetheless you receive the largest possible representation. The disadvantage to this approach is that you cannot ship the product until all features have been developed. Additionally the customer must have enough memory and storage capacity for the entire Application Program even though only a one Minor Service may have been purchased.

With Compile Time Featuring the source code representing the application has numerous sections delineated with conditional inclusions based on specified criteria. As an example in the C language it is customary to use 

The disadvantage to Compile Time Featuring is that it makes the source code difficult to understand. Additionally as more Minor Services are added the complexity of maintaining the source code increases thus introducing the prospects for inadvertent software errors known as bugs.

Load Time Featuring is not very common in the industry as there is little perceived benefit. Considering that the Application must know the features to test for there is little advantage in this approach versus the previously mentioned approaches.

An alternative method for dynamically configuring an application process during execution is to use a shared library ARNO86 ATT90 SUNS92 .

With shared libraries an application program references services available in the library without copying all of the text portion into the Application Program. When the Application Program is executed the resulting Application Process opens the shared library loads the service from the library and then executes the service. The service is retained until the Application Process explicitly request that the service is to be removed from the Application Process. The advantage of using shared libraries is that the underlying library can be upgraded altered or otherwise changed independently of the Application Program.

The disadvantage in using shared libraries in this manner is that the shared library can only be altered when there are no Application Processes referencing the shared library. Another disadvantage in using shared libraries is that Application Programs are not normally designed to explicitly search and load services from the shared libraries on demand.

Thus the prior art provides a mechanism to administer the Application Program software construction process based on available Minor Services. It does not however address the needs or requirements for dynamic reconfiguration of the Application Process. The distinction here is that the former approach constructs a static representation of the Application Program while the later is a dynamic representation of the Application Process.

The invention provides a Thread Directory Service to administer one or more Thread Service Directories. Through the Thread Directory Service a thread can 

In registering a new service a series of attributes are provided by the registering thread describing the type of service to be provided. These attributes are classified as Public or Private attributes. Public attributes are considered public information and are accessible through the Thread Directory Service by any thread executing locally or remotely. Private attributes are only accessible by the Thread Directory Service. The administrator of the Thread Directory Service has access to all attributes. A complete description of the attributes is provided in the Embodiment section below.

In registering a new service the Thread Directory Service assigns a unique Thread Communication Identifier to the new service and retains this Identifier in the Thread Service Directory.

Once registered any thread can call the Thread Directory Service to query for a Thread Service by providing one or more Public Attributes. The Thread Directory Service will then search the Thread Service Directory reporting the Thread Communication Identifier s of those services matching the specified attributes. In querying the Thread Service Directory a requesting thread can specify the search criteria attributes using Boolean expressions.

Only the Service Thread owner or the administrator of the Thread Directory Service can delete entries from the Thread Service Directory.

The Thread Communication Service TCS is a computer software method for dynamically administering the communications between two or more Minor Services of an Application Process.

The Thread Communication Switching Services system has several features. It routes communications between two or more threads interconnected through a Thread Communication Link. It minimizes the number of Thread Communication Links required to be maintained by the Thread Connect Service. It also packages multiple Thread Communication Packets into a single packet for long distance communications. It also provides redundancy of communications in the event that a Thread Communication Point in the Thread Communication Link terminates unexpectedly.

The Binding Service is a computer software method to dynamically administer the association of one or more arbitrary named representations with entities understood by the Application Process. Each arbitrary named representation is a sequence of one or more bytes applied at the Application Process level.

An arbitrary named representation is initially considered as Unbound. When an association between the arbitrary named representation is made with an entity understood by the Binding Service then the arbitrary named representation is considered Bound. The process of determining the association is called the Binding Process. The Binding Process applies an ordered series of Binding Methods to determine if an association between an arbitrary named representation and the entities understood by the Binding Service can be made.

To determine the significance of an arbitrary named representation within the scope of the Application Process the Application Process can request the Binding Service to apply the Binding Methods to the arbitrary named representation to determine what entity the name represents.

The Binding Service provides a series of Default Binding Methods including the ordering of Binding Methods as should be applied by the Binding Service. These Binding Methods and their ordering are specified in a Binding Configuration File which is read by the Binding Service during its initialization. Additional Binding Methods can be added to the Binding Configuration File by the end user. Other Binding Methods can be registered with the Binding Service during the Application Process run time execution. The registration of a Binding Method must include the information shown in Table 1.

Example descriptive Binding Methods and their definitions are shown in Table 2. An Example of implementing a Shared Library Binding Method and a Shared Object Binding Method are shown in shown in through and are compiled using the second command line of . provides a listing of a simple minor service that is compiled using the first command line shown in . An example execution of the said compiled program is shown in . The sampled output from the execution of said compiled program is shown in .

Pattern Matching if the arbitrary named representation matches the specified regular expression pattern then apply the Locate Operation to determine if the named representation can be found. If the Pattern Matching Method is specified as NULL then proceed as if the name was matched. If the arbitrary named representation does not match the specified regular expression pattern then go to the next Binding Method.

Transformation if the arbitrary named representation successfully completes the Pattern Matching operation then apply the Transformation operation to the arbitrary named representation and use this transformed name for subsequent operations. If the Transformation operation is not specified for this Binding Method then use the specified arbitrary named representation for subsequent operations.

Locate Operation use the registered Locate operation to see if the arbitrary named representation can be found. If the Locate Method returns success then the arbitrary named representation is considered BOUND using this Binding Method. If the Locate operation fails then the arbitrary named representation remains unbound.

Status Operation given a BOUND arbitrary named representation use this operation to retrieve the status information describing this entity. This includes the following information 

Query Operation given a BOUND arbitrary named representation report the status information as described by in the Status Operation.

The Dynamic Configuration Management hereinafter sometimes referred to as the DCM provides a method for an Application Process to dynamically construct and subsequently execute a Dynamically Configured Application Program offering an Application Service with zero or more Minor Services.

The Application Process constructs a Dynamically Configured Application Program in the DCM by specifying a series of RULES identifying the components of the Dynamically Configured Application Program the interactions between these components the policy for evaluating these components the order of evaluation of these components and a method for satisfying the RULE. Additionally the Application Process can specify zero or more data files referred to as Program Rules Files containing RULES for the Dynamically Configured Application Program. In this sense the Application Process provides the blueprint for constructing the Dynamically Configured Application Program either through an Application Programming Interface and through zero or mode Application Program Rules Files. Once constructed the Application Process can then request the DCM to execute the Dynamically Configured Application Program.

The specification of a RULE includes the information shown in Table 4 although additional information may be provided by the actual implementation 

There are two classifications of RULES supported by the DCM given as Reserved Rules and Universal Rules. The Reserved Rules have special meaning to the DCM and cannot be redefined. The Universal Rules are specified by the Application Process. In either case however the Rules contain the minimum information described in Table 4.

A series of one or more Reserved Rules referred to as the Flow Rules provide the framework for executing the Dynamically Configured Application Program. Whenever a Dynamically Configured Application Program is to be executed the DCM begins by evaluating the Flow Rules. All other actions are derived as a result thereof. The Flow Rules are shown in Table 5.

The MAIN RULE must be specified for the Dynamically Configured Application Program to execute. The other Flow Rules DCMINIT APINIT DONE APDONE and DCMDONE are optional .

The DCM groups all Rules with the same name together as if they were specified as a single entity. This permits for example the Application Process to specify potions of a Rule during initialization sequences and the remainder of the Rule when initialization has completed.

When the Dynamically Configured Application Program is to be executed the DCM will evaluate each of the specified Flow Rules. In evaluating a RULE the DCM views the RULE name as the current rule. The evaluation process is such that the DCM will first evaluate all Prerequisite Rules of the current rule. Thus a Prerequisite Rule becomes the current rule and the evaluation continues with its Prerequisite Rules. This is implemented using well known directed graph techniques.

When the current rule has no Prerequisite Rules listed and the DCM determines the current rule must be evaluated then the DCM will execute the method for this rule. After executing the method for the current rule the DCM attaches a time stamp value denoting when the current rule was evaluated.

When the current rule has one or more Prerequisite Rules then the DCM compares the time stamp value of the current rule with that of its Prerequisite Rules. If the time stamp value of the current rule is older than the time stamp value of its Prerequisite Rules then the current rule s method is executed to satisfy the rule and the time stamp value of the current rule is updated to denote when the current rule was evaluated. Otherwise the current rule s time stamp value remains unchanged and the method is not executed.

After evaluating the last Flow Rule of the Dynamically Configured Application Program the DCM considers the application as having completed and returns control back to the initial Application Process.

The policy for evaluating a RULE is determined by the DCM operator component of the RULE. By default a TIME.sub. VALUE operator will be applied which provides the behavior as described above. Additional DCM operators can be derived and implemented into the DCM to describe the relationship between the RULE and its Prerequisite Rules.

Initially when a RULE is specified the DCM makes no assumptions as to what the RULE name represents. During the evaluation of the RULE the DCM uses the Binding Service to associate the RULE name with an entity understood by the DCM. The list of entities understood by the DCM and their corresponding interpretation by the DCM are provided during the initialization of the DCM. In this sense the list of entities can be modified and updated over time based on market demand for new entities and their interpretations. The DCM provides the following default Binding Methods 

The DCM can exist as a co process of the Application Process or as a sibling process of the Application Process. In the former sense the DCM can be accessed by multiple Application Programs thus providing a sharing of information. In the later case the DCM resides within the Application Process. There are no constraints inherent in the model to preclude the use of the DCM across multiple computer systems.

Through the use of the Dynamic Configuration Management method Minor Services for an Application Service can be designed implemented tested and distributed independently of the corresponding Application Program. The end user can therefore purchase and install only those Minor Services of interest. When the Application Program is to be executed the resulting Application Process will dynamically configure itself to provide the available Minor Services. The advantage to the computer industry is that the Minor Services for example can be designed after the Application Program and sold individually to the end user. The implications are that 

The Configurable Application Process Service is a computer software method for dynamically administering the component Minor Services of an Application Process. The Configurable Application Process Service consists of a Configuration Administrator Minor Service thread using the Communication Manager Program Service described elsewhere in this patent application. Various other Minor Service threads may be created by the Configuration Administrator as described herein.

The Application Process uses the Configuration Administrator Minor Service hereinafter referred to as the CAMS to administer zero or more components of software. Each component is said to offer a well defined application Minor Service hereinafter singularly and collectively referred to as the AMS.

The specifications for the administration of the AMS can be provided directly by an Application Process or indirectly through a data store monitored by the CAMS. These specifications can instruct the CAMS to perform the desired operation immediately at a predefined time which may be an interval or as a result of some event which is later communicated to the CAMS.

There are fifteen general operations available through the Configurable Application Process Service given as 

Other technology which may be configured with the Configurable Application Program Service includes the Binding Service as described in this application.

The advantage to the computer industry is that an Application Program can be constructed and executed and subsequently re configured to take advantage of newly installed minor software services while the Application Process is executing. The implications of such a system are that 

This portion of the invention is a computer application service called the Named Execution Environment Manager. A series of one or more machines interconnected through some form of a networking scheme can register one or more arbitrary attributes describing the characteristics of the machine. These attributes are known as the Registered Environment Attributes within the Named Execution Environment. This registration process can be completed by the system administrator the owner of the machine or can be completed by an automated Application Process which probes the machine to determine the default attributes of the machine.

When an Application Process requires the use of an execution environment the Application Process calls the Named Execution Environment Manager and specifies one or more attributes describing the requirements of the desired execution environment. These attributes are referred to as the Required Environment Attributes. Further the Application Process provides the Named Execution Environment Manager specific information to be associated with the new environment if it can be created. This information is called the Named Execution Environment Attributes.

The Named Execution Environment Manager then selects an appropriate machine based on a boolean evaluation of the Required Environment Attributes provided by the Application Process and the Registered.Environment Attributes describing the physical machines.

When the Named Execution Environment Manager finds a machine whose Registered Environment Attributes satisfy the specified Required Environment Attributes the Named Execution Environment Manager then establishes an execution environment on the associated physical machine for use by the Application Process. The Named Execution Environment Manager then applies the various Named Execution Environment Attributes to this newly created execution environment and retains this information either in memory or on a storage device accessible to the Named Execution Environment Manager.

One of the Named Execution Environment Attributes specified by the Application Process is a logical name to be associated with the execution environment. The Application Process then provides the Named Execution Environment Manager the logical name of an environment and a request to execute in that environment. The Named Execution Environment Manager locates the associated environment and sends the Application Process s request to that environment. The request can be any command understood by the environment.

The returned values from executing the Application Process s request in the named environment is then sent to the Application Process. This is accomplished using the Thread Communication Service as described in this patent application.

This part of the invention is a state machine manager thread providing the administration of a state machine and the administration and execution of various components of a state machine.

Without limiting the generality of the invention as summarized above the following descriptions taken with the accompanying Figures further provide specific examples of how the various aspects of the invention may be embodied in particular software. Those skilled in the art will recognize that changes in form and details may be made therein without departing from the scope and spirit of the invention.

A Thread Service Directory contains zero or more entries describing Service Threads. A Service Thread is defined as an entity providing some form of a service which may or may not require direct interaction with an application program. Each Thread Service Directory entry contains items 2 and 4 below and desirably one or more of the other entries described below 

Access to the Thread Service Directory is provided by the Thread Directory Service which executes as a separate thread but which may be called from an application program. The Thread Directory Service offers a series of operations such as REGISTER DELETE QUERY and others.

When a new Service Thread is made available to the computer system it can register its service by calling the Thread Directory Service specifying a REGISTER operation and providing the required information along with any optional information or attributes. Alternatively a separate application can register other Service Threads available to the computer system by calling the Thread Directory Service and specifying a REGISTER operation along with the appropriate information. This permits a separate application program to provide this information without requiring the Service Thread to register itself. Duplicate entries in a given Thread Service Directory are not permitted. In this instance the Thread Directory Service will return an error indication to the registering thread. In registering the Service Thread the Thread Directory Service will assign a unique Thread Communication Identifier to be associated with the Service Thread. The Thread Directory Service will then return this identifier to the thread registering the service.

A Service Thread can subsequently request that its entry is to be deleted from the Thread Service Directory by calling the Thread Directory Service and requesting a DELETE operation. Alternatively a separate application thread with appropriate permissions can perform the same operation.

A thread can query the information in the Thread Service Directory by calling the Thread Directory Service specifying a QUERY operation and providing zero or more components of an entry on which the Thread Service Directory is to search for. This information is then made available to the requesting thread.

A special Thread Directory Administrator Service is also provided to the owner of the Thread Directory Service to perform various administrative functions such as report generation directory reordering billing and trouble reporting. The Thread Directory Service and its components provides for software what the telephone companies provide for their end users. The entire Thread Directory Service and its components are implemented through software and require no physical wire connection as does the telephone to use its service with the exception of any internal computer hardware.

Note that the Thread Directory Service and its representation of the Thread Service Directory can be maintained on separate computer facilities connected through some form of a communication channel such as but not limited to a network a telephone modem a direct link fiber connection or wireless connection. The only caveat is that there must be some form of communication available between these computer systems. Additionally it is possible for the Thread Directory Service to establish communications through several computer systems to ultimately reach one or more additional Thread Service Directories.

The Thread Communication Service TCS is a computer software method to dynamically administer the communications of two or more Minor Services of an Application Process. In this context the Minor Services are referred to as communication points.

A communication point can request the TCS to connect it to another communication point and in doing so the TCS is said to have established a Thread Communication Link TCL between the communication points. Through the TCL a communication point can send data to the connected communication point and can receive data from the connected communication point. When a communication point no longer needs the TCL it notifies the TCS to disconnect the TCL.

Communication primitives are the low level mechanism used to transmit and receive data between two or more communication points. The communication primitives are constructed using low level operating system interfaces which provide the underlying connectivity and synchronization requirements. To use a communication primitive with the Communication Manager the communication primitive must provide the following operations 

Two examples of communication primitives are the queueConditionThread and queueConditionProcess. The queueConditionThread provides a communication primitive between Application Services executing in the same address space whereas a queueConditionProcess provides a communication primitive for use between Application Processes executing in disjoint address spaces.

The TCS maintains a list of available communication primitives for use by the communication points. This list is referred to as the Communication Primitives List. The queueConditionThread and queueConditionProcess primitives are added to this list. Each member of this list is a communication primitive and contains references to the available operations for this primitive.

The Application Process can add a member delete a member or query member information from the Communication Primitive List.

Communication Primitives can be added for all low level physical networks and for higher level OSI protocols. These include NetWare TCP IP X.25 communications and the likes. The only requirement is that the communication primitive provide the operations described above.

The Application Process can request the TCS to REGISTER a communication primitive for use in subsequent communications. The communication primitive is identified by 

The Communication Primitive should however be a loadable module that the underlying operating system can load as part of the Application Process requesting a connection to a communication point as described below.

The list of Communication Primitives available to the Application Process can be retained in memory or retained in a file on a storage medium disk or retained in the TDS or retained in an Application Process accessible to the requesting Application Process.

The Application Process can requests the TCS to REGISTER a Minor Service as a communication point. The Minor Service is identified by 

In the registration process the communication point can be identified as either a Sender communication point a Receiver communication point or as both a Sender and a Receiver communication point. The registration process can also permit the Application Process to specify the desired low level communication primitive to use when the communication points is to Receive communications and the communication primitive to use when the communication point is to Send communications. The specifications for the low level communication primitive can include 

The list of registered communication points can be retained in memory or retained in a file on a storage medium accessible to the computer system or retained in the TDS or retained in an Application Process accessible to the requesting Application Process.

The Application Process can request the TCS to CONNECT two communication points with a TCL. In specifying the communication points the TCS ensures that one communication point is a Sender communication point and the other communication point is a Receiver communication point. Further the Communication Manager ensures that the Sender communication point and the Receiver communication point both use the same underlying synchronization primitive for connectivity and synchronization. If either condition is not satisfied the Communication Manager will abort the request and notifies the Application Process of the error condition.

Regardless of the method used the TCS must be able to resolve the name and location of the communication point. If the TCS cannot determine the name and location of the first communication point it will call the TDS to determine if the name represents a Thread Communication Identifier as described in the Thread Directory Service TDS section of this application.

If necessary based on registration data see the section on TIDS the TCS will start an invocation of a communication point as a separate thread of control. The invocation of a communication point can be as a separate process or as a separate thread. In either case the TCS will begin the invocation of the Minor Service if the Minor Service must be executed and if there are no administrative constraints such as the number of instances of runnable Minor Services of the specified type has been exhausted See the section on TDS .

Alternatively the Application Process can request that the TCS CREATE an instance of a particular Minor Service without specifying a communication point that should be attached to it. This permits the TCS to begin the execution of the communication point subject to the constraints in the preceding paragraph and permit the communication point to perform some processing prior to having a connected communication point. This is particularly useful for daemon Minor Services performing housekeeping memory management etc . At a later time the Application Process can request the TCS to connect a communication point to this CREATED communication point.

In creating the Minor Service the requesting Application Process can specify if the Minor Service is to be executed as a Sender Receiver or both. This information can be compared against the registered information to ensure the Minor Service has desired communication capability. The TCS performs the following actions 

The Application Process can request the TCS to connect two communication points such that the communication points can communicate with each other. If either communication point is not currently active the TCS will CREATE the missing communication point see Creating Communication Points .

When both communication points are created the TCS will link the two communication points based on the specified communication direction which is given as one of 

For the purposes of describing the connection process with reference for example to we describe the case of CP A being connected to CP B using communication direction 1 as described above 

For the case of CP C being connected to CP D using communication direction 2 as described above then step 1 and step 2 are not completed. For the case of CP E being connected to CP F using communication direction 3 as described above then step 3 and step 4 are not completed. For the case of CP G being connected to CP H using communication direction 4 as described above then step 1 step 2 step 3 and step 4 are not completed.

In this manner the TCS establishes a communication link between the two communication points. In specifying a CONNECT request the Application Process may specify only one of the two communication points.

If a Sender communication point is not specified then the requesting Application is Process is assumed to be the Sender communication point. If the specified Receiver communication point is not currently executing then the TCS will issue a CREATE operation for the Receiver communication point.

Alternatively if the Application Process does not specify a Receiver communication point then the Application Process is assumed to be the Receiver communication point. If the specified Sender communication point is not currently executing then the TCS will issue a CREATE operation for the Sender communication point.

Once connected the Receiver communication point uses the RECEIVE operation of its Receiver to Receive message. The Sender communication point uses the SEND operation of its Sender to send message.

Note that certain communication primitives require specialized initializations for establishing connections and hence if the communication primitive contains a CONNECT function pointer then the communication primitive s CONNECT function will be executed before any other steps in this section.

The Application Process can request the TCS to SUSPEND a TCL currently in use by two communication points. In suspending the TCL the TCS will temporarily suspend the execution of the Sender communication points. Alternatively if the Sender communication primitive has a special SUSPEND operation defined then the TCS will invoke that SUSPEND operation.

The Application Process can request the TCS to RESUME a TCL currently in the suspended state. In resuming the TCL the TCS will resume the execution of the Sender communication points. Alternatively if the communication primitive of the SENDER has a special RESUME operation defined then the TCS will invoke that RESUME operation.

The Application Process can request the TCL to DISCONNECT one or more communication points using a TCL. In performing the disconnect the TCS temporarily suspends the communication points removes the current TCL and restores the prior TCL associated with the communication points. The execution of the communication points are then resumed. The requesting Application Process can specify if the TCS is to terminate either or both of the communication points participating in the thread communication link being disconnected.

The Application Process can request the TCS to DESTROY a communication point. In doing so the TCS will eliminate the registered information regarding this communication points from its storage. If the communication point is currently executing then the TCS sends a signal to the communication point to terminate. On some implementations a special message may be sent by the TCS to the communication point notifying it that it is to terminate.

An Application Process can request the TCS to RECONNECT a specified communication point. In doing so the TCS will send a NULL message to the communication point. This is useful to determine the state of the communication point and to cycle the communication primitive.

The Application Process can request the TCS to EXECUTE a specified communication point. In doing so the TCS will examine its TCL for a communication point having the specified name. If the communication point is not currently executing then TCL will issue a CREATE request for the specified communication point. The communication point s thread is then specified to resume execution. In this manner a daemon Minor Service can be created.

Note that if the communication point is a Receiver communication point then the communication point will presumably block on its first call to its communication primitive s RECEIVE operation. Alternatively if the communication point is a Sender Minor Service then the communication point will presumably continue to send messages using its communication primitive s SEND operation and these message will remain until a Receiver communication point is connected.

The Thread Service Directory Communication Link provides the ability for a Thread Communication Link between Application Threads and Service Threads. A Service Thread may establish additional Thread Communication Links with other Service Threads or Application Threads. In this context each thread is said to be a Thread Communication Point TCP . Note As used in this section the term TCP does NOT refer to Transmission Control Protocol. In its simplest example this is shown in in which the Thread Communication Point labeled TCP 1 is connected to the Thread Communication Point labeled TCP 2 through a Thread Communication Link TCL . See .

With additional Thread Communication Points becoming linked through Thread Communication Links it is possible for a particular thread to request a Thread Communication Link to another thread already linked at some further point. As an example consider which shows a Thread Communication Point labeled TCP 1 connected to a Thread Communication Point labeled TCP 2 through a Thread Communication Link labeled TCL 1. Additionally TCP 2 is connected to a Thread Communication Point labeled TCP 3 through a Thread Communication Link labeled TCL 2. In this example if TCP 1 requested a link to TCP 3 an additional Thread Communication Link must be established. See . 

Through the use of this invention it is possible to have multiple Thread Communication Points sharing a Thread Communication Link by establishing a Thread Communication Switch to route the communications between the appropriate Thread Communication Points. As an example of using a Thread Communication Switch see which shows three Thread Communication Points labeled TCP 1 though TCP 3 connected to a Thread Communication Switch labeled TCS 1 through Thread Communication Links labeled TCL 1 through TCL 3. See . 

A Thread Communication Switch can be connected to a Thread Trunk Point TTP which provides for communications to another Thread Trunk Point which may in turn have a Thread Communications Link to a Thread Communication Switch or to a Thread Communication Point. This provides a communications link over longer distances than the simple point to point as described in . As an example of using a Thread Trunk Point see which shows four Thread Communication Points labeled TCP 1 through TCP 4 connected to a Thread Communication Switch labeled TCS 1. The TCS 1 has a Thread Communication Link to the Thread Trunk Point labeled TTP 1. This Thread Trunk Point in turn has a Thread Trunk Link labeled TTL 1 to a destination Thread Trunk Point labeled TTP 2. The TTP 2 has a Thread Communication Link to a second Thread Communication Switch labeled TCS 2. The TCS 2 has Thread Communication Links to Thread Communication Points labeled TCP 5 through TCP 7. See . 

The use of the Thread Communication Points the Thread Communication Link the Thread Communication Switch the Thread Trunk Link and Thread Trunk Points can span multiple computer systems interconnected through some form of communications such as but not limited to a network a direct connection a fiber connection a telephone modem and a wireless connection.

As will be appreciated by those skilled in the art the specific representation of the Thread Communication Link is dependent on the underlying operating system s communications capability and its synchronization primitives.

The Binding Service is a method implemented in computer software to dynamically administer the association of one or more arbitrary named representations with entities understood by the Application Process. Each arbitrary named representation is a sequence of one or more bytes applied at the Application Process level.

An arbitrary named representation is initially considered as Unbound. When an association between the arbitrary named representation is made with an entity understood by the Binding Service then the arbitrary named representation is considered Bound. The process of determining the association is called the Binding Process. The Binding Process applies an ordered series of Binding Methods to determine if an association between an arbitrary named representation and the entities understood by the Binding Service can be made.

To determine the significance of an arbitrary named representation within the scope of the Application Process the Application Process can request the Binding Service to apply the Binding Methods to the arbitrary named representation to determine what entity the name represents.

The Binding Service provides a series of Default Binding Methods including the ordering of Binding Methods as should be applied by the Binding Service. These Binding Methods and their ordering are specified in a Binding Configuration File which is read by the Binding Service during its initialization. Additional Binding Methods can be added to the Binding Configuration File by the end user. Other Binding Methods can be registered with the Binding Service during the Application Process s run time execution. The registration of a Binding Method must include the information shown in Table 6.

Each Binding Method must have associated with it the series of binding method operations shown in Table 8. The Binding Method is described to the Binding Service through five function pointers describing the location of each operation. The function pointers are specified in the order shown in Table 8.

Pattern Matching if the arbitrary named representation matches the specified regular expression pattern then apply the Locate Operation to determine if the named representation can be found. If the Pattern Matching Method is specified as NULL then proceed as if the name was matched. If the arbitrary named representation does not match the specified regular expression pattern then go to the next Binding Method.

Transformation if the arbitrary named representation successfully completes the Pattern Matching operation then apply the Transformation operation to the arbitrary named representation and use this transformed name for subsequent operations. If the Transformation operation is not specified for this Binding Method then use the specified arbitrary named representation for subsequent operations.

Locate Operation use the registered Locate operation to see if the arbitrary named representation can be found. If the Locate Method returns success then the arbitrary named representation is considered BOUND using this Binding Method. If the Locate operation fails then the arbitrary named representation remains unbound.

Status Operation given a BOUND arbitrary named representation use this operation to retrieve the status information describing this entity. This includes the following information 

Query Operation given a BOUND arbitrary named representation report the status information as described by in the Status Operation.

The Binding Service upon initialization will read a Binding Service Configuration File containing zero or more entries of the form 

The Application Process uses the Binding Service s Register interface to register additional Binding Methods not specified in a Configuration File. The specification for the new Binding Method requires the same data as that provided through the Configuration Files. The Register interface provides a mechanism to specify additional Binding Methods even after the Binding Service has started execution.

The Application Process uses the Binding Service s Set Order interface to establish a new order of evaluation to use when applying the registered Binding Methods to an arbitrary named representation.

The Application Process uses the Binding Service s Unregistered interface to remove a Binding Method from the list of available Binding Methods. The Binding Method can be removed only after all references to the Binding Method have completed their use of the method.

The Application Process applies the Binding Service s Bind interface to an arbitrary named representation. The Binding Service maintains a table in memory of the arbitrary named representations requested to be bound by the Application Process. This table contains the collection of arbitrary named representations previously specified to the Bind interface on behalf of the Application Process.

The first step in applying the Bind interface is to search the table to see if the specified arbitrary named representation has already been BOUND. If not then the Binding Service will create a new entry in the table for the specified arbitrary named representation. This entry includes the arbitrary named representation and initially is marked as unbound. If the specified arbitrary named representation is already listed in the table and is marked as BOUND then the Bind interface completes successfully without further action being required. If the specified arbitrary named representation is already listed in the table but is marked as UNBOUND then the Bind interface continues.

The Binding Service will then apply the Binding Methods based on the specified order of evaluation for the Binding Methods. The arbitrary named representation is then BOUND using the first Binding Method to complete successful.

In applying the Binding Methods the Binding Service will determine if the Binding Method has been loaded into memory. If not then the Binding Service uses the Location Operation for the Binding Method and the Name of Binding Method to dynamically load the Binding Method into memory. The Binding Method is then applied given the constraints mentioned above.

During the evaluation of the Binding Methods the Binding Service will first examine the Binding Method to see if it has an associated Pattern Matching operation. If so then the arbitrary named representation is compared against the specified expression pattern using the specified Pattern Matching operation. If the arbitrary name does not compare with the specified regular expression pattern then the next Binding Method is applied. If the Pattern Matching operation is specified as NULL or if the expression pattern is specified as NULL or if the arbitrary named representation compares with the specified pattern then the arbitrary named representation is considered for binding to this Binding Method.

Upon successfully completing the Pattern Matching operation the Binding Service applies the Name Transformation operation if specified for the Binding Method. The Name Transformation operation is used to generate an alternative named representation which will then be used for the Locate and the Status operations described below.

When the arbitrary named representation is considered for binding to a Binding Method then the Binding Service will invoke the Binding Method s Locate operation to locate the entity associated with the alternative named representation or the arbitrary named representation if the alternative is not defined. If the Locate operation fails and a pattern was specified then the arbitrary named representation is considered BOUND but not found. Otherwise the arbitrary named representation remains UNBOUND.

Finally when the arbitrary named representation has been BOUND and has been located then the Binding Service applies the Binding Method s Status Operation to ascertain the current status of the bound entity. This information is then retained in the Binding Service s table.

The Binding Service maintains the representation of the BOUND entity within its scope. This information is not directly available to the Application Process. Instead the Application Process must use the Binding Service s Query operation to access this information.

The Application Process uses the Binding Service s Unbind Interface to mark a previously bound arbitrary named representation as now being unbound.

The Application Process uses the Binding Service s Report interface to report useful information on the current representation of the contents of the Binding Service s data. This includes information relating to the Binding Methods.

The Query interface reports the information available through the Query operation of the Binding Method used to bind the arbitrary named representation. If the arbitrary named representation is currently UNBOUND then the Query interface returns only the name of the entity.

When the application calls the Binding Service s Purge interface the Binding Service deletes all arbitrary named references in its table that are UNBOUND at the time of the call.

The Application Process constructs a Dynamically Configured Application Program in the DCM by specifying a series of RULES identifying the components of the Dynamically Configured Application Program the interactions between these components the policy for evaluating these components the order of evaluation of these components and a method for satisfying the RULE. Additionally the Application Process can specify zero or more data files referred to as Application Program Rules Files containing RULES for the Dynamically Configured Application Program. In this sense the Application Process provides the blueprint for constructing the Dynamically Configured Application Program either through an Application Programming Interface and through zero or mode Application Program Rules Files. Once constructed the Application Process can then request the DCM to execute the Dynamically Configured Application Program.

The specification of a RULE includes the information shown in Table 9 although additional information may be provided by the actual implementation 

There are two classifications of RULES supported by the DCM given as Reserved Rules and Universal Rules. The Reserved Rules have special meaning to the DCM and cannot be redefined. The Universal Rules are specified by the Application Process. In either case however the Rules contain the minimum information described in Table 9.

A series of one or more Reserved Rules referred to as the Flow Rules provide the framework for executing the Dynamically Configured Application Program. Whenever a Dynamically Configured Application Program is to be executed the DCM begins by evaluating the Flow Rules. All other actions are derived as a result thereof. The Flow Rules are shown in Table 10.

The MAIN RULE must be specified for the Dynamically Configured Application Program to execute. The other Flow Rules DCMINIT APINIT DONE APDONE and DCMDONE are optional .

The DCM groups all Rules with the same name together as if they were specified as a single entity. This permits for example the Application Process to specify potions of a Rule during initialization sequences and the remainder of the Rule when initialization has completed.

The DCM will evaluate each of the specified Flow Rules in the order shown in Table 10. In evaluating a RULE the DCM views the RULE name as the current rule. The evaluation process is such that the DCM will first evaluate all Prerequisite Rules of the current rule. Thus a Prerequisite Rule becomes the current rule and the evaluation continues with its Prerequisite Rules. This is implemented using well known directed graph techniques.

When the current rule has no Prerequisite Rules listed and the DCM determines the current rule s method must be executed then the DCM will execute the method for this rule. After executing the method for the current rule the DCM attaches a time stamp value denoting when the current rule was evaluated.

When the current rule has one or more Prerequisite Rules then the DCM compares the time stamp value of the current rule with that of its Prerequisite Rules. If the time stamp value of the current rule is older than the time stamp value of its Prerequisite Rules then the current rule s method is executed to satisfy the rule and the time stamp value of the current rule is updated to denote when the current rule s method was executed Otherwise the current rule s time stamp value remains unchanged and the method is not executed.

After evaluating the last Flow Rule of the Dynamically Configured Application Program the DCM considers the application as having completed and returns control back to the requesting Application Process.

The policy for evaluating a RULE is determined by the DCM operator component of the RULE. By default a TIME.sub. VALUE operator will be applied which provides the behavior as described above. Additional DCM operators can be derived and implemented into the DCM to describe the relationship between the RULE and its Prerequisite Rules.

The Application Program Rules shown in provides an example of a Dynamically Configured Application Program. See . 

The DCMINIT and the APINIT Rules are shown without Prerequisite Rules. When the MAIN Rule is evaluated the DCM finds that it is dependent on Rule A and thus must evaluate Rule A. In doing so it finds Rule A is dependent on Rule B and must therefore evaluate Rule B. The evaluation of Rule B shows that Rule B does not have any prerequisite Rules. After Rule B has been evaluated the DCM resumes the evaluation of Rule A. Upon completion of Rule A the DCM resumes the evaluation of the MAIN Rule. When the MAIN Rule has been completed the DCM next evaluates the DONE Rule and finds that it has Rule C as a prerequisite rule. It therefore evaluates Rule C and then continues with the DONE Rule. Finally the APDONE and DCMDONE Rules are evaluated.

Initially when a RULE is specified the DCM makes no assumptions as to what the RULE name represents. During the evaluation of the RULE the DCM uses the Binding Service to associate the RULE name with an entity understood by the DCM. The list of entities understood by the DCM and their corresponding interpretation by the DCM are provided during the initialization of the DCM. The list of entities appear in the Binding Service s Configuration File. In this sense the list of entities can be modified and updated over time based on market demand for new entities and their interpretations. Initially the DCM provides the Binding Methods for 

SHARED LIBRARY BINDING METHOD The rule represents a shared library available to the Application Process.

SHARED OBJECT BINDING METHOD The RULE name represents a shared object from a shared library. If the RULE has a prerequisite RULE BOUND to a SHARED LIBRARY then the shared object is presumed to exist in that library. If the method for the rule is to be executed then the DCM opens the shared library extracts the shared object and executes the shared object. To specify a SHARED OBJECT BINDING METHOD the rule must have the Reserved Rule SHARED.OBJECT as a prerequisite rule.

THREAD BINDING METHOD The RULE name represents a procedure to invoke as a separate thread of execution within the Application Process. To specify a THREAD BINDING METHOD the rule must have the Reserved Rule THREAD as a prerequisite rule.

SHELL BINDING METHOD The RULE name does not represent a physical entity but rather its method is specified as statements to be executed by the underlying SHELL provided by the operating system. To specify a SHELL BINDING METHOD the rule must have the Reserved Rule SHELL as a prerequisite rule.

FUNCTION BINDING METHOD The FUNCTION BINDING METHOD associates the rule name with a function procedure available in the application program. The DCM will search the symbol name list for the Application Process to locate the address of the function. If the DCM must trigger the method for the rule then the function is invoked.

DEFAULT BINDING METHOD If no binding method has not been specified for the rule then the DCM will bind the rule name using the DEFAULT BINDING METHOD. The DEFAULT BINDING METHOD is to associate the rule name with a function procedure available in the application program. The DCM will search the symbol name list for the Application Process to locate the address of the function. If the DCM must trigger the method for the rule then the function is invoked. If the DCM cannot locate the function in the Application Process s symbol table then the RULE is considered to have failed.

In executing the report rule the DCM will first evaluate the prerequisite spellCheck rule. In evaluating the spellCheck rule the DCM will first evaluate the libspell.so rule. In evaluating the libspell.so rule the DCM will not find any prerequisites of the rule and will therefore attempt to bind the libspell.so rule name. The binding method will match using the SHARED LIBRARY BINDING METHOD and the name libspell.so will be BOUND to a shared library. In evaluating the SHARED.OBJECT rule the DCM will recognize that the spellCheck rule name is to be interpreted as a function available in the shared library libspell.so. If the method for the rule is to be executed then the spellCheck shared object is extracted from the shared library and is invoked as a function of the Dynamically Configured Application Program.

The DCM can exist as a co process of the Application Process or as a sibling process of the Application Process. In the former sense the DCM can be accessed by multiple Application Programs thus providing a sharing of information. In the later case the DCM resides within the Application Process. There are no constraints inherent in the model to preclude the use of the DCM across multiple computer systems.

A Word Processing Application Program is designed. Using a standard software construction utility converting the source code to the Application Program which in turn is sold to end users. After the initial market acceptance of the Word Processing Application Program additional features are developed including a Thesaurus a Spell Checking Feature and a Grammar Checking Feature. Each of these features is designed developed implemented and sold as separate Minor Services for the Word Processing Application Service.

When a user purchases the Word Processing Application Program the installation process creates a Application Program Rules file for the Word Processing Application Service. The Rules file contains 

The Application Program Rules file is then given to the DCM to establish the rules for the Dynamically Configured Application Program. When executed the APINIT rule is evaluated which causes the SetEnvironment rule to be evaluated which in turn causes the setEnv rule to be evaluated. The setEnv rule has a THREAD prerequisite causing the DCM to begin the procedure named setEnv as a thread of execution within the Application Process. Similarly the wp and clearEnv rules when evaluated will cause the DCM to create a thread of execution within the Application Process for their named procedures.

The user subsequently purchases the Spell Checker feature and the Thesaurus but not the Grammar Checking Feature. The installation of the Spell Checking Feature and the Thesaurus Feature cause the Application Program Rules file for the Word Processing Application Service to be modified as follows 

When the Dynamically Configured Application Program is executed the following actions are taken by the DCM 

The APINIT rule is evaluated. In evaluating the rule the setEnv setSpellEnv procedure from the spell.so shared library and the setThesEnv procedure from the thes.so shared library will both be executed during the evaluation of the APINIT rule. It is presumed that these procedures will modify the Application Process s data structures to identify their existence to the wp thread.

In this manner individual components of an Application Service are designed implemented and subsequently sold as individual units to the end user.

The Configurable Application Process Service is a computer software method for dynamically administering the component Minor Services of an Application Process. The Configurable Application Process Service consists of a Configuration Administrator Minor Service thread using the Communication Manager Program Service hereinafter referred to as the CMPS described in this patent application. Various other Minor Service threads may be created by the Configuration Administrator as described herein.

The Application Process uses the Configuration Administrator Minor Service hereinafter referred to as the CAMS to administer zero or more components of software. Each component is said to offer a well defined application Minor Service hereinafter singularly and collectively referred to as the AMS.

The specifications for the administration of the AMS can be provided directly by an Application Process or indirectly through a data store monitored by the CAMS. These specifications can instruct the CAMS to perform the desired operation immediately at a predefined time which may be an interval or as a result of sbme event which is later communicated to the CAMS.

Other technology which may be configured with the Configurable Application Process Service includes the Binding Service as described in this patent application hereinafter referred to as the BSV.

There are fifteen general operations available through the Configurable Application Process Service given as 

The LOCATE operation instructs the Configurable Application Process Service to locate a specified AMS. The default action performed by the CAMS is to search through the current Application Process for the specified AMS and if not found to search through zero or more specified shared libraries. Once located the CAMS returns the location of the specified AMS.

When used in conjunction with the CMPS the CAMS will also attempt to locate the specified AMS as a registered communication point.

When used in conjunction with the Binding Service the CAMS will also attempt to locate the specified AMS according to the specified rules for binding as defined in the BSV.

The LOAD operation instructs the Configurable Application Process Service to dynamically configure a specified AMS. The default action of the CAMS is to dynamically load the specified AMS if the AMS had not previously been loaded. Alternatively the Application Process can request that the Configurable Application Process Service to force the LOAD to be completed even if there is a previously loaded version of the specified AMS.

When used in conjunction with the CMPS the CAMS will register the specified AMS as a communication point if it has not already been registered. Note that when used with the CMPS the AMS may not be loaded into memory but simply marked as a communication point within the CMPS. In this sense the AMS is considered to have been configured by the LOAD operation.

Note that the LOCATE operation can be combined with the LOAD operation to provide a single operation performing the desired functionality.

Once loaded the specified AMS is added to the LOADED AMS List maintained by the Configurable Application Process Service.

During the LOAD operation the Application Process can specify certain attributes describing characteristics of the specified AMS. These attributes may include but are not limited to the following 

Note that the actions associated with the LOAD operation can be deferred until the receipt of a specified event by the Configurable Application Process Service. If the action is to be deferred the request is added to the EVENT AMS List maintained by the CAMS and no further action is taken by this operation.

The EXECUTE operation instructs the Configurable Application Process Service to begin the execution of a specified AMS. The specified AMS must have previously been configured with the LOAD operation.

The CAMS uses the CMPS to establish the necessary connectivity to the specified Minor Service. The communication primitives used by the CMPS are determined in part by the COMPRIMS operation described below.

Note that the actions associated with the EXECUTE operation can be deferred until the receipt of a specified event by the Configurable Application Process Service. If the action is to be deferred the request is added to the EVENT AMS List maintained by the CAMS and no further action is taken by this operation.

Note that the Application Process can specify the desired scope of the AMS to be executed. The scope must be specified as 

In either event the Configurable Application Process Service maintains a reference for the number of executions of the AMS currently in use.

The REPLACE operation specifies that the Configurable Application Process Service is to replace a specified ACTIVE AMS with a different specified AMS. The existing AMS must have been started using the EXECUTE operation thus must appear on the ACTIVE AMS List . The REPLACE operation searches the ACTIVE AMS List for the specified AMS to replace. If not found then the operation is aborted. The new AMS replacing the existing AMS must have previously been configured with the LOAD operation and must therefore appear in the LOADED AMS List.

The CAMS will replace the existing AMS with the new AMS and reroute the communications previously destined for the existing AMS to the new AMS.

The Application Process must specify the disposition of the existing AMS which describes to the Configurable Application Process Service what is to happen to the existing AMS upon replacement by the new AMS. The disposition can be one of 

Details on the REPLACE operation are provided in the section titled Replace Operation Detailed Architecture. 

Note that the actions associated with the REPLACE operation can be deferred until the receipt of a specified event by the Configurable Application Process Service. If the action is to be deferred the request is added to the EVENT AMS List maintained by the CAMS and no further action is taken by this operation.

The SUSPEND Operation specifies that the Configurable Application Process Service is to temporarily suspend the execution of the specified AMS which was previously invoked through the EXECUTE operation and can be found on the ACTIVE AMS List. Note that the actual suspension may be implemented differently on various computer systems depending on the lower level operating system instructions available for the implementation. Regardless however the SUSPEND Operation is guaranteed to suspend the execution of the specified AMS. Once suspended the specified AMS is moved from the ACTIVE AMS List to the SUSPENDED AMS List.

Note that the actions associated with the SUSPEND operation can be deferred until the receipt of a specified event by the Configurable Application Process Service. If the action is to be deferred the request is added to the EVENT AMS List maintained by the CAMS and no further action is taken by this operation.

The RESUME Operation specifies that the Configurable Application Process Service is to resume the execution of an AMS previously suspended with the SUSPEND operation. Once resumed the AMS is moved from the SUSPENDED AMS List to the ACTIVE AMS List.

Note that the actions associated with the RESUME operation can be deferred until the receipt of a specified event by the Configurable Application Process Service. If the action is to be deferred the request is added to the EVENT AMS List maintained by the CAMS and no further action is taken by this operation.

The DUMP.sub. MAP operation specifies that the Configurable Application Process Service is to send a DUMP.sub. MAP request to the specified AMS. The specified AMS must currently be on the ACTIVE AMS List.

The CAMS will allocate a storage area referred to as the MAP AREA for the specified AMS and associate an identifier with this MAP AREA. The CAMS will mark the MAP AREA with administrative information including but not limited to the specific machine architecture on which the specified AMS is currently executing timing information security information to prevent unauthorized access to the MAP AREA ownership information indicating the specified AMS as the owner of this MAP AREA and other information.

It is expected that upon receipt of the DUMP.sub. MAP request the AMS will write to the MAP AREA that information described by its MAP AREA attributes. This data is written in a machine independent format.

The Application Process can specify to the CAMS the persistence criteria for this MAP AREA. This information is used to determine when the CAMS is de allocate the MAP AREA. The options are to keep the MAP AREA until the specified AMS terminates with the TERMINATE Operation or to keep the MAP AREA until a LOAD.sub. MAP Operation specifying this MAP AREA is issued by the Application Process

The DUMP.sub. MAP Operation upon completion informs the Application Process of the identifier associated with MAP AREA.

The LOAD.sub. MAP operation specifies that the Configurable Application Process Service is to send a LOAD.sub. MAP request to the specified AMS. The operation requires the specification of a particular MAP AREA to be loaded. The specification of the MAP AREA may be through the identifier assigned during a DUMP MAP operation or specified values supplied by the Application Process.

Once the LOAD.sub. MAP operation has completed the CAMS determines if the specified MAP AREA is to be de allocated based on the persistence value set by the DUMP.sub. MAP operation and if necessary will de allocate this MAP AREA.

The TERMINATE operation specifies to the Configurable Application Process Service that the execution of the specified AMS is to be terminated. In performing the termination the Configurable Application Process Service will decrement the reference count associated with that AMS. If the reference count is non zero then other instances of the AMS are still in use. If the AMS was executed with a PUBLIC scope and the AMS reference count is non zero then no additional action is required by the Configurable Application Process Service. Upon termination the AMS is removed from the ACTIVE AMS List.

All pending communications to the specified AMS are de allocated according to the De allocation Attribute specified during the LOAD Operation for the specified AMS. Note that in certain cases this may result in the pending communications remaining untouched and not being de allocated

When used in conjunction with the CMPS the communications to the specified AMS will be terminated through a disconnect operation supplied by the CMPS.

Note that the actions associated with the TERMINATE operation can be deferred until the receipt of a specified event by the Configurable Application Process Service. If the action is to be deferred the request is added to the EVENT AMS List maintained by the CAMS and no further action is taken by this operation.

The NOTIFICATION operation specifies to the Configurable Application Process Service that a particular internal or external event has occurred. The Configurable Application Process Service searches the EVENT AMS List to determine the any actions it is to perform based on the receipt of this event and then performs these actions.

The INSERT operation specifies that the Configurable Application Process Service is to insert the specified AMS between two specified AMS s previously started with the EXECUTE operation. Note that the specified AMS being inserted must appear in the ACTIVE AMS List.

Note that the actions associated with the INSERT operation can be deferred until the receipt of a specified event by the Configurable Application Process Service. If the action is to be deferred the request is added to the EVENT AMS List maintained by the CAMS and no further action is taken by this operation.

The EXTRACT operation is the inverse of the INSERT operation. It specifies that the Configurable Application Process Service is to extract a specified AMS from between two other specified AMS s. Note that the Application Process can specify the disposition of the extracted AMS which must be one of 

Note that the actions associated with the EXTRACT operation can be deferred until the receipt of a specified event by the Configurable Application Process Service. If the action is to be deferred the request is added to the EVENT AMS List maintained by the CAMS and no further action is taken by this operation.

The COMPRIMS operation specifies the default communication primitives to be used by the Application Process when communicating with an AMS. Note that the Communication Manager can adjust these primitive specifications as necessary to ensure the proper communication link between the Application Process and the AMS. Note further that any existing communication links created prior to the execution of this operation remain untouched. In this manner the Application Process can reset its default communication primitive as needed.

The UNLOAD operation specifies that the Configurable Application Process Service is to unload the specified Minor Service from memory. The specified Minor Service cannot currently be on the ACTIVE AMS List or the operation is aborted. The specified Minor Service is then removed from the LOADED AMS List.

The QUERY operation specifies that the Configurable Application Process Service is to report specified information based on the current lists that it maintains. This information may include for example the list of all outstanding requests pending on the receipt of an event. This information is then made available to the Application Process.

An AMS may be executing as a separate thread of execution either locally on the same machine as the CAMS or remotely on a machine accessible to that machine on which the CAMS is executing. To replace this AMS with another AMS the default actions taken by the Configurable Application Process Service is given as 

Note that Step 2 is performed using the Thread Communication Switching Service described in this patent application.

An example of an Application Process using a Primary Service and three Minor Services is shown in . Here the Primary Service communicates with each of the Minor Services using a communication link provided by the CMPS. See . 

To reconfigure the Application Program to use AMS D in place of AMS C a REPLACE operation is applied. Upon receipt of this request the CAMS will temporarily suspend the input channel to AMS C from the Primary Service . It then loads AMS D. The input channel to AMS D is then established from the Primary Service as a replacement for input channel to AMS C. The CAMS then applies the specified disposition to AMS C. See . 

A Named Execution Environment hereinafter referred to as NEE is an execution environment created by the Named Execution Environment Manager on behalf of a requesting Application Process. The Application Process requesting the creation of the NEE is referred to as the Owner of the NEE. The Application Process does not know nor cares where the NEE is physically located only that the binding of the NEE to the physical execution environment by the Named Execution Environment Manager satisfies the REQUESTED ATTRIBUTE expression as specified by the Owner of the NEE. Through the creation process the Owner of the NEE specifies a logical name to be associated with the NEE and provides additional attributes describing the usage of the NEE. All subsequent references to the NEE by the Owner of the NEE or by other Application Processes specify the logical name of the NEE the operation to be performed and other parameters to be used. The underlying physical connectivity and physical information passing is then handled by the Named Execution Environment Manager.

A user or Application Process of a computer system registers with the Named Execution Environment Manager hereinafter referred to as the NEEM a set of one or more attributes describing an environment available on the computer system. These attributes known as the REGISTERED ATTRIBUTES may include but are not limited to those shown in Table 11.

Multiple REGISTERED ATTRIBUTES SETS can be registered for a single computer system. The REGISTERED ATTRIBUTES along with the name of the computer system are stored in memory or on a storage media accessible to the computer system on which the NEEM is executing. A permanent copy of the REGISTERED ATTRIBUTES along with their computer system name can be stored in the Named Execution Environment Configuration File hereinafter referred to as the NEECF. stored in memory or on a storage media accessible to the computer system on which the NEEM is executing. A permanent copy of the REGISTERED ATTRIBUTES along with their computer system name can be stored in the Named Execution Environment Configuration File hereinafter referred to as the NEECF.

The NEEM executes as a co process of the Application Process. As such the Named Execution Manager the NEEM is either linked with the Application Program directly either through static or dynamic linkage is executed as a separate process on a computer system accessible to the computer system executing the Application Process or is invoked through the Dynamic Configuration Management described in this patent application.

In any case when the NEEM is executed it reads the NEECF detailing the REGISTERED ATTRIBUTES describing the computer system. Note that additional REGISTERED ATTRIBUTES can be subsequently added registered deleted or otherwise modified even after the NEEM is executing.

The entries in the NEECF may include specifications identifying remote computer system accessible to the current computer system through some form of communications mechanism. Such an entry includes information detailing if the remote computer system is expected to have a NEEM executing on it and or if there is a NEECF located on that computer system.

The NEEM creates a Minor Service thread known as the NEEM STATUS THREAD to periodically poll the remote computer systems identified in the NEECF and performs a statistical analysis to determine their state. If a remote computer system fails or if the communications between the local computer system and the remote computer system fails then the NEE Status Thread will mark the remote computer system as UNACCESSIBLE by the NEEM. At such time as the NEE Status Thread can re establish contact with the failed remote computer system the NEEM will mark the computer system as ACCESSIBLE by the NEEM.

Initially each entry of the NEECF is read by the NEEM and its corresponding NEE is placed on an INACTIVE NEE List maintained by the NEEM. As new Named Execution Environments are created the NEEM adds them to the ACTIVE NEE List.

The Application Process makes a request to create a new NEE by specifying in a Boolean Expression one or more REQUESTED ATTRIBUTES. The Application Process also specifies one or more NEE ATTRIBUTES including but not Limited to 

The NEEM searches the REGISTERED ATTRIBUTE entries for an environment satisfying the REQUESTED ATTRIBUTES set forth by the Application Process. When a match has been found then the NEEM will establish a shell on the associated computer system to execute the requests of the Application Process. The newly created environment then becomes an ACTIVE NEE and is added to the ACTIVE NEE List maintained by the NEEM.

Note that if the REQUESTED ATTRIBUTES can be satisfied by an ACTIVE NEE with a PUBLIC NEE ATTRIBUTE then the NEEM will simply alias the specified logical name with the previous specified logical name of the current ACTIVE NEE satisfying the request. The reference count associated with this ACTIVE NEE is then incremented.

Just prior to executing the shell Application Process associated with a new ACTIVE NEE the NEEM will arrange for the standard input the standard output and the standard error file descriptors to be redirected to from the NEEM itself. In this manner the NEEM will be able to appropriately redirect all I O requests on this file descriptors appropriately. The NEEM will also establish Minor Service Reader Writer threads to read the standard output and standard error file descriptors and to redirect this output to the appropriate Application Process making a request to execute in the ACTIVE NEE. This is shown in .

An Application Process can request the NEEM to execute a request in a specific NEE by specifying the logical name of the NEE. The NEEM will look up the logical name in its ACTIVE NEE List and will send the request to that named environment. At this point the Application Process is considered ATTACHED to the logically named NEE and can read its standard output and its standard error through the NEEM. When the NEEM determines that the request has completed the NEEM will automatically DETACH the Application Process from the logically named NEE.

Using a standard Application Programming Interface the Application Process can read the standard output of the logically named NEE to which it is ATTACHED. This is accomplished by the Minor Service Reader Writer Thread of the NEEM that is reading the actual standard output of the NEE. It will send the standard output to the Application Process. Likewise the Minor Service Reader Writer Thread of the NEEM which reads the actual standard error will send the standard error output to the Application Process.

There are a series of commands understood by the NEEM through which the Application Process can control the use of a logically named NEE. These include 

The owner of the Named Execution Environment can terminate the Named Execution Environment by sending a TERMINATE request to the Named Execution Environment Manager.

The application program defines a set of states describing a state machine with exactly one start state and potentially many different end states. The application then attaches a datum to the State Machine. The State Machine Thread Manager then administers the transition of this datum through the state machine.

For each defined state there is a corresponding state thread. When a datum enters a particular state the State Machine Thread Manager invokes the State Thread as a separate thread of execution. The exiting value of this State Thread is then used to determine the next transition from the current state. In this manner various datums may simultaneously be attached to the same Multithreaded State Machine and the State Machine Thread Manager will administer and synchronize their transitions simultaneously.

Finally the State Machine Thread Manager provides a special Error state to which a datum will transition when the exiting value of the State Thread is undefined in the current state machine.

Software construction is the process of compiling source code components to produce a binary representation. In this instance a rule specification of the form 

action is specified to show that a target is dependent on prerequisites. If one or more of the prerequisites are newer than the target then the action is triggered to construct the target. Each prerequisite can be listed as a target of another rule. As an example consider 

In this example the rule to construct the target A shows it has a dependency on prerequisites B and C . Note however that B is dependent on b according to the second rule and that C is dependent on c based on rule 3. If c has changed since the last time C was constructed then the action for rule 3 would be triggered to reconstruct C. Similarly if b has changed since the last time B was constructed then the action for rule 2 would be triggered to reconstruct B. Note that the action for rule 2 and the action for rule 3 could in fact occur simultaneously since there are no other dependencies on these rules. After rule 2 and rule 3 has completed then rule 1 can continue. Here if B or C has changed since the last time A has been constructed then the action for rule 1 will be triggered to reconstruct A.

Using a procedural language the algorithm to provide this service can be specified as shown in Using a state machine representation the same algorithm would be given according to .

