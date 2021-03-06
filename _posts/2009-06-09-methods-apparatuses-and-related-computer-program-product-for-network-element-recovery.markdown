---

title: Methods, apparatuses, and related computer program product for network element recovery
abstract: It is disclosed a method (and related apparatus) comprising establishing a control session by transmitting and receiving control session-related messages, transmitting restart information indicating a restart of a network element, receiving at least one protocol-related message of a first control session including session-related detail information, transmitting a restoration request message based on the session-related detail information, receiving at least one session parameter necessary for restoring the at least one first session, and restoring the at least one first session based on the received session-related detail information and the at least one session parameter. It is further disclosed a method (and related apparatus) comprising receiving restart information indicating a restart of a network element, processing at least one protocol-related message of a first control session to include session-related detail information, and transmitting at least one session parameter necessary for restoring the at least one first session, and the at least one protocol related message.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09258368&OS=09258368&RS=09258368
owner: NOKIA SOLUTIONS AND NETWORKS OY
number: 09258368
owner_city: Espoo
owner_country: FI
publication_date: 20090609
---
Examples of the present invention relate to network element recovery. More specifically the examples of the present invention relate to methods apparatuses and a related computer program product for network element recovery. The examples of the present invention may be applicable e.g. to policy and charging control PCC in a packet based mobile network e.g. 3generation partnership project 3GPP system architecture evolution SAE for example recovery and restoration from a failure of a PCC network element.

When a network entity such as a policy and charging rules function PCRF fails and or restarts the existing ongoing user sessions may be maintained with no or minimal damage. This may be facilitated by the use of some kind of a recovery mechanism to restore the status and data of the ongoing sessions in the re started network entity. When hot redundancy i.e. every critical network entity is doubled the second entity running active hot beside the first entity and maintaining the session statuses and data is not used at least some of the other network entities connected to the re started entity may be involved actively or passively in restoring the session statuses and data in the restarted entity.

There have been considerations on restoration procedures for a network element. For example restoring a pre failure status of user sessions e.g. in the PCRF may be achieved e.g. by fetching the session status information and the related parameters from the network elements connected to the PCRF. Furthermore restoration procedures may use protocols e.g. general packet radio service GPRS tunneling protocol GTP that comprise different planes e.g. control plane user plane that separate the control and management functions from the user plane user session functions.

However in case of failure e.g. of the PCRF a backup instance is required such as PCEF AF or BBERF . The backup instance already contains at least some session state information and is used after the failure. In that case the failed and restarted entity is up dated restored with the latest up to date session information.

In consideration of the above according to examples of the present invention methods apparatuses and a related computer program product for network element recovery are provided.

The examples of the present invention are described herein below by way of example with reference to the accompanying drawings.

It is to be noted that for this description the terms PCRF PCEF AF P CSCF and or SPR user UE ID and OR IP address and request message and or user plane event are examples for restarted element connected related element session related detail information and protocol related message respectively without restricting the latter named terms to the special technical or implementation details imposed to the first named terms.

As shown in a communication system may comprise a UE not shown and a network not shown . In turn the network may further comprise a PCEF a PCRF an AF P CSCF and an SPR .

As shown in in steps Sand S e.g. the PCRF and network elements connected to the PCRF may establish a control session by transmitting and receiving control session related messages.

As shown in in steps Sor S e.g. the PCRF may perform transmitting restart information indicating a restart of a network element. The transmitted restart information may be received by the PCEF the AF P CSCF or the SPR .

Then in step Sproc e.g. the PCEF the AF P CSCF or the SPR may perform processing at least one protocol related message of a first control session to include session related detail information based on the received restart information.

In steps Sor S e.g. the PCEF the AF P CSCF or the SPR may perform transmitting responsive to the receiving the at least one protocol related message of a first control session.

Then in steps Sor S e.g. the PCRF may perform receiving the at least one protocol related message of a first control session including session related detail information. The protocol related message of a first control session may comprise an indication information indicating a need for restoration of at least one session.

Thus in step S e.g. the PCRF may perform restoring the at least one first session based on the received session related detail information and the at least one session parameter.

As developments for the method pertaining to the PCRF in optional steps S S Sor S the PCRF may perform the above restoring further comprising second transmitting a restoration request message based on the session related detail information and in optional steps S S Sor S second receiving at least one session parameter necessary for restoring the at least one first session.

