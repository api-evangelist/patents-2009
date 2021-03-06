---

title: Method and system for distributed computing interface
abstract: A method and system for distributed computing interface are disclosed. According to one embodiment, a computer implemented method comprises accessing a collaborative interface, wherein the collaborative interface comprises persistent shared space, wherein visual representation of the collaborative interface is identical for each client accessing the collaborative interface. In a single action, an object is dragged into the collaborative interface and the object is displayed in real time in the collaborative interface. The object is accessible to other clients in the collaborative interface and the state of the object is continuously synchronized. The object is manipulated in the collaborative interface and other clients accessing the collaborative interface are viewed.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08689115&OS=08689115&RS=08689115
owner: Net Power and Light, Inc.
number: 08689115
owner_city: San Francisco
owner_country: US
publication_date: 20090921
---
The present application claims the benefit of and priority to U.S. Provisional Patent Application No. 61 098 682 entitled Method and System for Distributed Computing Interface for Sharing Synchronizing Manipulating Storing and Transporting Data filed on Sep. 19 2008 and is hereby incorporated by reference.

The present system relates in general to computer applications and more specifically to a method and system for distributed computing interface.

According to Opera Software ASA in 1997 around 85 of the time spent at a computer was spent using desktop applications. In 2007 about 70 of the time was spent using a web browser. The web browser has become the most commonly used human interface for using computing.

However the ways people are using Internet services and the ways the internet services are provided in terms of underlying technology are changing. The three strong trends that demonstrate this ongoing change are Rich Internet Applications Cloud Computing and Mobile Internet Services.

As the browser is used for the majority of the time spent at a computer users demand rich functionality of complex software to be available through the web browser. Examples of the functionalities include image editing video processing document processing VoIP telecommunications video conferencing and distributed collaboration systems. Exisitng technologies Adobe Flex AJAX Java Applets enable the browser to run complex applications. Although such applications were developed for the web browser by a number of startup and large companies the architecture and legacy of the web browser place several limitations on application performance development ease and the user interface richness.

Companies in the cloud computing field are building infrastructure for cloud computing. As computing and storage have gotten cheaper hosting internet applications with massive usage millions of simultaneous users within a centralized data center has become possible. Such applications and data centers have been built by companies like Google search email Yahoo email Salesforce.com CRM . The next step was to build a set of application programming interfaces APIs around these datacenters to allow third party developers to host their applications on the robust infrastructures built and supported by large industry players. This new way of developing deploying providing and using Internet services and applications was named cloud computing. Cloud computing was pioneered by companies such as Amazon with their Amazon Web Services initiative which started with S3 APIs and service for cloud storage and EC2 computing . The followers included Google Google Application Engine and Microsoft Live Mesh initiative .

With the introduction of convenient zoom in zoom out multi touch user interfaces on mobile devices with small screens affordable pricing for unlimited Internet usage fast data transfer capabilities on cellular networks 3G built in global positioning devices photo and video cameras powerful processors and large storage mobile devices are becoming the new and great platform for rich mobile Internet applications and services including cloud based applications. No standard way of utilizing the computing and storage power of the cloud is available on mobile devices. The internet is accessed via custom web browsers built into mobile devices Opera iPhone or third party applications that lack a standard approach for using internet services.

The web browser used to access cloud applications uses http and https based protocols placing a number of limitations on the capabilities of cloud computing. In particular the current cloud computing platforms fail to enable data synchronization between multiple application users real time streaming capabilities and real time collaboration capabilities. User interface is lacking to utilize capabilities provided by rich applications running in the cloud cloud based applications . Also a browser cannot naturally offload data processing to the cloud e.g. graphic rendering or CPU intensive jobs and there is no way to make offloading transparent and seamless for the end user.

The web browser s underlying technological principles of operation and its architecture can no longer provide the best solution for certain crucial usage scenarios like for example sharing data real time collaboration around documents and media working with applications executing in a distributed computing environment.

The web browser architecture places limitations on performance user experience richness and ease of development of modern Internet applications.

The web browser architecture is not well suited to work with cloud based applications. In particular with those cloud based applications including real time communication functionality data sharing and data synchronization among multiple users. The web browser does not address the need of emerging rich Internet applications and cloud based Internet applications which include complex functionality on mobile device platforms

Beyond the browser there are a few methods that are commonly used by users to share the documents and collaborate. However most of these methods applications are even less convenient then the browser.

Users utilize email as the way to share documents as attachments but email has limitations such as the attachment size and difficulty of tracking document versions. FTP for document sharing does not enable real time communication and collaboration.

