---

title: Electrically actuated weapon system
abstract: An electrically actuated weapon system is provided, which may be mounted in a robotic vehicle or device, and controlled remotely by a user. In particular, the electrically actuated weapon system is composed of an electrically actuated weapon, a weapon control means connected thereto, and a controller means remotely located therefrom. The controller means is in wireless communication with the weapon control means, which is operable to control three linear actuators which cycle the weapon. These linear actuator means are controlled electronically, based on communications received from the controller means. Accordingly, if the weapon is stolen, lost, or captured by an enemy combatant during combat, the weapon will cease to be functional. Further, the weapon can be reliably operated from remote locations, as the cycling of the weapon is not dependent upon recoil forces.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08033207&OS=08033207&RS=08033207
owner: The United States of America as represented by the Secretary of the Army
number: 08033207
owner_city: Washington
owner_country: US
publication_date: 20090515
---
This application claims the benefit of U.S. Provisional Application Ser. No. 61 059 471 filed on Jun. 6 2008 entitled Electrically Actuated Weapon System which is incorporated herein by reference.

The invention described herein may be manufactured used and or licensed by or for the U.S. Government for governmental purposes without the payment of royalties by the U.S. Government to the inventors or any future assignees.

The present invention relates generally to an electronically controlled weapon system. In particular the present invention provides a weapon in which the cycling operation of the weapon is performed by electrical actuators which are remotely controlled by an electronic control system thereby enabling a user to restrict the use of the weapon to only authorized users.

Automatic guns can be generally classified according to their mode of operation as either self powered or externally powered. Self powered automatic guns utilize recoil or high pressure barrel gasses caused by firing to cycle operating mechanisms which load and fire the gun. In particular a mechanically actuated firing pin strikes a primer cap at the rear of the weapon cartridge to thereby ignite the propellant for the projectile. The bolt is driven rearward by the propellant gases shortly after the firearm is fired. This action i.e. cycling of the weapon pulls the spent cartridge from the chamber and ejects the empty shell. Once the bolt reaches the end of travel the bolt suddenly stops. A spring then provides forward bias to drive the bolt forward and pushes a new cartridge in the chamber.

Self powered automatic guns are inherently more portable or mobile than externally powered guns in which operating mechanisms of externally powered guns are driven by actuators or motors independently of firing forces are therefore usually preferred for small arms machine guns and light cannons. However for larger cannons external powered actuators are sometimes needed to operate the weapon systems including loading cycling and gun aiming movement. Since such larger guns are difficult to implement as self powered guns because of shell size weight and size of moving operational gun parts larger guns have typically been constructed to be contrast.

However automation of guns in general and large guns in particular such as those used in tanks and armored vehicles in particular has heretofore usually been limited to the automation of a single operational function. For example an actuator has been used for opening and closing the breech or loading shells into an open breech. A human operator has ordinarily functioned to operationally bridge the separately automated functions. Firing rates of such guns in which an operator performs the key role as system integrator have thus been limited by the operator s skill and ability in perceiving the operational status of the automated gun hardware and in deciding when the operating commands should be given to initiate each successive automated operation.

Many problems encountered in mechanizing automating large guns are attributable to the fact that the guns were not originally designed for automatic operation. Thus design of such guns has principally involved adaptations of pre existing manually operated guns. As a consequence their automation has usually consisted of little more than the retrofitting of existing gun hardware. Although some limited success has been achieved through such retrofitting the resulting gun systems have at best been awkward and non optimal in terms of gun operating speeds and firing rates and also in terms of system cost and reliability.

Moreover control systems for previously automated large caliber guns have controlled only a few sequential steps and have been implemented by simple and or logic elements flip flop circuits typically being used to control actuating motors or solenoids. Further the progression from one separately automated step to another has heretofore been sequenced by pre set timers so that gun operation proceeds in accordance with a fixed time schedule. Reliance upon such timing schedules however can cause serious problems because operating times may in fact vary widely in the same gun according to conditions. For example the time required to advance shells to the gun typically varies according to the number and hence the mass of shells which must be advanced.

