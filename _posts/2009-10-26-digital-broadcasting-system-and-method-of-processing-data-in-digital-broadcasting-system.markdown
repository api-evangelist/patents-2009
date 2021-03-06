---

title: Digital broadcasting system and method of processing data in digital broadcasting system
abstract: A method is provided for controlling a management server that is connected to a DTV through an IP connection, wherein the DTV is located in one independent space among a plurality of independent spaces physically separated from one another. The method including generating a message file including an Application Programming Interfaces (API) command and a parameter related to a display condition, accessing an IP address of a DTV serving as a destination of the generated message file, transmitting, if the accessing is successfully achieved, the generated message file to the DTV having the accessed IP address and receiving information for identifying whether the message file is successfully processed from the DTV.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08374180&OS=08374180&RS=08374180
owner: LG Electronics Inc.
number: 08374180
owner_city: Seoul
owner_country: KR
publication_date: 20091026
---
The present invention relates to a technology for controlling a Radio Frequency RF head end system and a plurality of TV sets in a limited space such as a hotel or hospital and more particularly to a method for transmitting a signal to a TV set of a specific room from among a plurality of TV sets installed in respective rooms of a hotel or hospital using a multiple access point control system defined in the following description.

Generally a broadcast receiver receives a data stream including a broadcast signal extracts a video and audio data stream corresponding to a user desired channel using service information contained in the received data stream and outputs the extracted video and audio data stream to a display device.

However according to the related art detailed protocols or methods for more effectively transmitting and processing data to each room of a limited space such as a hotel or hospital are not defined yet.

An object of the present invention is to provide a method for providing a local messaging service to each room of a hotel using a digital television DTV .

Another object of the present invention is to provide a method for providing a local messaging service to each room irrespective of physical communication environment of a hotel e.g. coaxial connection or IP connection environment .

To achieve these objects and other advantages and in accordance with the purpose of the invention as embodied and broadly described herein a method is provided for controlling a digital television DTV located in one independent space among a plurality of independent spaces physically separated from one another wherein the DTV is connected to a management server and includes an Access Point AP card the method including receiving a message file from the management server wherein the message file includes identification ID information of the independent space and primary additional information mapped to the independent space ID information determining whether the independent space ID information is identical to ID information of a current independent space displaying the primary additional information when the independent space ID information is identical to the current independent space ID information transmitting both a request signal for requesting secondary additional information corresponding to the primary additional information a response signal including the independent space ID information to the management server and displaying the secondary additional information received from the management server.

Reference will now be made in detail to the preferred embodiments of the present invention examples of which are illustrated in the accompanying drawings. The detailed description which will be given below with reference to the accompanying drawings is intended to explain exemplary embodiments of the present invention rather than to show the only embodiments that can be implemented according to the present invention.

Prior to describing the present invention it should be noted that most terms disclosed in the present invention are defined in consideration of functions of the present invention and correspond to general terms well known in the art and can be differently determined according to intention of those skilled in the art usual practices or introduction of new technologies. In some cases a few terms have been selected by the applicant as necessary and will hereinafter be disclosed in the following description of the present invention. Therefore it is preferable that the terms defined by the applicant be understood on the basis of their meanings in the present invention.

In accordance with the following embodiments of the present invention a system for controlling a multiple access point using a multiple access point control system is proposed. For example the access point may be a part for providing information to each limited physical space communicating with devices contained in the physical space and controlling the devices. By means of the multiple access point control system a specific access point may provide information to a user located in a corresponding physical space. In addition the devices located in the physical space may communicate with a server located outside of the physical space through the access point.

In addition the term physical space is separated from a communication space such as a cell defined in a wireless field. The cell acting as the communication space is in the range that is affected by radio waves from a specific base station such that a user equipment UE can communicate with a corresponding base station in the above mentioned range. However the access point may be a part for controlling and managing a specific physical space or local area e.g. each room of a hotel or hospital . Although the devices contained in the physical space can communicate with an access point of another physical space the devices communicate with the access point of the corresponding physical space and as such a detailed example thereof will hereinafter be described.

The multiple access point control system may transfer the same information to a corresponding physical space through a multiple access point or may transfer different information to individual physical spaces. The multiple access point control system may control the access point at a remote site such that information suitable for a user of a physical space including the access point can be independently provided. In accordance with one embodiment of the present invention the server of the multiple access point control system includes a user interface capable of allowing a person who controls the server to easily control the multiple access point.

The access point may be arranged at a specific position of each physical space. In order to easily provide information to the user the access point may be configured in the form of a card such that it can be inserted into a television or a set top box. In accordance with one embodiment of the present invention the card type access point designed to be inserted into a television or set top box may also be abbreviated to an AP. In the case where the AP card is inserted into the television the user can recognize information to be transmitted through the AP card by viewing the television.

Such a system may be located at a variety of places for example a hotel a hospital a school a prison etc. For convenience of description and better understanding of the present invention it is assumed that the above mentioned system is located at a hotel such that the multiple access point and a control system thereof are operated in the hotel. However the scope and spirit of the present invention are not limited thereto and the present invention is also applicable to other examples.

In the case of the hotel a user lodges in the hotel such that the user can view content such as broadcast content through a TV. If content provided to a user of a room through the TV is pay per view content an accounting system connected to the TV can charge a usage fee to user viewed content. However a driving circuit associated with the accounting system is installed in each TV. If there is a need to upgrade a corresponding system a hotel administrator who uses the related art must upgrade TV systems installed in all rooms resulting in greater inconvenience of use.

