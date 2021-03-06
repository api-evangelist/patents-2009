---

title: Connection system
abstract: Various embodiments include systems and methods for providing communication among a plurality of users with complementary requirements in an electronic network.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08346622&OS=08346622&RS=08346622
owner: eBay Inc.
number: 08346622
owner_city: San Jose
owner_country: US
publication_date: 20090421
---
The present application claims the benefit of priority of the following provisional patent application U.S. Provisional Patent Application No. 61 152 973 filed Feb. 17 2009 entitled Simple method system to connect people with complementary requirements the entirety of which is incorporated by reference herein.

People at different points in their lives may seek offer information data goods services partners etc. For these purposes people may seek commercial operations that specialize in specific areas of business e.g. a person seeking a book might visit a book store. Transactions may be person to person transactions. E.g. a person needs a babysitter in his her neighborhood. In some embodiments people or entities may be placed into one of the two categories a those who seek and b those who offer.

Several systems exist that connect those seeking with those offering. According to some classification schemes these can be broadly grouped as 

D. Direct matching systems including classified advertisements in print media subject focused Internet websites that match offerers with seekers e.g. auction dating and job sites e.g. general use free classified sites 

Systems A and B may be costly and are sometimes effectively limited to use by commercial businesses that have capital to allocate toward advertising and sales.

System C may limit the connection making process to the extent of a person s individual network of people.

As used herein a communication network may refer to a network of communication devices and or stations having wired or wireless interconnection for establishing communication. Communication may include without limitation transmitting and receiving signals. Communication may further include without limitation transferring information and data such as voice audio video graphics and the like. Communication network may include without limitation Internet intranet extranet Wide Area Network WAN wireless WAN WWAN Local Area Network LAN wireless LAN WLAN transducer links such as those using Modulator Demodulators modems telecommunication network personal area network and Global Navigation Satellite System GNSS . Telecommunication network may include without limitation Public Switched Telephone Network PSTN Global System for Mobile Communications GSM and Code Division Multiple Access network CDMA . Personal area network may include without limitation Bluetooth and Infrared and Global Navigation Satellite System GNSS .

In the following description specific details are set forth in order to provide a thorough understanding of various embodiments. However it will be apparent to a person of ordinary skill in the art that various embodiments may be practiced without these specific details or with additional details. Various aspects and features of example embodiments are described in detail hereinafter.

Various embodiments include systems and methods for connecting buyers seekers with sellers offerers. Various embodiments allow seekers and offerers to find one another without paying listing fees. Various embodiments allow seekers and or offerers to post an indication of a product or service to buy or sell. Various embodiments allow seekers and or offerers to post an indication of a desire to accomplish something. Various embodiments may allow the postings to remain active or relevant for significant periods of time such as days weeks months or years.

Various embodiments may allow seekers and or offerers to find each other with minimal data entry required. Various embodiments may allow seekers and or offerers to find each other without the necessity of extensively browsing postings or profiles of their counterparts. Various embodiments may allow seekers and or offerers to communicate with each other with minimal lag in communication.

Various embodiments may allow seekers and offerers to communicate directly. Various embodiments may provide similar perspectives and or user interfaces to both seekers and offerers. Various embodiments may account for the possibility that the number of offerers may not necessarily exceed the number of seekers and vice versa.

Various embodiments may allow seekers to communicate with offerers without revealing personal information such as email addresses. Various embodiments may allow offerers to communicate with seekers without revealing personal information such as email addresses.

Various embodiments may allow a poster e.g. a seeker or an offerer to specify a geographical reach for his her posting. Thus in some embodiments a poster may reach multiple cities with a single posting. E.g. a single posting may be accessible from multiple cities. In some embodiments a seeker may search for products services etc. across multiple geographic regions through a single site or interface.

Users may access UHIW Back end system using an electronic device such as computer cell phone or the like through communication network . The electronic device may host a UHIW client which uses communication network to connect with UHIW Back end system . UHIW client may be different for each user depending upon the electronic device.

In some embodiments users may register with UHIW Back end system . During registration users may provide their contact information. The contact information may include username user phone number user chat id email id etc.