Operating times also depend upon such factors as how clean or how well lubricated the gun is the extent of gun wear and the operating temperatures. If the gun design does not take such time affecting variables into consideration one operating step may be initiated before a preceding step is completed with potentially disastrous consequences. A particular event which is difficult to provide for in a fixed timing schedule is shell firing time. Typically shells fire within a few milliseconds after firing impact or as the case may be electrical contacting. Propellant combustion ordinarily occurs within the next few milliseconds and casing pressure is typically reduced to a safe casing extraction level in several more milliseconds. Thus only about 10 to 20 milliseconds of firing dwell time is ordinarily required.

However in system use a few shells presumably due to manufacturing defects do not fire as expected. Instead there is a brief delay after impact or electrical contact before ignition occurs. This phenomenon is commonly referred to as a hang fire condition. If a hang fire causes a shell to fire after a timed casing extraction has begun the gun may be destroyed and operating personnel may be injured. On the other hand if worst case hang fires are considered in establishing the gun operating time schedule gun performance will be compromised. If the timing schedule also takes into account all other possible worst case conditions affecting gun operating times the firing rate will be drastically reduced over that possible under most operating conditions. As a result the automatic operation of a gun on a fixed timing schedule is generally unsatisfactory.

Further currently robotic devices have begun to be commonly used in police and military applications. Systems for mounting firearms on such robotic devices have been recently developed. These systems for mounting firearms on robotic devices are designed however to utilize conventional gas powered self powered weapons. In particular the weapon such as a conventional shotgun or an M 4 is removably mounted in the system wherein the system allows a user to wirelessly control mechanical mechanisms to release the weapon safety switch and pull the trigger.

However such conventional systems for mounting firearms on robotic devices have several drawbacks. First an enemy can disable the robotic device remove the firearm from the mounting system and utilize the firearm against the controller of the robotic device and or friendly forces. Second as discussed above self powered weapons tend to periodically jam and require human interaction to clear the jam when same occurs placing the operator in a potentially fatal situation. Third by requiring placement of a conventional weapon in the mounting system a soldier usually must place his weapon into the mounting system of the robotic device during operation thereof which personally places the operator in a vulnerable position during operation of the robotic device.

It is therefore an object of the present invention to provide an externally powered electrically actuated weapon in which all firing operations of the weapon can be remotely externally operated.

It is another object of the present invention is to provide an externally powered electrically actuated weapon which if removed from the device upon which the weapon is mounted such as a robotic device is inoperable.

A further object of the present invention is to provide an externally powered electrically actuated weapon which operates on a strict logic basis rather than on a fixed timing schedule which stops operating if pre established logic conditions are not met and which provides status and malfunction information to the gun operator.

Another object of the present invention is to provide an externally powered electrically actuated weapon in which initiation of each operational step is conditioned on specific moving parts of the gun being in specific positions.

In order to achieve the objects of the present invention as described above the present inventor earnestly endeavored to develop an electrically actuated weapon in which all firing operations are performed by means external to the firing operation. In particular in a first embodiment of the present invention an electrically actuated weapon system is provided comprising 

 C a wireless receiver means capable of wireless communication with the wireless communication means 

 D a weapon control means in communication with the wireless receiver means said weapon control means operable to control firing operation of the weapon via linear actuator means and

 E an electrically actuated weapon in communication with the weapon control means the electrically actuated weapon comprised of a 

In a second embodiment of the present invention the electrically actuated weapon system of the first embodiment of the present invention is provided wherein the electrically actuated weapon comprises 

 a a weapon housing having a rear end a front end having a threaded cylindrical portion formed therein said front end disposed opposite the rear end and a middle portion disposed between the front end and the rear end said weapon housing comprising 

 b a cartridge magazine locking assembly movably disposed in the cartridge magazine locking assembly bore said cartridge magazine locking assembly comprising 

 c a cartridge extractor piston assembly disposed within the extractor piston track bore said cartridge extractor piston assembly comprised of 

 d an ejector rod disposed within the ejector rod bore perpendicular and off axis to the cartridge feeder piston track bore 

 e a cartridge feeder piston assembly disposed within the feeder piston track bore said cartridge feeder piston assembly comprised of 

 f a firing pin cam assembly disposed in the firing pin cam bore said firing pin cam assembly comprised of 

In a third of the present invention the electrically actuated weapon system of the first embodiment above is provided wherein the controller means is a computer processing means or a simple logic control device operable to communicate with the weapon control means.

