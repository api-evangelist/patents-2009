---

title: Method for enabling a mobile user equipment to drag and drop data objects between distributed applications
abstract: The invention concerns a system and a method for enabling a mobile User Equipment () to drag and drop data objects between at least two remote applications () or between a local application () and a remote application (), the system including a Drag Source (), a Drag Target (), a Drop Source (), and a Drop Target (). In the system according to the invention, the Drag Source () is configured for negotiating with the Drag Target () a transmission protocol () for exchanging said data object between said Drop Source () and said Drop Target ().
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08966386&OS=08966386&RS=08966386
owner: Lenovo Innovations Limited (Hong Kong)
number: 08966386
owner_city: Quarry Bay
owner_country: HK
publication_date: 20090601
---
The invention pertains to telecommunication field and concerns a system and a method for enabling a mobile user equipment to drag and drop data objects between at least two remote applications or between a local application and a remote application.

In traditional computing network systems Thin Clients are usually client computer or client software in a client server architecture wherein a central server actions activities such as desktop applications and wherein a web browser or a remote desktop software runs on the thin client device. Because application logic is handled by the Server there are many Thin Client advantages such as reducing IT maintenance and administration costs enhanced data and system security and reduced power consumption.

The first type is a WebTop System for Web and Desktop or WebOS Web Operating System which enables the user to interact with the web equivalent of a desktop. The applications and documents associated to a user are gathered to create a page representing this information. Web services scripting Application Programming Interface API such as SOAP XML Simple Object Access Protocol Extensible Markup Language are the main technologies used.

The second type is a Screen Top System for screen and Desktop wherein a remote administration software allows Graphical User Interface applications to be run remotely on a server while being displayed locally on the user s device. Thin Clients protocols such as ICA Independent Computing Architecture RDP Remote Desktop Protocol RFB Remote Frame Buffer or even AIP Adaptive Internet Protocol are main protocols used in order for a server to remotely control the screen display of a user s device.

One main issue in deploying Thin Client technology is to know whether an application should be local i e resident remote or both Because when no more network connection is available in mobility context applications such a phone book a media player or any other resident applications would be no more available. Consequently those applications and data should be duplicated locally on the device memory and remotely on e.g. a corporate network server.

In order to alleviate the data duplication problems standardized synchronization technologies are provided such as in OMA Device Management Open Mobile Alliance OMA Data synchronization and OMA Client Provisioning Working Group.

Moreover it is foreseen that a mobile device will have both resident applications that can still be locally used even when having no network connection and remote desktop applications i.e. screen Top to access office or specific enterprise applications or even home personal applications.

A drag and drop is performed when a user selects one or more graphical objects and drags this selection using a pointing device for instance a mouse a trackball a touch based interface and then release the pressure to perform a drop of the object s . Basically the window in which the pointing device points receives a message notifying a drop operation and the object to be transferred and preferably a description of the object.

Generally the data to be transferred is stored in a clipboard in appropriated format therefore requiring potential conversion. Such clipboard is usually encapsulated into a file or a group of files.

The existing solutions based on a shared clipboard present interoperability and synchronization limitations. On the one hand they do not enable to negotiate the format of the data to be dragged and dropped. On the other hand they are often tight to specific implementations and dependent upon the Operating System. Besides they are often used for text based object rather than files or directories as the shared clipboard becomes more complex to manage with huge amount of data.

Moreover the existing solutions can be used between a local and a remote application but are not applicable in the case of drag and dropping action between remote applications.

Patent application WO 2007 142708 A1 discloses a method for dropping data object of low size e.g. text message over the currently established terminal service session between a client component and a server component. This method is bound to the remote procedure call RFC of the object and does not enable to exchange the data using different data transfer means e.g. file transfer streaming . . . and is tight to the two devices involved in the session. Actually large data file may require other more suitable protocol depending on the desired dropping action.

