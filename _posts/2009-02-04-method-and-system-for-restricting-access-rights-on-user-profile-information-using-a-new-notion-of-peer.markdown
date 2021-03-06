---

title: Method and system for restricting access rights on user profile information using a new notion of peer
abstract: 


url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09628492&OS=09628492&RS=09628492
owner: International Business Machines Corporation
number: 09628492
owner_city: Armonk
owner_country: US
publication_date: 20090204
---
This application claims priority under 35 U.S.C. 119 a to European Patent Application Serial Number EP08151050.5 filed Feb. 5 2008 entitled METHOD AND SYSTEM FOR RESTRICTING ACCESS RIGHTS ON USER PROFILE INFORMATION USING A NEW NOTION OF PEER the entirety of which is incorporated herein by reference.

The present invention relates to the field of Network portals and in particular to a method and system for restricting access rights on user profile information using a new notion of peer groups.

In this field the term composite application defines an application hosted on a web portal platform which is built by combining and connecting multiple components such as portlets wikis document libraries and web services for a particular purpose such as a shop or a virtual team room application. A single portal platform may host multiple instances of the same composite application for example different team rooms for different associated user communities. Composite applications are built from a template describing the contained components and their set up and interconnection.

The templating application infrastructure TAI component manages the templates in the system which contain references to instantiable components in a local list of components . As an example a template for shopping applications could consist of a reference to a document library component which is used to hold the available goods and their descriptions a shop portlet that let clients process actual shopping transactions an invoice business component that handles the payment process and a blogging component that allows clients to comment on their satisfaction.

The TAI component also creates application instances from the templates via an instantiation component which creates separate instances of the referenced business components typically by creating or copying individual configurations for these components such that multiple application instances can be created from the same template without interfering with each other.

For the above mentioned sample template the instantiation would among other things create an individual storage compartment in the document library an individual configuration of the invoice component referring to the bank account and an individual configuration for the shop portlet that is set up to display goods from the created document library and to delegate payment processing to the created invoice component instance.

In particular the instantiation needs to create the necessary portal artifacts like pages that allow to interact with the created composite application which is typically done by employing a specific handler that creates those portal artifacts and links them with the business components of the application.

The created composite application instances hold a context that lists the component instances that make up the composite application

With reference now to the focus of the invention prior art composite applications are a key concept of prior art Service Oriented Architecture. They allow end users to assemble business logic out of a set of given components without programming by simply defining some meta information such as configuration data and application structure.

Prior art composite applications are supported for example by the prior art IBM WebSphere Portal and other known products.

With reference now to B and with respect to the very technical problem of the current invention prior art web based collaboration platforms typically support the concept of communities . A community e.g. circle in is a set of people e.g. persons D E F that share a specific working objective or interest. Being member of a given community typically comes with access to resources or portal objects shared within the community such as documents portal pages and portlets in order to be able to collaborate together in one or more composite applications. Other communities and coexist with similar function and persons contained therein.

Communities in prior art are created and managed in a dynamic on demand fashion with the creator of a community being the community manager that is allowed to invite other people to the community. This disadvantageously includes much manual work.

With particular reference to in prior art collaboration platforms access control on user data is typically managed by a logical program component in a way orthogonal to the community concept. This means a security administrator defines by way of a logical User Management program component which user is allowed to see profile information of what other users. Based on this access control information users can benefit from people awareness features like who is online right now . . . . Details thereto are explained with reference to .

With particular reference to illustrating prior art access management to users for a certain given single user when this single user initiates a search on an other user see step in this user uses a respective user interface for such search request which is provided by some portlet to him. This portlet passes his request to the user management component which intern provides the access to a user data store and a group data store see step .

Then in a further step an interaction step between component and access control component is performed during which it is checked if the before mentioned user Bob is allowed to see other users. The respective control information is managed by the access control component which stores and manages access information on all types of resources and so also of the resource user .

In order to do that the access control component looks up the access rights for user Bob in its current configuration see step .

In order to do that completely also the static access information from database is looked up by observing the entry for user Bob. The result is returned to the user management component which evaluates this result and sends the search request to a backend storage device for example the LDAP user store in order to perform search overall available users.

Further disadvantageously and with respect to step in there is no dynamic method available to allow an admin user concerned with security management tasks to restrict the available user base of a given user to the persons he has a need to collaborate to. If something like this is required the admin will need to manage the access rights for every user if a membership of a community has changed which results in a high personal manual effort of the admin.

Further prior art collaboration tools only allow each user to search all users from the available directory. This is of great disadvantage however as in many situations the full list of users e.g. several hundred or several thousands of them is simply too large to be scrolled and controlled by an individual.

Thus the desire results that a name is able to be made invisible for others. The only way to be invisible for other users however is by either using a black or a white list. Those lists however need to be maintained by each individual user however which again results in a high personal manual effort.

The objective of the present invention is thus to provide a more efficient and flexible method and system for restricting access rights on user profile information.

This objective of the invention is achieved by the features stated in enclosed independent claims. Further advantageous arrangements and embodiments of the invention are set forth in the respective subclaims. Reference should now be made to the appended claims.

According to the broadest aspect of the inventional method a method for restricting access rights on user profile information using a new notion of peer groups wherein a given user s peer group is defined to be the set of users containing all the members of all the user s communities wherein the individual communities are defined within the web portal wherein on said web portal a plurality of composite applications are implemented wherein each composite application has a predetermined number of users working with said composite application building a community for that composite application 

Further for the executing step b instead of a LDAP filter an explicit post filter step is implemented in order to discard all user profile information from the query result that is not associated to users contained in the requesting users peer group.

