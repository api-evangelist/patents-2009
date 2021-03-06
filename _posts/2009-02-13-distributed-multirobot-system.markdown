---

title: Distributed multi-robot system
abstract: A system is provided that includes at least one manager and one or more robots configured to communicate wirelessly. The manager can include certain functions that generate data, instructions, or both used by one or more robots. The manager can also facilitate communications among several robots, or robots could also be configured to communicate directly.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08755936&OS=08755936&RS=08755936
owner: Seegrid Corporation
number: 08755936
owner_city: Pittsburgh
owner_country: US
publication_date: 20090213
---
This application claims the benefit under 35 U.S.C. 119 e of U.S. Provisional Patent Application No. 61 028 320 filed Feb. 13 2008. This application is also a continuation in part application of U.S. Non provisional patent application Ser. No. 12 361 379 filed Jan. 28 2009 which claimed the benefit of U.S. Provisional Patent Application No. 61 024 028 filed Jan. 28 2008 which are incorporated herein by reference.

This application may be related to U.S. Non provisional Application No. filed Jan. 28 2009 and U.S. Non provisional application Ser. No. 12 361 300 filed Jan. 28 2009.

The present inventive concepts relate to designs architectures functions and methods for robot systems having more than one robot and in particular to systems and methods where communication with and among the robots is possible.

Traditionally the architecture for consumer service robots has consisted of a machine that includes all the physical actuators needed for the service tasks as well as all the perception and computation systems needed to perform the service task. This has resulted in service robots with severe cost and functionality restrictions. Moreover it has resulted in severe design restrictions with each robot needing to serve the same function competently within a wide array of facility environments.

In that regard the robots tended to be singular in purpose and autonomous in that they do not tend to interact in any service oriented manner. A service robot could be introduced into a home for example and would service the home according to the robot s on board preset algorithms. To the extent the robot had any real time adaptability capability it tended to be limited to object detection and avoidance.

In accordance with aspects of the present invention provided is a robot system architecture design and method that enable the creation and use of service robots that are much simpler than those typically used. To achieve this many on board robot functions can be provided as a shared central resource for any number of robots performing functions either serially or simultaneously in a facility.

A system can be provided that includes at least one manager and plural robots configured to communicate wirelessly. The manager can include certain functions that generate data instructions or both used by one or more robots. The manager can also facilitate communications among several robots or robots could also be configured to communicate directly.

In accordance with one aspect of the invention provided is a distributed multi robot system. The system includes a robot manager having a wireless communication module that transmits and receives robot information and a plurality of robots each having a wireless communication module configured to communicate with the robot manager in conjunction with performance of a robot service function.

The robot manager can include a mapping and navigation module configured to generate and update a map of an environment within which the plurality of robots operate.

The mapping and navigation module can be configured to track movement of the plurality of robots within the environment.

The mapping and navigation module can be configured to provide information and data to at least one robot that is used by the robot to navigate within the environment.

The robot manager can be configured to use information provided by at least one of the plurality of robots to generate and update the map of the environment.

The robot manager be configured to use information provided by a wireless transceiver to generate and update the map of the environment.

The map of the environment can include a map of at least one of an office building a warehouse a shopping mall a residential complex and a house.

The robot manager can further include an Internet communication subsystem configured to enable the robot manager to communicate with remote systems.

The robot manager can further include an application framework configured to download software from a remote system and to update the robot manager using the downloaded software.

The robot manager can further include an application framework configured to download software from a remote system and to provide enhanced or different functions to one or more of the plurality of robots using the downloaded software.

The robot manager can further comprise a scheduler configured to schedule operations of at least one robot from the plurality of robots.

The plurality of robots can include at least one of a cleaning robot a security robot and an entertainment robot.

In accordance with another aspect of the invention provided is a distributed multi robot system. The system includes a robot manager having a wireless communication module that transmits and receives robot information and a plurality of robots each having a wireless communication module configured to communicate with the robot manager in conjunction with performance of a robot service function. The robot manager includes a mapping and navigation module configured to generate and update a map of an environment within which the plurality of robots operate an Internet communication subsystem configured to receive information and data used to monitor and control the plurality of robots and an application framework configured to download software from a remote system and to update the robot manager using the downloaded software and to download to provide enhanced or different functions to one or more of the plurality of robots using the downloaded software.