In addition since administrating all rooms is manually carried out by the hotel administrator a large hotel having many rooms consumes an unnecessarily long period of time and great cost to manage such rooms.

With the increasing number of guests or lodgers who use wireless communication there are many cases wherein a wireless communication network is installed in each floor of a hotel. However there is a difficulty in providing enough bandwidth for all guests of respective floors to easily use the wireless communication network such that it causes greater inconvenience to a guest or administrator of a hotel.

In the case of an old hotel a hotel history may be considered to be a brand value of the hotel. In order to provide each room of the hotel with a control system a communication system and another system that allows individual services to be executed in all rooms a large amount of costs are consumed. If the hotel architecture is changed to another to install the above mentioned systems the hotel prestige or value may be greatly deteriorated.

Therefore according to the following embodiments of the present invention if individual services are provided to users of rooms serving as different physical spaces and an access point capable of entirely managing the rooms is installed in each room the following embodiments can solve the above mentioned problems by controlling only the access point of each room without great modification of a conventional hotel design. A multiple access point control system according to one embodiment of the present invention will hereinafter be described with reference to the annexed drawings.

In accordance with the related art shown in if a hotel administrator desires to upgrade a system applied to a TV of each room the hotel administrator has to manually upgrade TVs of all rooms of the hotel. In other words as shown in illustrating the related art if a device in any one room is wrongly operated or an empty room is brightly lit the hotel administrator should directly visit each room so as to correct the incorrect operation of the device or switch off the light of the empty room.

The above mentioned inconvenience will hereinafter be described in detail from the economic point of view.

Provided that a cost required for upgrading a TV driving circuit of each room once is denoted by a the number of rooms is denoted by b the number of software upgrade times every year is denoted by c and a lifetime of a TV is denoted by d a total cost a b c d is continuously consumed to maintain such a system.

Most hotels include an installation for a Video On Demand VOD accounting service for a TV. If an access point card is installed in the TV each hotel can provide many more services to the user through the access point card. Therefore a multiple access point control system can be easily installed in the hotel having many physical spaces and can also be easily managed and maintained by the hotel administrator.

A variety of services can be provided to a user through the TV having the access point card. Exemplary services are as follows. If the user enters the room a hotel logo is displayed on the TV and a message including respective user names can be displayed on the TV.

In addition the hotel notification or the hotel advertisement etc. can be displayed on the TV and travel or transportation information can be provided to the user. In addition user desired information of respective rooms can be separately provided to individual rooms and a detailed description thereof will hereinafter be described in detail.

Referring to the hotel administrator asks an external content provider or a system administrator either to manage a server for controlling TVs of respective rooms or to provide content. Accordingly according to the related art the content provider or the system administrator controls and manages not only content that must be provided to the user through the TV but also an accounting system for the content and therefore the TV of each room can provide a pay per view service to the user of each room.

According to the related art if the hotel administrator changes a pay per view service to another service the hotel administrator cannot directly control a detailed description required for the changed service. In the case of changing the system operation the hotel administrator has difficulty in changing such a system operation under the condition that the hotel administrator sends the external content provider no request. In other words it is next to impossible for the hotel administrator to change or manipulate services provided to each room independently from the system administrator.

Referring to the server of the multiple access point system according to another embodiment of the present invention can allow the hotel administrator to directly provide content to a user of each room and can also allow the hotel administrator to provide different information to the user. For example the server for use in the multiple access point control system may have a Web based editor. The user interface of the multiple access point control system can allow the hotel administrator to conveniently manage respective rooms such that the hotel administrator can conveniently provide requirements of each room and an individual service that must be provided to each room.

The hotel administrator can edit services provided to each room using the user interface and the Web based editor such that individual or common services can be provided to respective rooms. If the hotel administrator edits the Web based editor the server of the multiple access point system can easily transmit an additional message to a user of a specific room or can transmit specific content to the user. A detailed description thereof will hereinafter be described in detail.

In the case of most hotels a cable network is installed in each room as shown in . The cable network is connected to a set top box of each room or provides a VOD service to each room through a VOD server of the hotel.

For example if the VOD server transmits an IP packet having video content the IP to RF converter converts the IP packet into an RF signal and transmits the RF signal to the cable network.

In addition the set top box or TV of each room receives the RF signal from the VOD server and displays video content.

Referring to if the user of each room desires to use the Internet or a wireless phone using a notebook computer based on wireless communication it is necessary for each room to include a router connected to the Ethernet network or a wireless communication relay module. However presently most hotels include only a cable network and do not include a local area network LAN or a wireless communication network such that high costs are needed to additionally install communication lines.

Recently some hotels have installed one or two wireless communication relay models in each floor so as to provide a wireless communication service. However the user of each room may not often acquire a service of a desired bandwidth. As a result high costs are needed to install an additional wireless communication relay module in all rooms.

However the embodiment of the present invention may be applied to one case in which the hotel environment includes the Coax network and another case in which the hotel environment includes the Ethernet network. If the hotel environment includes the Ethernet network the hotel server additionally includes the accounting server to charge a usage fee on the VOD viewed by a user who lodges in the hotel.

In addition from the viewpoint of a protocol layer if the hotel environment includes the Coax network Digital Storage Media Command and Control DSM CC is converted into data based on an IP packet and the IP packet data is transferred using a cable modem protocol. On the other hand if the hotel environment includes the Ethernet network the DSM CC is transferred as the IP packet.

In the meantime the access point card may serve as a wireless communication module that transmits radio waves to a notebook computer or wireless phone of a user of each room. The notebook computer or wireless phone used by the user may communicate with an external server through the AP card the cable network or the router.

