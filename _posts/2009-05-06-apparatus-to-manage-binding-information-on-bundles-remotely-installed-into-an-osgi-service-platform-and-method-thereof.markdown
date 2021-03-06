---

title: Apparatus to manage binding information on bundles remotely installed into an OSGi service platform and method thereof
abstract: An apparatus to generate and manage binding information that is used to map a bundle remotely installed into an open service gateway initiative (OSGi) framework, to at least one controller device that is interested in a change of a life cycle of the bundle, by using a controlled device, in which an OSGi service platform is installed.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08375110&OS=08375110&RS=08375110
owner: Samsung Electronics Co., Ltd.
number: 08375110
owner_city: Suwon-si
owner_country: KR
publication_date: 20090506
---
This application claims the benefit of U.S. Provisional Application No. 61 051 139 filed on May 7 2008 and Korean Patent Application No. 10 2008 0081071 filed on Aug. 19 2008 in the Korean Intellectual Property Office the disclosures of which are incorporated herein in their entirety by reference.

The following description relates to an open service gateway initiative OSGi and more particularly to a method of managing a bundle that is remotely installed by a controller device by using an OSGi based controlled device.

With the development of various communication devices a first communication device may perform a function by cooperating with a plurality of other communication devices via a network so that the original functionality of the first communication device can be extended. Open service gateway initiative OSGi may be used to provide such an execution environment.

OSGi is a standard related to technology for dynamically installing new services into a network device and for executing the services. Controller devices that belong to a network may remotely install bundles in a controlled device in which an OSGi service platform is installed and may use services provided by the bundles.

Bundles are basic units which perform distribution and management in a network include at least one OSGi service and are managed by an OSGi framework. In other words the OSGi framework provides a standardized execution environment for various applications bundles . The general concept of OSGi is well known to one of ordinary skill in the art and is described in various OSGi release documents. However current OSGi technology does not provide a mechanism to map bundles that are remotely installed into an OSGi service platform to controller devices in which bundles are installed and to manage the bundles and the controller device.

One general aspect includes an apparatus to manage a bundle that is remotely installed via a network by using an open service gateway initiative OSGi based controlled device and a method thereof.

According to another general aspect there is provided a method of managing a bundle that is remotely installed by a controller device the method executed by an open service gateway initiative OSGi based controlled device the method including in response to a service event indicating that a predetermined service that is provided by the bundle is registered in an OSGi service registry occurring generating binding information that is used to map the bundle to the controller device by using the service and notifying an event on a change of a life cycle of the bundle to the controller device by using the generated binding information.

The generating of the binding information may include adding an identifier of the controller device to a bundle property of the bundle by using the service.

The method may further include in response to uninstallation of the bundle being requested by the controller device storing the identifier in a region which is not deleted even though the bundle is uninstalled wherein the notifying of the event comprises in response to a bundle event indicating that the bundle has been uninstalled occurring notifying the bundle event to the controller device by referring to the stored identifier.

The method may further include in response to an event unsubscription request on the bundle being received from the controller device deleting the identifier from the bundle property by using the service.

The method may further include in response to detecting that the controller device is disconnected from the network retrieving bundles comprising the identifier in the bundle property among bundles of the OSGi framework and deleting the identifier from bundle properties of the retrieved bundles by using predetermined services that are provided by the retrieved bundles.

The generating of the binding information may include in response to an identifier of other controller devices being included in an action invocation message or an event subscription request message received from the controller device together with the identifier of the controller device adding the identifiers to the bundle property by using the service.

According to yet another general aspect there is provided an apparatus to manage a bundle that is remotely installed by a controller device wherein the apparatus is an open service gateway initiative OSGi based controlled device including a binding information management unit generating binding information that is used to map the bundle to the controller device by using a predetermined service in response to a service event indicating that the service that is provided by the bundle is registered in an OSGi service registry occurring and an event notification unit notifying an event on a change of a life cycle of the bundle to the controller device by using the generated binding information.

The binding information management unit may add an identifier of the controller device to a bundle property of the bundle by using the service.

The apparatus may further include a binding information backup unit to store the identifier in a region which is not deleted even though the bundle is uninstalled in response to uninstallation of the bundle being requested by the controller device wherein the event notification unit notifies the bundle event to the controller device by referring to the stored identifier in response to a bundle event indicating that the bundle has been uninstalled occurring.

The binding information management unit may delete the identifier from the bundle property by using the service in response to an event unsubscription request on the bundle being received from the controller device.

The apparatus may further include a retrieval unit to retrieve the bundle including the identifier in the bundle property among bundles of the OSGi framework in response to detecting that the controller device is disconnected from the network wherein the binding information management unit deletes the identifier from bundle properties of the retrieved bundles by using predetermined services that are provided by the retrieved bundles.