The network element to which the restoration request message is sent may be found using e.g. one of the following a Session identifiers and or user UE identifiers and or IP address are received from an entity that received the restart information b The restarted entity e.g. PCRF may send the restoration request to all possible entities and receives an acknowledgement from the entity that recognizes the parameters of the message c Session identifiers and or user UE identifiers and or IP addresses of network elements are saved in a network entity and restored by the restarted entity after the restart.

The restoring may further comprise restoring a second control session related to the first control session based on the transmitted restoration request message and the received at least one session parameter and binding the first control session and the second control session based on the received session parameter s and or detail information.

Further the protocol related message may be e.g. a session modification request or a user plane event report message received from a policy and charging enforcement function an application function or a bearer binding and event reporting function and the restoration request message may be a restore session request transmitted to a policy and charging enforcement function an application function bearer binding and event reporting function or a subscription profile repository. Alternatively or additionally the restoration request message may be a regular request message requesting session information from an application function or from a policy and charging enforcement function and requesting user information from a subscription profile repository.

Still further the indication information may be constituted explicitly by indication information. Alternatively the indication information may be constituted implicitly by reception of the protocol related message.

Finally e.g. the PCRF may perform requesting from any related network element e.g. PCEF AF SPR after a preconfigured time restoration of at least one session not yet restored but started before the restart.

As developments for the method pertaining to the PCEF the AF P CSCF or the SPR the transmitting may further comprise transmitting the indication information indicating the need for restoring at least one session.

As developments for the method pertaining to the PCRF as well as to the PCEF the AF P CSCF or the SPR the restart information may be part of a restarted message and the session related detail information may comprise user or UE identifications and or internet protocol addresses. In that case the session related detail information may further comprise session identifications. Alternatively the restart information may be part of a restore session message or a Diameter or application message and may comprise user identifications and or internet protocol addresses and the session related detail information may be part of an acknowledgement message from an entity recognizing the at least one of user identifications and internet protocol addresses. Alternatively the session related detail information may be stored upon each control session establishment and may comprise user identifications and or internet protocol addresses.

Further e.g. the PCRF as well as the PCEF the AF P CSCF or the SPR may perform at the establishment of the control session or at a later message exchange before the restart or at the restart indication message exchange negotiating a restoration scheme upon connection set up for a control session. Alternatively the negotiating may be performed upon performing a session related message exchange or a non session related message exchange. Alternatively the PCRF as well as the PCEF the AF P CSCF or the SPR may perform pre configuring the restoration scheme. Negotiable issues may comprise e.g. an indication to use an indication to inform about a restart an indication to use soft recovery i.e. the related session statuses at the restarted entity are restored only when there is anyway a reason to perform message exchange for other purposes like e.g. a user session update an indication to send identifiers of active sessions and or user UE identifiers and or IP addresses from related entities to the restarted entity after a restart for example to help the restarted entity identify correct network elements messages e.g. dedicated or regular and protocols e.g. a dedicated protocol or the application protocol used for recovery purposes parameters e.g. session identifiers user or UE identifiers IP addresses required or used in recovery restoration messages responses.

Still further the restoring may further comprise restoration of session bindings based on internet protocol addresses and user or UE identifications. Moreover restart information may not be transmitted prior to an exchange of session termination messages.

In addition the indication information may be triggered by modification of a session. Alternatively the indication information may be triggered by a user plane event or by a subscription to an event.

Steps Connections may be established between the clients e.g. PCEF AF and the server PCRF . The use and details of a recovery mechanism may be negotiated during upon the connection establishment message exchange.

Steps User UE session e.g. IP CAN session AF session related Diameter control sessions may be established between PCEF and PCRF and between AF and PCRF .

Steps PCRF may inform the related network elements e.g. PCEF GW AF about the restart. The use and details of a recovery mechanism may be negotiated with a message exchange with the related network elements.

Step For example an IP connectivity access network IP CAN session modification or a user plane event may produce e.g. a request message e.g. a Diameter CC Request message from the PCEF to the PCRF . The PCEF may include user UE ID and or IP address and possibly other parameters in the message to enable the PCRF to recover restore the session details lost in the restart. Knowing that the system is recovering from a PCRF restart the PCEF may include a parameter to indicate that the request relates to an existing session.