After registering a user may submit details of one or more products through UHIW client . A user may submit requirement details of a product if the user wants to buy that product. A user may submit offering details of a product if the user wants to sell that product. A product may be any physical commodity good service or any information. A single user may submit requirement offering details for any number of products. The requirement details and the offering details may be provided in the form of keywords. Keywords may be entered using one or more means. For example keywords may be entered into a box using a keyboard or may be selected through a drop down menu.

Offering details and requirement details may be stored by UHIW Back end system . For each detail the contact information of the corresponding user who submitted the details may also be stored.

UHIW Back end system may match the requirement details with the offering details. Each requirement detail may match with one or more offering details and vice versa. A user who submits a particular requirement offering detail may be presented with all the matched results. For example Back end system may determine that a match exists between an offer and a requirement if a keyword from the offering details corresponding to the offer is the same as a keyword from the requirement details corresponding to the requirement.

A user through user interface may view all the matched results corresponding to the requirement offering details submitted by her.

Each incoming message may be pushed to the database . In some embodiments database may store all I want messages and I have messages received from various users. In addition database may also store contact information of some or all users.

In some embodiments matching engine matches an I want message with one or more I have messages. Matching engine may also match an I have message with one or more I want messages. Matching engine may use a search engine such as Lucene for matching results. Matching engine may index the stored messages in advance of the matching process in order to enable a faster matching process. An index of messages may be prepared corresponding to each keyword and keyword combinations. The matching process may include several iterations based on different fields of information in the message. As will be appreciated the matching engine may employ various search algorithms matching algorithms or various other algorithms according to various embodiments. The matched results may be stored in database .

Output module may output matched results to user through UHIW client . User may have the option to delete any result from the matched result list. So if a user subsequently accesses the matched result list the deleted result may not appear in the list.

Chat engine may provide a communication channel to user for establishing communication with other users. Communication may be through an external chat client an internal chat client and or through a combination of the two. Examples of external chat clients include Gtalk Yahoo messenger MSN messenger etc. Examples of internal chat clients include Jabber Coccinella etc.

If the user associated with a matched result is online e.g. on any of the chat client services available internal or external user may send her a request for a chat conversation. The other user may accept or deny user s request.

If the user associated with a matched result is offline user may send an offline message to her. The offline message may be sent as SMS to her cell phone as email or as a notification in a chat client.

Chat engine may also provide a mail inbox facility UHIW system message box to receive offline notifications from other users. User may view the notifications in UHIW system message box after she logs into the UHIW system. In some embodiments logging into the UHIW may be user s sole means of accessing the notifications.

At step after user has logged into the UHIW application she may be asked to choose from options of posting an I want or I have message. illustrate the display presented to user the display providing the user with various options. Options may be chosen by clicking on the tabs e.g. the I want tab or I have tab . User may choose I want tab to post requirement details an I want message for a product which user wants to purchase. User may choose I have tab to post offering details an I have message for the product she wants to sell.

At step an interface as illustrated in may be provided to user enabling her to post a new I want message. In some embodiments an I want interface display may include a text area a submit button and a table . Text Area is the portion where an I want message for the product may be posted. An I want message may comprise a combination of keywords. Text area may provide one or more text boxes where a user may enter keywords. The keywords may reflect a product name product specifications a cost associated with a product or any other feature or characteristic of a product service etc. Various mechanisms may be used for entering keywords. In some embodiments keywords may be typed in using a keyboard. In some embodiments keywords may be selected using a drop down menu. For example keyword California may be selected through a drop down menu which lists all state names in the USA. In some embodiment keywords may be entered under various headings using the advanced interface illustrated in .

For example in multiple headings such as category year price range etc. are provided. There may be a separate space to fill in general keywords. In the example illustrated in the user has filled in keywords autos 2004 after 25 35 K Mercedes C Class Autos

Table lists I want messages previously posted by user . User may delete any message from table and then the message may also be deleted from database .

At step the new I want message posted may be stored in database . Thereafter this I want message may also appear in table .

At step UHIW Back end system matches the new I want message with one or more I have messages in database . Matching engine retrieves keywords from the I want message and may use various algorithms for example search algorithms to match the messages. Matching engine may also apply these algorithms to the contact information of user . The I have messages that match with the new I want message are associated with the new I want message. For example database may create a record to store the new I want message and may store within that record an identifier associated with each of the matching I have messages.