The server of the multiple access point control system may provide video content or the like to the user of each room or provide a variety of services suitable for the user to the user of each room.

If the AP card is inserted into the television the AP card may include middleware to drive a variety of applications provided to the user. In addition the AP can support the multi protocol interface such that it may be used as an access point of the AP wireless communication or may control devices of respective rooms.

The IP to RF converter transmits the IP packet over a cable network and the AP card includes the RF to IP converter such that it can provide an Internet based communication service and a multimedia broadcast service to the user. The AP card includes general purpose middleware standardized for the application provided to the user. Therefore the service provided by the hotel administrator can be displayed on the TV regardless of TV functions. The AP card that enables respective hotels to use different content protection functions so as to charge a usage fee for content includes an operating system that enables various content protection modules to be implemented with software. Therefore although respective hotels use different content protection functions content can be transferred to the user through the same AP card and a detailed description thereof will hereinafter be described in detail.

In the case of a hotel a user may request a call service for a specific time from the hotel administrator. In the case of using the multiple access point control system a reserved message may be transferred to the user through the television.

The AP card may communicate with other devices of each room and drive the application supported by the multiple protocol interface such that the user of the room may also control devices of the room through the TV.

The television including the AP card may provide a user interface for enabling the user to control devices of the room. For example the television including the AP card may display various devices capable of being controlled in each room. The television may display a corresponding room and the positions of devices installed in the corresponding room.

For example if the AP card communicates with the curtain control device the user can freely open or close a curtain through the user interface displayed on the TV.

In addition when adjusting an air conditioner or a hygrometer the user does not directly adjust a corresponding device and can remotely operate the user interface displayed on the TV including the AP card.

Referring to the entire system according to one embodiment of the present invention includes a back office a network infrastructure devices and applications etc. The network management server shown in carries out functions of the multiple access point control system and the AP card carries out functions of the multiple access point.

For example the back office includes a digital headend a media gateway a gateway application servers a network management server etc. The back office may be used to transmit broadcast data and IP data. For example the back office may be a broadcast station or the like.

The network infrastructure may include for example a Master Data Unit MDU etc. For example the devices and applications includes an Access Point AP card interactive applications for example DTV a laptop a Portable Multimedia Player PMP a WiFi phone WiFi CE devices etc.

Specifically the network management server may be managed by the hotel or the service provider. The network management server controls the MDU such that it provides various data to the AP card mounted to the DTV of each room of the hotel.

The AP card may transmit and receive data that is associated with VoIP VOD 2 way communication personal area network etc. and may process such data.

As shown in the DTV including the AP card may share such data with peripheral devices e.g. etc. of of the DTV.

In addition although it is assumed that the MDU is connected to the AP card through a coaxial cable as shown in the scope and spirit of the present invention are not limited thereto and the embodiment of the present invention may also include another case wherein the network management server is connected to the AP card over the Ethernet.

Referring to the Digital Video Broadcasting DVB broadcaster transmits a DVB signal the DVB to ATSC Converter converts the DVB signal into an ATSC signal and the QAM modulator modulates the converted ATSC signal into a QAM signal.

The VOD server transmits a VOD signal the IP converter converts the VOD signal into the IP signal and the IP to RF converter converts the IP signal into the RF signal.

The Data Server transmits an HTML signal the HTML to Data converter converts the HTML signal into data and the QAM modulator modulates the converted data into a QAM signal.

An AP CARD RF to IP converter receives the QAM signals from the QAM modulators and and the IP to RF converter .

The AP CARD RF to IP converter may directly transmit the QAM signal to the DTV . If necessary the AP CARD RF to IP converter may convert the QAM signal into the IP signal and transmit the IP signal to the set top box STB .

In addition the DTV may process the QAM signal received from the AP CARD RF to IP converter and the processed signal may be displayed according to various display schemes for example LCD PDP ELD VFD etc.

Meanwhile the DVB broadcaster the VOD server and the Data Server may be managed by a broadcast station a Content Provider CP a Service Provider SP etc. For example the DVB to ATSC Converter the IP Converter the HTML to Data Converter the QAM Modulator the IP to RF Converter and the QAM Modulator may be managed by a hotel a hospital etc. For example the AP card RF to IP Converter the STB or the DTV may represent a digital broadcast receiver.

Therefore in the case of using the system shown in a hotel not providing Internet services can easily provide Internet services e.g. Internet services received from the VOD server or the Data Server to guests of each room of the hotel.

Referring to the AP card includes a variety of modules for example a PCB antenna an AP chipset a homenetwork chipset a Coax module an interface a controller a USB etc. As shown in the DTV includes a variety of modules for example a controller a tuner a demultiplexer a decoder an output module a memory a user interface a USB etc. However for better understanding of the present invention the MDU shown in may also correspond to the MDU shown in as necessary.

The AP card may be connected to the MDU through the coax line. The controller may copy packets between the AP chipset and the homenetwork chipset . Further the controller controls the AP chipset and the homenetwork chipset . For example the homenetwork chipset may be a Multimedia over Coax Alliance MoCA chipset or a Home Phoneline Networking Alliance HPNA chipset etc.

The AP chipset may control communication with a plurality of devices contained in each room including the DTV . In more detail the AP chipset may provide a wireless Internet service such as WiFi to the devices.