The binding information management unit may the identifiers to the bundle property by using the service in response to an identifier of other controller devices being included in an action invocation message or an event subscription request message received from the controller device together with the identifier of the controller device.

According to still another general aspect there is provided a computer readable recording medium having recorded thereon a program to perform a bundle management method executed by an open service gateway initiative OSGi based controlled device including instructions to cause a computer to in response to a service event indicating that a predetermined service that is provided by the bundle is registered in an OSGi service registry occurring generate binding information that is used to map the bundle to the controller device by using the service and notify an event on a change of a life cycle of the bundle to the controller device by using the generated binding information.

Other features and aspects will be apparent from the following detailed description the drawings and the claims.

Throughout the drawings and the detailed description unless otherwise described the same drawing reference numerals will be understood to refer to the same elements features and structures. The relative size and depiction of these elements may be exaggerated for clarity illustration and convenience.

The following detailed description is provided to assist the reader in gaining a comprehensive understanding of the methods apparatuses and or systems described herein. Accordingly various changes modifications and equivalents of the systems apparatuses and or methods described herein will be suggested to those of ordinary skill in the art. Also descriptions of well known functions and constructions may be omitted for increased clarity and conciseness.

Often the controller device that is interested in the bundle may be a controller device in which the bundle is installed. However other controller devices may need to be notified of a change of a state of the bundle. Thus a plurality of controller devices may be mapped to one bundle according to a user s determination.

As illustrated in the controller device installs a bundle into an OSGi framework of a controlled device remotely via a network .

A device binding service DBS among services provided by the started bundle is registered in an OSGi service registry . DBS is a name of a service that is newly suggested in the current embodiment and manages binding information of the bundle installed into the OSGi framework.

In other words according to an example embodiment it is assumed that all bundles that are installed into a controlled device by using a controller device include a DBS for managing binding information of a bundle. Thus when the bundle remotely installed into the controlled device starts the DBS of the bundle is registered in the OSGi service registry. For the convenience of explanation and without limiting thereto hereinafter all bundles may be referred to as remotely installed bundles.

Referring again to binding information is generated by using the DBS . In other words the DBS that is registered in the OSGi service registry of the controlled device provides an application programming interface API to generate binding information. The generation of the binding information may include adding an identifier of the controller device that has installed the bundle in a bundle property by using the API of the DBS.

The bundle property is a file that stores various information pertaining to the bundle. Where an identifier of the controller device is included in the bundle property the controller device that has installed the bundle may be identified. As such the identifier of the controller device included in the bundle property of a specific bundle may be binding information that is obtained by mapping the bundle to the controller device corresponding to the identifier.

Hereinafter it is assumed that the identifier of the controller device included in the bundle property is binding information. However the binding information may be in various formats in which the bundle and the controller device are mapped to each other. Also binding information may be stored in regions other than the bundle property.

Referring to it is assumed that the binding information is generated when the bundle starts. However the binding information may be generated in other operations according to implementation examples. For example where a control protocol between the controller device and the controlled device is universal plug and play UPnP in response to the controlled device receiving a UPnP control message or a UPnP event subscription request message that requests a specific action the binding information may be generated.

Where an identifier of another controller device is included in an action invocation message or an event subscription request message the controlled device generates binding information that is obtained by mapping two controller devices to one bundle. For example two identifiers may be added to a bundle property of a bundle. A number of controller devices that are mapped to one bundle may be two or more.

An identifier of a controller device may be a universal resource identifier URI of the controller device.

A bundle event that indicates the bundle stops occurs . An OSGi framework notifies a bundle event to an event listener whenever a life cycle of the bundle changes.

The controlled device extracts an identifier of the controller device that has installed the bundle remotely from a bundle property of the stopped bundle .

The controlled device notifies of the bundle event to the controller device by referring to the extracted identifier .

Accordingly an OSGi based controlled device manages binding information that is obtained by mapping a bundle installed into the OSGi framework to an identifier of a controller device that is interested in the bundle thereby determining to which controller device a bundle event will be notified.

A controlled device receives an event unsubscription request on a specific bundle from a controller device .

The controlled device deletes an identifier of the controller device from a bundle registry of a bundle by using a DBS of the bundle .

The controlled device extracts an identifier of the controller device from a bundle property of a bundle requested to be uninstalled .

The controlled device stores the extracted identifier in a region which is not deleted even though the bundle is uninstalled . This procedure is performed to back up the identifier of the controller device before the bundle is uninstalled. Since the bundle property cannot be referred to after the bundle is uninstalled the identifier of the controller device may be backed up before the bundle is uninstalled. If the identifier of the controller device is not backed up before the bundle is uninstalled it is difficult to determine which controller device to notify.