Steps and are steps that may be executed if user wants to post an I have message using the I have screen. Step and are analogous to steps and respectively. As illustrated in I have messages posted by user in text area may appear in table after the user has saved them using save button . Text area may provide one or more text boxes to enter keywords and the messages may then be stored in database . In some embodiments an advanced interface shown in may also be used to post an I have message.

The step of matching may be performed by UHIW system for each I want message and each I have message stored in database . Thus corresponding to each I want message there may be one or more matching I have messages. Similarly corresponding to each I have message there may be one or more matching I want messages.

Matching for a message may be done immediately after any message is posted or may be done after a fixed time. User may log off after posting the message.

In case user wants to view the matched results for his I have I want messages step is executed. illustrates an exemplary display for displaying matched results to user . User may view the matched results by clicking on matches tab .

Table presents each matching result in a row. According to some embodiments each matching result may include type of message message description user id or alias of user who posted that matched message and a link to contact that user. The type of messages may be I want if the match corresponds to an I have message and I have if the match corresponds to an I want message. User may also have the option to delete any matched result using the delete option. In that case the entry may be deleted from matched results of that message in database .

Table may indicate which of the users associated with the matched results are online. A user may be online if she is logged into UHIW Back end system or if she is available on her chat id e.g. if she is logged onto an external chat system . If a user associated with a matched result is online user may contact her by clicking on the chat now link.

At step UHIW Back end system may receive a request from user to contact an online user e.g. an online user corresponding to a match that user has received . For example referring to user may click on or otherwise select Chat now in order to request to contact the user known as Air guy in the matched results.

At step on approval of the user Air guy user may chat with her. Chat engine may facilitate the chatting functionality between the two users. In case the corresponding user e.g. Agent is offline an offline message may be sent to her UHIW application email cell phone or any external chat client. In user may check her chat histories or offline messages in view message link .

UHIW client may also provide a display to user for changing her account settings. In an exemplary Settings screen is illustrated. The Settings Screen may comprise a Sign in tab a personal information area an external chat information area and an alerts information area . Personal information area may comprise a user name user location UHIW ID etc.

External chat information area allows user to be connected to the UHIW application while available on external chat or email services. User may provide priority to external chats and may provide her id or related information for receiving any message or chat request. User may also sign in to external chat clients using sign in tab . For an external chat client UHIW application may store the corresponding server address which may include address and port number for the particular external chat client which enables a user to connect to that external chat client. Alerts information area allows user to receive messages when not on the Internet e.g. to receive messages on his cell phone or email. User may select the frequency of the messages.

According to some embodiments UHIW System may also provide a user with the option of tracking listening to I have messages related to a specific field. Tracking may be done without posting an I want message. This functionality is called listener .

Listening rules may be related to a product for which user desires a periodic or continuous stream of information. The user may for example desire to eventually purchase air tickets to New York. For this purpose user may want to view all I have messages related to Air Tickets to New York . So user may provide Air tickets to New York in the listening rules. After saving the rule using save button the listening rule is submitted to UHIW Back end system and the rule is listed in table .

UHIW Back end system may match listening rules with stored I have messages. Matched I have messages e.g. some or all matched I have messages may be presented to user in table in . The messages may be presented and or updated periodically and or continuously.

According to some embodiments user may not directly contact users posting the I have messages. After user gets an idea of what people are selling in a particular domain she may post an I want message in a manner such that the message may match with the I have messages that are of interest to her. Thus after suitable matching has been done user may contact the users associated with the matched results.

At step user may provide some listening rules. As illustrated in user may provide listening rules by clicking on listening rules link . She may be directed to a set listening rules screen which has been illustrated in . Keywords may be provided as listening rules.

Listening rules may be related to some specific products for which user requires a continuous stream of information. For example user may want to view all I want messages related to laptops . Accordingly she may enter laptops under the heading category in text area . After saving the rule using save button the listening rule is submitted to UHIW Back end system and the rule is listed in table .