The homenetwork chipset may convert the RF signal into IP data through a cable network coax . If it is necessary to transmit the IP data to a wireless communication device of each room the homenetwork chipset may transmit the IP data to the AP chipset . The homenetwork chipset may convert the IP data received from the AP chipset into an RF signal and transmit the RF signal to the coax module . The PCB antenna may be a module that enables several devices of each room including the DTV to wirelessly communicate with the AP chipset .

In the meantime the tuner receives the RF broadcast signal. The USB of the AP card may transmit and receive data to and from the USB of the DTV for example large amounts of data for firmware or data for setting a Service Set Identifier SSID may be communicated between the USB and the other USB .

The AP card transmits and receives a VoIP signal through for example the AP chipset transmits a VOD signal to the DTV through the USB and provides information e.g. GEM application data etc. associated with data broadcast content of the hotel through the USB . The controller of the DTV controls a tuner a demultiplexer a memory a user interface etc. The demultiplexer may demultiplex a video signal an audio signal and data received from either the AP card or the tuner .

The decoder may decode the demultiplexed video and audios signals and the demultiplexed data. The output module may output the decoded video and audio signals and the decoded data.

Further the memory may store some or all information received from the AP card . The user interface may transmit a user entry command signal to the controller .

Referring to the AP card includes a plurality of modules for example a PCB antenna an AP chipset a first interface Interface a second interface Interface etc. For example the DTV includes a plurality of modules for example a controller a tuner a demultiplexer a decoder an output module a memory a user interface an interface etc. However for better understanding of the present invention the network management server shown in may also correspond to the network management server shown in .

Differently from the AP card shown in receives the Ethernet signal from the network management server and the AP chipset may communicate with several devices contained in each room having the DTV .

In more detail the AP chipset may provide an Internet service such as WiFi to several devices. The PCB antenna may be a module that enables several devices of each room including the DTV to wirelessly communicate with the AP chipset .

Further the first interface Interface is a module for transmitting and receiving an Ethernet signal to and from the network management server . The second interface Interface is a module for transmitting and receiving an Ethernet signal to and from the interface contained in the DTV .

In addition the controller of the DTV controls a demultiplexer a decoder an output module a memory a user interface etc. The demultiplexer may demultiplex a video signal an audio signal and data received from the AP card .

The decoder may decode the demultiplexed video and audios signals and the demultiplexed data. The output module may output the decoded video and audio signals and the decoded data.

Further the memory may store some or all information received from the AP card . The user interface may transmit a user entry command signal to the controller .

Referring to the master may perform a function of the above mentioned multiple access point control system. The AP card may perform for example a function of the multiple access point.

First of all the embodiment of the present invention discloses a system for providing an Internet service installed in a specific place such as a hotel having one or more rooms. Referring to the above mentioned system includes the master connected to the Internet local slaves and and a management slave . The master is connected to the Internet. The local slaves and are connected to the master by wire and are wirelessly connected to personal devices and of specific local areas to K. The management slave may be connected to the local slaves and through the master .

In the meantime the master may be for example a hotel server or a headend. The management slave is for example a personal computer PC installed in a hotel reception area or front desk. The local slave or may be for example a TV installed in each hotel room.

In addition as can be seen from the local slaves and may include a wired wireless communication unit for communicating with the PCs and e.g. a laptop computer and a mobile phone used by the user who is located at a corresponding local area and may further include another wired wireless communication unit for communicating with the master .

For example the wireless communication unit may be a WiFi PAN access point module. For example the wired communication unit may be a MoCA HPNA module. Meanwhile the WiFi PAN access point module is manufactured in the form of a wireless communication chip that can perform wireless communication through the Personal Area Network PAN according to the WiFi technology for supporting various wireless network standards e.g. 802.11 802.11a 802.11b and 802.11g protocols .

In addition the MoCA HPNA module is manufactured in the form of a chip using a telephone line a power line or a coaxial cable Coax . In this case the Multimedia over Coax Alliance MoCA technology and the Home Phoneline Networking Alliance HPNA technology may be applied to the manufactured chip such that the chip can communicate with the master by wire.

Referring to the management slave or the local slaves and shown in generate Pseudo Random Numbers indicating a unique Service Set Identifier SSID and a Wired Equivalent Privacy WEP key using two Exclusive OR gates and a 9 bit shift register.

For example the SSID is a unique ID N bytes long e.g. unique ID 32 bytes long added to each header of packets transmitted over a wireless LAN and is used like a code or password when connected to wireless terminals. The SSID may discriminate one wireless LAN from other wireless LANs. Therefore according to one embodiment of the present invention all access points or wireless terminals that desire to access a specific wireless LAN are designed to use the same unique SSID.

The WEP encrypts data that is communicated between an adaptor and an access point connected to the wireless LAN into 64 bits 40 24 or 128 bits 104 24 resulting in increased security. According to one embodiment of the present invention the WEP key value is used as an encryption key value and the same WEP key value is assigned to a plurality of communication terminals.

In the meantime the SSID is configured in the form of a predetermined unique value that is a combination of a unique number e.g. a hotel room number 501 assigned to a specific local area and a name e.g. KIM of a user who uses the specific local area. The WEP key is configured in the form of a predetermined unique value that is a combination of a name e.g. KIM of a user who uses the specific local area and a card number e.g. 4518 XXXX XXXX XXXX .

The local slave transmits the SSID to personal devices and contained in the corresponding local area LOCAL AREA and displays the WEP key value on the screen. The user may establish the SSID and the key value in each personal device. Therefore the personal device in which the SSID and the WEP key value are established may receive Internet service through the local slave and the master and a detailed description thereof will hereinafter be described with reference to .

