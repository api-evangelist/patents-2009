---

title: Image forming device, and activation method, activating or deactivating program on package basis
abstract: An image forming device includes an information storage part which stores sales package information and function package information. A function package information updating part increments, when activation of a sales package is performed, an activation component number of each of program components of the sales package in the function package information, and sets a flag of one of the program components to an activated state when the flag of one of the program components prior to the activation indicates a deactivated state. A starting information updating part registers a component identifier of one of the program components into starting information when the flag of one of the program components is changed from the deactivated state to the activated state by the activation.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08363252&OS=08363252&RS=08363252
owner: Ricoh Company, Ltd.
number: 08363252
owner_city: Tokyo
owner_country: JP
publication_date: 20090624
---
This invention relates to an image forming device which starts program components contained in a sales package when the sales package is activated.

In an information processing device which executes programs to perform various functions the number of the functions of the information processing device can be increased or decreased according to the increase or decrease of the number of programs installed therein. Even after the information processing device is purchased a user can use an additional desired function on the information processing device if a program which provides the desired function is purchased and installed in the information processing device.

As for some programs activation of the programs in an information processing device must be performed at a time of installation of the programs or after the time of the installation in order to enable the functions provided by the programs to be effectively used on the information processing device. This activation is to perform an operation that licenses the user to use the program on the information processing device or to generate license information that certifies the license and store the license information in a predetermined server or information processing device. Refer to Japanese Laid Open Patent Publication No. 07 110767.

By the activation method disclosed in Japanese Laid Open Patent Publication No. 07 110767 a program ID which identifies a program is contained in the license information and stored in the predetermined server or information processing device. If an unauthorized person attempts to install the program with the program ID in a secondary information processing device the predetermined server or information processing device detects the program ID contained in the license information and inhibits the unauthorized person from activating the program in the secondary information processing device. Hence the unauthorized person cannot use the function provided by the program on the secondary information processing device.

Therefore if the activation method of Japanese Laid Open Patent Publication No. 07 110767 is applied activation of respective programs in a secondary information processing device is inhibited by the predetermined server or information processing device. Even if all the respective programs are installed beforehand in the original information processing device it is possible to prevent each of the programs from being illegally used regardless of whether the programs are actually purchased.

Moreover Japanese Laid Open Patent Publication No. 2006 279935 discloses an information processing device wherein license information of a user is stored in a removable recording medium and when the removable recording medium is inserted in the information processing device the user is permitted to use the information processing device. In this information processing device the authentication information of a recording medium is further stored in the information processing device.

By the information processing device disclosed in Japanese Laid Open Patent Publication No. 2006 279935 it is possible to prevent an unauthorized person from copying the license information or using the information processing device.

When activation of the programs installed beforehand is performed the operation of performing activation of each of the respective programs one by one in accordance with the demanded function is troublesome.

For example there is a method of sales in which a package containing a plurality of programs is purchased. There is a set of application programs which can be effectively used as a result of association of some of functions provided by a plurality of programs of a sales package.

In this case the user has to perform activation of corresponding programs from among the plurality of programs of the sales package individually and in many cases selection of the programs to be activated from among the plurality of programs by the user becomes a difficult task.

In one aspect of the invention the present disclosure provides an improved image forming device in which the above described problems are eliminated.

In one aspect of the invention the present disclosure provides an image forming device which is able to perform activation of a plurality of programs for each sales package and able to easily set up the activation or deactivation of each of the plurality of programs.

In an embodiment of the invention which solves or reduces one or more of the above mentioned problems the present disclosure provides an image forming device which starts one or more program components contained in a sales package and registered in starting information at a time of activation of the sales package the image forming device including an information storage part to store sales package information in which a first flag indicating an activated or deactivated state of a sales package and a component identifier of each of one or more program components contained in the sales package are registered and to store function package information in which an activation component number indicating the number of program components activated by the activation among purchased program components and a second flag indicating an activated or deactivated state of each of the one or more program components are registered a function package information updating part to increment when activation of the sales package is performed the activation component number of each of the one or more program components registered in the function package information and to set the second flag of one of the one or more program components to an activated state when the second flag of the one of the one or more program components prior to the activation indicates a deactivated state and a starting information updating part to register a component identifier of one of the one or more program components into the starting information when the second flag of the one of the one or more program components is changed from the deactivated state to the activated state by the activation.

In an embodiment of the invention which solves or reduces one or more of the above mentioned problems the present disclosure provides an activation method activation method of an image forming device which starts one or more program components contained in a sales package and registered in starting information at a time of activation of the sales package and includes an information storage part which stores sales package information in which a first flag indicating an activated or deactivated state of a sales package and a component identifier of each of one or more program components contained in the sales package are registered and stores function package information in which an activation component number indicating the number of program components activated by the activation among purchased program components and a second flag indicating an activated or deactivated state of each of the one or more program components are registered the activation method including incrementing by a function package information updating part of the image forming device when activation of the sales package is performed the activation component number of each of the one or more program components registered in the function package information and setting the second flag of one of the one or more program components to an activated state when the second flag of the one of the one or more program components prior to the activation indicates a deactivated state and registering by a starting information updating part of the image forming device a component identifier of one of the one or more program components into the starting information when the second flag of the one of the one or more program components is changed from the deactivated state to the activated state by the activation.

Other objects features and advantages of the present invention will become more apparent from the following detailed description when read in conjunction with the accompanying drawings.

A description will be given of embodiments of the invention with reference to the accompanying drawings.

In the state illustrated in only a sales package A is first activated. A function package and a function package which are contained in the sales package A are activated. A function package and a function package are contained in a sales package B. Because activation of the sales package B is not performed the function package is in a deactivated state. In starting information function packages which can be started by the image forming device are registered. Therefore only the function package and the function package are registered in the starting information .

On the other hand when activation of the sales package B is performed as in the function package is also activated. Then the function package is newly registered in the starting information . Because the function package contained in the sales package B is already activated it is not newly added to the starting information .