Step PCRF may have no status information for the session ID in the request but the PCRF may assume this session exists because of the indication from the PCEF or simply because a request was received after a restart where session statuses were lost . PCRF may restore the session status e.g. may store the session ID and possibly other session information and parameters for the User UE identity and or IP address related control session. PCRF may also start re creating the related control sessions with other network elements e.g. AF SPR because the PCRF may have lost the statuses and data e.g. session ID of the control session upon the failure restart.

Step PCRF may send a RESTORE SESSION request to AF to restore the related control session with the AF and possibly to get the related session information lost during the failure restart . PCRF may use the user UE ID and or IP address and possibly other parameters received from PCEF to identify the session towards the AF .

Step PCRF may also send a RESTORE SESSION request to SPR to restore the related control session with the SPR and possibly to get the related user subscription information lost during the failure restart . PCRF may use the user UE ID and or IP address and possibly other parameters received from PCEF to identify the session towards the SPR .

Step AF may acknowledge the SESSION RESTORE request and may send the session ID session information and possibly other parameters to the PCRF .

Step SPR may acknowledge the SESSION RESTORE request and may send the session ID user subscription information and possibly other parameters to the PCRF .

Step PCRF may restore the session status es e.g. may store the session ID s and other session status information and parameters for the User UE identity and or IP address related control session.

Steps to PCRF may use further regular control session related Diameter messages to get session or user subscription related information or to report events to AF or SPR if the session restore message exchange steps to did not cover these issues.

Step As a response to the CC Request from the PCEF step the PCRF may send a CC Answer including PCC rules created from the session information received from AF and possibly from the user information if fetched from the SPR to the PCEF .

Steps Connections may be established between the clients e.g. PCEF AF and the server PCRF . The use and details of a recovery mechanism may be negotiated during upon the connection establishment message exchange.

Steps User UE session IP CAN session AF session related Diameter control sessions may be established between PCEF and PCRF and between AF and PCRF .

Step PCRF may inform the related network elements e.g. PCEF GW AF about the restart. The use and details of a recovery mechanism may be negotiated with a message exchange with the related network elements.

Step For example an AF session modification or a need to change a subscription to user plane events may produce a request message e.g. a Diameter AA Request from the AF to the PCRF . The AF may include user UE ID and or IP address and possibly other parameters in the message to enable the PCRF to recover restore the session details lost in the restart. Knowing that the system is recovering from a PCRF restart the AF may include a parameter to indicate that the request relates to an existing session.

Step PCRF may have no status information for the session ID in the request but the PCRF may assume this session exists because of the indication from the AF or simply because a request was received after a restart where session statuses were lost . PCRF may restore the session status e.g. stores the session ID and possibly other session information and parameters for the User UE identity and or IP address related control session. PCRF may also start re creating the related control sessions with other network elements e.g. SPR PCEF because the PCRF may have lost the statuses and data e.g. session ID of the control session upon the failure restart.

Step PCRF may also send a RESTORE SESSION request to SPR to restore the related control session with the SPR and possibly to get the related user subscription information lost during the failure restart . PCRF may use the user UE ID and or IP address and possibly other parameters received from AF to identify the session towards the SPR .

Step SPR may acknowledge the SESSION RESTORE request and may send the session ID user subscription information and possibly other parameters to the PCRF .

Step PCRF may restore the session status e.g. may store the session ID and other session status information and parameters for the User UE identity and or IP address related control session.

Step PCRF may send a RESTORE SESSION request to PCEF to restore the related control session with the PCEF . PCRF may use the user UE ID and or IP address and possibly other parameters received from AF to identify the session towards the PCEF . The PCRF may also send other session related information e.g. PCC rules and event subscriptions in the session restore command to the PCEF .

Step PCEF may acknowledge the SESSION RESTORE request and may send the session ID and possibly other parameters e.g. the IP CAN session related details parameters to the PCRF .

Step PCRF may restore the session status e.g. may store the session ID and other session status information and parameters for the user UE identity and or IP address related control session.

Steps to PCRF may use further regular control session related Diameter messages to send session related information e.g. PCC rules and event subscriptions if the session restore message exchange steps and did not cover these issues.

The PCRF may comprise a CPU or core functionality CF a memory a transmitter or means for transmitting a receiver or means for receiving a restorer or means for restoring and an optional requester or means for requesting .