Referring to if a user who desires to lodge in a hotel checks in to the hotel at step S a management slave Slave indicating a personal computer PC located at the front desk of the hotel combines a unique number of a hotel room in which the user will stay with name of the user and generates a unique SSID and a WEP key value at step S.

The Slave establishes the SSID and the WEP key value in a local slave Slave connected to the Salve through the master at step S. For example the Slave transmits the SSID to the Personal Device using a beacon signal at step S.

If the personal device selects the SSID at step S the user may attempt to access the Internet service. In this case the personal device transmits a connection try command signal to the AP card at step S. If the AP card recognizes an Internet service access attempt signal on the basis of the connection try command signal at step S the AP card wakes the DTV contained in the Slave at step S.

The AP card may transmit the SSID and the WEP key value to the DTV at step S and the DTV may display the WEP key value on the screen at step S. The user enters the displayed WEP key value in the personal device so as to perform a series of WEP key setup operations at step S. Thereafter the user requests the Internet service such that the personal device can receive the Internet service and the like through the local slave Slave and the master using the established Internet SSID and WEP key value.

For example if a user who desires to lodge in a hotel checks in to the hotel at step S a management slave Slave indicating a personal computer PC located at the front desk of the hotel may transmit a unique number of a hotel room in which the user will stay the user s name the user s resident registration number or the card number to the AP card of the Slave connected to the Slave through the master at step S.

In the meantime the AP card combines the unique number of the hotel room and the user s name such that it generates a predetermined unique SSID using the combined result. The AP card combines the user s resident registration number and or the card number such that it generates a predetermined unique WEP key value at step S.

If the personal device selects the SSID at step S the user may attempt to access the Internet service. In this case the personal device transmits a connection try command signal to the AP card at step S. If the AP card recognizes an Internet service access attempt signal on the basis of the connection try command signal at step S the AP card wakes the DTV contained in the Slave at step S.

The AP card may transmit the SSID and the WEP key value to the DTV at step S and the DTV may display the WEP key value on the screen at step S.

The user enters the displayed WEP key value in the personal device so as to perform a series of WEP key setup operations at step S. Thereafter the user requests the Internet service such that the personal device can receive the Internet service through the local slave Slave and the master using the established Internet SSID and WEP key value.

For example if a user who desires to lodge in a hotel checks in to the hotel at step S a management slave Slave indicating a PC located at the front desk of the hotel may transmit a unique number of a hotel room in which the user will stay the user s name the user s resident registration number or the card number to the AP card of the Slave being connected to the Slave through the master at step S.

The AP card may wake the DTV of the local slave Slave at step S and transmit a unique number of the hotel room a user name and a user s resident registration number or a card number to the DTV at step S.

The DTV combines the unique number of the hotel room and the user s name such that it generates a predetermined unique SSID. In addition the DTV combines the user s name the user s resident registration number and or the card number such that it generates a predetermined unique WEP key value at step S.

The DTV transmits the SSID and the WEP key value to the AP card at step S. The DTV automatically enters a power saving mode i.e. a sleep mode at step S. The AP card wirelessly transmits the SSID to the personal device using a beacon signal at step S.

If the personal device selects the SSID at step S the user may attempt to access the Internet service. In this case the personal device transmits a connection try command signal to the AP card at step S. If the AP card recognizes an Internet service access attempt signal on the basis of the connection try command signal at step S the AP card wakes the DTV contained in the Slave at step S.

The AP card may transmit a command signal that asks the DTV to display the WEP key value to the DTV at step S and the DTV may display the WEP key value on the screen at step S.

The user enters the displayed WEP key value in the personal device so as to perform a series of WEP key setup operations at step S. Thereafter the user requests the Internet service such that the personal device can receive the Internet service and the like through the local slave Slave and the master using the established Internet SSID and WEP key value.

In the case of using the above mentioned embodiment although a first device Device of a Room is close to an AP Card of a Room it communicates with an AP Card of the Room . Similarly although a second device Device of a Room is close to the AP Card of the Room it communicates with the AP Card of the Room . Therefore respective AP cards may not communicate with devices of other rooms whereas they communicate with devices of a corresponding physical space. That is according to one embodiment of the present invention the user of each room may sufficiently receive a communication service of a given bandwidth irrespective of an amount of data used for communication with a user of another room.

Further the network management server may transmit the same or another control signal to AP cards of individual rooms shown in . As a result the DTV to which the AP card of each room is mounted can display a room interactive service including a variety of services capable of being provided in the hotel for example room service hotel information a reservation service a check out information service an entertainment service a game service etc.

Different room interactive services may be provided to individual rooms. Otherwise only some rooms of the hotel may receive different room interactive services or all the rooms of the hotel may receive the same room interactive services.

In the meantime the device located at each room of the hotel may receive data of a VoIP service data of a VOD service or data of an Internet service.

In accordance with the related art the American Public Broadcasting System carries a message to be transmitted to all areas through a general MPEG 2 stream. In addition according to Open Cable Standard if an emergency alert message is transmitted through Out Of Band OOB the emergency alert is compulsorily tuned to a specific channel. However the above mentioned methods can be controlled only by a broadcast station and are unable to provide different message services to individual rooms of a hotel or the like. One embodiment of the present invention provides a method for solving the problems of the related art. Specifically a management server and a DTV under the coaxial communication environment and the IP communication environment according to the embodiment of the present invention will hereinafter be described in detail. For example the management server may be a server that is managed by a hotel or the like.

First of all the management server and the DTV for use in a hotel under a coaxial communication environment according to one embodiment of the present invention will hereinafter be described in detail.