The controlled device notifies of the bundle event to the controller device by referring to the identifier of the stored controller device .

While depicts the operations performed where the controller device leaves the network normally depicts operations where the controller device is abnormally terminated by not making an event unsubscription request.

Referring to the controlled device detects that the controller device is disconnected from the network .

The controlled device retrieves bundles that include an identifier of the controller device in a bundle property among bundles installed into an OSGi framework .

The controlled device deletes the identifier of the controller device from bundle properties of the retrieved bundles by using device binding services DBSs of the retrieved bundles .

Accordingly in response to the controller device leaving the network the controlled device deletes binding information related to the controller device and thus does not need to transmit an event message where an event related to a life cycle of the bundle occurs.

Referring to the controlled device includes an OSGi framework a binding information management unit an event notification unit a binding information backup unit a retrieval unit and a network interface module .

The OSGi framework is known to one of ordinary skill in the art has been described in an OSGi standard document and thus a description thereof will not be repeated.

The network interface module processes a control protocol between a controller device and the controlled device . For example a UPnP may be used as the control protocol between the controller device and the controlled device.

The binding information management unit generates binding information by using a DBS when a service event indicating that a DBS of a remotely installed bundle has been registered in an OSGi service registry occurs.

As described above the binding information may be generated when another action invocation message other than an action invocation message requesting start of the bundle or an event subscription request message is received from the controller device. The binding information may be implemented as an identifier included in a bundle property and a plurality of controller devices may be mapped to one bundle.

In addition the binding information management unit deletes binding information related to the controller device by using a DBS of the bundle where the event unsubscription request on the bundle installed into the OSGi framework is received from the controller device or the controller device is disconnected from the network.

The event notification unit notifies a bundle event i.e. an event related to a change of a life cycle of the bundle to the controller device by using the binding information.

In response to the controller device requesting uninstallation of the bundle the binding information backup unit backs up the binding information in a safe place before the bundle event on uninstallation of the bundle occurs. For example where the binding information is implemented by adding a URI of the controller device to the bundle property if the bundle is completely uninstalled the bundle property cannot be referred to and thus it cannot be determined which controller device to notify. Thus the binding information backup unit stores the URI of the controller device in a region which is not deleted even though the bundle is uninstalled before the bundle is completely uninstalled.

The retrieval unit retrieves the binding information corresponding to the controller device in response to detecting that the controller device is disconnected from the network. For example a bundle property including the URI of the controller device that leaves the network is selected from bundle properties of bundles installed into the OSGi framework . The binding information management unit deletes the URI of the controller device which is included in the selected bundle property.

A controller device invokes an action of a device control protocol DCP module and requests a start of a bundle .

The DCP module provides a service of the bundle installed into an OSGi framework to the controller device based on a protocol between the controller device and a controlled device invokes an API of the OSGi framework according to the action invocation of the controller device and returns the result of the invocation to the controller device . Thus the DCP module functions as a gateway between an OSGi service platform of the controlled device and the controller device .

The DCP module may be implemented as a bundle or a native application that is outside the OSGi service platform.

When the bundle starts the bundle registers a DBS in an OSGi service registry of the OSGi framework .

The OSGi framework notifies a service event indicating that the DBS has been registered to the DCP module .

The DCP module requests the DBS to generate binding information by using an URI which is an identifier of the controller device by invoking the API of the DBS . Here the API is referred to as AddDeviceEntry .

As a result of the updating of the bundle property in the URI is added to the bundle property . In other words binding information that is used to map the bundle and the controller device is generated.

The OSGi framework returns the result of invoking of the API which is performed in to the DCP module .

The DCP module transmits a response message to the action invocation that is performed in to the controller device .

The controller device requests start of the bundle by invocating an action of the DCP module . In this case a URI is included in an action invocation message. In other words a different identifier from the URI which is an identifier of the controller device is included in the action invocation message.

Referring to through are the same as operations through of and thus a description thereof will not be repeated.

The DCP module requests to generate binding information by using the URI which is an identifier of the controller device by invoking an API AddDeviceEntry of the DBS .

The DCP module requests to generate binding information by using the URI which is an identifier of another controller device by invoking the API AddDeviceEntry of the DBS .

As a result of the updating in the URI and the URI are added to the bundle property . In other words binding information that is used to map the bundle and two controller devices is generated.

The DCP module transmits a response message to the action invocation that is performed in to the controller device .

The controller device invokes an action to stop the bundle among actions provided by the DCP module .