Further NWE may comprise a CPU or core functionality CF or processor or means for processing a memory a transmitter or means for transmitting and a receiver or means for receiving .

As indicated by the dashed extensions of the functional blocks of the CPU or the means for restoring and the means for requesting of the PCRF may be functionalities running on the CPU or of the PCRF or NWE or may alternatively be separate functional entities or means.

The CPUs wherein x and may respectively be configured for example by software residing in the memory to process various data inputs and to control the functions of the memories the means for transmitting and the means for receiving and the means for restoring and the means for requesting of the PCRF . Further it is to be noted that the CPUs the means for transmitting and the means for receiving may constitute means for negotiating means for pre configuring or means for establishing in the sense of the first and second examples of the present invention. The memories may serve e.g. for storing code means for carrying out e.g. the methods according to the example of the present invention when run e.g. on the CPUs . It is to be noted that the means for transmitting and the means for receiving may alternatively be provided as respective integral transceivers. It is further to be noted that the transmitters receivers may be implemented i as physical transmitters receivers for transceiving e.g. via the air interface e.g. between the UE and the PCRF via some other network element ii as routing entities e.g. for transmitting receiving data packets e.g. in a PS packet switching network e.g. between the PCRF and NWE when disposed as separate network entities iii as functionalities for writing reading information into from a given memory area e.g. in case of shared common CPUs or memories e.g. of the PCRF and NWE when disposed as an integral network entity or iv as any suitable combination of i to iii .

As shown in e.g. the means for establishing of the PCRF and network elements connected to the PCRF may establish a control session by transmitting and receiving control session related messages.

As shown in e.g. the means for transmitting of the PCRF may perform transmitting restart information indicating a restart of a network element. The transmitted restart information may be received by the means for receiving of the PCEF the AF P CSCF or the SPR .

Then e.g. the means for processing of the PCEF the AF P CSCF or the SPR may perform processing at least one protocol related message of a first control session to include session related detail information based on the received restart information.

For example the means for transmitting of the PCEF the AF P CSCF or the SPR may perform transmitting the at least one protocol related message of a first control session.

Then e.g. the means for receiving of the PCRF may perform receiving the at least one protocol related message of a first control session including session related detail information. The protocol related message of a first control session may comprise an indication information indicating a need for restoration of at least one session.

Thus e.g. the means for restoring of the PCRF may perform restoring the at least one first session based on the received session related detail information and the at least one session parameter.

As developments for the PCRF e.g. the means for restoring of the PCRF may perform the above restoring further by second transmitting a restoration request message based on the session related detail information and second receiving at least one session parameter necessary for restoring the at least one first session.

The network element to which the restoration request message is sent may be found using e.g. one of the following a Session identifiers and or user UE identifiers and or IP address are received from an entity that received the restart information b The restarted entity e.g. PCRF may send the restoration request to all possible entities and receives an acknowledgement from the entity that recognizes the parameters of the message c Session identifiers and or user UE identifiers and or IP addresses of network elements are saved in a network entity and restored by the restarted entity after the restart.

The means for restoring may further be configured to restore a second control session related to the first control session based on the transmitting restoration request message and the received at least one session parameter and to bind the first control session and the second control session based on the received session parameter s and or detail information.

Further the protocol related message may be e.g. a session modification request or a user plane event report message received from a policy and charging enforcement function an application function or a bearer binding and event reporting function and the restoration request message may be a restore session request transmitted to a policy and charging enforcement function an application function bearer binding and event reporting function or a subscription profile repository. Alternatively or additionally the restoration request message may be a regular request message requesting session information from an application function or from a policy and charging enforcement function and requesting user information from a subscription profile repository.

Still further the indication information may be constituted explicitly by indication information. Alternatively the indication information may be constituted implicitly by reception of the protocol related message.

Finally e.g. the means for requesting of the PCRF may perform requesting from any related network element e.g. PCEF AF SPR after a preconfigured time restoration of at least one session not yet restored but started before the restart.

As developments for the PCEF the AF P CSCF or the SPR the transmitting may further comprise transmitting the indication information indicating the need for restoring at least one session.