The image forming device of this embodiment can perform activation of each sales package and thereby activate a plurality of function packages which correspond to a plurality of plug in components which can be effectively used as a result of association of some of functions provided by the plurality of programs of the sales package. When performing activation of the purchased programs confusion of the user in the selection of the programs to be activated can be avoided.

In this embodiment installation of a plug in component means that the plug in component is stored in a storage unit of the image forming device and activation of a plug in component means that a state where the plug in component stored in the storage unit is changed to a state where the plug in component can be started with starting of the image forming device .

Conversely in this embodiment uninstallation of a plug in component means that the plug in component is erased from the storage unit of the image forming device and deactivation of a plug in component means that a state of the plug in component is changed to a state where the plug in component is not started if the image forming device is started.

Installation and activation may be performed simultaneously and uninstallation and deactivation may be performed simultaneously.

The image forming device is connected to the license server via a network which is for example the Internet or an LAN local area network .

For example the license server is constructed by a computer including a CPU a RAM a ROM a non volatile memory a communication device an input output interface etc. which are interconnected by a bus. The license server creates a license file which will be described later.

For example the image forming device is constructed by a multi function peripheral MFP which includes one or more functions of a printer a copier a facsimile and a scanner. Although the image forming device includes hardware elements specific to image forming devices such as a printing part and a scanner part the image forming device may be considered an information processing device in performing one or more plug in components . Therefore the installing method of plug in components by the image forming device of this embodiment is suitably applicable to an information processing device which is not provided with a printing function.

The information processing device provided by the image forming device in this case includes a CPU a main storage an auxiliary memory a non volatile memory a communication device which is linked to a network a recording medium I F to which a recording medium is attached an input device which includes a keyboard and a mouse and a display control part which displays an image on a display device which are interconnected by a data bus.

The image forming device of this embodiment includes a controller a plotter a scanner a fax control unit and another hardware resource which are interconnected by a serial inter bus such as a PCI bus a PCI X bus or PCI Express. An operation panel is connected to the controller . A storage medium memory card which stores an activation management program is detachably attached to the controller .

The controller is a control part which controls the whole image forming device . The controller controls various processes which include reading of documents printing facsimile transmitting receiving inputting of messages from the operation panel etc. by using the fax control unit the plotter the scanner and the hardware resource .

The plotter is constructed by a monochrome plotter and or a 1 drum color plotter. The plotter forms an image for each page based on a printing job data or image data obtained by the reading of the scanner . The image is transferred to a recording sheet. For example by using the electrophotographic printing process using a laser beam a toner image is formed on a photoconductor drum the toner image is transferred to a recording sheet and the recording sheet is subjected to heat and pressure by a fixing device so that the recording sheet is output.

The scanner optically reads a document placed on the contact glass performs the A D conversion of the reflected light performs image processing of the resulting image signal such as error diffusion and gamma conversion and transforms the processed image signal into the digital data of a predetermined resolution to generate image data.

The fax control unit is connected to a public telephone network via an NCU network control unit . The fax control unit transmits and receives a facsimile data according to the communications protocols which are in conformity with for example the G3 and G4 facsimile standards. Before transmitting the facsimile data the fax control unit performs data processing of image data such as compression and modulation. After receiving the facsimile data the fax control unit performs decompression and error correction of the received facsimile data to restore the image data.

The controller includes a CPU a north bridge NB a system memory MEM P a south bridge SB a local memory MEN C an ASIC application specific integrated circuit a hard disk drive HDD an NIC network interface card a wireless LAN I F an IEEE 1394 I F a USB host and a memory card I F . An ASP accelerated graphics port is arranged to connect the ASIC and the NB .

The CPU controls the whole image forming device through the MEM P the ASIC and the NB . The NB performs transmission control of the data which are delivered on the bus which connects the wireless USB host and others.

The NB is a bridge IC for connecting the CPU the MEM P and the AGP. The MEM P is a system memory which is used as a drawing memory in the image forming device .

The MEM C is a local memory which is used as a copy image buffer and a coding buffer. The ASIC is provided with various registers and logical circuits. The ASIC functions as a head pulse generating part. The ASIC functions as a control part of various motor drivers. Furthermore the ASIC functions as the bridge which interconnects the AGP the HDD and the MEM C respectively.

The operation panel is an operation unit which receives input information from or displays message information to the user. The operation panel includes a keyboard and a touch panel as an input part. The operation panel further includes a display device such as a LCD liquid crystal display .

The HDD is a storage part which accumulates image data programs font data and forms. The HDD may be constituted by a non volatile memory such as a flash memory MRAM magneto resistive random access memory etc. In this embodiment an activation management program which manages activation of programs is stored in the HDD .

The AGP is a bus interface for graphics accelerator cards which is adapted to accelerate graphic processing. The AGP directly accesses the system memory to accelerate processing of a graphics accelerator card with a high throughput.

The NIC is for example an Ethernet registered trademark card and performs processing in accordance with the protocols specified for the physical layer and the data link layer of the OSI basic reference model. In association with the NIC a mail application which will be described later performs processing in accordance with the upper layer protocol such as SMTP or POP3 to receive or transmit an e mail between the image forming device and the license server . Moreover a web application which will be described later performs processing in accordance with the upper layer protocol such as FTP or HTTP to receive or transmit a license file between the image forming device and the license server .

The wireless LAN I F is an interface for communicating with devices which are provided to meet the requirements of the telecommunications standards IERE 802.11 a b g. The wireless LAN I F is connected to a network such as an LAN via an access point. The IEEE 1394 I F is an interface for communicating with devices which are provided to meet the requirements of the telecommunications standards IEEE 1394. The IEEE 1394 I F may be used to establish a daisy chain connection of a plurality of devices. This interface is suitable for transmitting data with large sizes such as video data and the devices to which the IEEE 1394 I F is connected are for example a digital camera a video camera etc.