In a fourth embodiment of the present invention the electrically actuated weapon system of the first embodiment is provided wherein the weapon control means is a computer processing means or a simple logic control device and is capable of controlling operation of the linear actuator means.

In a fifth embodiment of the present invention the electrically actuated weapon of the second embodiment above is provided further comprising a weapon barrel having a first end a second end a chamber disposed adjacent the first end and a bore disposed between the chamber and the second end.

In a sixth embodiment of the present invention the electrically actuated weapon of the first and second embodiments above is provided wherein the extractor linear actuator means feeder linear actuator means and the cam actuator means is an electric hydraulic or pneumatic linear actuator means.

In a seventh embodiment of the present invention the electrically actuated weapon system of the first embodiment above is provided further comprising a power supply in communication with the weapon control means.

In an eighth embodiment of the present invention the electrically actuated weapon system of the second embodiment above is provided wherein the electrically actuated weapon further comprises an ammunition supply means said ammunition supply means in communication with the cartridge magazine through slot.

In a ninth embodiment of the present invention the electrically actuated weapon system of the eighth embodiment above is provided wherein the ammunition supply means is selected from a weapon cartridge a hopper means and a belt feeding means.

In a tenth embodiment of the present invention the electrically actuated weapon system of the second embodiment above is provided wherein the ejector rod of the electrically actuated weapon is disposed within the ejector rod bore perpendicular to and off axis at about a 45 angle in relation to the cartridge feeder piston track bore.

In an eleventh embodiment of the present invention the electrically actuated weapon system of the second embodiment above is provided wherein the cartridge ejection slot of the electrically actuated weapon is disposed perpendicular to and off axis by about 45 in relation to the cartridge feeder piston track bore and in the same plane as the ejector rod bore.

In a twelfth embodiment of the present invention an electrically actuated weapon is provided comprising 

 A a weapon housing having a rear end a front end having a threaded cylindrical portion formed therein said front end disposed opposite the rear end and a middle portion disposed between the front end and the rear end said weapon housing comprising 

 B a cartridge magazine locking assembly movably disposed in the cartridge magazine locking assembly bore said cartridge magazine locking assembly comprising 

 C a cartridge extractor piston assembly disposed within the extractor piston track bore said cartridge extractor piston assembly comprised of 

 D an ejector rod disposed within the ejector rod bore perpendicular and off axis to the cartridge feeder piston track bore 

 E a cartridge feeder piston assembly disposed within the feeder piston track bore said cartridge feeder piston assembly comprised of 

 e a firing pin cam assembly disposed in the firing pin cam bore said firing pin cam assembly comprised of 

As illustrated in the present invention provides an electrically actuated weapon system comprised of a power supply not shown a controller means comprised of a computer processing means not shown which may alternatively be a simple logic control means and a wireless communication means in connection with the computer processing means. A user is able to remotely control the firing operations of the electrically actuated weapon via a user interface not shown any conventional user interface may be utilized in connection with the controller means via the wireless communication means.

Importantly the electrically actuated weapon of the present invention which may be mounted remotely from the user such as on a robotic device or vehicle may not be operated other than via the controller means. In particular the firing operations of the weapon such as the loading firing of a weapon cartridge ejection thereof and reloading of a weapon cartridge into the weapon are all controlled by linear actuator means rather than through a gas operated recoil based system as conventionally used . These linear actuator means are controlled electronically based on communications received from the remote controller means. Accordingly if the weapon is stolen lost or captured by an enemy combatant during combat the weapon will cease to be functional.

The controller means may be a computer processing means such as a personal computer PC Personal Digital Assistants PDA hand held computer palm top computers lap top computer smart phone or any other information processing devices. A PC can be one or more IBM or compatible PC workstations running a Microsoft Windows or LINUX operating system one or more Macintosh computers running a Mac OS operating system or an equivalent. In another embodiment the computer processing means may run through a server system such as a SUN Ultra workstation running a SunOS operating system or IBM RS 6000 workstation and server running the AIX operating system. However a simple logic control device may be utilized in place of such information processing devices to facilitate simple user control of the electrically actuated weapon .

The controller means is in communication with a wireless communication means so as to enable the user to remotely control the operation of the electrically actuated weapon . The wireless communication means may be any conventional wireless communication device such as a wireless LAN device radio transmitter etc. The wireless communication means and controller means are in communication with one or more power supplies.