The exemplary object of the invention is achieved by means of a system using a distributed communication protocol that distinguishes the Drag Source from the Drop Source as well as the Drag Target from the Drop Target.

In the following description and in the claims a Data Object consists of Dragged Data Object and Dropped Data Object. Dragged Data Object is defined as the description of at least one object e.g. an icon representative of a file or a directory or any widgets such as a button or a form a text selection or an application window that will be dropped. Dropped Data Object is defined as the raw data object s associated to the Dragged Data Object sent to the Drop Target upon the action by the user of dropping said Dragged Data Object into the Drag Target. More than one raw data Objects can be associated to one Dragged Data Object so said action of dropping can lead to the transmission of one or more of the possible raw data objects having potentially different types e.g. video file text . . . . A Drag Source owns said Dragged Data Object and is defined as the Initiator of the drag and drop communication protocol. A Drag Target is defined as the receiver of said Dragged Data Object. A Drop Source is defined as the drop element configured by the Drag Source and that sends the Dropped Data Object using appropriate data transfer mechanism and a Drop Target represents the drop element that receives the Dropped Data Object. A Drag Drop Proxy is defined as the element that acts as a proxy forwarding drag and drop signaling without modification of the messages stateless proxy or inspecting the messages modifying the messages to include itself in the communication path used to exchange the Dropped Data Object and forwarding the modified messages statefull proxy .

An in the band transmission refers to the transmission of the Dropped Data Object within the drag and drop communication protocol while an out of the band refers to the transmission of the Dropped Data Object in a different channel than the one in which is transferred the Dragged Data Object. For instance the Dropped Data Object can be sent in a separate user data channel. The separate channel can be an end to end data pipe wherein a File Transfer Protocol is used over potentially a different Radio Access Network technology e.g. a WiFi access network interface a Cellular network access interface or a Bluetooth access network interface . . . .

The exemplary object of the invention is reached by means of a system for enabling a mobile user equipment to drag and drop data objects between at least two remote applications or between a remote application and a local application wherein said system comprises a Drag Source a Drag Target a Drop Source and a Drop Target and wherein the Drag Source is configured for negotiating with the Drag Target a transmission protocol for exchanging said Dropped Data Object between said Drop Source and said Drop Target.

The user can drag and drop a virtual data object from a resident application to a first remote desktop application respectively from RDA to a resident application arrow or can drag and drop a virtual data object between said first and second remote desktop applications RDA and RDA arrow .

As shown in this the drag and drop signaling is exchanged between Drag Source and Drag Target via a first channel while the data objects are exchanged between Drop Source and Drop Target via a second channel different from the first channel .

It is to be noted that the logical separation of channel and channel does not prevent that Drag Source and Drop Source respectively Drag Target and Drop Target to be hosted in the same physical device. Nevertheless this architecture enables those elements to be in separate entities thereby enabling new business models new use cases and capabilities.

A DRAG NOTIFICATION sent by the Drag Source to the Drag Target to notify said Drag Target to handle the drag of an object selection i.e. the Dragged Data Object . Preferably the DRAG NOTIFICATION includes a description of the object s of the selection and further a graphical representation of said object. The graphical information enables the Drag Target to visually render the drag object with the cursor graphical effect. The description of the object s enables the Drag Target to register the location information of drag object and its properties e.g. a list of supported format which can further enable automatic selection of application if no specific application is pointed by the pointing device i.e. this is so called in present invention as a precise less feature . The DRAG NOTIFICATION can further include a list of actions supported by the Drag Source .

The DRAG OBJECT REFUSE is returned to the Drag Source in response to a DRAG NOTIFICATION if the Drag Target cannot handle or refuse to handle the drag and drop operation.