The USB host is an IC which is called a USB controller. The USB host is controlled by the device driver driver software which is executed by the CPU to constitute a USB I F. The USB host communicates with a USB memory which is inserted into the USB slot of the controller . Similarly the memory card I F communicates with a memory card which is inserted into the slot of the controller . The memory card I F is an interface for reading data from the memory card and for writing data to the memory card . The memory card is for example an SD card a multimedia card an xD card etc.

The software composition of the image forming device is connected to the plotter the scanner and the hardware resource via the hardware interface HW I F . The software composition generally includes a platform and an application layer .

As illustrated in the platform includes a control service block which interprets a processing request from the application layer and generates an acquisition request to the hardware resources a system resource manager SRM which manages one or more hardware resources and arbitrates acquisition requests from the control service block an operating system OS and an activation management part .

The control service block is constructed by a plurality of control service modules. The control service block includes an SCS system control service an ECS engine control service an MCS memory control service an OCS operation panel control service an FCS fax control service and an NCS network control service .

The platform includes an API application programming interface which receives a processing request from the application layer by the pre defined program.

The OS is a general purpose operating system such as LINUX registered trademark or UNIX registered trademark . The OS is capable of performing the respective programs of the platform and the application layer in parallel as processes respectively. The OS includes various kinds of device drivers which respectively communicate with the NIC the wireless LAN I F the IEEE 1394 I F the USB host and the memory card I F .

The SRM performs control of the system and management of the resources in association with the SCS . The process of the SRM performs scheduling of the use of the hardware resource in response to the request from the upper layer and controls operation of the hardware resource.

The process of the SCS performs management of the applications control of the operation panel displaying of the system screen displaying of the LED resource management control of the interrupting applications etc. The process of the ECS controls the engines of the hardware resources.

The process of the MCS performs acquisition and releasing of the image memory utilization of the HDD compression and decompression of image data etc. The process of the FCS provides the API for performing facsimile receiving and transmitting from the application layer of the system controller using the PSTN ISDN network registering accessing of various facsimile data stored in the backup SRAM facsimile reading facsimile receiving printing and combined transmitting receiving.

The process of the NCS is a process for providing the services which can be used in common by the application layer which requires the network I O. The process of the NCS performs data transferring at the time of distributing data received in accordance with each protocol from the network to each application of the application layer or at the time of transmitting data from the application layer to the network. Specifically the NCS includes various demons of the respective protocols such as FTP provides client functions of the respective protocols.

The process of the OCS controls the operation panel which functions as an information transmitting part between the user and the controller . The OCS includes the portion which acquires key in information input from the operation panel as a key event and transmits a key event function corresponding to the acquired key in information to the SCS and the portion of the OCS function library in which drawing functions to output various screens to the display part in response to the requests from the application layer or the control service block as well as other functions to perform control of the operation panel are registered beforehand.

The application layer includes a mail application which transmits and receives an e mail a printer application for a printer the plotter a copier application for a copier the scanner and the plotter a fax application for a fax the FCU and a scanner application for the scanner .

The activation management part is arranged in the control service block . The activation management part works as a process in the control service block and performs activation deactivation processes of the various kinds of plug in components which constitute the function packages and various other processes related to the activation deactivation processes which will be described later.

As illustrated in the activation management part includes a plug in management part and a plug in starter . The activation management part is constituted by the CPU executing the activation management program or by using a predetermined microprocessor.

The plug in management part performs processing of installation uninstallation activation deactivation etc. of various plug in components . The plug in starter performs starting processing of each plug in component by making reference to the starting information at the time of starting of the image forming device . Namely the plug in starter starts each plug in component which is registered in the starting information .

For example the plug in components the sales package information the function package information and the license file are stored in the HDD . A plug in component is one of various kinds of programs installed in the image forming device and there is a one to one correspondence between the plug in component and the function package managed by the plug in management part .

The sales package information the function package information and the license information will be described later. Briefly the sales package information is information in which an activation state of a sales package which is purchased in the image forming device is registered the activation state indicating whether activation of the sales package is performed or not . The function package information is information in which activation deactivation of each of the function packages is registered. The license file is created by the license server and registered in the license file as information which certifies the license of using the sales package activation of which is performed.

One line of the table illustrated in is equivalent to a license file of a single sales package. Hence a plurality of license files may be stored in the image forming device in which activation of a plurality of sales packages is performed. However in the following embodiment the plurality of license files are not distinguished from each other and they are collectively called the license file .

In the Table as illustrated in License Unique ID is an ID identifier which uniquely identifies a license file . Hence once the license unique ID is assigned to the image forming device or information processing device that license unique ID is never assigned to a license file of another image forming device or information processing device.

 Sales Package ID is an ID identifier of a sales package which has been the object of activation. Hence if the license file is referred to the sales package currently purchased in the image forming device the user can be identified.

 Lock Code is an ID identifier which uniquely identifies the image forming device or information processing device to which the license file is assigned. In the image forming device a lock code which is specific to the image forming device is stored in for example the system memory MEM P and the image forming device transmits this lock code to the license server . Even if an authorized person is going to copy the license file to another image forming device activation cannot be performed with the copied license file because the lock code of the license server and the lock code from such image forming device are not in agreement.

 Expiration Date is an expiration date of the license file itself or the contents described in the license file . By requesting an update process for updating the current expiration date to the license server the image forming device can obtain a new expiration date.

 Date of Creation is the date time the license file is created by the license server . By using the date time of creation in Date of Creation checking whether the system clock of the image forming device is reliable can be performed. Namely this checking is performed in order to detect whether the system clock of image forming device is illegally turned back in order to avoid restriction of the expiration date.

The license server generates a license file for each sales package. For example when the image forming device accesses the license server for the first time or when a sales package is installed in the image forming device for the first time the license server generates a license file . The license server generates a license unique ID which is a different ID from the lock code and does not overlap with the previously generated license unique IDs. Preferably the license server generates a license unique ID which is not a consecutive number.

The license server stores a master file of the license file and transmits a copy of the master file to the image forming device . In response the plug in management part stores the license file in the HDD for example.

The license file may be encrypted by using the lock code. In such a case decryption of the encrypted license file which is illegally performed by other image forming devices with a different lock code can be prevented.