In accordance with another aspect of the invention provided is a method of controlling a plurality of robots in an environment. The method can comprise providing a robot manager having a wireless communication module that transmits and receives robot information and the robot manager communicating with each of a plurality of robots within the environment in conjunction with performance of a robot service function.

The method can further include generating and updating a map of the environment within which the plurality of robots operate.

The method can further include navigating at least one of the plurality of robots through the environment using the map.

The method can further include scheduling operations of at least one robot from the plurality of robots using the robot manager.

The method can further include downloading software from a remote system via the Internet and updating the robot manager using the downloaded software.

The method can further include downloading software from a remote system via the Internet and providing enhanced or different functions to one or more of the plurality of robots using the downloaded software.

The method can further include multiple robots sharing the same information stored at the robot manager.

The method can further include multiple robots updating similar information stored at the robot manager.

The method can further include at least two robots from the plurality of robots communicating with each other.

Hereinafter aspects of the present invention will be described by explaining illustrative embodiments in accordance therewith with reference to the attached drawings. While describing these embodiments detailed descriptions of well known items functions or configurations are typically omitted for conciseness.

It will be understood that although the terms first second etc. are be used herein to describe various elements these elements should not be limited by these terms. These terms are used to distinguish one element from another but not to imply a required sequence of elements. For example a first element can be termed a second element and similarly a second element can be termed a first element without departing from the scope of the present invention. As used herein the term and or includes any and all combinations of one or more of the associated listed items.

It will be understood that when an element is referred to as being on or connected or coupled to another element it can be directly on or connected or coupled to the other element or intervening elements can be present. In contrast when an element is referred to as being directly on or directly connected or directly coupled to another element there are no intervening elements present. Other words used to describe the relationship between elements should be interpreted in a like fashion e.g. between versus directly between adjacent versus directly adjacent etc. .

The terminology used herein is for the purpose of describing particular embodiments only and is not intended to be limiting of the invention. As used herein the singular forms a an and the are intended to include the plural forms as well unless the context clearly indicates otherwise. It will be further understood that the terms comprises comprising includes and or including when used herein specify the presence of stated features steps operations elements and or components but do not preclude the presence or addition of one or more other features steps operations elements components and or groups thereof.

Spatially relative terms such as beneath below lower above upper and the like may be used to describe an element and or feature s relationship to another element s and or feature s as for example illustrated in the figures. It will be understood that the spatially relative terms are intended to encompass different orientations of the device in use and or operation in addition to the orientation depicted in the figures. For example if the device in the figures is turned over elements described as below and or beneath other elements or features would then be oriented above the other elements or features. The device may be otherwise oriented e.g. rotated 90 degrees or at other orientations and the spatially relative descriptors used herein interpreted accordingly.

In the preferred embodiment the system can include one or more robots and one or more robot managers e.g. servers. The number of servers will be much fewer than the number of robots in the preferred embodiment.

Further the service robots can include one or more functional devices mechanisms systems or subsystems. These will tend to depend on the types of services or functions that robot is configured to perform. In some embodiment these can include one or more of 

As will be appreciated by those skilled in the art the actual functional devices mechanisms systems and subsystems included in or with a robot will depend on the functional expectations for the robot.

The communication between the robot manager and one or more robots can be via any one or more known or hereafter developed wireless networks and can also include one or more wired networks. For example such networks can include a Bluetooth network satellite network cell phone network wireless modem or home network and the like. The manager can be for example local to one or more of the robots or remote. As an example robots can communicate with one or more robot managers over the Internet via a wireless modem attached to a manager or personal computer within a user s home or within a commercial facility.

Each manager and robot can include at least one processor and at least one data storage device configured to store information and computer instructions.

Robot A is a floor cleaning robot designed to navigate throughout home while vacuuming floors and avoiding obstacles. Robot B is child care robot designed to monitor the location and activities of children and to provide entertainment options. The manager is in communications with both robots A B and with the Internet in this embodiment.

Traditionally home cleaning robots navigate by following curved paths until encountering an obstacle and then changing direction. By randomly walking the environment they eventually clean the whole area. This is because of the power and size limitations which make it prohibitive to include complex mapping functionality on the robot.

Traditional home entertainment robots are little more than computers on wheels that can be programmed to perform simple motions while playing pre recorded behaviors. Again this is because of the limitations of including rich functionality in low cost mobile platform.