The DROP OBJECT REQUEST is returned by the Drag Target to the Drag Source in response to the DRAG NOTIFICATION when the Dragged Data Object is dropped in the Drag Target . It includes the object identifier and the preferred data transfer mechanism. It also includes an action selected by the Drag Target . Such as a copy of an object an alias of an object a copy and the deletion of an object or a stream transmission of an object etc. . . . This enables the Drag Source to perform more accurate actions during and after the dropping of the object. If no action is specified by the Drag Target then the Drag source shall undertake a default action which can be a copy of an object

This message includes either the requested data in the band or the data exchange protocol and the required associated parameters e.g. IP addresses and port number . The Drag Source therefore configures arrow the Drop Source based on selected data exchange protocol and the Drag Target configures arrow the Drop Target to receive the data. In a particular embodiment of the invention the DROP OBJECT RESPONSE further includes license information associated to the action of a stream transmission of an object thereby enabling a DRM agent in the Drop Target to play back a video stream from a Drop Source.

A DRAG DROP END that signals the completion of the drag and drop operation between Drag Source and Drag Target . An indication is provided in this message that notifies whether Dropped Data Object transfer is completed because this message may not always relate to the end of the Dropped Data Object transmission. In a particular exemplary embodiment this DRAG DROP END message may be sent while a video is still being streamed just to notify that everything is working well. Nevertheless in some situation such as a move action dropping result the Drag Target sends the DRAG DROP END message to notify that the Dropped Data Object has been received and that it can be removed by the Drag Source and or Drop Source .

It is to be noted that those messages can be combined with existing thin client protocol messages for accurately handling the drag and drop and further drag and drop messages may be added to ensure accurate drag and drop operation. So an acknowledgment message in response to a drop object request can be sent by the Drag Source to the Drag target to avoid blocking until reception of a drop object response as the request may take times to complete. Also the Drag Source may cancel the drag and drop operation and as such it can send either a drop object refuse message not represented in the figure or a refuse indication in said acknowledgment message to cancel the drag and drop operation. For instance the Drag notification message results from a mouse button pressure event followed by an extension of movement event the release of a button event triggering the drop object request message if the cursor is within the boundary of the Drag Target window.

As shown in at step the Drag Source transmits to the Drag Target a Drag Notification message in order to request the UE to handle the dragging of the selected object s . Such notification provides information about the object graphical representation list of supported data format object properties supported actions .

At step the Drag Target sends a drop object request message or a drag refuse message. Said Drop object request enables the Drag Source to initiate the transfer of the requested object from said thin client server. The following information is included in said Drop object request 

The identification and the selected format of the Dragged Data Object including the necessary information for the Drag Source to understand which object needs to be dropped e.g. a region such as display coordinates x y or an object ID . The selected format of an object is preferably sent for instance in the form of MIME format.

The requested action on the object. For instance it can indicate whether it is a copy or a move copy then delete operation or a video stream delivery. It will be appreciated that the Drag Source device may have several actions associated to a Dragged Data Object. If none is specified by the Drag Target the Drag Source shall perform a default action for instance copy the object .

The preferred data transfer mechanisms. The data object can be provided in the band or out of the band using appropriate protocol. For instance a file object can be transferred using File Transport Protocol FTP .

At step the thin client server sends to the UE a drop object response with the selected data transfer mechanism. The data object can be sent within the response itself in the band or out of the band using a well known protocol e.g. File Transfer Protocol Real time Transport Protocol . In the later case the response includes the required protocol parameters server address or domain name port number . . . . This enables the Drag Source to configure arrow the Drop Source to receive the data object. The Drag Source may send back an ACK message not represented before sending the drop object response in order to avoid blocking the Drag Target since the configuration of the Drop Source may take time to complete.

Upon completion of the data transfer a drag drop end message is sent to cleanly end the drag and drop operation. Depending on the action such as a move operation this can lead to the deletion of the object. It will be appreciated that sending this message may not necessarily means that the data exchange is completed so it is up to the implementation to carefully handle the drag and drop completion and an indication is provided in the drag drop end message to notify the Drag Source whether the transfer of the Dropped Data Object is completed or not. For example if an video object is streamed to the UE the Drag Source might not wait for the end of the stream and other drag and drop can run in parallel.

