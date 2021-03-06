---

title: System for virtualisation monitoring
abstract: A system for virtualization monitoring is provided as a hardware interface provided on a physical machine supporting a virtualization layer. The interface comprises an indication of the state of virtualization on the physical machine to monitor any virtual machines running on the physical machine. The interface also comprises means for interacting with the virtualization layer, for example for activating a maintenance mode by a migration of virtual servers running on a physical machine.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09501305&OS=09501305&RS=09501305
owner: Inernational Business Machines Corporation
number: 09501305
owner_city: Armonk
owner_country: US
publication_date: 20090408
---
This invention relates to the field of virtualization systems. In particular the invention relates to virtualization monitoring and display of virtualization status on a physical machine.

Physical computing machines comprise liquid crystal display LCD or light emitting diode LED panels to indicate hardware related status information for example central processing unit memory etc . While virtualization becomes standard across all platforms there is no visual status indication for virtualization events or errors. Many users rely strongly on visual error indications.

System downtime is a serious overhead which must be minimized. There is no way for a technician to determine whether a physical system is running virtual servers by sight. Advanced administration skills are required to determine operating status of one or more virtual servers. Additionally there is no way for a technician to interact with virtual systems locally without administration access. For example a common requirement for virtual system interaction is to vacate physical systems of virtual workload s .

Known virtualization systems do not have an interface between the user and the physical hardware to monitor virtual system status and interact with virtual systems. Accordingly there is a need for an interface that supports management of one or more virtual systems.

The invention comprises a system method and article for resolving management of virtual serves through one or more status indicators.

In one aspect of the present invention there is provided a system for virtualization control comprising a hardware interface provided on a physical machine to support a virtualization layer. The interface comprises an indication of the state of virtualization on the physical machine to monitor any virtual machines running on the physical machine.

In another second aspect of the present invention a method is provided for virtualization control comprising monitoring a virtualization layer on a physical machine and displaying externally to the physical machine indicators of the status of any virtual machines active on the physical machine.

In yet another aspect of the present application a computer program product is provided stored on a computer readable storage medium for virtualization control comprising computer readable program code for monitoring a virtualization layer on a physical machine and displaying externally to the physical machine indicators of the status of any virtual machines active on the physical machine.

Other features and advantages of this invention will become apparatus from the following detailed description of the presently preferred embodiment of the invention taken in conjunction with the accompanying drawings.

It will be appreciated that for simplicity and clarity of illustration elements shown in the figures have not necessarily been drawn to scale. For example the dimensions of some of the elements may be exaggerated relative to other elements for clarity. Further where considered appropriate reference numbers may be repeated among the figures to indicate corresponding or analogous features.

In the following detailed description numerous specific details are set forth in order to provide a thorough understanding of the invention. However it will be understood by those skilled in the art that the present invention may be practiced without these specific details. In other instances well known methods procedures and components have not been described in detail so as not to obscure the present invention.

System virtual machines sometimes called hardware virtual machines allow multiplexing the underlying physical machine between different virtual machines VMs each running its own operating system. The software layer providing the virtualization is called a virtual machine monitor or hypervisor. A hypervisor can run on hardware Type 1 or native VM or on top of an operating system Type 2 or hosted VM .

The main advantages of system VMs are multiple OS environments can co exist on the same computer in strong isolation from each other and the virtual machine can provide an instruction set architecture ISA that is somewhat different from that of the real machine. Multiple VMs each running their own operating system called guest operating system are frequently used in server consolidation where different services that used to run on individual machines in order to avoid interference are instead run in separate VMs on the same physical machine.

Referring to a block diagram shows an example embodiment of a system including native virtualization support. A physical server has a hardware platform . A virtualization layer runs on the hardware platform as an operating system control program and abstracts the processor memory storage and network resources into multiple virtual machines . Guest operating systems can run on each of the virtual machines . A virtual management application or console manages the virtualization layer via web services.

Referring to an exemplary computer system for implementing a physical server comprises a data processing system suitable for storing and or executing program code including at least one processor coupled directly or indirectly to memory elements through a bus system . The memory elements can comprise local memory employed during actual execution of the program code bulk storage and cache memories which provide temporary storage of at least some program code in order to reduce the number of times code must be retrieved from bulk storage during execution.

The memory elements may comprise system memory in the form of read only memory ROM and random access memory RAM . A basic input output system BIOS may be stored in ROM . System software may be stored in RAM including operating system software . Software applications may also be stored in RAM .

The system may also comprise a primary storage such as a magnetic hard disk drive and secondary storage such as a magnetic disc drive and an optical disc drive. The drives and their associated computer readable media provide non volatile storage of computer executable instructions data structures program modules and other data for the system . Software applications may be stored on the primary and secondary storage means as well as the system memory .

The computing system may operate in a networked environment using logical connections to one or more remote computers via a network interface .

Input output devices can be coupled to the system either directly or through intervening I O controllers. A user may enter commands and information into the system through input devices such as a keyboard pointing device or other input devices including but not limited to a microphone a joy stick game pad a satellite dish a scanner or the like. Output devices may comprise speakers printers etc. A display device is also connected to system bus via an interface such as video adapter .

Referring to a system is shown and described providing a physical display interface for displaying virtualization status and events allowing a user to monitor and interact with a virtualization layer directly on a physical system . The physical display interface may be provided external to the physical system such as an external component to associate with the physical system allowing easy access to the interface . In one embodiment the interface may be an integrated panel in a physical machine. Similarly in a further embodiment the hardware interface may be implemented by utilising existing indicators and control means of a physical machine.

