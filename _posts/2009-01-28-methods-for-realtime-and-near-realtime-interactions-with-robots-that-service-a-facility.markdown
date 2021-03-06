---

title: Methods for real-time and near real-time interactions with robots that service a facility
abstract: In accordance with aspects of the present invention, a service robot and methods for controlling such a robot are provided. In particular, the robot is configured to sense the presence of a person and to take a next action in response to sensing the presence of the person. As examples, the robot could leave the area, await commands from the person, or enter an idle or sleep state or mode until the person leaves.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08892256&OS=08892256&RS=08892256
owner: Seegrid Corporation
number: 08892256
owner_city: Pittsburgh
owner_country: US
publication_date: 20090128
---
This application claims the benefit of priority under 35 U.S.C. 119 e from provisional application Ser. No. 61 024 019 filed on Jan. 28 2008 which is incorporated herein by reference in its entirety.

The present inventive concepts relate to methods for optimal interactions between people and service robots including robotic cleaners while they are servicing a facility.

One of the advantages of service robots is that they can do the dull and dirty jobs in human facilities such as homes commercial and industrial buildings and institutions. However that very action of robotic service itself may be unpleasant inconvenient disruptive or even dangerous to a human that comes into proximity of the working robot.

Previous service robots have ignored this problem. As an example current robot cleaners blithely treat humans the same way they treat the leg of a stool usually by bumping into it going around it and continuing their work.

Although some robots built for human interaction have included the ability to recognize humans in their proximity to date this has been used to further the interaction itself but not to further a distinct service agenda.

The present invention has been conceived to solve the above mentioned problems occurring in the prior art. In accordance with aspects of the present invention provided is a system and method that allows a robot to service a facility while more effectively interacting with people.

In order to achieve the above aspects there is provided various methods of enabling the robot to optimally respond in the presence of a person.

The robot can be configured to have a work pause whereby when the robot senses the proximity of a person it stops working and remains still and silent.

The robot can be configured to move out of the way whereby when the robot senses the proximity of a person it stops working and actively moves into a position of the room that is least disturbing the person. This may be away from the person or nearer the person depending on other factors.

The robot can be configured to move out of the room whereby when the robot sense the proximity of a person it moves to another area of the facility where it is no longer in proximity to people.

The robot can be configured to look to a person to point things out when the person enters the room. This can provide a seamless way to improve the decision making process of the robot.

The robot can be configured to keep track of a work stoppage so that it can restart work in the area once the person has left.

Hereinafter aspects of the present invention will be described by explaining illustrative embodiments in accordance therewith with reference to the attached drawings. While describing these embodiments detailed descriptions of well known items functions or configurations are typically omitted for conciseness.

It will be understood that although the terms first second etc. are be used herein to describe various elements these elements should not be limited by these terms. These terms are used to distinguish one element from another but not to imply a required sequence of elements. For example a first element can be termed a second element and similarly a second element can be termed a first element without departing from the scope of the present invention. As used herein the term and or includes any and all combinations of one or more of the associated listed items.

It will be understood that when an element is referred to as being on or connected or coupled to another element it can be directly on or connected or coupled to the other element or intervening elements can be present. In contrast when an element is referred to as being directly on or directly connected or directly coupled to another element there are no intervening elements present. Other words used to describe the relationship between elements should be interpreted in a like fashion e.g. between versus directly between adjacent versus directly adjacent etc. .

The terminology used herein is for the purpose of describing particular embodiments only and is not intended to be limiting of the invention. As used herein the singular forms a an and the are intended to include the plural forms as well unless the context clearly indicates otherwise. It will be further understood that the terms comprises comprising includes and or including when used herein specify the presence of stated features steps operations elements and or components but do not preclude the presence or addition of one or more other features steps operations elements components and or groups thereof.

Spatially relative terms such as beneath below lower above upper and the like may be used to describe an element and or feature s relationship to another element s and or feature s as for example illustrated in the figures. It will be understood that the spatially relative terms are intended to encompass different orientations of the device in use and or operation in addition to the orientation depicted in the figures. For example if the device in the figures is turned over elements described as below and or beneath other elements or features would then be oriented above the other elements or features. The device may be otherwise oriented e.g. rotated 90 degrees or at other orientations and the spatially relative descriptors used herein interpreted accordingly.