According to a particular feature of the invention the data object information sent in the drag notification message enables the Drag Target to automatically identify the appropriate application and the action to perform with this object. Advantageously the information can further include a tag identification representative of a specific application phone book calendar text editor application . . . so that the Drop Target can automatically store the object more accurately. Such tag can be implemented in the form of a Uniform Resource Identification.

At step the Drag Source transmits to the Drag Target a Drag Notification message in order to request the thin client server to handle the dragging of the data objects selected by the user . Such notification provides information about the selected object graphical representation list of supported data format object properties supported actions 

At step the Drag Target sends a drop object request message or a drag refuse message to the Drag Source . The drop object request message initiates the transfer of the requested object from the UE to the thin client server .

The Dragged Data Object identifier and desired format including the necessary information for the Drag Source to understand which object needs to be Dropped e.g. a region such as display coordinates x y or an object ID . The selected format of an object is preferably sent for instance in the form of MIME format.

The requested action on the object. For instance it can indicate whether it is a copy or a move i.e. copy then delete operation or a video stream delivery. It will be appreciated that the Drag Source device may have several actions associated to a Dragged Data Object. If none is requested by the Drag Target the Drag Source shall provide a default action for instance copy the object .

The preferred data transfer mechanisms. Such indication enables the data object to be provided in the band or out of the band using appropriate protocol. For instance a file object can be transferred using File Transport Protocol FTP .

At step the UE sends to the thin client server a drag object response message with the selected data transfer mechanism. The data object can be sent within the response itself in the band or out of the band using a well known protocol e.g. FTP . In the later case the response includes the required protocol parameters server address or domain name port number . . . . This enables the Drag Source to configure arrow the Drop Source to receive the data object. The Drag Source may send back an ACK message not represented in the figure before sending the drag object response in order to avoid blocking the Drag Target since the configuration of the Drop Source may take time to complete. In a particular embodiment the storage device is a Universal Subscriber Identification Module USIM that has its own processing unit. The USIM stores the Dropped Data Object and handles the transmission of this object to the Thin Client Server . The UE communicates with the USIM through SIM Interface. Thus in one particular case of use the user is able to drag and drop an object from the USIM to the Thin Client Server.

Upon completion of the data transfer a drag drop end message is sent to cleanly end the drag and drop operation. Depending on the action such as a move operation this can lead to the deletion of the object. It will be appreciated that sending this message may not necessarily means that the data exchange is completed so it is up to the implementation to carefully handle the drag and drop completion. For example if an video object is streamed to the UE the Drag Source might not wait for the end of the stream and other drag and drop can run in parallel.

At step the Drag Source transmits to the Drag Target a drag notification message in order to request the transfer of the object s from the first thin client server acting as Drag Source to the second thin client server acting as Drag Target . Such notification provides information about the object graphical representation list of supported data format object properties supported actions .

At step the Drag Target sends a drop object request or a drag refuse to the Drag Source . The drop object request message initiates the transfer of the requested object from the first thin client server acting as Drag Source to the second thin client server acting as Drag Target .

The Dragged Data Object identifier and desired format including the necessary information for the Drag Source to understand which object needs to be dropped e.g. a region such as display coordinates x y or an object ID . The selected format of an object is preferably sent for instance in the form of MIME format.

The requested action on the object. For instance it can indicate whether it is a copy or a move copy then delete operation or a video stream delivery. It will be appreciated that the Drag Source device may have several actions associated to a Dragged Data Object. If none is specified by the Drag Target the Drag Source shall provide a default action for instance copy the object .

The preferred data transfer mechanisms. Such indication enables the data object to be provided in the band or out of the band using appropriate protocol. For instance a file object can be transferred using File Transport Protocol FTP .