The wireless communication means is operable to communicate with a wireless receiver means. The wireless receiver means like the communication means may be any conventional wireless communication device such as a wireless LAN device radio transmitter etc. The wireless receiver means is in communication with a weapon control means. Like the controller means the weapon control means may be a computer processing means or a simple logic control device.

As illustrated in the weapon control means is in communication with a second power supply. A second power supply is required as the weapon is operated remotely from the controller means. The weapon control means is operable to receive communications commands from the controller means concerning operation of the linear actuator means and . In particular during operation a user wirelessly communicates commands to the weapon from the controller means to the weapon control means.

The controller means generally comprises a first switch for powering the extractor linear actuator means a second switch for powering the feeder linear actuator means and a third switch for powering the cam actuator means . Specifically commands to activate one or more of the linear actuator means and i.e. move the piston of the linear actuator means forward and backward are sent by the user to the weapon control means not shown . By activating the linear actuator means and the weapon control means cycles the weapon thereby loading firing extracting and reloading a weapon cartridge as desired by the user.

The extractor linear actuator means the feeder linear actuator means and the cam actuator means are in conductive communication with the second power supply either directly or via the weapon control means . Each of the linear actuator means and may be an electric hydraulic or pneumatic linear actuator. Preferably electric linear actuators are used due to their quick responsiveness.

As illustrated in the electrically actuated weapon of the present invention has a weapon housing having a rear end a middle portion and a front end . As illustrated in the front end has a threaded cylindrical portion formed therein. As called for in the second embodiment of the present invention and as illustrated in a weapon barrel having a first end and a second end may be screwed onto the weapon housing via the threaded cylindrical portion thereof. Further as shown in a chamber is disposed in the weapon barrel adjacent the first end thereof and a bore is disposed between the chamber and the second end of the barrel .

The weapon housing defines an extractor piston track having an extractor piston track bore and an extractor actuator through slot extending from the piston track bore to the exterior of the weapon housing .

The weapon housing further defines a cartridge feeder piston track defined by the weapon housing the track being disposed parallel to the extractor piston track bore . The cartridge feeder piston track is comprised of a feeder piston track bore having a rear end a front end and a feeder actuator through slot extending from the feeder piston bore to the exterior of the weapon housing .

A cartridge magazine through slot as shown in is defined by the weapon housing and is disposed perpendicular to the extractor piston track and in communication with the extractor piston track bore . As illustrated in an ammunition supply means is removably disposed within the cartridge magazine through slot . The ammunition supply means may be any conventional weapon cartridge as shown in . Alternatively the ammunition supply means may be a hopper device which feeds weapon cartridges into the weapon via a hopper mechanism or a conventional belt feeding means which feeds weapon cartridges to the weapon via a belt.

A transition cavity illustrated in is defined by the weapon housing and serves to connect the extractor piston track bore to the cartridge feeder piston track bore . The transition cavity is disposed perpendicular to and in communication with both the extractor piston track bore and the cartridge feeder piston track bore .

A cartridge magazine locking assembly bore illustrated in adjacent the rear end shown in of the weapon housing is disposed parallel to the extractor piston track bore and extends from the rear end of the weapon housing to the cartridge magazine through slot .

A firing pin cam bore defined by the weapon housing is disposed perpendicular to the cartridge feeder piston track bore and extends from the exterior of the weapon housing to the cartridge feeder piston track bore . A cartridge restrictor pivot bore defined by the weapon housing is disposed between and perpendicular to both the extractor piston track bore and the cartridge feeder piston track bore and extends through the weapon housing .

As illustrated in an ejector rod bore is defined by the weapon housing and is disposed perpendicular to and off axis to the cartridge feeder piston track bore .

As illustrated in a cartridge magazine locking assembly handle slot is defined by the weapon housing . The cartridge magazine locking assembly handle slot is disposed perpendicular to the cartridge magazine locking assembly bore and extends from the exterior of the weapon housing to the cartridge magazine locking assembly bore .

As illustrated in a cartridge ejection slot is defined by the weapon housing . The cartridge ejection slot is disposed perpendicular to and off axis of the cartridge feeder piston track bore shown in and in the same plane as the ejector rod bore shown in . Preferably as shown in the cartridge ejection slot is disposed perpendicular to and off axis by about 45 in relation to the cartridge feeder piston track bore and in the same plane as the ejector rod bore shown in .