The system comprises a physical server with a virtualization layer running multiple guest operating systems . The server is connected to a virtualization management application for example via a network.

An interface application in the form of an agent is provided residing in the management partition of the virtualization layer . The interface application interacts with a virtualization management application to initiate actions and detect status changes. A virtualization layer provides an application programming interface APIs for interaction for example for entering a maintenance mode so the interface application can communicate with the API of the virtualization layer .

The interface application resides in a management partition of a virtualization layer . For example the management partition may be Console OS for VMware domain 0 for Xen Xen is a trade mark of XenSource Inc. or Parent Partition for Microsoft Hyper V Hyper V is a trade mark of Microsoft Corporation . The interface application is specific to each type of virtualization layer .

The interface application may be provided as a plug in or extension to the management partition of virtualization layer which can be added to provide the means for driving the physical display interface and providing a link between the host system management hardware software and the virtualization management application .

A physical display interface or panel is provided for displaying virtualization status and events. The display interface interacts with the interface application via the server s system management hardware or software .

The interface application communicates and interacts with the central virtualization management application . For example the virtualization management application may be VMware VirtualCenter or Microsoft Systems Center Virtual Machine Manager. The interface application also reacts to physical system events. In one embodiment this may be through the systems management hardware or adapter. Alternatively in one embodiment this may be though system management software such as the IBM director agent.

The interface application drives the physical display interface reflecting the virtualization status. The interface application sends commands to the management partition of the virtualization layer in order to execute virtualization related actions instigated via the display interface for example maintenance mode.

The display interface comprises monitoring means including display means such as light indicators and number displays and control means such as buttons for initiating interaction with the virtual environment.

As an example in the event of a critical hardware alert the virtualization layer will automatically be put into maintenance mode through the following procedure which is displayed using the display interface . A systems management alert is passed to the systems management hardware or software which is passed to the virtualization management application which is passed to the display agent via the interface application .

An example display interface is shown in . The display interface comprises monitoring means including a number of LEDs and alphanumeric displays indicating major virtualization related statuses and errors. For example the monitoring means comprises an indication of how many if any virtual machines are running on the system and indication of the host name. The monitoring means also comprises an indication of the status of management communication . The display interface shown in is based on a VMware server and the monitoring means also comprises indications of the status of the modes of predictive failure alert PFA protect distributed resource scheduler DRS and high availability HA service .

The display interface also comprises a control means which in this example is a button for interaction with the virtual environment. In this example the button is a maintenance mode button which allows a technician to put a system into a safe maintenance mode ensuring all workload has been migrated to alternative virtualization hosts. The changing status can be indicated for example by an LED frame around the button or a separate indicator providing an indication such as changing from red flashing to green.

Referring to a flow diagram shows an example interaction by a user with the virtualization environment using a display interface as described.

A user activates a control means on the interface to activate a maintenance mode in the virtualization environment. In one embodiment the control means may be activated by pressing a button or actuating a switch. A virtualization management console for example in VMware the VMware VirtualCenter in VirtualIron the VirtualIron Virtualization manager etc. is notified of the activation and an indicator indicates the activation for example by flashing red . The virtualization management console initiates the maintenance mode and migrates the virtual servers.

It is determined if the host is in maintenance mode. If not the determination repeats until the host is in maintenance mode. When the host is in maintenance mode the display interface sets the indicator to a color indicating the mode . In one embodiment the color green is employed on the interface as an indicator of the maintenance mode.

In one embodiment the virtualization management console can also provide notification of an event and the display interface is changed to indicate the event.

Users like the ability to see the state of hardware from the outside casing of a server. As the use of virtualization is becoming greater an indication of the status of the virtual machines running on a server is required. Users administrators engineers etc. are able to determine the virtual status of a physical system by looking at the display interface and will also be able to interact with the virtual management system through the display interface. This interaction can be carried out without integration into the wider system s management infrastructure.

As an example of the advantage of such an external physical interface an engineer may need to work on a physical machine which hosts multiple virtual machines. Using the external physical interface he can see the number of virtual machines running on the physical machine and can bring the system down to vacate the host by activating a maintenance mode via the physical interface. Once the physical interface indicates that the host is in maintenance mode and all the virtual machines have been vacated the engineer can carry out the required work or maintenance.

The invention can take the form of an entirely hardware embodiment an entirely software embodiment or an embodiment containing both hardware and software elements. In an embodiment the invention is implemented in software which comprises but is not limited to firmware resident software microcode etc.

The invention can take the form of a computer program product accessible from a computer usable or computer readable medium providing program code for use by or in connection with a computer or any instruction execution system. For the purposes of this description a computer usable or computer readable medium can be any apparatus that can contain or store the program for use by or in connection with the instruction execution system apparatus or device.

The medium can be an electronic magnetic optical or semiconductor system or apparatus or device . Examples of a computer readable medium comprise a semiconductor or solid state memory magnetic tape a removable computer diskette a random access memory RAM a read only memory ROM a rigid magnetic disk and an optical disk. Current examples of optical disks comprise compact disk read only memory CD ROM compact disk read write CD R W and DVD.

It will be appreciated that although specific embodiments of the invention have been described herein for purposes of illustration various modifications may be made without departing form the spirit and scope of the invention. In particular the interface may include means for interacting with the virtualization layer including but not limited to means for activating a maintenance mode by migrating the virtual servers running on a physical machine. Additionally the method may employ an interface application provided in the virtualization layer for communication with a virtualization management application and for driving the hardware interface. Interfacing with a virtualization management application may include monitoring a virtual machine and or interacting with a virtual machine. Accordingly the scope of protection of this invention is limited only by the following claims and their equivalents.