The inventional method provides an automatic visibility control for users based on community membership wherein users are automatically allowed to see i.e. be aware of the other community members.

By way of the inventional method it is advantageously possible to limit the set of visible users to exactly those users that are collaborating with each other e.g. the members of a shared community.

Further advantageously the inventional method provides to automatically assess the relevance of individual communities for individual users.

The present invention is based on the idea to introduce peer groups wherein a peer group is related to a given user and is the set of users that share at least one community membership with the given user. The membership to a certain community is defined preferably by the membership to the same composite application or in other terms to the same collaborative application.

Further according to this guideline access control to the before mentioned resources of a web portal is based according to the invention on the above mentioned peer groups. So the inventional method and system support a specific operational mode in which the access control valid for a given user is solely controlled by his membership to the respective composite or collaborative application. By that a user is allowed to be aware of the existence of another user and may access the user profile of such user only if this user is a part of his peer group.

With general reference to the figures and with special reference now to when running a program implementing a preferred embodiment of the inventional method in a portal environment the access to user information for a single user Bob is described as follows 

The first steps 1 2 3 and 4 are performed as described above with the discussion of prior art. They are denoted in with reference numbers to respectively. This ends up with the result if Bob is allowed to see other users which result is made available to the user management component .

Then in a novel step a community filter component provided by this inventional embodiment implements a restriction of the visibility of the current users to the subset of users of Bob s communities. In order to do that the inventional community filter sends an ask request for all users and groups the exemplary user Bob is sharing a composite application with. This request is directed to the application infrastructure which is known from prior art and stores and manages information about composite applications implemented in the portal. This program component first determines all composite applications the exemplary user Bob is member of. This information is based upon the composite application Bob is able to join and the users or groups which are listed as members of those composite applications. The application infrastructure component retrieves this information from the Datastore see step . The application component returns this information to the user management component see step .

Now the user management component uses the plurality of user names representing the members of the plurality of Bob s composite applications in order to establish a filter criterion which is generated by the inventional enriched user management component . So as a result of this evaluation a search request is generated by user management component in cooperation with the community filter component which includes the composite applications and the respective restricted members thereof corresponding to Bob s composite applications.

This generated search request is then sent by the community filter of the user management component to the backend user data store in order to get the user information of the restricted plurality of users instead of all users as done in prior art.

The effect of the inventional method is a restricted user visibility for any exemplary user such as user Bob in the forgoing description. By means of the inventional method special peer groups are established wherein the users of the portal are now implicit members of their individual peer groups.

With reference to the peer group of user E is the set of persons B D F. Further the peer group of person A is an empty set. The peer group of user B are persons D E the peer group of person C are persons D F and the peer group of person D are persons C F B E.

Due to the inventional method all users are automatically allowed to communicate with the persons of their individual peer groups without being constrained to perform a difficult user selection from the set of all users having access to the portal. By that the user comfort is significantly increased because the communication is significantly simplified because the selection to which user a communication shall be established is significantly simplified. So automatically any exemplary user only sees communication partners of composite applications in which he is member and thus he is collaborating with.

As reveals also from for example for user C this user is not aware of user E since user E and user C have no shared composite application. Remark that each circle in corresponds to a composite application and a position for person within circle symbolizes the membership of that person in that composite application.

Further advantageously illustrates that in case a new user A joins the community she will automatically see the users C D and F as they are also members of composite application . The inventional method may also include an additional access control step which may be applied on top of the access control performed by the inventional method in its base form as it was described above. This can be preferably done in particular situations for example when a person has to provide some administration and is thus provided with quite high access rights but still does not have access rights to the whole entire plurality of users of a portal. This may be of great advantage for example in situations in which a merger of two enterprises is performed wherein two preexisting portals are merged and wherein the user management and portal management is determined to be continued quite individually for each of the merged enterprises. In addition it is still possible to provide some users the right to see more users as defined through their peer group. This is for the purpose to send an invitation to a new user who does not belong to any community.

The invention can take the form of an entirely hardware embodiment an entirely software embodiment or an embodiment containing both hardware and software elements. In a preferred embodiment the invention is implemented in software which includes but is not limited to firmware resident software microcode etc.

Furthermore the invention can take the form of a computer program product accessible from a computer usable or computer readable medium providing program code for use by or in connection with a computer or any instruction execution system. For the purposes of this description a computer usable or computer readable medium can be any apparatus that can contain store communicate propagate or transport the program for use by or in connection with the instruction execution system apparatus or device.

The medium can be an electronic magnetic optical electromagnetic infrared or semiconductor system or apparatus or device or a propagation medium. Examples of a computer readable medium include a semiconductor or solid state memory magnetic tape a removable computer diskette a random access memory RAM a read only memory ROM a rigid magnetic disk and an optical disk. Current examples of optical disks include compact disk read only memory CD ROM compact disk read write CD R W and DVD.

A data processing system suitable for storing and or executing program code will include at least one processor coupled directly or indirectly to memory elements through a system bus. The memory elements can include local memory employed during actual execution of the program code bulk storage and cache memories which provide temporary storage of at least some program code in order to reduce the number of times code must be retrieved from bulk storage during execution.

Input output or I O devices including but not limited to keyboards displays pointing devices etc. can be coupled to the system either directly or through intervening I O controllers.

Network adapters may also be coupled to the system to enable the data processing system to become coupled to other data processing systems or remote printers or storage devices through intervening private or public networks. Modems cable modem and Ethernet cards are just a few of the currently available types of network adapters.