Minimizing energy consumption is a key design objective when developing mobile platforms. Removing the need for intense computational power from a mobile platform allows for longer battery life lower cost and lighter weight.

The robot manager is a stationary device plugged into the wall in this embodiment. This would allow manager to be manufactured using traditional computer hardware designs which allow for low cost and high performance. However the computer itself would have to be configured and or programmed to provide the unique functionality disclosed herein. Any functionality that does not control the most primitive functionality of the mobile robot could be assigned to the robot manager . Therefore the robots can be configured to be extremely sophisticated in their functionality without requiring the robot itself to have a wealth of sophisticated programming resident or on board. This allows for lower cost robots configurable through the manager .

Robot A the floor cleaning robot could navigate through the environment using its normal simplistic strategy the first time it operates in the environment. It would periodically update the manager with its position determined in a variety of ways e.g. dead reckoning or other localization techniques and the presence or absence of obstructions. The manager could consolidate this information into a map of the environment. The next time the cleaning robot A is operated it could now be commanded by the home manager to follow a more efficient planned route determined by the manager . This provides a more efficient cleaning function without making the robot more complex.

Furthermore the map developed on the manager could also be used to guide the operation of the child care robot B. The robots would both be able to update the manager of the whereabouts of obstacles and or children which would immediately allow the maps to be updated and allow more effective use of the cleaning robot A. If the children wanted to play an interactive game with the robot B robot B could have access to all of the information available on the Internet and to speech recognition and synthesis capabilities running on the manager again without increasing the power consumption of the robot B.

As is shown in in another embodiment a user worn transceiver or transponder could be used to create a map of the environment e.g. in the form of a bracelet or belt clip device as examples. The transceiver could also be used to provide instructions to the robot manager or to at least one robot via the robot manager. The transceiver is equipped with a wireless communication device configured to communicate with manager in this embodiment. As one or more users walks through the home the transceiver could provide location information to the robot manager which could then create and or update a map of the home. Optionally the transceiver could have a button on it depression of which could cause a signal to be sent to the manager indicating the presence of an obstruction e.g. table.

The transceiver could also optionally include a microphone to receive information from the user. For example the user could push the obstruction button when he reaches a table and say permanent to indicate to the manager that the obstruction is intended to persist in that location. As another example the user could push the obstruction button and say table to indicate to the manager that the obstruction is a table. The manager can process the input and indicate in its map that the obstruction is permanent or a table. As will be appreciated by those skilled in the art the transceiver of is not limited to the particular embodiment shown. In other embodiments the obstruction button could just be a communication enabling button that enables the user to communicate verbally with the robot manager. Various other forms of non verbal communication could also be supported.

In yet another embodiment a user can control and monitor its robots A B from remote locations via manager . In such an embodiment the user could access such robot information from a Web site that communicates with manager which in turn communicates with robots A B.

Here robot manager is shown including the following functional modules a wireless communication module used to connect to the robots as well as other wireless enabled devices and Internet gateways in the facility an Internet connection module which can be a wired or wireless connection a scheduling system used to schedule robot activity e.g. to coordinate the activity of multiple robots and or to coordinate the scheduling of the robots with the human occupants of the facility a human machine interface that provides a high functionality and high performance interface where the occupants can interact program schedule and otherwise interface to the service robots a mapping and navigation module a monitoring module that monitors the robots activity and or performance and an application framework whereby additional software can be downloaded from a remote manager to update the system or to provide enhanced or different functions. Manager also includes at least one storage device configured to store maps as well as other program code and data useful or needed to support other functions of the manager and or robots A B.

In this embodiment a remote user could wake up cleaning robot A and have it vacuum the house e.g. before the user got home. The user could also watch the robot navigate through the house via the rendering of a computer screen that includes a representation similar to that shown in . The present invention is not limited in this sense this example is provided merely for illustration.

Since the robot manger is in communication with robots A B computationally intensive functions can be done primarily by server rather than at the robots A B. The manger can then communicate the results of the computationally intensive functions or instructions based thereon to the appropriate robot A B. This allows for highly capable yet relatively simple and low cost robots.

While the foregoing has described what are considered to be the best mode and or other preferred embodiments it is understood that various modifications can be made therein and that the invention or inventions may be implemented in various forms and embodiments and that they may be applied in numerous applications only some of which have been described herein.