The bundle requests the OSGi framework to unsubscribe services that are registered by the bundle in an OSGi service registry before the bundle is stopped .

The OSGi framework notifies a service event indicating that the services of the bundle are unsubscribed from the OSGi service registry to the DCP module .

The OSGi framework returns the result of invoking the API which is performed in operation to the DCP module .

The DCP module transmits a response message to the action invocation that is performed in operation to the controller device .

The OSGi framework notifies a bundle event indicating that the bundle has stopped to the DCP module which is an event listener .

The DCP module extracts an URI of the controller device from a bundle property of the stopped bundle .

The DCP module notifies the bundle event indicating that the bundle has stopped to the controller device by referring to the extracted URI of the controller device .

Referring to the bundle stops due to a request of the controller device . However the bundle may be stopped due to the OSGi framework as when a dependency failure occurs. Nevertheless operations after through will be performed in the same manner regardless of the manner in which the bundle stops.

The controller device requests uninstallation of an active bundle by invoking an action of the DCP module .

The bundle requests the OSGi framework to unsubscribe services that are registered by the bundle in the OSGi service registry before the bundle is stopped .

The OSGi framework notifies a service event indicating that services of the bundle have been unsubscribed from the OSGi service registry to the DCP module .

The OSGi framework notifies a bundle event indicating that the bundle has stopped to the DCP module .

The DCP module stores the URI of the controller device in a region which is not deleted even though the bundle is uninstalled .

In order to notify the bundle event indicating that the bundle has been uninstalled the URI of the controller device that is interested in the bundle may be referred to. Where binding information is included in the bundle property in response to the bundle uninstalled the DCP module may not access the bundle property any more. Thus the URI of the controller device needs to be backed up in a safe place in advance before the bundle is uninstalled.

The DCP module notifies the bundle event indicating that the bundle has stopped to the controller device .

The OSGi framework returns the result of invoking the API which is performed in operation to the DCP module .

The DCP module transmits a response message to the action invocation that is performed in operation to the controller device .

The OSGi framework notifies the bundle event indicating that the bundle has been uninstalled to the DCP module which is an event listener .

The DCP module notifies the bundle event indicating that the bundle has been uninstalled to the device controller by referring to the URI of the controller device that is backed up in .

The controller device transmits its own URI to the DCP module and requests unsubscription of an event on a change of a life cycle of the bundle .

The DCP module invokes DeleteDeviceEntry which is an API that is used to delete binding information among a plurality of APis of the DBS . In this case the URI of the controller device is transmitted to the DBS .

The DBS updates a bundle property of a bundle in which the controller device is no longer interested .

As a result of the above updating the URI of the controller device is deleted from a bundle property . Thus the bundle event indicating a change of a life cycle of the bundle will no longer be notified to the controller device .

The DCP module that detects that the controller device is disconnected from the network collects binding information of all bundles installed into an OSGi framework . In other words URIs included in bundle properties of the bundles are collected.

The DCP module checks a URI of the controller device that is disconnected from the network among the collected URIs .

The DCP module requests DBSs on each of bundles that include the URI of the controller device disconnected from the network in the bundle property to delete the URI of the controller device . Accordingly DeleteDeviceEntry of the DBSs are invoked and the URI of the controller device is transmitted.

The methods described above including a binding information management method may be recorded stored or fixed in one or more computer readable media that includes program instructions to be implemented by a computer to cause a processor to execute or perform the program instructions. The media may also include alone or in combination with the program instructions data files data structures and the like. The media and program instructions may be those specially designed and constructed or they may be of the kind well known and available to those having skill in the computer software arts. Examples of computer readable media include magnetic media such as hard disks floppy disks and magnetic tape optical media such as CD ROM disks and DVDs magneto optical media such as optical disks and hardware devices that are specially configured to store and perform program instructions such as read only memory ROM random access memory RAM flash memory and the like. Examples of program instructions include both machine code such as produced by a compiler and files containing higher level code that may be executed by the computer using an interpreter. The described hardware devices may be configured to act as one or more software modules in order to perform the operations and methods described above or vice versa.

According to certain embodiments described above when a controller device is abnormally terminated a controlled device deletes binding information related to the controller device automatically so that unnecessary transmission of an event message can be prevented.

Also a controlled device in which an OSGi service platform is installed may identify controller devices to notify changes of life cycles of bundles installed into an OSGi framework by using binding information.

A number of example embodiments have been described above. Nevertheless it will be understood that various modifications may be made. For example suitable results may be achieved if the described techniques are performed in a different order and or if components in a described system architecture device or circuit are combined in a different manner and or replaced or supplemented by other components or their equivalents. Accordingly other implementations are within the scope of the following claims.