At step UHIW Back end system may match each received I want message with the listening rules. Some or all matched I want messages may be stored in database .

At step some or all matched I want messages may be presented to the user . The messages may be presented once periodically or continuously according to various embodiments. According to some embodiments a message may be presented to user at run time after the message has been posted by another user. According to some embodiments some or all matched results may be displayed on the listener screen in table . According to some embodiments some or all matched results may be emailed to user or may be sent to user through chat client or may be sent to the user via some other mode of communication

After user gets an indication of the I want messages in the desired business specific category she may post a new I have message with UHIW Back end system to meet the requirements highlighted in those I want messages. For example user may receive 20 messages which indicate that users are looking for Dell laptops IBM laptops etc. which are 2 years old and within a specific price range. So user may create a new I have message such that UHIW Back end system will be able to match the new I have message with those 20 I want messages. In the above mentioned example chances of matching may be increased by user by choosing keywords like Dell laptop and 

At step user may create an I have message through the process described in . UHIW Back end system may then perform a match between this newly created I have message and the I want messages stored in database. The users who posted matched I want messages will then be presented with the offering details of user and may contact him though the process as discussed in .

Embodiment A. A computer implemented method for providing person to person communication among a plurality of users the method comprising the steps of 

Receiving requirement details for a first product from a first user wherein the requirement details comprise a plurality of keywords associated with the first product 

Receiving offering details for a second product from a second user wherein the offering details comprise a plurality of keywords associated with the second product 

Matching the requirement details of the first product with the offering details of the second product 

In the event of a successful match presenting the offering details for the second product to the first user wherein the presentation further comprises the option of contacting the second user 

Embodiment B. The computer implemented method of embodiment A wherein the communication channel may be telecommunication internet or any other communication channel.

In the event of a successful match presenting the requirement details of the first product to the second user wherein the presentation further comprises the option of contacting the first user 

Embodiment D. The computer implemented method of embodiment A wherein the first product may be a good service or information.

Embodiment E. The computer implemented method of embodiment A wherein the second product may be a good service or information.

Embodiment F. A computer implemented method for providing person to person communication among a plurality of users for commercial purposes the method comprising 

Receiving requirement details for a first product from a first user wherein the requirement details comprise a plurality of keywords associated with the first product 

Receiving offering details for a second product from a second user wherein the offering details comprise a plurality of keywords associated with the second product 

Receiving offering details for a third product from a third user wherein the offering details comprise a plurality of keywords associated with the third product 

Matching the requirement details of the first product with the offering details of the second product and the third product 

In the event of a successful match presenting the second and third offering details to the first user in an arranged manner wherein arrangement is done based on the keywords in the requirement details provided by the first user 

Receiving an indication from the first user to contact a target user the target user being one of the second user and the third user and

Embodiment G. The computer implemented method of embodiment F wherein the arrangement of offering details further comprises the arrangement according to the geography provided by the first user in the requirement details.

Receiving requirement details for a fourth product from a fourth user wherein the requirement details comprises a plurality of keywords associated with the fourth product 

Matching the offering details of the second product with the requirement details of the first product and the fourth product 

In the event of a successful match presenting the first and fourth requirements details to the second user in an arranged manner wherein arrangement is done based on the keywords in the offering details provided by the second user 

Receiving an indication from the second user to contact a target user the target user being one of the first user and the fourth user and

Embodiment I. The computer implemented method of embodiment H wherein the arrangement of first and fourth requirement details further comprises the arrangement according to the geography provided by the second user in the offering details.

Embodiment J. A computer implemented method for establishing person to person communication the method comprising 

Receiving listening details corresponding to a first product from a first user wherein the listening details comprise a plurality of keywords associated with the first product 

Establishing communication between first user and one or more users corresponding to the matched requirement details and

In various embodiments a first user may contact a second user who is logged onto an external chat service. For example an I have description submitted by the first user may have been matched with an I want description entered by the second user. The first user may have thereupon been presented with an option to contact the second user.

In various embodiments an external chat service may include a chat service run or maintained by a third party and or an unaffiliated chat service. Examples may include chat services offered by Google AOL and Yahoo.