Under the condition that a DTV located in one independent space among a plurality of independent spaces physically separated from each other is connected to the management server through coaxial connection the management server encodes a Transport Stream TS packet multiplexes the encoded TS packet and a general broadcast signal and transmits the multiplexed TS packet and the general broadcast signal to the DTV. However a header of the TS packet includes at least one of ID information of the independent space text data to be displayed location information of the message file and a display time period for which the text data is displayed.

Further the message file may be configured in a XML format. For example the message file includes at least one of information about the total number of messages contained in the message file information for identifying whether or not displayed text data is repeated a type of the text data information about a location where the text data is displayed color information of the text data and transparency information of a background where the text data is displayed.

In the meantime under the condition that a DTV located in one independent space among a plurality of independent spaces physically separated from each other is connected to the management server via a coaxial line the DTV receives a TS packet and decodes the TS packet. If ID information of the independent space defined in the TS packet header is identical to pre stored ID information of the independent space including the DTV the DTV extracts the message file using the location information of the message file and stores the extracted message file. However a header of the TS packet includes at least one of ID information of the independent space text data to be displayed location information of the message file and a display time period for which the text data is displayed.

Further the DTV determines whether a current time reaches a target time at which the text data should be displayed using the time period information. If the current time reaches the target time the DTV displays the text data.

Therefore according to the above mentioned method the differential local messaging service can be provided to individual rooms of a hotel under a coaxial communication environment.

Next the management server and the DTV for use in a hotel under an IP communication environment according to one embodiment of the present invention will hereinafter be described in detail.

Under the condition that a DTV located in one independent space among a plurality of independent spaces physically separated from each other is connected to the management server through IP connection the management server generates a message file including an Application Programming Interfaces API command and a parameter related to a display condition and gains access to an IP address of a DTV to which the generated message file is to be transmitted. If the management server has successfully accessed to the IP address of the DTV it transmits the generated message file to the DTV of the accessed IP address and receives information for identifying whether the message file is successfully processed from the DTV.

Further the message file may be configured in a XML format. For example the message file may correspond to a command signal for displaying text data defined in the message file. The parameter related to the display condition includes at least one of information about the total number of messages contained in the message file information for identifying whether or not displayed text data is repeated a type of the text data information about a location where the text data is displayed color information of the text data and transparency information of a background where the text data is displayed.

In the meantime under the condition that a DTV located in one independent space among a plurality of independent spaces physically separated from each other is connected to the management server through IP connection the DTV receives a message file including an API command and a parameter related to a display condition and parses the received message file. If the API command contained in the parsed message file corresponds to a command signal for displaying the text data defined in the message file the DTV displays the text data in response to the parameter and feeds back specific information for identifying the success or failure of processing the message file to the management server.

Further the specific information for identification is designed to include at least one of an IP address of the DTV and a DTV ID mapped to the IP address.

Therefore according to the above mentioned method the differential local messaging service can be provided to individual rooms of a hotel under an IP communication environment.

The message file according to one embodiment of the present invention can be newly defined as shown in . Individual attributes shown in will hereinafter be described in detail.

If the message is added deleted or changed the value of 1 is added to the message Ver attribute resulting in message Ver attribute 1 such that message Ver attribute 1 is newly distributed to each DTV. When each DTV reads the message file and the message Ver attribute is increased the DTV reads a conventional message and newly receives a corresponding message.

If the additionalInfo attribute receives a key signal corresponding to the Enter button among a plurality of buttons of the remote controller it is connected to an information page of a corresponding ID from among several information pages present in a conventional DTV or STB. For example the additionalInfo attribute is linked to any of information pages e.g. weather information page restaurant menu page etc. generally used in a hotel environment or the like such that the guest can immediately access a corresponding page while the message file is displayed.

The startTime attribute means for example a time in 24 hour format and the startDate attribute means a date.

The repeat attribute determines establishment of repetition on a basis of the StartTime attribute and repeatType attribute determines the type of repetition for example everyday Monday Friday Monday Saturday etc. If the repeat attribute is disabled this attribute is meaningless. At a time point at which a specific message begins to be displayed the repeat 0 non repeating message is deleted from an EEPROM and repeat 1 repeating message changes the startDate attribute to another on the basis of the repeatType condition. For example if it is assumed that the repeatType field indicates the range of Monday Friday and a date of today is October 16 Friday the startDate attribute is changed to October 19 Monday and is overwritten in an EEPROM.

The messageType attribute may display a unique message. For example the welcome message may display not only a predetermined audio video stream but also content. The fire alarm message may inform the guest of where an emergency exit or a shelter is. If a predetermined period of time has elapsed the fire alarm message is switched off. For another example the messageType attribute may also indicate a general message as a default.

The exposureSeconds attribute may indicate an exposure time in seconds. A corresponding message is continuously displayed during the time defined in the exposureSeconds attribute is continuously displayed until it is replaced with a new message or is continuously displayed until a user or guest turns off this message.

The letterColor attribute may determine an RGB based color of a letter and the BGColor attribute may determine an RGB based color of a background.

A method for allowing the management server of a hotel or the like to manage the message file shown in will hereinafter be described in detail.

The management server receives messages through various user interfaces e.g. web interface and the like and stores the received messages in a format of a meta data script file.

One message file includes at least one message and the management server may delete unnecessary messages using the time threading scheme. For example the management server may manage N 1 messages where N is the total number of DTVs present in each room of a hotel or the like that is N is the number of messages different in individual DTVs and the value of 1 means one common message.