The relationship between the sales package information and the function package information before and after activation will be explained.

In it is assumed that activation of the sales package B is performed initially. The sales package information is generated by the plug in management part at the time the plug in component is installed. Therefore the function package which is included in each of the sales packages A and B is detected beforehand by the plug in management part .

As is apparent from the sales package information in which activation of only the sales package B is performed the two sales packages dist sales ID 1111 and dist sales ID 1222 are purchased in the image forming device which indicates that the package dist is in a deactivated state and the package dist is in an activated state. The sales package dist includes the function packages with the function IDs and and the sales package dist includes the function packages with the functions ID and respectively.

In the function package information the name of each function package the function ID which uniquely identifies each function package the purchase P number which indicates the number of the function packages purchased in the image forming device the activation purchase P number which indicates the number of the function packages which are activated among the purchased function packages and the activation column which indicates whether activation for each function package is performed are registered.

As is apparent from the function package information in which activation of only the sales package B is performed the numbers of the respective function packages with the names func func and func which are purchased in the image forming device are 1 2 and 1 respectively. The function package func is common to the sales packages A and B and the purchase P number of function package func is 2.

In the state in which activation of only the sales package B is performed the function package func and the function package func are activated. Hence the activation purchase P number of the function package func is set to 0 the activation purchase P number of each of the function packages func and func is set to 1 . The activation column is set to O when at least one of the function packages included is activated. Hence the activation column of each of the function packages func and func is set to O .

When activation of the sales package A is performed the function packages and included in the sales package A are activated. First O is registered in the activation column of the name dist of the sales package information by the activation of the sales package A. Second both the function packages and in the sales package A are activated and the activation purchase P number of each of the name func and the name func of the function package information is incremented respectively. Moreover the activation column of the name func of the function package information is set to O .

In this manner the plug in management part updates the sales package information and the function package information in accordance with the activation of the sales package A.

In the plug in management part illustrated in an activation control part controls the whole activation process and performs activation of each function package per sales package. The activation control part returns the state of the activated function package to a deactivated state or non activation state if needed.

An installation control part installs each function package at the time of purchasing of a sales package and uninstalls each function package if needed. A starting information updating part registers into the starting information the function package which is activated by the activation by making reference to the starting information .

A sales P information updating part updates the sales package information according to the activation as illustrated in . Similarly when a function package is deactivated the sales P information updating part updates the sales package information .

A function P information updating part updates the function package information according to the activation as illustrated in . Similarly when a function package is deactivated the function P information updating part updates the function package information .

A license file access part can perform the process which is allowed to access the license file and provides the information read from the license file to another functional block. The license file access part verifies the electronic signature of the license file and authenticates the license file only when its electronic signature matches with the correct electronic signature.

A date time comparing part compares the date time of creation of the license file with the current date time of the system clock. When the former precedes the latter the date time comparing part causes the activation control part to inhibit activation thereby preventing the unauthorized use of the license file .

An expiration date reminding part sends the user a reminding message reminding the user of the expiration date when the expiration date of a sales package is approached. A timer management part sets up the timer for detecting expiration of an expiration date for each sales package and performs uninstallation of the sales package concerned when the set up date time thereof is reached. An ID permanence part performs an ID permanence process to set a license unique ID to a permanent ID and inhibits duplication of license unique IDs of sales packages.

An example of activation of a sales package performed by the image forming device of an embodiment of the invention will be described with reference to B A and B.

As illustrated in sales packages A D are installed in the image forming device and activation of the sales packages A and B among them is performed initially. In this state function packages and are included in the sales package A and function packages and are included in the sales package B. Hence the activated function packages are the function packages and . In the state of it is not necessary that sales packages C and D be installed in the image forming device at that time.

In the function package information activation purchase P number of function package O and activation column of function package x .

For this reason in the starting information illustrated in the function packages and are registered. Hence the plug in starter starts the function packages and at the time of starting of the image forming device .

Subsequently as illustrated in the activation of sales package C or installation of sales package C is performed by the input operation of the user. The activation control part makes reference to the sales package information and determines the function packages activation of which is to be performed based on the function ID list of the sales package information . The activation control part detects whether the function packages and are included in the plug in components stored in the HDD and performs activation of the function packages and .

First the sales P information updating part sets the activation column of the sales package C in the sales package information to O . The function P information updating part sets the activation column of function package in the function package information to O . The function P information updating part increments the activation purchase P number of each of function packages and in the function package information respectively.

The starting information updating part makes reference to the function package information and registers into the starting information the function package the activation column of which is newly set to O . Hence at the next time the image forming device is started the function package will also be started.

Because activation of the function package is already performed the function package is already registered in the starting information .

In the function package information activation purchase P number of function package 1 and activation column of function package O .

In this embodiment the respective function packages included in each sales package can be set up in an activated or deactivated state on a sales package basis and it is no longer necessary that the user performs activation of the respective function packages individually.

Next an example of deactivation of a sales package performed by the image forming device of an embodiment of the invention will be described with reference to B A and B.

In this embodiment if deactivation of a sales package is performed each of the function packages included in the sales package can be set in a deactivated state.

It is assumed that before deactivation of a sales package A is performed activation of sales packages A B and C is initially performed as illustrated in . The state of the sales package A is returned to a deactivated state by the deactivation.

In the function package information activation purchase P number of function package 2 activation column of function package O activation purchase P number of function package 2 activation column of function package O activation purchase P number of function package 1 activation column of function package O activation purchase P number of function package 1 activation column of function package O activation purchase P number of function package 1 and activation column of function package O .

As described above if uninstallation of a sales package is performed the sales package is always set in a deactivated state. In this meaning uninstallation is the same as deactivation.

The activation control part makes reference to the sales package information and determines the function packages which are to be deactivated based on the function ID list in the sales package information .

First the sales P information updating part sets the activation column of sales package A in the sales package information to x . The function P information updating part sets the activation column of function package to x . The function P information updating part decrements the activation purchase P number of each of the function packages and respectively.