As developments for the PCRF as well as to the PCEF the AF P CSCF or the SPR the restart information may be part of a restarted message and the session related detail information may comprise user or UE identifications and or internet protocol addresses. In that case the session related detail information may further comprise session identifications. Alternatively the restart information may be part of a restore session message or a diameter or application message and may comprise user identifications and or internet protocol addresses and the session related detail information may be part of an acknowledgement message from an entity recognizing the at least one of user identifications and internet protocol addresses. Alternatively the session related detail information may be stored upon each control session establishment and may comprise user identifications and or internet protocol addresses.

Further e.g. the means for negotiating of the PCRF as well as the PCEF the AF P CSCF or the SPR may perform prior to the transmitting at the establishment of the control session or at a later message exchange before the restart or at the restart indication message exchange negotiating a restoration scheme upon connection set up for a control session. Alternatively the negotiating may be performed upon performing a session related message exchange or a non session related message exchange. Alternatively the means for pre configuring of the PCRF as well as the PCEF the AF P CSCF or the SPR may perform prior to the transmitting pre configuring the restoration scheme. Negotiable issues may comprise e.g. an indication to use an indication to inform about a restart an indication to use soft recovery i.e. the related session statuses at the restarted entity are restored only when there is anyway a reason to perform message exchange for other purposes like e.g. a user session update an indication to send identifiers of active sessions and or user UE identifiers and or IP addresses from related entities to the restarted entity after a restart for example to help the restarted entity identify correct network elements messages e.g. dedicated or regular and protocols e.g. a dedicated protocol or the application protocol used for recovery purposes parameters e.g. session identifiers user or UE identifiers IP addresses required or used in recovery restoration messages responses.

Still further the means for restoring may further be configured to restore session bindings based on internet protocol addresses and user or UE identifications. Moreover no restart information may not be transmitted prior to an exchange of session termination messages.

In addition the indication information may be triggered by modification of a session. Alternatively the indication information may be triggered by a user plane event or by a subscription to an event.

Furthermore all additional or optional method features described hereinabove in conjunction with also apply as corresponding apparatus features and are not repeated for the sake of description brevity.

Furthermore at least one of or more of the above described means for transmitting means for receiving means for restoring means for requesting means for processing means for negotiating means for pre configuring and means for establishing as well as the PCRF and NWE or the respective functionalities carried out may be implemented as a chipset module or subassembly.

Finally the present invention also relates to a system which may comprise the PCRF and NWE according to the above described first and second examples of the present invention.

Without being restricted to the details following in this section the examples of the present invention may be summarized as follows 

OPTION 1 The entity e.g. PCEF GW or AF receiving the RESTARTED message may send the UE user IDs and or IP addresses possibly even the session IDs of the sessions it has with the restarted element PCRF in the response to the RESTARTED message. This way the restarted element PCRF knows identifies the network element e.g. PCEF GW or AF per UE user and is able to contact the correct network element.

OPTION 2 The restarted entity e.g. PCRF may send the RESTORE SESSION message or the regular Diameter application message to all possible entities e.g. PCEF GW or AF . The acknowledgement message is received from the entity that recognizes the UE user identity and or IP address whereas the other entities reject the request message . Now the restarted entity e.g. PCRF knows identifies the correct network element e.g. PCEF GW or AF .

OPTION 3 The addresses identities possibly even the session IDs of the network elements related to a given UE user session may be saved upon each control session establishment. The addresses identities are restored after the restart. The entity saving the information may be one or several or all of the involved entities or an external entity . Only one entity may not be safe enough because it may fail and restart itself . For example GW 1 and SPR may save the addresses identities of each other and the address identity of the AF related to a given UE user session. After a restart the saving entity can send the saved addresses identities of the network elements related to the UE user identities and or IP addresses to restarted entity e.g. PCRF e.g. in a response message to the RESTARTED message.

According to an example of the present invention in a first aspect this object is for example achieved by a method comprising 

According to further refinements of the example of the present invention as defined under the above first aspect 

According to an example of the present invention in a second aspect this object is for example achieved by a method comprising 

According to further refinements of the example of the present invention as defined under the above first and the second aspect 

According to an example of the present invention in a third aspect this object is for example achieved by an apparatus comprising 

According to further refinements of the example of the present invention as defined under the above third aspect 

According to an example of the present invention in a fourth aspect this object is for example achieved by an apparatus comprising 

According to further refinements of the example of the present invention as defined under the above fourth aspect 

Although the present invention has been described herein before with reference to particular embodiments thereof the present invention is not limited thereto and various modification can be made thereto.