In case of such messages different in individual DTVs each message file is entitled to as message serial number or room number .xml such that it is prevented that a DTV having a different serial number or a different room number gains access to the above message file. If the above mentioned message design is applied to the embodiment of the present invention a message capable of being displayed only on a DTV of a specific room can be easily designed and an identifier is added to a file name so that an amount of load required for implementing the local messaging service environment of the present invention can be greatly reduced.

Particularly shows an exemplary case in which an BannerAttribute information displayed on the screen of a DTV located in each room of the hotel is written in Java.

For example the Xlet application determines attributes of a banner such that it can generate BannerAttribute information shown in . In addition the Xlet application registers the generated BannerAttribute information. Further the BannerManager attribute e.g. hotel server management server etc. may directly construct a banner image displayed on the display screen according to the generated BannerAttribute information. For this purpose the BannerAttribute information may be implemented in a Java class.

The BannerManager attribute receives the generated BannerAttribute information from the Xlet application such that it changes a status of a banner displayed on the display screen. For this purpose the The BannerManager attribute may include a plurality of Application Programming Interfaces APIs .

In more detail the BannerManager attribute may include a status control API setBanner for controlling the output of the banner in response to a command received from the Xlet application and a status information API getBanner for indicating a current output status.

For example there are four banner states each of which is displayed by the above mentioned status information API getBanner . In more detail the four banner states are a Not Ready state a Ready state an In Progress state and a Pause state. The Not Ready state means that a banner image is not prepared yet. The Ready state means that a banner image is prepared but not yet displayed. The In Progress state means that a banner image is displayed on the display screen. The Pause state means that displaying of a banner image is stopped.

If a user desires to display such a display image on the display screen the application calls the BannerManager in which manner attribute information is registered and the called BannerManager constructs a banner image using the registered banner attribute information.

For example the Xlet application may transmit a showMessage command to the BannerManager such that the BannerManager may display a banner image on the display screen using banner attribute information defined in the BannerAttribute field.

As described above the hotel management server according to one embodiment of the present invention may configure a message file provided to each room in an XML format shown in or an API format shown in or .

Referring to under a coaxial communication environment of a hotel or the like a method for allowing the management server to transmit a message file to a DTV and a method for allowing a DTV to receive process the message file will hereinafter be described in detail.

A hotel administrator configures a message file to be transmitted to each room in an XML format using the web interface and transmits the XML format message file to the file system of the management server .

The encoder of the management server encodes the received XML file and thus configures a TS packet. However a header of the TS packet may include the message file name the Message Ver attribute shown in an attribute of a pointer to actual message file and an attribute of a pointer to end message file. The attribute of each of the pointer to actual message file and the pointer to end message file may designate an actual position of a message file in a stream.

The transmitter transmits the TS packet as a carousel stream. The modulator modulates the received carousel stream into a Radio Frequency RF data stream. The multiplexer multiplexes the RF data stream and a general broadcast signal e.g. an RF A V stream and transmits the multiplexed result to a DTV of each room of the hotel.

The tuner of the DTV receives the encoded TS packet from the multiplexer . The decoder analyzes the header of the TS packet. If the ID information of the independent space defined in the TS packet is identical to pre stored ID information of an independent space including the DTV the XML parser extracts the message file using the location information of the message file.

In accordance with another embodiment of the present invention a first case 1 in which the message file is either a common message or a file for accurately designating a serial number and a DTV ID of a corresponding DTV and or in a second case 2 in which the Message Ver attribute value is higher than an attribute value of a current message file the system according to the embodiment of the present invention extracts a message file from a stream using the pointer to actual message file and the pointer to end of message file attribute and transmits the extracted message file to the XML parser.

The XML parser extracts information stored in the message file and stores the extracted information in the file system . The display unit displays text data of the message file when the StartTime date condition is satisfied.

Referring to under an IP communication environment of a hotel or the like a method for allowing the management server to transmit a message file to a DTV and a method for allowing a DTV to receive process the message file will hereinafter be described in detail.

The file system of the management server of the hotel or the like generates an XML file including an API command and a parameter related to a display condition. The CPU gains access to an IP address of a DTV serving as a destination of the generated message file using the LAN device .

If the above mentioned access was successful the generated message file is transmitted to the LAN device of the DTV of the accessed IP address. In addition the management server receives ID information for identifying the success or failure of processing the message file through the LAN devices and .

The DTV receives a message file including an API command and a parameter related to a display condition through the LAN device . The XML parser parses the received message file. If the API command contained in the parsed message file corresponds to a command signal for displaying the text data defined in the message file the display unit displays the text data in response to the parameter and feeds back specific information for identifying the success or failure of processing the message file to the management server through the LAN device .

In other words under the IP communication environment the management server can manage and control respective DTVs in real time using the API call scheme. The management server can determine whether to display all messages and control display times of all the messages such that an amount of data to be transmitted to each DTV is reduced and the DTV need not store the message file therein.

The system for use in the IP communication environment transmits XML information in the same manner as a command such that it can control the displaying of one message of each DTV differently from the coaxial communication environment in which each DTV receives and maintains a raw message file. In addition the system for use in the IP communication environment need not designate an ID of a target ID and may gain directly access to an IP address of a corresponding DTV and transmit a message file e.g. XML file .

However the message file includes for example an API command and parameters related to a display condition. The API command may correspond to a command signal for displaying text data defined in the message file. The parameter related to the display condition includes at least one of information about the total number of messages contained in the message file information for identifying whether or not displayed text data is repeated a type of the text data information about a location where the text data is displayed color information of the text data and transparency information of a background where the text data is displayed.