At step the first thin client server acting as Drag Source sends to the second thin client server acting as Drag Target a Drag object response with the selected data transfer mechanism. The data object can be sent within the response itself in the band or out of the band using a well known protocol e.g. FTP . In the later case the response includes the required protocol parameters server address or domain name port number . . . .

Upon completion of the data transfer a drag drop end message is sent to cleanly end the drag and drop operation. Depending on the action such as a move operation this can lead to the deletion of the object. It will be appreciated that sending this message may not necessarily means that the data exchange is completed so it is up to the implementation to carefully handle the drag and drop completion. An indication is therefore provided in the drag drop end message to notify whether the transfer of the Dropped Data Object has completed or not. For example if an video object is streamed to the UE the Drag Source might not wait for the end of the stream and other drag and drop can run in parallel.

In the Statefull mode the UE acts as a back to back agent in the data exchange communication between a first remote application and a second remote application by acting as a proxy Drop Target for the Drop Source and by acting as a proxy Drop Source for the Drag Target .

In the Stateless mode the UE just forwards the drag and drop signaling messages. It is unaware of how the object data will be exchanged.

When the UE acts as a drag and drop data object proxy in statefull mode it acts itself as a back to back agent within the drag and drop signaling to set itself as the receiver for the drop source and as the sender for the drop target.

Referring to at step the Drag Source transmits to the UE acting as a drag and drop data object proxy a Drag Notification in order to request the transfer of the object s from the drag source located at a first thin client server to the drag target located at a second thin client server. Such notification provides information about the object graphical representation list of supported data format object properties supported actions .

At step the UE acting as a drag and drop data object proxy forwards said drag notification message to the drag target

At step the Drag Target sends to the UE acting as a drag and drop data object proxy a drag refuse or a Drop object request message.

The Dragged Data Object identifier and desired format including the necessary information for the Drop Source to understand which object needs to be dropped e.g. a region such as display coordinates x y or an object ID . The selected format of an object is preferably sent for instance in the form of MIME format.

The requested action on the object For instance it can indicate whether it is a copy or a move copy then delete operation or a video stream delivery. It will be appreciated that the Drag Source device may have several actions associated to a Dragged Data Object. If none is specified by the Drag Target the Drag Source shall provide a default action for instance copy the object .

The preferred data transfer mechanisms. The data object can be provided in the band or out of the band using appropriate protocol. For instance a file object can be transferred using File Transport Protocol FTP .

At step the UE acting as a drag and drop data object proxy forwards said Drop object request message to the drag source .

At step the drag source sends to the UE acting as a drag and drop data object proxy a Drag object response message with the selected data transfer mechanism.

In a first variant of the invention in which the UE acts as stateless drag and drop data object proxy the data exchange is performed end to end without necessarily going via the UE at step .

In a second variant of the invention in which the UE is as statefull drag and drop data object proxy it acts as a back to back agent within the drag and drop signaling to set itself as the receiver for the drop source through a first data exchange protocol step and as the sender for the drop target source through a second data exchange protocol step .

Upon completion of the data transfer a drag drop end message is sent to cleanly end the drag and drop operation Depending on the action such as a move operation this can lead to the deletion of the object. It will be appreciated that sending this message may not necessarily means that the data exchange is completed so it is up to the implementation to carefully handle the drag and drop completion. For example if an video object is streamed to the UE the Drag Source might not wait for the end of the stream and other drag and drop can run in parallel.

In a preferred exemplary embodiment the drag and dropping operation is configured on the remote and local device with default preferences. For instance it may always refer to a move operation or it may always be a copy operation without deleting the object from its location after being copied . Moreover this can be configured on a per application basis or per user preferences basis.