A cartridge magazine locking assembly as illustrated in is movably disposed in the cartridge magazine locking assembly bore shown in . As illustrated in the cartridge magazine locking assembly is comprised of a cartridge magazine locking assembly piston having a rear end and a front end . The cartridge magazine locking assembly piston is slidably disposed within the cartridge magazine locking assembly bore .

A handle is provided in communication with the cartridge magazine locking assembly piston . In particular the handle shown in is disposed perpendicular to and slidably disposed within the cartridge magazine locking assembly handle slot shown in . As illustrated in a spring having a first end and a second end is disposed within the cartridge magazine locking assembly bore the second end of the spring being disposed adjacent to the rear end of the cartridge magazine locking assembly piston . A plug is removably disposed at the rear end of the cartridge magazine locking assembly bore and adjacent to the first end of the spring .

A cartridge extractor piston assembly as illustrated in is disposed within the extractor piston track bore shown in . The cartridge extractor piston assembly is comprised of a cartridge extractor piston slidably disposed within the extractor piston track bore . As illustrated in an extractor actuator rod having a first end and second end is disposed perpendicular to the cartridge extractor piston shown in slidably disposed within the extractor actuator through slot shown in and is in communication with the cartridge extractor piston at the first end of the extractor actuator rod .

As illustrated in an extractor linear actuator means is disposed adjacent to the weapon housing and is in communication with the second end of the extractor actuator rod such that the extractor linear actuator means operates to slide the cartridge extractor piston within the extractor piston track bore shown in via the extractor actuator rod . As illustrated in an ejector rod is disposed within the ejector rod bore perpendicular to and off axis of the cartridge feeder piston track bore shown in . Preferably as illustrated in the ejector rod is disposed within the ejector rod bore perpendicular to and off axis at about a 45 angle in relation to the cartridge feeder piston track bore shown in .

As illustrated in a cartridge feeder piston assembly is disposed within the feeder piston track bore shown in . As shown in the cartridge feeder piston assembly is comprised of a cartridge feeder piston having a first end a second end and a circumferential portion disposed there between. The cartridge feeder piston is slidably disposed within the feeder piston track bore .

As illustrated in a firing pin bore is disposed through the side of the cartridge feeder piston shown in from the first end of the piston to the second end of the piston. The firing pin bore has a diameter adjacent the first end of the cartridge feeder piston smaller than a diameter adjacent the second end of the cartridge feeder piston .

As illustrated in a firing pin slot defined by the cartridge feeder piston is disposed perpendicular to firing pin bore illustrated in and extending from the exterior of the cartridge feeder piston to the firing pin bore . The firing pin slot has a width smaller than the diameter of the firing pin bore . As illustrated in a plug is removably disposed at the rear end of the firing pin bore and adjacent to the first end of the firing pin spring .

As further illustrated in a firing pin is slidably disposed within the firing pin bore and the firing pin slot . A firing pin spring having a first end and a second end is also disposed within the firing pin bore the second end of the spring being disposed adjacent to the rear end of the firing pin .

The cartridge feeder piston further has a plurality of extractor finger grooves and an extractor rod groove disposed therein. The extractor finger grooves are formed in and are defined by the cartridge feeder piston. An extractor finger is disposed within each of the extractor finger grooves . Each extractor finger is composed of a flexible memory retaining material such as spring steel which is capable of temporarily deforming so as to grasp the rear lip of the ammunition cartridge.

As shown in an ejector rod groove is disposed within the cartridge feeder piston and extends the entire length thereof. As shown in the ejector rod is movably disposed within the ejector rod groove and the ejector rod bore .

As illustrated in a feeder actuator rod having a first end and second end is disposed perpendicular to the cartridge feeder piston shown in . The feeder actuator rod is slidably disposed within the feeder actuator through slot shown in and is in communication with the cartridge feeder piston at the first end of the feeder actuator rod .

A feeder linear actuator means as shown in is disposed adjacent to the weapon housing and in communication with the second end of the feeder actuator rod . The feeder linear actuator means which may be any electrical or hydraulic linear actuator slides the cartridge feeder piston within the feeder piston track bore shown in via the feeder actuator rod .