Tools exist that work with one or a few file types but do not address the sharing and collaborating around many rich media types such as pictures music videos games or applications. Existing collaboration tools do not provide support for cloud based Internet applications.

Based on the above there is a need for an improved base application for using Internet services with a different user interface and architecture better suited to answer the emerging needs such as the richness of Internet applications support for and taking advantage of cloud computing applications and utilizing these two trends on the emerging mass market mobile device platforms.

A method and system for distributed computing interface are disclosed. According to one embodiment a computer implemented method comprises accessing a collaborative interface wherein the collaborative interface comprises persistent shared space wherein visual representation of the collaborative interface is identical for each client accessing the collaborative interface. In a single action an object is dragged into the collaborative interface and the object is displayed in real time in the collaborative interface. The object is accessible to other clients in the collaborative interface and the state of the object is continuously synchronized. The object is manipulated in the collaborative interface and other clients accessing the collaborative interface are viewed.

A method and system for distributed computing interface are disclosed. According to one embodiment a computer implemented method comprises accessing a collaborative interface wherein the collaborative interface comprises persistent shared space wherein visual representation of the collaborative interface is identical for each client accessing the collaborative interface. In a single action an object is dragged into the collaborative interface and the object is displayed in real time in the collaborative interface. The object is accessible to other clients in the collaborative interface and the state of the object is continuously synchronized. The object is manipulated in the collaborative interface and other clients accessing the collaborative interface are viewed.

In the following description a new term c space is utilized when referring to a shared collaboration space.

In the following description for purposes of explanation specific nomenclature is set forth to provide a thorough understanding of the various inventive concepts disclosed herein. However it will be apparent to one skilled in the art that these specific details are not required in order to practice the various inventive concepts disclosed herein.

Some portions of the detailed descriptions that follow are presented in terms of algorithms and symbolic representations of operations on data bits within a computer memory. These algorithmic descriptions and representations are the means used by those skilled in the data processing arts to most effectively convey the substance of their work to others skilled in the art. A method is here and generally conceived to be a self consistent process leading to a desired result. The process involves physical manipulations of physical quantities. Usually though not necessarily these quantities take the form of electrical or magnetic signals capable of being stored transferred combined compared and otherwise manipulated. It has proven convenient at times principally for reasons of common usage to refer to these signals as bits values elements symbols characters terms numbers or the like.

It should be borne in mind however that all of these and similar terms are to be associated with the appropriate physical quantities and are merely convenient labels applied to these quantities. Unless specifically stated otherwise as apparent from the following discussion it is appreciated that throughout the description discussions utilizing terms such as processing or computing or calculating or determining or displaying or the like refer to the action and processes of a computer system or similar electronic computing device that manipulates and transforms data represented as physical electronic quantities within the computer system s registers and memories into other data similarly represented as physical quantities within the computer system memories or registers or other such information storage transmission or display devices.

The present method and system also relates to apparatus for performing the operations herein. This apparatus may be specially constructed for the required purposes or it may comprise a general purpose computer selectively activated or reconfigured by a computer program stored in the computer. Such a computer program may be stored in a computer readable storage medium such as but is not limited to any type of disk including floppy disks optical disks CD ROMs and magnetic optical disks read only memories ROMs random access memories RAMs EPROMs EEPROMs magnetic or optical cards or any type of media suitable for storing electronic instructions and each coupled to a computer system bus.

The algorithms and displays presented herein are not inherently related to any particular computer or other apparatus. Various general purpose systems may be used with programs in accordance with the teachings herein or it may prove convenient to construct more specialized apparatus to perform the required method steps. The required structure for a variety of these systems will appear from the description below. In addition the present invention is not described with reference to any particular programming language. It will be appreciated that a variety of programming languages may be used to implement the teachings of the method and system as described herein.

As will be appreciated the teachings of the present invention can be readily implemented on a variety of computing platforms including mobile and portable platforms the personal desktop simply being a convenient paradigm for discussion. Additionally the wide variety of features and functionality described below are optional and implementation dependent. Those skilled in the art will readily understand which features are suitable and required for any specific implementation.

The shared space includes images or videos representing Users participating in a data sharing and manipulation session. By way of example a number of files and documents are represented all of which can be shared by participating users during a sharing session in a shared space 

The shared space may provide various ease of use functionality. For example the shared space may be resized using the resize control in the lower right corner . The shared space may also be minimized closed or maximized to occupy all the available viewing area of the shared space using controls on the upper right corner. A flip control can be used to see the files stored in a distributed computing system as well as using these stored files in a distributed data session.