When the resident application detects step that the cursor is moving from within the boundary limits of said resident application to within boundary limits of the remote application window the client side of the remote application is notified of this event and sends a drag notification message step to the server side of the remote application. The drag notification message preferably includes a session identifier thereby enabling to start a drag and drop session. The notification event includes the data object information list of available formats name author supported actions graphical representation of the selection etc. . . . . and a list of available data exchange protocol e.g. FTP RTF and Trivial FTP . The thin client server acting as a Drag Target registers this event as a cursor press combined with cursor move event and updates the display by incorporating the graphical representation with the cursor. The object can be dragged within the remote application. Upon release of the object at the client side i.e. Drag source a button release event is sent to the server which triggers the Server i.e. Drag Target to identify the appropriate action and send to the client side either a drag refuse message step or a drop object request message step . The necessary server preferences for instance including the action to copy the object and preferably retrieve it using FTP protocol are embedded in the request and the Client then selects the data transfer mechanism being a file transfer in this embodiment.

In case of a drag refuse message the drag and drop action is resumed step and the Drag Source is put in monitoring state step in which it monitors the position of the cursor in the resident application window. Preferably the drag refuse message includes the session number thereby enabling Drag Target and Drag Source to close said drag and drop session.

In case of a drop object request message the client sends an acknowledgment not represented to the server to inform it that it has received the request and is preparing to respond. As such the client prepares the FTP Server acting as a Drop Source step and sends to the thin client server step a Drop object response with the necessary parameters including the FTP Server address and port number or protocol identifier .

The transmission of said Drop object response can be in the band step or out of the band step . In this embodiment an out of the band transmission is selected by using a File Transfer Protocol over a predefined data channel.

At step the server responds to the client by a drag drop end message notifying that the Drop Target is receiving the file object.

Since the object is copied in a memory area called clipboard and identified by an object identifier the FTP server drop source can send the requested object upon reception of a FTP client request drop target by the thin client server.

At step the drag target receives the drag notification message sent by the drag source. The drag and drop session is started.

If the cursor is out of the boundary limits of the remote application window the drag target sends a drag refuse message to the drag source step . If the drag target and or the drop target cannot handle the data object the drag target also sends a drag refuse message. The drag and drop session is closed.

If a drop event is detected the Drag target register the object information and identify the data transfer preferences step and sends a drop object request message at step .

At step the drag source sends step a drop object response to the drag target in the band step or out of the band step . In a particular embodiment the Drag Target configures a FTP Client i.e. Drop Target to receive the Dropped Data Object being a file object.

When the resident application detects that the cursor is moving from within the boundary limits of the resident application to within the boundary limits of the remote application the client side of the remote application is notified of this event and sends a drag notification message step to the thin client server of the remote application. Upon release of the object at the client side a release event is sent to the Server side which triggers the thin client server to identify the appropriate action and send a drop object request message .

The client side sends an acknowledgment to the thin client server to inform it that it has received the request and is preparing to respond. The client side prepares the FTP Server and sends a Drop object response with the necessary parameters including the FTP Server address and port number or protocol identifier . Since the object is copied in a memory area called clipboard and identified by an object identifier the FTP server can send the requested object upon reception of a FTP client request by the thin client server .

It is to be noted that the copied object in a memory pool area remains locked until it is downloaded by the legitimate thin client server and is preferably stored in a separate clipboard than the one currently existing in the local machine. Actually if the copied object referred to a move operation and if the user performs a paste operation on a local application before the thin client server downloads it this will result in moving the object on the local machine instead of the thin client server. So the copied object should be bound to the operation move or copy and bound to the legitimate thin client server to which is destined the object in case of a move operation only. In case of a copy operation the copied object can remain in the memory pool. It may be copied several times on the same or different thin client server.

A DRAG NOTIFICATION drag and drop message sent by Drag Source to Drag Target includes the following information 

For example only in case of retrieve URI action the In the band data information can contain an URI string with a procedure indication e.g. start a web browser with the URI store the URI or make a phone call .

The system according to the invention enables the data to be exchanged between different entities than the one involved in a drag and drop procedure.