In the meantime if the DTV receives the message file from the management server it extracts the API command i.e. a command signal for displaying text data defined in the above mentioned message file and displays messages in response to the aforementioned parameters in real time. The DTV may transmit a response signal to the management server .

The response signal may include ID information for identifying the success or failure of processing the above mentioned message file. For example the ID information may be 1 at least one of an IP address and a DTV ID mapped to the IP address 2 content of text data or 3 information indicating the success OK or failure NG of displaying the text data.

Under the condition that a management server is connected to a DTV located in one independent space among a plurality of independent spaces physically separated from one another the DTV including the AP card receives the message file shown in or the message file shown in or from the management server. However the management server may be managed by a hotel or the like. The message file may include ID information of the independent space and primary additional information mapped to the ID information of the independent space.

Further the ID information of the independent space may correspond to for example an ID of each room belonging to one hotel. For example the primary additional information may include at least one of hotel advertisement information neighbor map information restaurant information event information reserved in the hotel and information about hotel facilities.

Therefore the hotel server can provide primary additional information customized for a guest of each room to a DTV of the room such that the DTV can display the display image as shown in . Alternatively if a guest of each room enters the corresponding room the welcome message shown in may also be displayed on the DTV.

In contrast a system according to yet another embodiment of the present invention firstly determines whether the independent space ID information contained in the message file is identical to ID information of a current independent space instead of unconditionally parsing and displaying the above mentioned primary additional information. If the independent space ID information contained in the message file and the current independent space ID information are identical to each other the primary additional information is displayed. Therefore the hotel management server can provide various data services to individual rooms and increase the protection of guest privacy.

Furthermore the DTV according to the present invention transmits a request signal for requesting secondary additional information corresponding to the first additional information and a response signal including the above mentioned independent space ID information to the management server. The DTV displays the secondary additional information received from the management server as shown in . Although shows only secondary additional information corresponding to the restaurant item as an example of the above mentioned primary additional information the DTV according to the present invention may also transmit a request signal for requesting secondary additional information corresponding to other items e.g. neighbor map event and hotel facility items and a response signal including the above mentioned independent space ID information to the management server and the management server may provide the secondary additional information to the DTV in response to the request signal and the independent space ID information. Subsequently the management server may also provide not only a signal for requesting third additional information related to secondary additional information but also another signal for requesting third additional information related to a response signal including the independent space ID information to the DTV corresponding to the independent space ID information. For example although not shown in the drawing if the guest of the hotel room selects the Chinese Food item names and locations addresses of the principal Chinese restaurants may be provided to the DTV. Moreover as well as information about the neighbor map event and hotel facilities transportation and weather information may be further added to the DTV.

When the hotel management server provides additional information to a DTV of each room and receives a response signal from each room of the hotel the hotel management server stores ID information of each room. As a result the hotel management server can also process different request signals from several rooms. Therefore the interactive service can be achieved between the DTV located in each room of the hotel and the management server the management server need not initially transmit heavy data to all DTVs of the hotel and can provide more detailed information related to guest requested information to the guest. Technically the AP card contained in the DTV is designed to convert data of cable modem type into data of IP type.

Therefore the system according to the embodiment of the present invention provides the messaging interface between the DTV of each room of the hotel and the management server such that the hotel administrator or hotelier can differentially provide various messages to respective rooms.

Regardless of a physical communication environment of the hotel e.g. coaxial communication environment or IP communication environment the system according to the embodiment of the present invention can implement the local messaging service in the hotel. Furthermore the welcome message may be automatically transmitted to each guest through the PMS server or the like or a function for providing information about food menus to the guest may be easily added to the system. In addition the system may interoperate with a GEM broadcast system such that it can recognize detailed information about the corresponding message using the GEM application.

In the meantime the product invention and the process invention have been disclosed in the present invention and the product invention may be complementary to the process invention as necessary.

The method disclosed in the present invention may be implemented in the form of program commands executable by a variety of computer means and recorded on a computer readable recording medium.

The computer readable recording medium may include program commands data files data structures etc. individually or in combination. The program commands recorded on the medium may be ones specially designed and configured for the present invention or ones known and available to those skilled in computer software. Examples of the computer readable recording medium include magnetic media such as a hard disk a floppy disk and a magnetic tape optical media such as a compact disc read only memory CD ROM and a digital versatile disc DVD magneto optical media such as a floptical disk and hardware devices specially configured to store and execute program commands such as a ROM a random access memory RAM and a flash memory. Examples of the program commands include high level language codes that may be executed by a computer using an interpreter etc. as well as machine language codes such as those produced by a compiler.

The above stated hardware devices may be configured to operate as one or more software modules to perform the operation of the present invention and vice versa. Although the present invention has been described in conjunction with the limited embodiments and drawings the present invention is not limited thereto. Those skilled in the art will appreciate that various modifications additions and substitutions are possible from this description. Therefore the scope of the present invention should not be limited to the description of the exemplary embodiments and should be determined by the appended claims and their equivalents.

As apparent from the above description the present invention provides a technology for automatically generating customized service information and provides the customized service information to a guest who uses a hotel or the like. In addition the present invention can provide a technology for providing the customized service information and at the same time improving security.

It will be apparent to those skilled in the art that various modifications and variations can be made in the present invention without departing from the spirit or scope of the inventions. Thus it is intended that the present invention covers the modifications and variations of this invention provided they come within the scope of the appended claims and their equivalents.

