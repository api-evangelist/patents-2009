---

title: System and method for production of multiuser network game
abstract: Provided is a system and method for production of a multi-user network game that may produce and debug a multi-user network game and simply construct a multi-user network game environment using a single game production tool to thereby reduce a game production time. A system for production of a multi-user network game being performed between a game server and a plurality of game clients via a network, may include: a game production module configured to produce and debug the multi-user network game and a multi-user network execution environment; and an emulation module configured to emulate an execution of the multi-user network game by constructing a virtual network execution environment that comprises at least one server virtual machine and at least one client virtual machine configured to execute the produced or debugged multi-user network game.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08583761&OS=08583761&RS=08583761
owner: NHN Corporation
number: 08583761
owner_city: Seongnam-si
owner_country: KR
publication_date: 20091117
---
This application claims priority from and the benefit of Korean Patent Application No. 10 2008 0115868 filed on Nov. 20 2008 which is hereby incorporated by reference for all purposes as if fully set forth herein.

Exemplary embodiments of the present invention relate to a system and method for production of a multi user network game. More particularly the present invention relates to a system and method for production of a multi user network game that may produce and debug a multi user network game and simply construct a multi user network game environment using a single game production tool to thereby reduce a game production time.

Currently computers are widely distributed and used. Accordingly network games using the computers are in development. Companies programming the network games using a game production tool are investing a great amount of manpower to provide various types of network games. A game production tool is a tool to complete a game by combining contents constituting a user interface for example design elements sound and the like and logic required to perform the game.

In the case of a network game multi user games enabling a plurality of users to simultaneously play a single game are currently becoming popular.

However most conventional game production tools are based on a single user game played by a single user.

Accordingly a conventional method for production of a multi user network game may include the steps of developing a game client using a game production tool configured to develop the game client developing a game server using another game production tool configured to develop the game server and repeatedly executing the developed game client and game server to construct a network execution environment and a multi play execution environment.

The conventional method for the production of the multi user network game may have the following problems.

First since each of the game client and the game server needs to be developed using a separate game production tool it generally takes a long time to produce the multi user network game.

Second the network execution environment and the multi play execution environment are different for each network game service system. Accordingly a process of modifying a game that is developed to be installed in a corresponding network game service system and to interoperate with another server system may need to be performed. Specifically it may be difficult to easily provide a network game service.

Exemplary embodiments of the present invention provide a system and method for production of a multi user network game that may produce and debug a multi user network game and simply construct a multi user network game environment using a single game production tool to thereby reduce a game production time.

Additional features of the invention will be set forth in the description which follows and in part will be apparent from the description or may be learned by practice of the invention.

An exemplary embodiment of the present invention discloses a system for production of a multi user network game being performed between a game server and a plurality of game clients via a network the system including a game production module configured to produce and debug the multi user network game and a multi user network execution environment and an emulation module configured to emulate an execution of the multi user network game by constructing a virtual network execution environment that includes at least one server virtual machine and at least one client virtual machine configured to execute the produced or debugged multi user network game.

An exemplary embodiment of the present invention also discloses a method for production of a multi user network game being performed between a game server and a plurality of game clients via a network the method including the steps of executing a game production module for the production of the multi user network game to provide a game production screen producing a game script for the multi user network game based on a script language using the game production module constructing in a game preview step a virtual network execution environment that includes at least one server virtual machine and at least one client virtual machine configured to execute the game script to thereby emulate an execution of the game script in the virtual network execution environment and debugging the game script according to a result of the game preview step.

It is to be understood that both the foregoing general description and the following detailed description are exemplary and explanatory and are intended to provide further explanation of the invention as claimed.

The invention is described more fully hereinafter with reference to the accompanying drawings in which exemplary embodiments of the invention are shown. This invention may however be embodied in many different forms and should not be construed as limited to the embodiments set forth herein. Rather these exemplary embodiments are provided so that this disclosure is thorough and will fully convey the scope of the invention to those skilled in the art. In the drawings the size and relative sizes of layers and regions may be exaggerated for clarity. Like reference numerals in the drawings denote like elements.