In the scenario depicted above User wishes to share the Word document on his personal computer desktop. User selects the document and drags it from the PC desktop into the open shared space . The path of the dragged file is shown by images . The other documents shown can be shared in a similar way.

The user drags a document into their shared space and it occupies the available viewing area of the shared space and presents to each shared space session participant as shown in . As will be appreciated dragging is one embodiment for introducing an object into the sharing space the user may be provided additional and or alternative mechanisms for initiating a sharing session.

In this example Users represented by images or videos are sharing a Word document in shared space . Once the document has been dragged or otherwise brought in the document is represented as a viewer and occupies the entire available shared space to maximize the shared experience. Each User here Users see exactly the same content and exactly the same view of the document as the other users participating in the session the view of the shared space is also synchronized over time among the participants of data sharing and manipulation session. Other embodiments of the present invention may enable asynchronous operations or support security measures which place limits on information sharing and or provide other ways of sharing data not necessarily in an absolutely synchronous manner.

Once the dragging is complete the PowerPoint viewer is presented synchronously to all participants of the data sharing session. In addition the Word document previously being shared is no longer visible. As with the shared Word document the PowerPoint viewer occupies all the available viewing area of the shared space and presents to each shared space session participant as shown below in . Of course other embodiments could simultaneously display multiple simultaneously shared documents and or a user could be involved in multiple C Space sessions simultaneously.

The shared space contains images or videos representing Users participating in a data sharing and manipulation session. User wants to share a web browser session and opens a web browser and navigates to a web page on his personal computer desktop. User initiates shared browsing by dragging the Internet address link into the shared space shown with 

Within the shared space a shared browser viewer directed to the desired Internet address opens. The shared viewer is constantly synchronizing among the data sharing and data manipulating session participants.

Note that the Internet browser viewer shows navigation buttons a URL address field and a bookmarks bar . 

The browser viewer is a simplified browser distinct from standard browsers in that it is hosted within the shared session. Each time a user clicks a web page element within the browser viewer the view is synchronized among the shared session participants.

The browser itself is synchronized across participants of the collaborative session and can display audio files video files and flash animations can process JavaScript as well as regular HTML pages and.

All the listed data object types are shared within C Space data sharing and data manipulation sessions by a simple single action dragging interface. A User can drag a file or a folder of files from his PC desktop into the shared space and it will open with a viewer of the corresponding data type. Additionally these objects can be activated from a storage location on a distributed computing system shown in subsequent examples .

The shared space contains images or videos representing Users participating in a data sharing and data manipulation session in a shared space . The Users are sharing a Word document which is visible to all session participants from the viewer in the shared space. As always this document is synchronized between the participants of the session.

User wants to save a copy of this shared document to his own PC desktop for reference. He clicks the document header and then drags it from the shared space onto his PC desktop shown with .

While the shared document remains available to the session participants in the viewer User will have saved a local copy of the file on his own computer desktop.

A user accesses a Windows desktop . A User participating in a collaborative session has Adobe Photoshop running on his local personal computer which is represented on the local taskbar by an icon . The active C space session is also represented by an icon on the taskbar.

To begin sharing the local Photoshop application among other C space session User selects the C Space icon in the taskbar and drags it into shared C Space session . A visual representation of the Photoshop application opens immediately within the shared space where all session participants can see the open Photoshop application. Each user will be able to manipulate and control the open application in synchronized real time. In this way they can collaborate using the open application for example running a tutorial collaborating on a design project or otherwise collaborating using the application.

User drags an object into the shared space shown as dragging path . The application begins to run in an application viewer .

On computer desktop one of the Users has an application running such as an Adobe Photoshop file . User also has a C Space collaborative session running.

User selects the Photoshop application and drags it illustrated by into the C Space session . User continues to have the application running locally. In addition a visual representation of the Photoshop application is visible to all session participants and the application is fully operational and constantly synchronized among all the participants.

A C Space is running with Users participating in a collaborative session using C Space . One of the users wants to start a data manipulation session which would utilize an application running in a distributed computer system and activates an application repository user interface control . This control includes all of the applications which are working in a distributed application system which is used by the C Space interface.

The applications shown here are represented as and can include a visual representation of the application as well as textual descriptions. The application repository control can have a search element that allows session participants to search all of the available applications running in the distributed computing system.

