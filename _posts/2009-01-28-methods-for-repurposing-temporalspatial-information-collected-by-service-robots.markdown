---

title: Methods for repurposing temporal-spatial information collected by service robots
abstract: Robots and methods implemented therein implement an active repurposing of temporal-spatial information. A robot can be configured to analyze the information to improve the effectiveness and efficiency of the primary service function that generated the information originally. A robot can be configured to use the information to create a three dimensional (3D) model of the facility, which can be used for a number of functions such as creating virtual tours of the environment, or porting the environment into video games. A robot can be configured to use the information to recognize and classify objects in the facility so that the ensuing catalog can be used to locate selected objects later, or to provide a global catalog of all items, such as is needed for insurance documentation of facility effects.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08433442&OS=08433442&RS=08433442
owner: Seegrid Corporation
number: 08433442
owner_city: Pittsburgh
owner_country: US
publication_date: 20090128
---
This application claims the benefit of priority under 35 U.S.C. 119 e from provisional application Ser. No. 61 024 028 entitled METHODS FOR REPURPOSING TEMPORAL SPATIAL INFORMATION COLLECTED BY SERVICE ROBOTS filed on Jan. 28 2008 which is incorporated herein by reference in its entirety.

The present inventive concepts relate to methods for repurposing temporal spatial information collected by service robots.

Service robots have traditionally been tasked with doing the dull and dirty jobs in human facilities such as homes commercial and industrial buildings. However that very action of performing the service creates a large fund of temporal spatial information and knowledge about the facility in which the work is performed.

Previous service robots have ignored this large fund of information and knowledge as an asset resulting in its waste.

According to one aspect of the invention provided is a method of servicing a facility with at least one service robot that obtains temporal spatial information. The method includes navigating a robot through an environment using automatic self control by the robot sensing the temporal spatial information while performing a primary service function and storing the temporal spatial information.

The method can further include communicating the temporal spatial information via a wireless network to a control system.

The method can further include at least one other service robot accessing the temporal spatial information from the control system via the wireless network.

The method can further include at least one other autonomous control system accessing the temporal spatial information from the control system.

The method can further include the service robot directly communicating the temporal spatial information via a wireless network to at least one other service robot.

The method can further include the service robot performing a secondary service using the temporal spatial information.

The method can further include the service robot analyzing the temporal spatial information to improve the effectiveness and efficiency of the primary service that originally generated the temporal spatial information.

The method can further include creating a three dimensional 3D model of the environment using the temporal spatial information.

The method can further include recognizing and classifying objects in the environment using the temporal spatial information.

The method can further include generating a catalog of objects and using the catalog to subsequently locate selected objects in the environment.

In accordance with another aspect of the invention provided is a service robot system. The service robot includes a platform supporting a servicing subsystem a navigation controller coupled to a drive mechanism and configured to navigate the platform through an environment one or more sensors configured to sense collect temporal spatial information while performing a primary service and a storage media on which the temporal spatial information is stored.

The system can further include a communication module configured to communicate the temporal spatial information via a wireless network to a control system.

At least one other service robot can be configured to access the temporal spatial information from the control system via the wireless network.

The system can further include a communication module configured to directly communicate the temporal spatial information via a wireless network to at least one other service robot.

The service robot can be configured to perform a secondary service using the temporal spatial information.

The service robot can be further configured to analyze the temporal spatial information to improve the effectiveness and efficiency of the primary service that originally generated the temporal spatial information.

The service robot can be further configured to create a three dimensional 3D model of the environment using the temporal spatial information.

The service robot can be further configured to recognize and classify objects in the environment using the temporal spatial information.

The service robot can be further configured to generate a catalog of objects and to use the catalog to subsequently locate selected objects in the environment.

The system can further include at least one other autonomous control system configured to access the temporal spatial information from the control system.

Hereinafter aspects of the present invention will be described by explaining illustrative embodiments in accordance therewith with reference to the attached drawings. While describing these embodiments detailed descriptions of well known items functions or configurations are typically omitted for conciseness.

It will be understood that although the terms first second etc. are be used herein to describe various elements these elements should not be limited by these terms. These terms are used to distinguish one element from another but not to imply a required sequence of elements. For example a first element can be termed a second element and similarly a second element can be termed a first element without departing from the scope of the present invention. As used herein the term and or includes any and all combinations of one or more of the associated listed items.

It will be understood that when an element is referred to as being on or connected or coupled to another element it can be directly on or connected or coupled to the other element or intervening elements can be present. In contrast when an element is referred to as being directly on or directly connected or directly coupled to another element there are no intervening elements present. Other words used to describe the relationship between elements should be interpreted in a like fashion e.g. between versus directly between adjacent versus directly adjacent etc. .

The terminology used herein is for the purpose of describing particular embodiments only and is not intended to be limiting of the invention. As used herein the singular forms a an and the are intended to include the plural forms as well unless the context clearly indicates otherwise. It will be further understood that the terms comprises comprising includes and or including when used herein specify the presence of stated features steps operations elements and or components but do not preclude the presence or addition of one or more other features steps operations elements components and or groups thereof.

Spatially relative terms such as beneath below lower above upper and the like may be used to describe an element and or feature s relationship to another element s and or feature s as for example illustrated in the figures. It will be understood that the spatially relative terms are intended to encompass different orientations of the device in use and or operation in addition to the orientation depicted in the figures. For example if the device in the figures is turned over elements described as below and or beneath other elements or features would then be oriented above the other elements or features. The device may be otherwise oriented e.g. rotated 90 degrees or at other orientations and the spatially relative descriptors used herein interpreted accordingly.

In step the robot performs the service functions such as vacuuming. In step the robot collects temporal spatial information while performing the service e.g. as in step . In step the temporal spatial information is made available for other uses by other applications and or robots and or by the robot collecting the information. For example in some implementations robots can work in teams and communicate such information back and forth via wireless networks. One robot could scout locations requiring service and note whether they are occupied and communicate the need and availability to another one or more robots as an example.

The robots can include sensors to collect such temporal spatial information such as those generally known in the art. For example sensors could include acoustic motion detection camera or other sensors.

As will be appreciated by those skilled in the art a service robot e.g. vacuum includes a memory for storing instructions and data and a processor for executing the instructions. Thus the methods discussed above can be programmed into the service robot for execution to accomplish the functions disclosed herein.

Also while the service robot was indicated as a robotic cleaner in this embodiment those skilled in the art will appreciate that methods in accordance with the present invention could be applied to any number of service robots and could implement any number and types of sensors.

In another embodiment the service robot would communicate the temporal spatial data collected to a server or other computer which would include the processor for manipulating the data and a storage system for storing the data. This server could be used to communicate the re purposed information back to the original robot or to other robots or servers which can make use of it.

As an example the following description will describe a potential application for this method and illustrate its operation. A service robot is used to clean the floors in an industrial facility. It is programmed to follow a path which carries it throughout the facility. A temperature sensor is mounted to the robot and as it is doing its primary function it is also recording the temperature of the environment at intervals along the programmed path. The temperature location data is transmitted to the facility heating system which maps the position data from the robot to its control zones. It thus can use the recorded temperatures to adjust the heating output of the different zones.

While reference has been made to using wireless networks in various embodiments any of a variety of data communication schemes can be used such as wired batch wireless networked Point to point and so on.

While the foregoing has described what are considered to be the best mode and or other preferred embodiments it is understood that various modifications can be made therein and that the invention or inventions may be implemented in various forms and embodiments and that they may be applied in numerous applications only some of which have been described herein.