According to exemplary embodiments of the present invention a multi user network game produced using an emulation module by generating each of a client virtual machine and a server virtual machine for executing and debugging the multi user network game may be emulated in a virtual network execution environment. Through this it is possible to produce and debug the multi user network game in a game production environment and simply construct a multi user network game environment using a single game production tool and to thereby reduce a game production time.

Also according to exemplary embodiments of the present invention a virtual machine container may include a client virtual machine container and a server virtual machine container that independently operate with each other in a virtual network environment. Accordingly in a network execution environment of an actual multi user network game when it is set to drive the client virtual machine container in a user client to drive the server virtual machine container in an online game server and to use an actual network instead of using a network emulator it is possible to drive a client virtual machine and a server virtual machine in an online service environment. Therefore it is possible to easily install in a multi user network game service system the multi user network game developed by a production system and to enable the multi user network game to interoperate with other server systems.

Referring to the multi user network game production system may include a game production module configured to produce and debug the multi user network game and a multi user network execution environment and an emulation module configured to provide the virtual network execution environment and to emulate in the virtual network execution environment the multi user network game that is produced by generating each of at least one client virtual machine and at least one server virtual machine for executing and debugging the multi user network game. The at least one client virtual machine and at least one server virtual machine may be configured to execute the produced or debugged multi user network game.

The game production module may include a game production user interface a game edit tool and a game previewer .

The game production user interface may provide a user with a user interface for the production of the multi user network game using a game production screen. Therefore the user may create the multi user network game and a network execution environment by manipulating the game edit tool via the game production user interface . The game production user interface may support a full screen mode and a single window mode on a computer operating system such as WINDOWS . The game production user interface may be based on an object oriented program language.

The game edit tool may provide the user or a developer with a multi user network game production environment in a game production environment so that the user or the developer may perform generating editing a sprite or an image defining generating editing a game object appearing in a corresponding game and generating editing or debugging a client game script and a server game script for executing the game and a network environment.

The game edit tool may include a sprite editor configured to produce an object independently moving in the game or constituting a background a game object editor configured to produce an object that needs a motion in the game a script editor configured to produce a game script defining a game play environment of the object based on a script language and a script debugger configured to debug the game script. The script language may include for example JAVASCRIPT VBScript PYTHON LUA and the like. Any type of script languages providing an object oriented model may be used.

The game previewer may drive the emulation module to display on the game production screen an execution process of the produced multi user network game. The game previewer may emulate in a virtual network environment a script of the multi user network game that is produced via the game edit tool and thereby enable the user to preview an emulation result of the multi user network game.

The emulation module may construct the virtual network environment in the multi user network game production environment to emulate the multi user network game. For example the emulation module may emulate the multi user network game and the network execution environment by constructing the virtual network environment where at least one game room that is at least one server virtual machine and at least one game client i.e. client virtual machine may participate.

For this as shown in the emulation module may include a virtual machine container and a network emulator .

The virtual machine container may include a client virtual machine container configured to manage client virtual machines CVM through CVM n and a server virtual machine container configured to manage server virtual machines SVM through SVM n. Therefore in the game production environment the virtual machine container may drive the client virtual machine container and the server virtual machine container in the same environment to thereby construct the virtual network environment in an integrated production environment. In an actual network service environment the virtual machine container may drive the client virtual machine container in a user personal computer PC that is a client and drive the server virtual machine container in an online game server system so that a game produced in the game production environment may operate comparably even in an actual online game service environment.

As shown in according to an exemplary embodiment of the present invention the client virtual machine container may include a client virtual machine drive module a network event management module an external module interoperation management module and a window control management module .

The client virtual machine drive module may generate and manage a number of client virtual machines CVM through CVM n corresponding to a numeral set by the user using a client virtual machine application programming interface API provided from the client virtual machines CVM through CVM n.

The network event management module may transfer an event between each of the client virtual machines CVM through CVM n and each of the server virtual machines SVM through SVM n via the client virtual machine drive module . Here when a network event for example a transmission reception of a network packet a network connection a network disconnection or the like occurs the network event management module may convert the network event to a format that may be understood by each of the client virtual machines CVM through CVM n.