According to the invention the transmission protocol negotiated between the Drag Source and the Drag Target uses either an in the band transmission channel or an out of the band transmission channel for transmitting Dropped Data Objects from said Drop Source to said Drop Target.

In a first exemplary embodiment of the invention the mobile user equipment selects a set of objects on a Remote Desktop Application and drops the selected objects into a local application.

In a second exemplary embodiment of the invention the mobile user equipment selects a set of objects on a first Remote Desktop Application and drops the selected objects into a second Remote Desktop Application. For example the objects can be dragged from a thin client server at the office to a thin client server at home and vice versa.

In a third exemplary embodiment of the invention the mobile user equipment selects a set of objects on a local application and drops the selected objects into a Remote Desktop Application.

The Dropped Data Object associated to Said selected objects may be exchanged between entities not necessarily involved in the drag and drop procedure. For example a selected object can be dragged from a thin client server to a mobile User Equipment i. e. a Dragged Data Object is exchanged and a video file i.e. a Dropped Data Object associated to said selected object can be streamed from a video playback server to the mobile User Equipment.

According to a particular variant of the invention the Drag Source and the Drop Source are located in the mobile User Equipment while the Drag Target and the Drop Target are located in a unique remote server.

In another variant the Drag Source and the Drop Source are located in the mobile User Equipment while the Drag Target and the Drop Target are distributed in different remote servers.

The method according to an exemplary aspect of the invention is characterized by the fact that the Drag Source and the Drag Target exchange drag and drop signaling over a first data channel while the Drop Source and the Drop Target can exchange the data objects over a second data channel different from said first data channel.

Accordingly the method according to the exemplary aspect of the invention proves advantageous in that the drag and drop method adopts a distributed approach thereby separating the drag and drop control signaling from the drag and drop data object exchange.

Moreover the user is able to interact with both local and remote applications and drag and drop objects as if all objects were on the same device.

The method therefore provides a transparent and similar functionality as traditional copy paste methods but using different mechanisms and enabling customized dropping results.

the Drag Source detects that a selected data object moves outside limits of its application window boundaries to within the boundaries of the Drag Target application window. So the Drag Source transmits to the Drag Target a drag notification to notify to said Drag Target to handle the drag of a selected data object 

in response to said drag notification the Drag Target responds to the Drag Source either by a DRAG OBJECT REFUSE message if the Drag Target cannot handle the drag and drop operation or if the Drag Target detects that said selected data object i.e. Dragged Data Object is returning to within the boundaries of the Drag Source application window or by a DROP OBJECT REQUEST if the Dragged Data Object is dropped and accepted in the Drag Target application window 

upon reception of said DROP OBJECT REQUEST the Drag Source transmits to said Drag Target a DROP OBJECT RESPONSE including either the requested data in the band or the data exchange protocol along with associated parameters such as IP addresses and port number so that the Drop Target can retrieve the Dropped Data Object from the Drop Source 

upon reception of said DROP OBJECT RESPONSE the Drag Source configures the Drop Source based on selected data exchange protocol and the Drag Target configures the Drop Target to receive the selected data 

the Drag Target transmits the Drag Source a DRAG DROP END signal to announce the completion of the drag and drop operation between Drag Source and Drag Target.

Other messages can be sent for accurate handling of the drag and drop operation. As such the Drag Source may send an acknowledgment message to the Drag Target to avoid blocking the Drag Target the Drag Source may also abandon the drag and drop operation by sending either another message e.g. a DROP OBJECT REFUSE message or an indication within the acknowledgment message e.g. a DROP OBJECT REQUEST ACK .

Preferably said drag notification comprises a description of the selected data object to enable the Drag Target to register the location information of selected data object and its properties which can further enable automatic selection of application and a graphical representation of said selected data object to enable the Drag Target to visually render the selected data object in addition to the traditional cursor graphical effect. The drag notification can further include a list of actions supported by the Drag Source to enable the Drag Target to efficiently select a preferred action. Said action refers to an expected dropping result.