In accordance with aspects of the present invention a robotic cleaner or other type of service platform can be configured to implement a method of more effectively interacting with people while servicing a space. The platform and method can determine that the platform is in the presence of people and implement a different servicing pattern or behavior as a function thereof. The determination that the robotic platform is in the presence of people can be accomplished using any one or more of a plurality of types of sensors mounted on integral with or coupled to the robotic platform or mounted elsewhere in the environment and in communication directly or indirectly with the robotic platform.

In step the robot is in the process of servicing e.g. cleaning a room or area . In step the robot senses whether or not a person has entered the room. A variety of different types of sensors could be used such as for example motion detection sensors video camera sensors acoustic sensors and so on.

If in step a person was not sensed the process continues in step where the robot continues to clean in this example. Thus the sensing can serve as an interrupt condition to the servicing condition of the robot. If in step the answer was yes then the process continues to step where the robot stops and sits still. The robot can then can then transition to a quiet sleep or inactive mode where it makes little or no noise and uses minimum power e.g. at least enough to power the sensors.

In step the robot senses whether the person left the room or area. If not the process remains or returns to step where the robot remains idle. If the person did leave the room or area then the process continues to step where the robot resumes cleaning i.e. wakes up.

In step the robot is cleaning in an area. In step a determination is made of whether a person has entered the area. This is preferably an on going sensing activity rather than a discrete standalone step. If a person was not sensed the process continues in step where it is cleaning. However if in step it was determined that a person entered the room or area the process continues to step . In this step the robot leaves the area it was cleaning. In step the robot enters a new area and can begin cleaning that area if needed. Preferably the new area is one without people.

In step the robot is cleaning in an area. In step a determination is made of whether a person has entered the area. This is preferably an on going sensing activity rather than a discrete standalone step. If a person was not sensed the process continues in step where it is cleaning. However if in step it was determined that a person entered the room or area the process continues to step . In this step the robot stops cleaning and moves to another location within the area it was cleaning e.g. a least disturbing area. A set of rules can be defined for choosing the least disturbing area such as either within or outside a certain distance from the user proximate to the entrance of the area through which the user entered and so on. In step the robot senses when the person leaves and then returns to step and its cleaning operation.

In step the robot is cleaning in an area. In step a determination is made of whether a person has entered the area. This is preferably an on going sensing activity rather than a discrete standalone step. If a person was not sensed the process continues in step where the robot is cleaning. However if in step it was determined that a person entered the room or area the process continues to step where the robot stops cleaning. In step the robot awaits commands from the person for its next action e.g. continue cleaning leave area enter sleep mode etc. In step the robot executes the commands.

In step the robot is cleaning in an area. In step a determination is made of whether a person has entered the area. This is preferably an on going sensing activity rather than a discrete standalone step. If a person was not sensed the process continues in step where the robot is cleaning. However if in step it was determined that a person entered the room or area the process continues to step where the robot records its current location. The robot could record its location in an on going basis so that it maintains a record of all areas cleaned whether fully or partially. In step the robot moves to another area to service e.g. clean that area. In step the robot returns to the original area to finish cleaning.

In the various service robot methods therefore the robot can be configured to keep track of the work stoppage so that it can restart work in that area once the person has left.

As will be appreciated by those skilled in the art a service robot e.g. vacuum includes a memory for storing instructions and data and a processor for executing the instructions. Thus the methods discussed above can be programmed into the service robotic for execution to accomplish the functions disclosed herein.

In another implementation of the method the sensing of the person in the area of the robot may be performed by sensors installed in the environment and communicating directly or indirectly with the service robot. In this embodiment the sensors may be serving other functions such as temperature control or security sensing of the environment and communicating with other control components of the environment. The implementation requires the spatial relationships between the robot and the sensors is known. There are many possible implementations of this including perception of the sensors by the robot a priori knowledge of the sensors locations in a map or information provided by an environment wide control system.

Portions of the above description refer to the robot being configured to execute different behaviors in response to the presence of people. This configuration can be implemented as a pre programmed behavior or as a set up menu providing a series of optional behaviors to be executed under certain triggering conditions as is commonly available on consumer and industrial products.

Also while the service robot was indicated as a robotic cleaner in this embodiment those skilled in the art will appreciate that methods in accordance with the present invention could be applied to any number of service robots and could implement any number and types of sensors.

While the foregoing has described what are considered to be the best mode and or other preferred embodiments it is understood that various modifications can be made therein and that the invention or inventions may be implemented in various forms and embodiments and that they may be applied in numerous applications only some of which have been described herein.