The starting information updating part makes reference to the function package information and deletes from the starting information the function package the activation column of which is newly set to x . Hence at the next time the image forming device is started the function package will not be started.

In the function package information activation purchase P number of function package 1 activation column of function package O activation purchase P number of function package 1 activation column of function package O activation purchase P number of function package 1 activation column of function package O activation purchase P number of function package 1 activation column of function package O activation purchase P number of function package O and activation column of function package x .

In this embodiment if deactivation or uninstallation of a sales package is performed it is no longer necessary to perform deactivation or uninstallation of the respective program components included in the sales package individually.

Next an example of uninstallation of a sales package with a time limit according to a timer which is performed by the image forming device of an embodiment of the invention will be described with reference to A B A and B. In this embodiment if the time limit is reached the sales package is automatically uninstalled.

As illustrated in the expiration date is specified in the sales package A. For example this expiration date may be directly input by the user from the operation panel . Alternatively an expiration date which is for example one year later from the date of activation or the date of installation may be automatically set by the activation control part . Alternatively an expiration date of a license file may be used as the expiration date of the sales package A.

The activation control part notifies the expiration date to the sales P information updating part and the sales P information updating part registers the received expiration date in the sales package information .

When the expiration date is set in the sales package information the timer management part sets up the timer for detecting expiration of an expiration date for each relevant sales package.

In the sales package information activation column of sales package A O activation column of sales package B O activation column of sales package C O and activation column of sales package D x .

In the function package information activation purchase P number of function package 2 activation column of function package O activation purchase P number of function package 2 activation column of function package O activation purchase P number of function package 1 activation column of function package O activation purchase P number of function package 1 activation column of function package O activation purchase P number of function package 1 and activation column of function package O .

As illustrated in the expiration date 3 31 is specified in the sales package A. The timer management part sets the timer to a date time which is 0 00 a.m. of the next day of this expiration date. Or the date time is stored in the timer as a time limit.

The timer management part compares the date time of the timer with the current date time which is extracted from the calendar information in the image forming device or a predetermined server which calendar information will be called a system clock . When the date time of the timer precedes the current date time the timer management part notifies the installation control part of the expiration of the time limit of the sales package A. Hence the installation control part starts uninstallation of the sales package A.

The installation control part makes reference to the sales package information detects the function packages and included in the sales package A and notifies them to the sales P information updating part . Then the installation control part performs uninstallation of the sales package A. Uninstallation of a sales package may be carried out by either deleting the complete package from the HDD or deleting only the access information of the sales package.

The sales P information updating part updates the function package information with respect to the received function packages and . Namely the activation purchase P number of each of the function packages and is decremented and the activation column of the function package the activation purchase P number of which is equal to zero is set to x .

The starting information updating part makes reference to the function package information and deletes from the starting information the function package the activation column of which is newly set to x . Hence at the next time the image forming device is started the function package will not be started.

In the sales package information activation column of sales package A x activation column of sales package B O activation column of sales package C O and activation column of sales package D x .

In the function package information activation purchase P number of function package 1 activation column of function package O activation purchase P number of function package 1 activation column of function package O activation purchase P number of function package 1 activation column of function package O activation purchase P number of function package 1 activation column of function package O activation purchase P number of function package O and activation column of function package x .

In this embodiment the expiration date is set in the sales package and if the expiration date is exceeded the sales package is automatically uninstalled. Hence it is possible to provide a use license of a sales package with a time limit.

Next another embodiment of the invention will be described. When different expiration dates are set in a plurality of sales packages the different expiration dates are registered in the function packages which overlap over two or more sales package. In such a case uninstallation of a sales package may be performed by expiration of an expiration date. Alternatively only starting of the function packages in the sales package may be inhibited without uninstalling the sales package.

As illustrated in the expiration date 1 11 is specified in the sales package A the expiration date 2 22 is specified in the sales package B the expiration date 3 24 is specified in the sales package C and the expiration date 4 1 is specified in the sales package D respectively.

In this embodiment in order to manage the expiration dates of the respective sales packages an expiration date list is provided in the function package information as illustrated in . An expiration date list of a function package contains a list of expiration dates of all the sales packages including that function package.

Hence in the function package information of the expiration date list of function package contains 1 11 2 22 and 4 1 the expiration date list of function package contains 1 11 and 3 24 and the expiration date list of function packages contains 3 24 and 4 1 .

In this embodiment when a function package has a plurality of expiration dates the starting information updating part associates the function package with the latest expiration date among the plurality of expiration dates and registers the function package associated with the latest expiration date in the starting information .

Hence as illustrated in the expiration date list of function package is 4 1 the expiration date list of function package is 3 24 and the expiration date list of function package is 4 1 .

At the time the image forming device is started the plug in starter compares each expiration date of the starting information with the current date time acquired from the system clock of the image forming device and does not start the function package the expiration date of which precedes the current date time.

Therefore in this embodiment an expiration date is specified in each function package and if the expiration date is exceeded starting of the function package is inhibited without uninstalling the sales package.

Next another embodiment of the invention will be described. There is also a case in which no expiration date is set in a certain sales package.

When both a sales package with one or more expiration dates and a sales package without an expiration date exist the starting information updating part gives priority to the sales package without an expiration date associates each of function packages in the priority sales package with none item no expiration date and registers them in the starting information as illustrated in .

If an expiration date of a sales package is updated the function P information updating part updates the expiration date list of each of function packages in the sales package S . In this embodiment the none item is contained in some of the expiration date lists of the function packages.

Subsequently the starting information updating part determines whether the current expiration date list which contains the none item exists S . When no none item is included in the expiration date list No in S the starting information updating part sets the expiration date of each function package to the latest expiration date among the respective expiration dates of the expiration date list S .

When the none item is included in the expiration date list Yes in S the starting information updating part sets the expiration date of the function package to none S .

Subsequently the starting information updating part updates a corresponding expiration date of the starting information for each function package by using the set up expiration date S .