The external module interoperation management module may conduct the interoperation of each of the client virtual machines CVM through CVM n with a service system for an extrinsic online service of a game while the multi user network game is being executed. For this the external module interoperation management module may include a protocol for an interoperation with an external module and support a communication between the external module and each of the client virtual machines CVM through CVM n using a function callback. Here the protocol may be different for each game service. Accordingly the external module interoperation management module may connect the virtual machine container and the external module needing the communication with each of the client virtual machines CVM through CVM n in a plug in form. The service system for the extrinsic online service of the game may be for example a lobby server a room server a database module a ranking service server a location management service server or the like.

The window control management module may transfer to each of the client virtual machines CVM through CVM n via the client virtual machine drive module a game window displaying a screen of the multi user network game and a game event occurring in the game window. Specifically the window control management module may generate the game window and coordinate a location of the game window to transfer to each of the client virtual machines CVM through CVM n the game event such as a mouse click a keyboard input or the like occurring in the game window.

As shown in according to an exemplary embodiment of the present invention the server virtual machine container may include a server virtual machine drive module a network event management module an external module interoperation management module and a thread control management module .

The server virtual machine drive module may generate and manage a number of server virtual machines SVM through SVM n corresponding to a numeral set by the user using a server virtual machine API provided from the server virtual machines SVM through SVM n. Generally each of the server virtual machines SVM through SVM n may indicate a single game room.

The network event management module may transfer to each of the server virtual machines SVM through SVM n via the server virtual machine drive module a network event that occurs while the multi user network game is being executed. Here when the network event for example a transmission reception of a network packet a network connection a network disconnection or the like occurs the network event management module may convert the network event to a format that may be understood by each of the server virtual machines SVM through SVM n.

The external module interoperation management module may conduct the interoperation of each of the server virtual machines SVM through SVM n with a service system for an extrinsic online service of a game while the multi user network game is being executed. For this the external module interoperation management module may include a protocol for an interoperation with service systems and support a communication between the service systems and the server virtual machines SVM through SVM n using a function callback. Here the protocol may be different for each game service. Accordingly the external module interoperation management module may connect the virtual machine container and the service systems needing the communication with each of the server virtual machines SVM through SVM n in a plug in form. The service systems for the extrinsic online service of the game may include for example a database server a ranking service server a location management service server and the like.

The thread control management module may provide a thread pool so that the server virtual machine drive module may generate and manage the plurality of server virtual machines SVM through SVM n. Here the thread pool may be required since the number of server virtual machines SVM through SVM n may vary according to the capacity of a game server for example the number may increase or decrease to be suitable for the capacity of the game server . When executing the game the thread control management module may drive the server virtual machines SVM through SVM n by allocating an available thread to the server virtual machines SVM through SVM n.

The server virtual machine container may further include a timer event management module not shown configured to transfer to each of the server virtual machines SVM through SVM n via the server virtual machine drive module a timer event occurring in the execution of the multi user network game.

As shown in each of the client virtual machines CVM through CVM n of may include an object oriented script engine a graphic engine a sound engine a network engine a game object system a graphic engine script interface a sound engine script interface a network engine script interface and a game object script interface .

The object oriented script engine may provide an execution environment of a script file generated using an object oriented program language.

The graphic engine may provide an execution environment for rendering animation and design on a screen of the multi user network game.

The network engine may convert to a network event network messages that are generated within a game script being performed by a client virtual machine and that are transferred and may transfer the network event to the client virtual machine container managing the client virtual machine. In this case the network event management module of the client virtual machine container may provide an environment for a network communication with each client and server by transferring the network event to another client virtual machine and or server virtual machine via the network emulator .

The game object system may be in charge of managing objects generated within the game script being performed by the client virtual machine transferring a message between the objects processing the game event and managing statuses of game objects. In the case of the message transfer between the objects when an object to receive the message is an object generated in another client virtual machine and or server virtual machine the message may be transferred via the network engine .