According to various embodiments messages may be relayed to an external chat service and received from the external chat service via an application programming interface API . An example API is jYSMG which provides an interface by which Java applications can utilize the Yahoo Instant Messenger protocol.

According to various embodiments an API or other means may also be used to detect whether a user e.g. the second user is logged onto an external chat service. The second user may be identified via an alias that the second user employs on the external chat service. If the second user is logged on then the first user may be informed that the second user is logged on. However the first user may not necessarily be told the alias used by the second user on the external chat service. Rather in some embodiments the first user may be told a second different alias. The second alias may correspond to an alias used by the second user on the present system according to various embodiments.

In various embodiments a first description of a first product for sale is received from a first user. A second description of a second product that a second user desires to purchase is received from the second user. The first description is compared to the second description. It is determined that the first description matches the second description. For example there are matches of one or more key words. It is determined that the first user is logged onto an external chat service. An indication that the first user is logged onto the external chat service is provided to the second user. For example the second user is given the option to click to chat with the first user. An indication of a desire to communicate with the first user is received from the second user. For example the second user actually does click on a link labeled click to chat . A signal is sent to the first user via the external chat service indicating that the second user wishes to communicate with the first user. For example a message is sent to the first user telling the first user that someone else s description has matched his description and that the other person wishes to chat. Permission is received from the first user to put the second user in communication with the first user. For example the first user sends a message back in which he agrees to chat with the second user. A message is transmitted from the second user to the first user via the external chat service.

In various embodiments determining that the first description matches the second description may comprise determining that a first word in the first description is the same as a second word in the second description. For example the first description may be sailing vessel and the second description may be water vessel . Accordingly the two descriptions may be deemed a match because of the common word vessel .

In various embodiments determining that the first description matches the second description may comprise determining a first geographic region based on the first description determining a second geographic region based on the second description and determining that the first geographic region is proximate to the second geographic region. Geographic regions may be determined from a description in various ways including determining latitude and longitude coordinates determining a city determining GPS coordinates determining a zip code determining a state determining a street address determining a street intersection determining a highway exit determining a landmark determining a subset of a large region e.g. Southern New Jersey is a subset of New Jersey and in various other ways as will be appreciated. In various embodiments a first geographic region may be deemed proximate to a second geographic region if the two regions are the same if the two regions are within a predetermined distance of one another e.g. if the two regions are within 10 miles of one another if the two regions are on the same landmass e.g. on the same island e.g. on the same continent if the two regions are accessible to one another e.g. accessible by foot e.g. accessible by car e.g. accessible by bus if the two regions are within the same city if the two regions are within the same country or if the two regions together satisfy one or more other criteria.

In various embodiments a first alias is received from the first user the first alias serving to identify the first user on the external chat service. It may then be determined whether the first user is logged onto the external chat service by checking the status of the first alias with the external chat service. For example the first alias may be joe1999 . It may be determined whether the first user is logged on by checking the status of joe1999 with the external chat service e.g. via an API .

In various embodiments even if a first user has a first alias on an external chat service the first user may designate a second alias on an internal chat service or other communication system. For example even if the first user is known as joe1999 on an external chat service the user may provide an alias sam555 on an internal chat service. In this way a second user may have the option of communicating with the first user internally but may be unable to identify the first user outside of the system. E.g. the second user may know the alias sam555 but may remain ignorant of the alias joe1999 . In this way the privacy and or anonymity of the first user may be maintained.

In various embodiments a first and second user may communicate via a combination of external and internal chat services. For example a second user may use an internal chat service to send a message to a first user who is logged onto an external chat service. The system according to some embodiments may then relay the message to the external chat service so that it reaches the first user. The message may be relayed using an API to the external chat service for example.

In various embodiments a user who posts an I want or I have message may receive multiple matches. The matches may then be presented to the user in a particular order e.g. in an order defined by a top to bottom arrangement a left to right arrangement or any other arrangement . In some embodiments the matches may be ordered according to one or more criteria. In some embodiments for two or more matches a geographic distance is determined between locations indicated in the matched descriptions. For example if message is matched with message and message describes location A and message describes location B then a distance may be determined between location A and location B. With distances among matched descriptions determined the matches may be sorted according to distance. In some embodiments matches that correspond to shorter distances may be displayed before e.g. above e.g. to the left of matches corresponding to longer distances.