Consequently the expiration date list of function package contains 1 11 and none and the expiration date list of function package contains none and 4 1 as in the example of . In this case the starting information updating part sets the expiration date of each of the function packages and in the starting information to none respectively.

In this embodiment when no expiration date is set in a certain sales package an expiration date is not set up for each of the function packages included in the sales package. Such setting is useful for a plug in component which is configured provide a fundamental function.

Next another embodiment of the invention will be described. In this embodiment the updating of an expiration date of the starting information is performed by a newly activated sales package. When activation of a sales package is newly performed an expiration date of a function package included in common in the sales package and another sales package which is previously activated may vary.

In this case the starting information updating part updates an expiration date of each of the function packages and in the starting information if needed.

Similar to the previous embodiment of FIG. A among the expiration dates of the function packages in the starting information priority is given to the function package with the none item. Because the expiration date list of function package which is included in each of the sales package A C and E contains 1 11 none and 6 30 the expiration date of function package in the starting information remains unchanged none even after activation of the sales package E is performed.

On the other hand the expiration date list of function package which is included in each of the sales packages A and E contains 1 11 and 6 30 and after activation of the sales package E is performed the expiration date of function package in the starting information is changed to 6 30 .

In this manner the starting information updating part updates an expiration date of the starting information when activation of the sales package with an expiration date is performed.

Similarly the updating of an expiration date of the starting information which is performed by uninstallation of a sales package with an expiration date will be explained.

The sales package D which is uninstalled includes the function packages and and the starting information updating part updates an expiration date of each of the function packages and in the starting information if needed.

By uninstallation of the sales package D the expiration date list of function package which is included in each of the sales package A B and D is changed from the list of 1 11 2 22 and 4 1 to the list of 1 11 and 2 22 . Hence the starting information updating part changes the expiration date of function package to 2 22 .

The expiration date list of function package which is included in each of the sales packages C and D is changed from the list of none and 4 1 to none by uninstallation of the sales package D. In this case the expiration date of the function package in the starting information remains unchanged none even after uninstallation of the sales package D is done. Hence the starting information updating part does not change the expiration date of the function package in the starting information .

Next the updating of an expiration date of the starting information which is performed when an expiration date of a sales package in an activated state is updated will be described. It is assumed that an expiration date of the sales package A in an activated state is changed from 1 11 to 7 31 .

When updating an expiration date of a sales package the function P information updating part temporarily deletes the expiration date before the updating from the expiration date list and then registers a new expiration date into the expiration date list.

In the example of the expiration date list of function package which is included in each of the sales packages A and B contains 1 11 and 2 22 . When the expiration date of the sales package A is updated the function P information updating part temporarily deletes 1 11 from the expiration date list. Hence the expiration date list of function package contains only 2 22 temporarily.

Similarly the expiration date list of function package which is included in each of the sales package A C and E contains 1 11 none and 6 30 . When the expiration date of the sales package A is updated the function P information updating part temporarily deletes 1 11 from the expiration date list. Hence the expiration date list of function package contains only none and 6 30 temporarily.

Similarly the expiration date list of function package which is included in each of the sales packages A and E contains 1 11 and 6 30 . When the expiration date of the sales package A is updated the function P information updating part temporarily deletes 1 11 from the expiration date list. Hence the expiration date list of function package contains only 6 30 temporarily.

Subsequently the function P information updating part registers the new expiration date of the sales package A after the updating in the expiration date list of each of the function packages. In this example the new expiration date of the sales package A after the updating is 7 31 .

The function P information updating part adds 7 31 to the expiration date list of function package and the updated expiration date list of function package contains 7 31 and 2 22 . Because the starting information updating part sets the latest one among the expiration dates in the expiration date list of function package to the starting information the starting information updating part updates an expiration date of function package in the starting information to 7 31 .

Similarly the function P information updating part adds 7 31 to the expiration date list of function package and the updated expiration date list of function package contains 7 31 none and 6 30 . Because the starting information updating part gives priority to the function package with the none item among the expiration dates in the expiration date list of function package in the starting information the starting information updating part does not update the expiration date of function package in the starting information which is still none .

The function P information updating part adds 7 31 to the expiration date list of function package and the updated expiration date list of function packages contains 7 31 and 6 30 . Because the starting information updating part sets the latest one among the expiration dates in the expiration date list of function package to the starting information the starting information updating part updates the expiration date of function package to 7 31 .

In this embodiment if an expiration date of a sales package is updated the updated expiration date is made to reflect in the expiration date of each function package included in the sales package and each function package can be started unless the expiration date is exceeded.

Next an example of management of activation performed by the image forming device of an embodiment of the invention will be described.

As described above the plug in management part stores the license file and the lock code with the association of the license file and the lock code. In this embodiment the lock code stored in the license file is compared with the lock code specific to the image forming device and it is determined whether the license file is correctly the license file specific to the image forming device . The plug in management part of this embodiment performs the comparison and determination process at the time the activation process is started and when the license file is authenticated normally the plug in management part of this embodiment permits one of activation deactivation installation and uninstallation to be performed.

As illustrated in the plug in management part reads out the lock code from the system memory MEM P of the image forming device 1. Reference 

Next the license file access part reads out the lock code stored in the license file from the HDD . The plug in management part of this embodiment performs the comparison and determination process described above 2. Reference Comparison . Only when both the lock codes are in agreement the activation control part permits the activation or deactivation including the updating of the sales package information the function package information and the starting information .

In this embodiment it is possible to prevent the activation of program components in another image forming device which is illegally performed by using the license file copied from the image forming device and it is possible to improve security of the license file .

Next an example of management of an expiration date of a service package using an expiration date of a license file performed by the image forming device of an embodiment of the invention will be described.

In this embodiment the management of an expiration date of a sales package is performed by associating the expiration date of the sales package and an expiration date of a license file .

As described above an expiration date can be set in a license file the expiration date of the license file is set to the expiration date of the sales package.

As illustrated in the plug in management part or the license file access part reads out an expiration date of the license file 1. Read In this example the expiration date of the license file is 3 31 .