The DROP OBJECT REQUEST includes an object identifier a preferred data transfer mechanism a description of the preferred action selected by the Drag Target.

The DROP OBJECT RESPONSE includes the object identifier and the selected data transfer mechanism along with potential data exchange protocol parameters. The DROP OBJECT RESPONSE further comprises license information associated to the action of a stream transmission of an object to enable a DRM agent in the Drop Target to play back a video stream from the Drop Source.

The method according to an exemplary aspect of the invention comprises a set of possible actions supported by the Drag Source consisting of 

a stream of a selection action to enable said Drop Target to receive a stream of the selection from said Drop Source 

an alias of a selection to enable the drop target to receive a link address to the physical data object from the drop source 

a move command of a selection which is a copy of a selection action followed by the removal of the selection 

a retrieval command of a URI associated to the selection to enable the Drop Source to use said URI and do appropriate procedure using said URI.

In a variant of the invention the DROP OBJECT RESPONSE further comprises license information associated to said action of a stream transmission of an object to enable a DRM agent in the Drop Target to play back a video stream transmitted by the Drop Source.

In a particular implementation the drag and drop messages i.e. drag notification drag object refuse drop object request drop object response drag drop end include a session identification number in order to accurately handle the drag and drop session. Both Drag Source and Drag Target can thereby identify the session to which pertain the drag and drop messages and start a timer when sending said drag and drop messages to avoid blocking situation by discarding said drag and drop session.

Advantageously communication errors and malicious attacks can be prevented and multiple drag and drop session can run in parallel.

The method according to an exemplary aspect of the invention is implemented by means of a Computer program product stored in a memory storage and adapted when executed in a computer for enabling a mobile user equipment to drag and drop data ejects between at least two remote applications or between a remote and a local applications in a system comprising a Drag Source a Drag Target a Drop Source and a Drop Target said computer program comprising 

instructions for enabling a mobile user equipment to drag and drop data objects between at least two remote applications or between a remote and local application and to configure itself either as a Drag Source or a Drag Target or both 

instructions for enabling the Drag Source to detect a movement of an objects selection outside the boundaries of said Drag Source application window 

instructions for enabling the Drag Source to transmits to the Drag Target a drag notification to notify to said Drag Target to handle the drag of a selected data object i.e. a Dragged Data Object 

instructions for enabling the Drag Target to respond to the Drag Source either by a DRAG OBJECT REFUSE if the Drag Target cannot handle the drag and drop operation or if the selected data object moves from within the Drag Target application window boundaries to the boundaries of the Drag Source application window or by a DROP OBJECT REQUEST if the Dragged Data Object is dropped and accepted in the Drag Target 

instructions for enabling the Drag Source to transmit to said Drag Target a DROP OBJECT RESPONSE including either the requested data in the band or the data exchange protocol along with associated parameters such as IP addresses and port number to enable the Drop Target to retrieve the Dropped Data Object from the Drop Source. If however the Drag Source wishes to abandon the drag and drop operation it sends either another message e.g. a DROP OBJECT REFUSE message or an indication within an acknowledgment message e.g. a DROP OBJECT REQUEST ACK message acknowledging the reception of said DROP OBJECT REQUEST 

instructions for enabling the Drag Source to configure the Drop Source based on selected data exchange protocol and the Drag Target to configure the Drop Target to receive the selected data 

instructions for enabling the Drag Target to transmit the Drag Source a DRAG DROP END signal to announce the completion of the drag and drop operation between Drag Source and Drag Target.

While the invention has been particularly shown and described with reference to exemplary embodiments thereof the invention is not limited to these embodiments. It will be understood by those of ordinary skill in the art that various changes in form and details may be made therein without departing from the sprit and scope of the present invention as defined by the claims.

This application is based upon and claims the benefit of priority from European patent application No. 08157603.5 filed on Jun. 4 2008 the disclosure of which is incorporated herein in its entirety by reference.