The graphic engine script interface may provide an interface between the game script and the graphic engine using the object oriented script engine .

The sound engine script interface may provide an interface between the game script and the sound engine using the object oriented script engine .

The network engine script interface may provide an interface between the game script and the network engine using the object oriented script engine .

The game object script interface may provide an interface between the game script and the game object system using the object oriented script engine .

As shown in each of the server virtual machines SVM through SVM n of may include an object oriented script engine a network engine a game object system a network engine script interface and a game object script interface .

The object oriented script engine may provide an execution environment of a script file generated using an object oriented program language.

The network engine may convert to a network event network messages that are generated within a game script being performed by a client virtual machine and that are transferred and may transfer the network event to the server virtual machine container managing the server virtual machine. In this case the network event management module of the server virtual machine container may provide an environment for a network communication with each client and server by transferring the network event to another client virtual machine and or server virtual machine via the network emulator .

The game object system may be in charge of managing objects generated within the game script being performed by the server virtual machine transferring a message between the objects processing the game event and managing statuses of game objects. In the case of the message transfer between the objects when an object to receive the message is an object generated in another client virtual machine and or server virtual machine the message may be transferred via the network engine .

The network engine script interface may provide an interface between the game script and the network engine using the object oriented script engine .

The game object script interface may provide an interface between the game script and the game object system using the object oriented script engine .

The network emulator of may manage a network socket a network identifier ID and a message queue and may emulate a network message transfer process. In doing so it may provide a virtual network execution environment as if the user is connected to an actual network and enable an analysis of the transferred message. Here the network ID may be used as a virtual address to indicate a connection of the network socket and thus may enable a message transmission without using an actual network address.

The virtual machine container may generate and manage a plurality of client virtual machines and a plurality of server virtual machines and include a table containing virtual machine network ID for a network connection. The network emulator may also include a table containing a network ID network socket in order to manage its management targets.

Hereinafter the process of driving the virtual machine container and the network emulator according to an exemplary embodiment of the present invention will be described with reference to and .

In operation S the virtual machine container requests the network emulator for a virtual network connection. Specifically in operation S the virtual machine container may transfer to the network emulator a request to connect the client virtual machine and the server virtual machine.

In operation S the network emulator performs the virtual network connection and then assigns a network ID. Specifically in operation S the network emulator may perform the virtual network connection and then add to a table a network ID and a network socket corresponding to the network connection.

In operation S the network emulator transfers the assigned network ID to the virtual machine container . Specifically in operation S the network emulator may transfer to the virtual machine container the network ID that is added to the table. Accordingly the virtual machine container may complete the network connection process by adding to a table a virtual machine network ID corresponding to the network connection that is transferred from the network emulator .

Hereinafter the process of transmitting the message from the client virtual machine to the server virtual machine according to an exemplary embodiment of the present invention will be described with reference to and .

In operation S the client virtual machine generates a network packet and transfers the generated network packet to the virtual machine container . Here when the client virtual machine transfers a message to the virtual machine container the client virtual machine may generate the network packet in a form of origination destination and message . Each of the origination and the destination may correspond to a network ID. The message may correspond to game execution information.

In operation S the network packet transferred from the client virtual machine is transferred to the network emulator via the virtual machine container .

In operation S the network emulator emulates a process of transferring the message of the network packet to the destination and transfers the network packet to the virtual machine container . Specifically the network emulator may emulate a process of receiving the network packet to transfer the message to a network socket corresponding to the network ID of the destination. In particular the network emulator may emulate a network characteristic that the message is accumulated in a queue in a form of a packet. The network emulator may transfer to the virtual machine container the network packet in a form of origination destination and message .

In operation S the virtual machine container receives the network packet from the network emulator and transfers the message to the destination of the network packet. Here the virtual machine container may determine a virtual machine to transfer the message based on the destination of the network packet transferred from the network emulator and may transfer the message to the determined virtual machine. For example when a network ID of the destination corresponds to a network ID of a server virtual machine the virtual machine container may transfer the message to the server virtual machine.