Subsequently the sales P information updating part sets the expiration date of the sales package information to 3 31 2. Set .

Thereby 3 31 is added to the expiration date list of each of the function packages included in the sales package. Because the starting information updating part can update the starting information if needed management of an expiration date of the license file and the sales package can be performed in a uniform manner.

Next an example of management of an expiration date of a service package using a validity period performed by the image forming device of an embodiment of the invention will be described.

There is a case where it is desired to designate an expiration date of a sales package by a predetermined validity date. For example if an expiration date is set up at the time of shipment a time lag between the shipment and the activation may arise which causes inconvenience to the user.

To avoid the problem the image forming device of this embodiment is arranged to set up an expiration date of a sales package by a predetermined validity period.

The validity period may be registered in the license file . Alternatively the validity period may be directly input by the user from the operation panel . Alternatively a date time which is for example one year later from the date of activation or the date of installation may be automatically set as the validity period by the activation control part .

As illustrated in the license file access part reads out a validity period registered in the license file 1. Reference The validity period in this example is set to 10 days .

Next the activation control part reads out the current date time from the system clock of the image forming device 2. Reference .

Next the activation control part adds the validity period 10 days to the acquired current date time 3. Computation . The computed date time is set to an expiration date of the sales package A.

Next the sales P information updating part sets the computed date time in the sales package information 4. Data Change .

Subsequently the function P information updating part uses this expiration date of the sales package A in the expiration date list of each of the function packages in the sales package A and the starting information updating part updates an expiration date of the starting information if needed. Therefore it is possible to prevent the time lag between the shipment and the activation from arising thereby improving the convenience to the user.

Next an example of reminding a user of an expiration date performed by the image forming device of an embodiment of the invention will be described.

In the previous embodiment the plug in starter does not start the function package if the expiration date is exceeded. If the user is notified prior to the expiration date that the expiration date is approaching the user can understand that the expiration date will be reached.

In this embodiment a date which is earlier than an expiration date by a predetermined period called a remaining activation period is set as the reminding date. Because the expiration date is set in the sales package information the reminding date may be registered in the sales package information . Alternatively the reminding date may be registered in the HDD independently.

Without setting the reminding date in the sales package information the determination as to whether the current date time is earlier than the expiration date by the remaining activation period may be made each time the image forming device is started.

As illustrated in the expiration date reminding part makes reference to the sales package information and reads out an expiration date 1. Read Out Data .

Next the expiration date reminding part subtracts the remaining activation period from the expiration date 2. Computation .

Next the expiration date reminding part determines the reminding date 3. Reminding Date Time . In the example of the remaining activation period is set to 30 days about one month .

For example if the expiration date of the sales package is 3 31 and the remaining activation period is subtracted from the expiration date the reminding date is determined as being 3 1 . If the reminding date 3 1 is reached the reminding of the expiration date to the user is performed. For this purpose the reminding date time may be set exactly to 0 00 a.m. of 3 1 .

The expiration date reminding part registers the reminding date in the sales package information so that the reminding date is stored. Because an expiration date is set up for each sales package the reminding date is also registered for each sales package which is stored with the association of the reminding date and the sales ID of the sales package .

The expiration date reminding part may store as a constant the remaining activation period. Alternatively the remaining activation period may be directly input by the user from the operation panel . When the user sets up the remaining activation period the remaining activation period is stored in the HDD .

As illustrated in the expiration date reminding part compares the reminding date time with the current date time acquired from the system clock and detects whether the current date time reaches the reminding date time 1. Reference .

Next the expiration date reminding part sends a warning mail request so that a warning mail is created and transmitted 2. Warning Mail Request Is Sent .

In the warning mail the expiration date is included in order to improve the convenience to the user. For this purpose the expiration date reminding part reads out from the sales package information an expiration date of the sales package with which the reminding date is reached.

The expiration date reminding part reads out from the HDD an e mail address of the user or the administrator of the image forming device a subject name and a text which are stored beforehand therein. The expiration date reminding part adds the expiration date and the name of the sales package read from the sales package information to the expiration date item in the text. The expiration date reminding part sends these information items to the e mail application and the e mail application transmits the warning mail according to the communication protocol such as SMTP via the NIC .

An example of the warning mail is illustrated in . This warning mail depicts that the expiration date of sales package AAA is 3 31 and that the updating of the expiration date before that date is requested. Alternatively the warning mail may depict that the expiration date of sales package AAA will be reached in 30 more days . In this case the remaining activation period is notified to the user.

In this embodiment the user is notified of the expiration of a service package before the expiration date is exceeded thereby improving the convenience to the user.

The warning mail may be transmitted on the reminding date at a particular time. After the reminding date is reached the warning mail may be transmitted at intervals of a given period for example in every week . The frequency of transmitting the warning mail may be increased as the expiration date is approaching.

Next an example of determination of execution of activation performed by the image forming device of an embodiment of the invention will be described.

In this embodiment the current date time is compared with the date of creation of the license file and it is determined whether activation is performed. When the current date time from the system clock of the image forming device is earlier than the date of creation of the license file by a predetermined time the activation is determined as a failure. Even if the contract term is defined by an expiration date the service package may be illegally used beyond the expiration date by slowing the system clock of the image forming device . This embodiment is adapted to avoid the problem.

As described above the license file is created by the license server and the date the license file is created by the license server is the date of creation of the license file . Because the date time of the license server is periodically maintained with the NTP server the date time may be considered the exact date time. Usually the date time at which the activation is performed using the license file follows the date of creation of the license file .

For this reason there is no possibility that the date time at which the activation is performed precedes the date of creation of the license file . In other words if the system clock of the image forming device is earlier than the date of creation of the license file it is highly possible that the user altered the system clock of the image forming device intentionally in order to illegally use the plug in component beyond the contract term.

In this embodiment if the current date time of the system clock is detected as being earlier than the date of creation of the license file the date time comparing part requests the activation control part to inhibit the activation. The date time comparing part transmits a message indicating that the system clock of the image forming device should be corrected to the user who has requested the activation.

