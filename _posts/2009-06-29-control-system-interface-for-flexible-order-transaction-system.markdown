---

title: Control system interface for flexible order transaction system
abstract: The present invention provides a control system interface for accessing a plurality of functions relating to a flexible order transaction system.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08306864&OS=08306864&RS=08306864
owner: SAP AG
number: 08306864
owner_city: Walldorf
owner_country: DE
publication_date: 20090629
---
This application claims priority under 35 U.S.C. 121 to U.S. patent application Ser. No. 10 850 814 entitled Control System Interface for Flexible Order Transaction System which is herein incorporated by reference in its entirety. This application also incorporates by reference the following patents in their entirety U.S. Pat. No. 7 409 351 entitled Method And System For Splitting An Order In A Flexible Order Transaction System U.S. Pat. No. 7 464 038 entitled Method And System For Changing An Order In A Flexible Order Transaction System U.S. Pat. No. 7 464 039 entitled Method And System For Merging Orders In A Flexible Order Transaction System and U.S. Pat. No. 7 363 238 entitled Method And System For Cost Integration In A Flexible Order Transaction System.

The present invention relates to information systems and computer interfaces. In particular the present invention provides a method and system for a user interface allowing access to unique features of a flexible order system. In one embodiment of the present invention the flexible order system relates to a shop floor manufacturing system controlling an already in progress production order.

Modern enterprise business software systems may provide among other services functions for Supply Chain Monitoring Supply Chain Collaboration Demand Planning Supplier Network Planning Multilevel Supply and Demand Matching Global ATP Available to Production Production Planning Transportation Training and Vehicle Scheduling Maintenance and Service Training Master Data and Administration Functions. These services may be made available from a single software application which is referred to herein as an APO Advanced Planning Optimizer . Associated with an APO is a set of tables containing business data. These tables may be accessed by functions provided by the APO.

With respect to production planning as production and manufacturing cycles become more complex it becomes apparent that the software must provide services for tracking these complex transactions and allow for flexible transaction processing. Particularly for certain complex environments such as the semiconductor industry it is often necessary to accommodate highly complex order splits merges and changes.

In addition to providing functions to handle complex split merge and change requirements it would be beneficial to provide access to these services in a convenient manner such as through a convenient user interface such as graphical user interface GUI . This is particularly apparent as it is often necessary to access these functionalities from an industrial environment.

The present invention provides a user interface for accessing and implementing a set of split merge and change functionalities via a graphical user interface through a supply chain management system or through an application programming interface.

POM provides services for showing the status of orders. In addition POM provides functionality for accessing functions provided by FOT such as order splits merges and changes. POM provides GUI that allows for access of the services and functions in POM. In particular as shown in POM may access functions in FOT via GUI .

PAH provides access to FOT function module via convert actions . BAPI provides API calls to access FOT functions .

Upon choosing selection button user may select particular FOT functions to be executed. In particular with respect to and for illustrative purposes only it is assumed that user has selected a split function included in FOT . Upon this selection interactive screen is displayed to user .

In order to effect a split for a particular order the user enters a product in product field order number in order number field quantity in quantity field description in description field and reporting points of parent and child in respective fields and . The control system fills in fields and .

Also shown in is original parent order window . Original parent order window shows table headings for reporting points yield scrap UoM Unit of Measure and Active.

Selecting simulate button allows the user to perform a simulation of the split action in order to experiment with quantities etc. A subsequent screen see will show the outcome of the split upon which the user may then decide to actually execute the split perform another simulation or cancel the split.

At this point the user may enter new split data to perform another simulation by choosing simulate button execute the split by choosing execute button or cancel by choosing cancel button .

The user may enter a surviving order number in surviving order number field and a merge order number in merge order number field . In addition the user selects a surviving order reporting point by entering the appropriate information in surviving order reporting point field . Note that corresponding product and product description are respectively displayed in product fields and .

The user may then simulate the merge using simulate button . The simulate function operates identically to the operation described with respect to . In addition the user may execute the merge via button cancel the order via cancel button or toggle orders via toggle orders button .

Surviving order window merging order window and resulting order window are respectively display upon selection of a merge operation.