The information storage unit emulator may provide a simulation function with respect to an information storage unit not shown configured to store extrinsic information of a virtual game by emulating an information transfer between each of client virtual machines and server virtual machines and the information storage unit which is shown in . Here the extrinsic information of the virtual game may include an ID of a game player membership information a game grade and the like. The information storage unit may be a database configured to store the extrinsic information. The extrinsic information may be stored in a form of a script file generated using a script language.

As shown in the information storage unit emulator may include an information loader and a temporary storage unit .

The information loader may load extrinsic information of a corresponding game from an information storage unit in response to a request for an information transfer from at least one of the client virtual machines and the server virtual machines using the virtual machine container .

The temporary storage unit may store the extrinsic information that is loaded from the information loader and may transfer the loaded extrinsic information to a corresponding client virtual machine and or server virtual machine via the virtual machine container .

Hereinafter the method for the production of the multi user network game according to an exemplary embodiment of the present invention will be described with reference to and . The operations and steps may be stored as part of an executable program on a non transitory computer readable storage medium where the program may instruct a microprocessor to perform the operations and steps.

In operation a game production screen is provided by executing the game production module for the production of the multi user network game which is shown in .

In operation a game script used to drive the multi user network game is produced based on a script language using the game production module . Operation may include operations of loading a game level that is pre produced using the game production module or generating a new game level and editing the loaded game level or the new game level. The operation of editing the game level may include operations of generating editing a sprite or an image of the loaded game level or the generated new game level defining generating editing a game object of the loaded game level or the generated new game level and editing the game script of the loaded game level or the generated new game level.

In operation a virtual network execution environment is constructed using the emulation module and a game script produced by each of client virtual machines and server virtual machines for executing and debugging the game script is emulated in the virtual network execution environment.

In operation the game script produced using the game production module is debugged based on an emulation result of operation which is shown in .

In operation it is determined whether a game production is completed. Specifically the game production may be completed by re emulating the debugged game script in the virtual network execution environment and by repeating operations S and S until the game production is completed which is shown in .

In operation S each of a server virtual machine and N client virtual machines is generated and driven using the virtual machine container .

In operation S a virtual network execution environment is constructed using the network emulator to relay a network communication between the server virtual machine and the N client virtual machines.

In operation S a server script is loaded to the server virtual machine and is executed using the virtual machine container .

In operation S a client script is loaded to each of the N client virtual machines and is executed using the virtual machine container .

In operation S an execution result of each of the N client virtual machines is displayed on a game production screen.

The emulation process of may further include an operation of emulating an information transfer between each of the N client virtual machines and the server virtual machine and an information storage unit configured to store extrinsic information of a virtual game.

Specifically as shown in in operation S when at least one of the client virtual machines and the server virtual machine requests an information transfer the virtual machine container requests the information storage unit emulator to transfer information.

In operation the information storage unit emulator loads extrinsic information of a corresponding game from the information storage unit using the information loader .

In operation the information storage unit emulator stores in the temporary storage unit the extrinsic information that is loaded using the information loader and transfers the loaded extrinsic information to a corresponding client virtual machine and or server virtual machine using the virtual machine container .

The method for the production of the multi user network game according to the above described exemplary embodiments of the present invention may be configured as a program that may be performed using various types of computer units. Here the program to implement the method for the production of the multi user network game may be recorded in computer readable media such as hard disks compact disc read only memory CD ROM disks digital versatile discs DVDs read only memory ROM read access memory RAM flash memory and the like.

As described above a system and method for production of a multi user network game according to an exemplary embodiment of the present invention may emulate in a virtual network execution environment a multi user network game that is produced using an emulation module by generating each of at least one client virtual machine and at least one server virtual machine for executing and debugging the multi user network game. Through this the system and method for the production of the multi user network game may produce and debug the multi user network game and simply construct a multi user network game environment using a single game production tool to thereby reduce a game production time.

Referring to the multi user network game service system may include a plurality of game clients . . . a game server and backend service servers and .