In some embodiments a user may provide a description that receives multiple matched descriptions. Two matched descriptions may match on different keywords however. For example a user may enter Tennis racket Brooklyn . The user may receive two matches with the following descriptions tennis racket and Brooklyn racket . In some embodiments multiple matched descriptions may be presented to a user in a certain order based on which key words have matched. In determining the order of matches presented certain key words or categories of key words may be given more weight or higher priority than others. For example key words that indicate or correspond to geography may be given higher priority than other key words. Thus Brooklyn racket may be given the higher priority among the two matches described above since the matched word of Brooklyn has a geographic connotation whereas the matched word of tennis does not. Note that both of the above descriptions have matched on the word racket so this word may not favor either match in terms of priority.

Categories of key words may include words that pertain to geography words that pertain to product age words that pertain to product quality words that pertain to product price and other categories.

For example in some embodiments matches based on key words relating to geography may be given priority over matches relating to words based on product age.

It will be appreciated that in some embodiments matches need not only be made based on key words and that other factors leading to matches may be used in determining the order of matches. For example pairs of matched descriptions may be ordered based on the degree of similarity in price between each of the two matched descriptions.

In various embodiments various rules may be used for alerting a user to a match. Rules may specify how frequently a user is to be alerted about new matches at what address a user is to be alerted e.g. which of multiple addresses a user has provided is to be used to alert the user which mode of communication is to be used to alert a user e.g. email versus short messaging service for which types of matches a user is to be alerted e.g. a user is to be alerted for matches on all key words but not for matches on only one key word and any other criteria.

A rule may specify a frequency with which a user is to be alerted about new matches. For example a rule may specify that a user is to be alerted immediately about a new match that a user is to be alerted once a day about all his new matches that a user is to be alerted once a week about all his new matches or any other frequency. In some embodiments a user may be alerted with different frequencies on different modes of communication. For example a user may be alerted after every match on his cell phone but only once per day at his email address.

In some embodiments an alert may alternately be sent to one of two different addresses depending on the type or nature of a match. For example a user may be sent an alert for a match on his cell phone e.g. via SMS if there is a match on price but an alert at his email address if there is a match on geography. For instance a user may consider certain types of matches more urgent than others and may therefore wish to be alerted e.g. on a cell phone for more urgent matches and on email for less urgent matches.

In some embodiments a first user may receive a match substantially immediately e.g. within a very short period e.g. within a few seconds after entering a first description. For example the first description entered by the first user may match a second description previously entered by a second user. In some embodiments the first user may later receive another match on the first description. The new match may be with a third description that was entered by a third user after the first user had entered the first description. Thus the first user may receive a second match significantly after having received the first match e.g. an hour later e.g. a day later e.g. a week later . Thus in various embodiments matches may be sought for a given description long after the description has been entered.

In various embodiments a user posting an I have message may enter a network address indicating a location where more information can be found about the product being described. The network address may be a uniform resource locater URL for example.

In various embodiments communication among users employing different modes of communication may be facilitated. For example through the system a user on a chat client internal or external may communicate with a user employing a cellular phone e.g. using SMS . In various embodiments the system may receive a first message from a first user via an Internet chat client and transmit the first message to a cellular phone belonging to a second user via Short Messaging Service. The system may also perform the reverse process. Namely the system may receive an SMS message and transmit the message to the Internet chat client.

In various embodiments a first user who has posted an I have message can view the search criterion used to find the product he has posted. Thus in some embodiments if a second user has entered search criterion e.g. has entered key words that have matched the product posted by the first user then the first user will have the opportunity to view the search criterion e.g. the keywords entered by the second user. In some embodiments the first user may further view other information about the second user such as an identifier or alias of the second user.

In some embodiments a search criterion entered by the second user may include an indication of a geographic region.

It will be understood that while various embodiments have been illustrated and discussed these are not to be construed as limiting. Various alterations may be made thereto without departing from the broader spirit and scope of the various contemplated embodiments. The specification and drawings are accordingly to be regarded in an illustrative sense rather than a restrictive sense.