As illustrated in a firing pin cam assembly is disposed in the firing pin cam bore shown in . The firing pin cam assembly is comprised of a trigger cam as shown in having a trigger cam hole disposed therethrough as shown in which is movably disposed within the firing pin cam bore . A cam pin as shown in is disposed within the trigger cam hole such that the cam pin is in movable communication with the trigger cam . A firing pin cam cover as shown in is disposed on the weapon housing adjacent the firing pin cam bore .

As illustrated in a cam actuator rod having a first end and second end is disposed perpendicular to and in communication with the cam pin . The cam actuator rod is also rotatably disposed adjacent the firing pin cam bore . A cam actuator means as shown in is disposed adjacent to the weapon housing and in communication with the second end of the cam actuator rod . Like the extractor linear actuator means and the feeder linear actuator means the cam actuator means may be any electrical or hydraulic linear actuator. The cam actuator means operates to rotate the cam actuator rod within the firing pin cam bore via the cam actuator rod shown in .

The following sequence of actions takes place during the firing process of the electrically actuated weapon system of the present invention 

1. On the controller means the first switch is engaged so as to direct power to the extractor linear actuator means .

2. The extractor linear actuator means is now moved to the extended position which moves the cartridge extractor piston assembly along the extractor piston track bore extracting one weapon cartridge from the ammunition supply means and pushing the weapon cartridge along the extractor piston track bore .

3. The weapon cartridge is allowed to pass through the transition cavity and reside in the feeder piston bore .

4. The extractor linear actuator means is now stopped in the extended position which prevents any subsequent Cartridges from being extracted and internally disconnects all power from the extractor linear actuator means .

5. On the controller means the second switch is then engaged directing power to the feeder linear actuator means .

6. The feeder linear actuator means is now moved to the extended position which moves the cartridge feeder piston assembly along the feeder piston bore moves the cartridge into the chamber of weapon barrel and locks the extractor fingers onto the weapon cartridge flange.

7. The feeder linear actuator means is now stopped in the extended position which seals the weapon cartridge into the chamber of weapon barrel and internally disconnects all power from the feeder linear actuator means .

8. On the controller means the third switch is now engaged directing power to the cam actuator means .

9. The cam actuator means is now moved to the extended position which rotates the firing pin cam assembly counterclockwise 90 . This retracts the firing pin against the firing pin spring and then releases the firing pin so it then impacts the primer located at the rear of the weapon cartridge thereby initiating the propelling charge.

10. The cam actuator means is now stopped in the extended position which internally disconnects all power from the cam actuator means .

11. On the controller means the second switch is reengaged directing power to the feeder linear actuator means .

12. The feeder linear actuator means is now moved to the retracted position which moves the cartridge feeder piston assembly along the feeder piston bore . This pulls the expended weapon cartridge out of the chamber of the weapon barrel along the feeder piston bore and into the ejector rod forcing the expended weapon cartridge loose from the extractor fingers ejecting the expended weapon cartridge out of the weapon housing through the cartridge ejection slot .

13. The feeder linear actuator means is now stopped in the retracted position which internally disconnects all power from the feeder linear actuator means .

14. On the controller means the third switch is then reengaged directing power to the cam actuator means .

15. The cam actuator means is now moved to the retracted position which rotates the firing pin cam assembly clockwise 90 .

16. The cam actuator means is now stopped in the retracted position which internally disconnects all power from the cam actuator means .

17. On the controller means the first switch is then reengaged directing power to the extractor linear actuator means .

18. The extractor linear actuator means is now moved to the retracted position which moves the cartridge extractor piston assembly along the extractor piston track bore .

19. The extractor linear actuator means is now stopped in the retracted position which internally disconnects all power from the extractor linear actuator means .

After the above process is completed the electrically actuated weapon system is in the pre fire configuration as described above and is ready to begin the firing process as described above.

Although specific embodiments of the present invention have been disclosed herein those having ordinary skill in the art will understand that changes can be made to the specific embodiments without departing from the spirit and scope of the invention. The scope of the invention is not to be restricted therefore to the specific embodiments. Furthermore it is intended that the appended claims cover any and all such applications modifications and embodiments within the scope of the present invention.