To share an application running on a distributed computing system the User clicks the application icon on their local desktop and drags it into shared space the dragging path is shown as . As the application is dragged into the shared space the application activates and begins the data manipulation session in which Users are participating. The view inside the application shared space is synchronized among all the collaborative session participants. The application is working in a distributed computing system rather than locally. Though some resources may run locally on session participants local computers a significant portion of resources run on the distributed computing system.

One way to access an application which is running on a distributed computing system is via a unique resource locator a URL which can be used to access an application via a browser in many applications that support access thru the Internet and web browsers. It can be used to access them as a web service using send protocols.

The application can be shared in a collaborative session in which Users are collaborating by dragging URL from a local web browser into collaborative shared space . The dragging path is illustrated in . Once the URL is dragged in to the collaborative space if C Space recognizes and is able to work within the application s standard protocols the URL link expands into an application running within the collaborative session. All users see a synchronized view of this application and they can work with and manipulate data within this application.

Icons in the shared space are shared among all the participants of the shared session all the participants see how icons are arranged in the shared space can move them around can change display size and can activate them. Objects or applications are activated when a session participant clicks on the icon in the shared space. A viewer for the appropriate data object opens represented here as .

Users can delete data objects from the shared space by right clicking on icons representing these objects in shared space and selecting Remove option from the context menu. Users can also move them around within the shared space and can move them in and out of the shared space . Copy on desktop icon remains in shared space . User can access data files stored in the storage subsystem of the distributed computing system in a data sharing session through C Space interface.

The shared space presents remote files and data as if they were on the User s local machine. A shared space has an application running inside of it. The application may access data stored in the distributed computing system which the shared space allows it to do seamlessly.

An area exists where a User chooses files they want to manipulate. In this case the files are data objects. illustrate files or objects located in a remote distributed computing system.

Another way for Users to access and manipulate data files stored in a remote distributed computing system while in a C Space shared session is to use the flip button . Clicking it makes the C Space appear to flip and shows the file structure of stored objects and files Word documents Excel spreadsheets PowerPoint presentations images movies etc within the C Space s cloud storage system. Not only can Users can navigate this file storage system as with any standard file storage structure but its use is full incorporated into the data sharing and data manipulation functionality of the C Space.

Users can use a search field to find a specific object stored in the cloud storage system. Objects can be activated to add to a data sharing and data manipulation session in progress by right clicking the object and selecting from the menu. Once activated within the session all participants can synchronously see edit and otherwise manipulate the file.

A shared space has an application running. On the left the client running on a shared space User s PC is shown. On the right is a diagram of the cloud a distributed computing system with multiple processing units which can be actually separate computers which can be hosted in a data center networked talking to each other and or having attached storage . 

There are also a number of important components that are crucial in synchronizing the UI to the distributed computing system 

There is also a range of virtual devices and applications that can be running in the distributed computing system. The distributed computing system interprets these as natural devices such as input devices like a mouse keyboard or microphone or output devices monitor speakers mainly graphical and sound output. 

Data Transfer Encoding Compression Layers make communication between the distributed computing system and the client using it more efficient more secure and generally operating very well.

The Client has a shared space is a paradigm of operation in applications using the distributed computing system The applications can be launched and activated. Data objects can be started which can be utilized. The client UI for data manipulation and data synchronization has the following capabilities according to one embodiment 

Synchronization layer consists of the four components that enable the synchronization of the several user interfaces working around the same data objects or the same application. The four components are as follow 

Step 1 A user is engaged in a data sharing and data manipulation session with aim to share Word document data object . User initiates sharing of a data object by dragging it into the shared space . A viewer for the appropriate data object is activated in this case a viewer for Word documents.

Step 2 The moment it is activated an event system of the client computer of a user participating in the data sharing and manipulation session sends an event to the event synchronization server that the new data object is being shared. The event synchronization server requests the list of session participants from the session component in the distributed computing system and the session component discovers that two participants are working with the user in collaborative session . The events that the data is being shared with them are sent to the participants of the sharing session by event synchronization server. Upon receiving events clients start displaying animation to notify the users that synchronization is starting.

Step 3 The data synchronization components on the clients start exchanging messages and event between each other and the data synchronization server according to data synchronization protocol. The data object itself is split into chunks and are synchronized chunk by chunk. Immediately without waiting for the entire file to be uploaded into the distributed computing system the parts of the file or data object that arrive in the distributed computing system are synchronized with the data synchronization component to participants shown by path .

At the same time all the copies of these bits of data are stored in the distributed computing system s storage area. A local copy of the data is stored seamlessly and transparently at the event of sharing. De duplication system is in place which makes sure no two copies of identical files are stored in the storage system.