As illustrated in if the user operates the operation panel to start the activation the license file access part reads out a date of creation of the license file 1. Reference .

Next the date time comparing part compares the current date time of the system clock with the date of creation of the license file 2. Reference Comparison . If it is clearly detected that the current date time of the system clock of the image forming device precedes the date of creation of the license file the date time comparing part notifies the activation control part of the result of the detection. Thereby the date time comparing part requests the activation control part to inhibit the activation from being performed.

The detection of the system clock may be performed in order to allow some fluctuations of the system clock of the image forming device . When the fluctuations of the system clock fall within the allowable range the activation may be permitted. Otherwise if the current date of the system clock of the image forming device is earlier than the date of creation of the license file by three or more days the activation is inhibited from being performed.

The date time comparing part transmits a message indicating that the system clock of the image forming device should be corrected to the user who has requested the activation.

In this embodiment it is possible to prevent the illegal use of the plug in component when the system clock of the image forming device is altered intentionally.

Next another embodiment of the invention will be described. In this embodiment at the time of deactivation of a sales package the license unique ID of the sales package is prevented from being used in other sales packages ID permanence . Thereby the image forming device of this embodiment prevents the illegal use of the plug in component by the illegal copy of the license file .

As described above the license unique ID is unique to the license file . If the license unique ID is continuously available after the deactivation is performed there is a possibility that the sales package for which the expiration date is exceeded may be illegally activated again without setting a new expiration date.

In this embodiment an ID permanence process to allow a same license unique ID to be used only once is performed in order to inhibit the activation using the old license unique ID after the expiration date. It is possible for this embodiment to prevent the re activation of the sales package using an illegally copied license file after the expiration date is exceeded. In the following the term ID permanence means keeping the license unique ID unique.

As illustrated in the ID permanence part reads out a license unique ID from the license file received from the license server 1. Reference .

Next the activation control part performs the activation process of a sales package 2. Activation Process .

Next the sales P information updating part registers the license unique ID into the sales package information 3. Process Result Is Incorporated .

In the case where the activation of the sales package of sales ID 343434 is newly performed if a license unique ID of the same sales package generated by the license server is 654321 the ID permanence part registers 654321 into the column license unique ID of the sales package in the sales package information .

As illustrated in the activation control part performs the deactivation process of a sales package 1. Deactivation Process .

Next the sales P information updating part deletes a corresponding license unique ID of the sales package from the sales package information 2. Process Result Is Incorporated .

At the time of the deactivation the ID permanence part registers the license unique ID of the sales package the deactivation process of which is performed into a used license ID list 3. License ID Is Incorporated . The used license ID list is stored in the HDD .

In the example of when the sales package of sales ID 343434 is deactivated the ID permanence part stores the license unique ID 654321 of the sales package into the used license ID list . Other processing steps at the time of the deactivation are performed as described above in the previous embodiment.

At the time of this activation the user does not request the license server to generate a license file and attempts to use the already generated license file to perform the activation of the sales package.

As illustrated in the ID permanence part reads out a license unique ID from the license file 1. Reference .

Next the activation control part starts performing the activation process of the sales package 2. Activation Process . At this time however the ID permanence part compares the license unique ID read from the license file with the license unique ID read from the used license ID list and detects whether the license unique ID from the license file is already registered in the used license ID list 2.1 Reference Comparison .

When it is registered the ID permanence part notifies the activation control part that the license unique ID is illegally used. Thereby the activation control part stops performing the activation process of the sales package.

For example when the license server transmits the old license unique ID 654321 to the image forming device the ID permanence part detects that the old license unique ID 654321 is already registered in the used license ID list . the ID permanence part stops activation. Hence it is possible to prevent the illegal activation of a sales package from being performed using the same license file .

First the plug in management part receives or detects a request for activation of a sales package S .

Subsequently the license file access part checks the electronic signature of the license file which is stored in the image forming device S .

As a result of the checking S when the electronic signature is altered the plug in management part displays an error message indicating the alteration of the electronic signature on the display part S . Next the activation process is terminated.

When the electronic signature is not altered Yes in S the date time comparing part compares the date of the system clock of the image forming device with the date of creation of the license file and determines whether the date of the system clock is not earlier than the date of creation of the license file by a predetermined period S .

As a result of the determination when the date of the system clock is earlier than the date of creation of the license file No in S the plug in management part displays an error message indicating the alteration of the system clock on the display part S . Next the activation process is terminated.

When the date of the system clock is not earlier than the date of creation of the license file Yes in S the license file access part compares the lock code stored in the license file with the lock code of the image forming device S .

As a result of the comparison when the two lock codes are not equal No in S the plug in management part displays an error message indicating the alteration of the lock code on the display part S . Next the activation process is terminated.

When the two lock codes are equal Yes in S the activation control part specifies the sales package by reading the sales package ID which is the target of the activation from the license file S . Next the activation control part determines whether the sales package is installed in the image forming device S .

When the sales package is not installed No in S the plug in management part displays an error message on the display part S . Next the activation process is terminated.

Subsequently the sales P information updating part sets an expiration date of the sales package read from the license file into the sales package information S .

The function P information updating part activates the function packages included in the sales package S . The states of the function packages which are included in the sales package and already activated are not changed. Next the function P information updating part adds an expiration date to the expiration date list of each of the function packages included in the sales package S .

The starting information updating part specifies an expiration date of each function package based on the updated expiration date list S . Next the expiration date of the starting information is updated S .

The image forming device of this embodiment can perform activation of each sales package and thereby activate the plurality of plug in components which can be effectively used as a result of association of some of functions provided by the plurality of programs of the sales package.

As described in the foregoing the image forming device of one embodiment of the invention can perform activation of a plurality of programs on a package by package basis and can easily set up the activation or deactivation of each program.

The present invention is not limited to the specifically disclosed embodiments and variations and modifications may be made without departing from the scope of the present invention.

The present application is based on Japanese patent application No. 2008 171636 filed on Jun. 30 2008 the contents of which are incorporated herein by reference in their entirety.