The plurality of game clients through denotes a plurality of terminal devices that is connected to a network to receive various types of game applications for example KARTRIDER GOGOSSING GOSTOP poker and the like and thus may include for example a desktop PC a notebook a mobile phone a personal digital assistant PDA a Mobile Broadcast System MBS phone and the like.

As shown in game client may be any of the game clients through and may include a web browser a game client script storage unit a client virtual machine and a client virtual machine container .

The game client script storage unit may store a game script file corresponding to a game application. The game script file may be provided via the web browser and may not necessarily be installed in the game client script storage unit .

The client virtual machine may load the game script file stored in the game client script storage unit to execute a game.

The client virtual machine container may drive the client virtual machine and transmit game execution information of the client virtual machine to the game server . The client virtual machine container may receive game execution information from the game server to provide the received game execution information to the client virtual machine . The client virtual machine container is constructed to be the same as the client virtual machine container of the multi user network game production system of . Therefore further detailed description related thereto will be omitted here.

As shown in the game server may include a game server script storage unit N server virtual machines and a server virtual machine container .

The game server script storage unit may store a game server file corresponding to a game application.

The N server virtual machines may load game script files stored in the game server script storage unit to execute a game. Here each of the N server virtual machines may be a game room.

The server virtual machine container may drive each of the N server virtual machines and relay game execution information between the game clients through . The server virtual machine container is constructed to be the same as the server virtual machine container of the multi user network game production system of . Therefore further detailed description related thereto will be omitted here.

The backend service servers and may be for example a lobby server a room server a database module a ranking service module a location management service server and the like.

Similar to the aforementioned multi user network game production system a multi user network game service system according to an exemplary embodiment of the present invention may drive a client virtual machine and a server virtual machine in a network execution environment of a multi user network game using a virtual machine container . Accordingly it is possible to easily install the developed multi user network game in the multi user network game service system and to create the multi user network game to easily interoperate with other server systems.

Referring to the P2P multi user network game service system may include a plurality of game clients . . . that is connected via a network and backend service servers and .

The plurality of game clients through denote a plurality of terminal devices that is connected to the network to receive various types of game applications for example KARTRIDER GOGOSSING GOSTOP poker and the like and thus may include for example a desktop PC a notebook a mobile phone a PDA an MBS phone and the like.

Any one of the game clients through may perform a game server function. As shown in for example the game client may include a web browser a game client script storage unit a client virtual machine a game server script storage unit N server virtual machines and a virtual machine container .

The game client script storage unit may store a game script file corresponding to a game application. Here the game script file may be provided via the web browser and may not necessarily be installed in the game client script storage unit .

The client virtual machine may load the game script file stored in the game server script storage unit to execute a game.

The game server script storage unit may store a game server file corresponding to a game application.

The N server virtual machines may load the game script file stored in the game server script storage unit to execute the game. Here each of the N server virtual machines may be a game room.

The virtual machine container may drive each of the client virtual machine and the N server virtual machines and may relay game execution information between the game clients through 

Each of the remaining game clients excluding a first game client from the plurality of game clients through for example each of the remaining game clients through excluding the game client from the plurality of game clients through are constructed to be the same as the game clients through of . Therefore further detailed description related thereto will be omitted here.

The backend service servers and may be for example a lobby server a room server a database module a ranking service server a location management service server and the like.

Like the aforementioned multi user network game production system a P2P multi user network game service system according to an exemplary embodiment of the present invention may drive a client virtual machine and a server virtual machine in a network execution environment of a P2P multi user network game using a virtual machine container. Accordingly it is possible to easily install the developed multi user network game in the P2P multi user network game service system and to create the multi user network game to easily interoperate with other server systems.

Even when a virtual machine container according to an exemplary embodiment of the present invention is installed in various types of consoles such as XBOX 360 PLAYSTATION 3 WII and the like the virtual machine container may execute a multi user network game downloaded from a game service system.

It will be apparent to those skilled in the art that various modifications and variation can be made in the present invention without departing from the spirit or scope of the invention. Thus it is intended that the present invention cover the modifications and variations of this invention provided they come within the scope of the appended claims and their equivalents.