Step 4 When all the bits of data that have been transferred to the participants of the data sharing session the participants tell the event synchronization server that the synchronization has been completed. Upon receiving all of these events the server sends out confirmation events and the clients make the data object available for manipulation sharing and collaboration for the users.

A distributed computing system has all of the computing units and timed synchronization component timed synchronization server and has an application running in a distributed computing system . This application has been launched and is actually working for the user interface for data manipulation and data sharing which was initiated by the client. This application is working through the cloud.

The application working in a distributed computing system is receiving its input like mouse movement or keyboard strokes from a virtual input layer which in fact receives those commands from the C Space User interface over the network. The application outputs graphics to a virtual graphic device. That output which represents a set of commands such as triangles or low level graphic primitives is captured by the system and encoded and compressed to minimize traffic. It is transmitted over network to client where it is decompressed decoded and put to the virtual output device.

Before that timestamp of the frames of the graphic output are compared. The time is always synchronized among all of the participants of the collaboration session. The synchronization is tight resulting in each session participant s viewing and or hearing the same thing. It is synchronized by an algorithm which is referenced in our previous patent.

Consider a frame of graphics data to be displayed on a client computer being received in the moment of time T and let s assume that the frame is time stamped T Prime . If T Prime is less than T by significant amount T which varies by application according to its latency requirements the frame is discarded. Whichever user has the fastest computer receives the best picture the best output. A user with a slower computer or connection experiences skipped frames in order to keep them at the same level of synchronization at the same frame of the graphical output.

This graphical output is decompressed decoded. A frame can be cut or dropped if it is out of time but it can also remain there. Everything else goes to the virtual output device which actually redirects the output to the hardware output device which can be the screen of a mobile phone a plasma TV connected to a home entertainment center or a laptop display.

Users A B C are participating in a data sharing and manipulation session by using C Space interface. They have shared spaces open respectively. All the C Space clients in the session in question are running the same application App. Different instances of the applications are represented as App App and App running inside application viewer plug ins .

Distributed computing system is running the following components used in this client synching session according to one embodiment 

Each of C Space User Interface clients have the following 3 components involved in the synchronization process according to one embodiment 

Time synchronization server and time synchronization components implement algorithm and protocol for precise continuous time synchronization among multiple participants in a communication session described in sections 0041 0076 of the previously filed patent application 2008 0181260 A1 Method and system for precise synchronization of audio and video streams during a distributed communication session with multiple participants . The implementation of these methods introduces a common time system which is synchronized to the order of milliseconds or tens of milliseconds.

The synchronization occurs by exchanging time stamped events encoded in messages which also carry payload data between clients and distributed computing system. A sample seven step sequence of exchange is illustrated in the figure and described below.

Step 1. An event that needs to be synchronized e.g. a mouse click or a drag in of a data object into C Space session is generated by Event Synchronization Client Component . It contains a timestamp provided by Time Synchronization Client Component on Step 1a synchronization state all variables etc. and payload data object supplied by Data Synchronization Client Component i.e. a chunk of a file that is being synchronized .

Step 2. Event Synchronization Server places a request to Session Management Server Component to get all the participants of the data sharing and manipulation session unless it has the list cached in its memory stack.

Step 3 Session Management Component returns the addresses of the users and request Time Synchronization Server to put a timestamp on the event.

Step 4. Notification events time stamped by Time Synchronization server are sent out to clients and are processed by their event synchronization components.

Step 5 Payload data objects are sent as separate messages with timestamps and synchronization state associated with the initial event that was generated.

Step 6 Event synchronization Client Component on the cloud discards event and modifications that originated by time T earlier before the actual arrival because that data may become irrelevant. Constant T varies per application. All events that arrive within a given timeframe un discarded state and payload data are applied and mixed .

Step 7 The modified state content and payload data is sent back to the event and data synchronization servers with their timestamp and the process completes the loop of perpetual synchronization.

Synchronization of live data audio and video streams during a data manipulation session can be accomplished through any suitable mechanism. One example technique is described in U.S. Published Patent Application No. 2008 0181260 A1 entitled Method and system for precise synchronization of audio and video streams during a distributed communication session with multiple participants the contents of which are incorporated herein by reference.

A method and system for distributed computing interface are disclosed. It is understood that the embodiments described herein are for the purpose of elucidation and should not be considered limiting the subject matter of the present embodiments. Various modifications uses substitutions recombinations improvements methods of productions without departing from the scope or spirit of the present invention would be evident to a person skilled in the art.

