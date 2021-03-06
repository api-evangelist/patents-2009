---

title: Information processing device, data processing method, and program
abstract: An information processing device includes: a local memory unit for storing data including an encrypted content; a memory for storing data including key information used to reproduce the encrypted content; and a data processing unit performing a process of writing data to the local memory unit and the memory, and a process of reproducing the encrypted content, wherein the data processing unit performs a process of writing encrypted content downloaded from a server or encrypted content copied from a medium to the local memory unit, and performs a process of decoding the encrypted content or a validity authenticating process using the data stored in the local memory unit and the data stored in the memory when reproducing the encrypted content written to the local memory unit.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08549620&OS=08549620&RS=08549620
owner: Sony Corporation
number: 08549620
owner_city: Tokyo
owner_country: JP
publication_date: 20090819
---
The invention relates to an information processing device a data processing method and a program and more particularly to an information processing device a data processing method and a program which are configured to perform a content writing process or a content copying process on a recording medium.

DVD Digital Versatile Disc Blu ray Disc registered trademark and the like are often used as recording mediums for various content such as music and movies. These information recording mediums having data recorded thereon include mediums ROM type not permitting the writing of new data thereto and mediums R type RE type and the like permitting the writing of data thereto. By using the data writable information recording mediums it is possible to copy or move content recorded in other mediums. For example it is also possible to download and record content for example through a network or by the use of devices installed in public locations.

In addition to the DVD and the Blu ray Disc registered trademark hard disks and flash memories are used as the recording mediums on which content is recorded.

 a a process of copying or moving content from a medium for example a ROM disk having the content recorded thereon to another medium 

 c a process of recording content by the use of a terminal located in a public space such as a front of a store.

However the copyright the distribution right and the like of various types of content such as music data and image data are possessed by the authors or sellers thereof. Therefore when content is provided to users predetermined usage restriction is generally taken that is the usage of the content is permitted to only a user having the regular right of usage and unauthorized copying is not permitted.

For example AACS Advanced Access Content System is known as a standard for usage restriction of content. In the AACS standard when a content is copied between the mediums like a this copy process is based on the premise that copy permission information should be acquired from a management server. That is the copy process is permitted under predetermined management. This copy process is called managed copy MC .

The content providing process of b that is the download type content providing process is called EST Electric Sell Through . The content providing process of c using public terminals is called MoD Manufacturing on Demand The AACS standard requires these processes to be performed in accordance with a predetermined rule.

For example as shown in a of the managed copy MC is a process of allowing a user to set an information recording medium disk having a content recorded thereon to an information processing device performing a data recording and reproducing process and copying the content read from the information recording medium disk to for example a data writable R RE type disk such as an R type or RE type or a second information recording medium such as a hard disk or a flash memory.

At the time of performing this content copying process it is necessary that the data recording and reproducing device accesses a management server via a network and obtains the permission to content copy from the management server .

A configuration for performing the content copying process between plural mediums by the use of a single information processing device that is only one device is shown in but two devices of a device having a medium as a copy source attached thereto and another device having a medium as a copy destination attached thereto may be connected to each other with for example a USB cable or the like.

The process of downloading content from a server and recording the content on an information recording medium is called EST Electric Sell Through . As shown in b of the EST is a process of fitting a user s medium for example a data writable R or RE type disk into an information processing device such as a PC possessed by the user and receiving and recording a content from a content server EST server through a network .

The content providing process using a public terminal is called MoD Manufacturing on Demand . As shown in c of the MoD is performed when a user intends to record content on a medium using a content server as a terminal installed in public spaces such as convenience stores or stations. The MoD is a process of allowing the user to set the user s data writable medium such as an R or RE type disk into the content server MoD server as the terminal of a convenience store and recording desired content on the disk according to the operation by the user such as selection of content.

In this way users can record content on data writable mediums and utilize reproduce and the like the recorded content. However for example when the content is to be protected by copyright it is necessary to control the usage of content to prevent unauthorized usage.

As described above the AACS Advanced Access Content System is known as a standard for the content copyright protection techniques. In the AACS standard usage control information usage rule corresponding to content is defined and the content is used in accordance with the usage control information usage rule . In addition strict usage control is realized by dividing content into units preparing encrypted content using unit keys corresponding to the units and allowing only a specific user to acquire the unit keys.

When the disk having content recorded thereon is a medium such as a ROM type disk permitting only reproduction and not permitting the writing of new data additional writing or editing of new content is not performed on the medium. Therefore it is possible to provide users with the content specific control information usage rule or unit keys corresponding to the content recorded on the medium in a state where the usage rule or unit keys are recorded on the medium.

However in an example where content is recorded on a data writable R or RE type medium such as a disk a hard disk and a flash memory and used the content recorded on the medium is not fixed but can be subjected to the data updates such as the recording of new content or the deleting of recorded content. The usage rule or the unit keys need to be updated with content stored in the medium.

In this way when a user records content on a medium it is necessary to perform various complex processes such as recording various accessory data corresponding to the recorded content as well as recording the content.

Particularly the key information and the like needs to be prevented from leaking and various ID information and content management data are data that is not to be falsified. When the leakage of the key information or various ID information and the content management data is falsified the possibility of non permitted usage of contents increases.

It is desirable to provide an information processing device a data processing method and a program which are configured to safely write and use data such as key data or ID information that is not to be leaked or falsified when storing content downloaded from a server or content copied from another medium in a local memory unit.

According to a first embodiment of the invention there is provided an information processing device including a local memory unit storing data including encrypted content a memory storing data including key information used to reproduce the encrypted content and a data processing unit performing a process of writing data to the local memory unit and the memory and a process of reproducing the encrypted content. Here the data processing unit performs a process of writing encrypted content downloaded from a server or encrypted content copied from a medium to the local memory unit and performs a process of decoding the encrypted content or a validity authenticating process using the data stored in the local memory unit and the data stored in the memory when reproducing the encrypted content written to the local memory unit.

In the information processing device according to the embodiment of the invention the data processing unit may transmit the information processing device specific data stored in the memory to the server receive server authentication information in which the transmitted data is signed with a secret key of the server and store the received server authentication information in the local memory unit.

In the information processing device according to the embodiment of the invention the data processing unit may perform a process of acquiring key information using a device specific device key set stored in the memory on a key block stored in the local memory unit when reproducing the encrypted content written to the local memory unit.

In the information processing device according to the embodiment of the invention the data processing unit may perform a process of downloading content from the server as well as performing a process of acquiring a volume unique key correlated with the downloaded content and content management data and storing the acquired data in the memory.

In the information processing device according to the embodiment of the invention the data processing unit may store the volume unique key in the memory as data corresponding to a title of the content.

In the information processing device according to the embodiment of the invention the data processing unit may store the content management data in the memory as data corresponding to a title of the content a volume ID correlated with the content a medium ID specific to a content storing disk and a falsification verification code.

In the information processing device according to the embodiment of the invention the data processing unit may perform a process of reading a volume ID correlated with the content stored in the medium and a medium ID specific to a content storing disk and writing the data to the memory when performing the process of copying and writing the encrypted content stored in the medium to the local memory unit.

In the information processing device according to the embodiment of the invention the data processing unit may perform a process of acquiring key information using a device key set which is stored in the memory specific to the information processing device on a key block stored in the medium and perform a process of writing the acquired key information to the memory when performing the process of copying and writing the encrypted content stored in the medium to the local memory unit.

In the information processing device according to the embodiment of the invention the data processing unit may perform a process of transmitting information processing device specific data stored in the memory to the server receiving server authentication information in which the transmitted data is signed with a secret key of the server and storing the received server authentication information in the local memory unit and perform a process of acquiring a content certificate for authenticating the validity of the copied content from the server and storing the acquired content certificate in the local memory unit when performing the process of copying and writing the encrypted content stored in the medium to the local memory unit.

According to a second embodiment of the invention there is provided a data processing method performed by an information processing device including the steps of allowing a data processing unit to perform a process of writing encrypted content downloaded from a server or encrypted content copied from a medium to a local memory unit and allowing the data processing unit to perform a process of transmitting information processing device specific data stored in memory other than the local memory unit to the server receiving server authentication information in which the transmitted data is signed with a secret key of the server and storing the received server authentication information in the local memory unit.

According to a third embodiment of the invention there is provided a program for processing data in an information processing device including allowing a data processing unit to perform a process of writing encrypted content downloaded from a server or encrypted content copied from a medium to a local memory unit and allowing the data processing unit to perform a process of transmitting information processing device specific data stored in memory other than the local memory unit to the server receiving server authentication information in which the transmitted data is signed with a secret key of the server and storing the received server authentication information in the local memory unit.

The program according to the embodiment of the invention is a computer program which can be provided to a general purpose computer system executing various program codes by a recording medium or a communication medium in a computer readable manner. By providing the program in the computer readable manner processes corresponding to the program are carried out by the computer system.

Other advantages features and effects of the invention will become apparent by the following detailed description based on specific embodiments of the invention or the accompanying drawings. A system referred to in this specification means a logical set of plural devices and is not limited to a configuration in which the devices are disposed in the same chassis.

According to the above mentioned embodiments of the invention in the configuration for storing content downloaded from a server or content copied from a medium in a local memory unit it is possible to safely store key data with high secrecy in memory other than the local memory unit. Accordingly for example even when data stored in the local memory unit is copied and leaks out it is possible to prevent the non permitted usage of the contents by preventing the data stored in the memory from being leaked out. In addition the device specific ID information and the like stored in the memory is transmitted to the server and the server authentication data is received and stored in the local memory unit. Accordingly the correlation of the content stored in the local memory unit with the device is reliably carried out.

Hereinafter an information processing device a data processing method and a program according to an embodiment of the invention will be described in detail with reference to the drawings.

First a process example of the managed copy MC performed by an information processing device according to an embodiment of the invention will be described with reference to . As described above the managed copy MC is a process of copying content to another medium on the condition that copy permission information is received from a management server.

In a disk having content recorded thereon an information processing device reading the content from the disk and recording the read content to a data writable second recording medium a data writable second recording medium which is the copy destination of the content and a management server providing permission information for the content copying process or management data are shown from the left side.

The data writable second recording medium as the copy destination of the content is a recording medium such as a hard disk a R RE disk and a flash memory.

The information processing device is constructed for example by a PC a recording and reproducing device or the like and has a function of reading data from the disk and writing the read data to the second recording medium .

As shown in the drawing a BD J application which is a Java registered trademark application program a managed copy management file MCMF management data and an encrypted content are recorded in the disk .

The BD J application is a program which is executed by the information processing device at the time of performing a managed copy MC process and is used to perform for example a process of communication with the management server . The BD J application may be constructed by a single application program or a combination of plural BD J applications performing specific processes.

For example the plural BD J applications can include a BD J application making a communication with a server and a BD J application performing a charging process. At the time of copying content the plural BD J applications are executed by the information processing device .

The managed copy management file MCMF is a file used to perform a content copying process and is an XML described data file including the following information 

 a a content ID which is an identifier ID uniquely representing content recorded in the information recording medium disk 

 b URI URL which is information for accessing a management server giving permission to copy at the time of copying content and generating a token by a binding process for example information for accessing the management server and

 c directory name and file name which are information on names of a directory and a file in which data for permitting a copy process is recorded.

The management data is management data defined by an AACS Advanced Access Content System which is a standard management system for content copyright protecting techniques and includes a CPS unit key file including keys unit keys used to decode the encrypted content usage control information a content certificate CC representing the validity of the content and an MKB Media Key Block which is an encryption key block including key information medium key for acquiring the CPS unit keys.

The encrypted content is an encrypted content according to for example the AACS standard. For example the encrypted content includes an AV Audio Visual stream of moving image content such as HD High Definition movie content which is high definition moving image data music data a game program an image file voice data or text data.

The encrypted content is configured to control usage by for example content management units CPS units and is an encrypted content to which different unit keys CPS unit keys are applied by the content management units CPS units . Different keys CPS unit keys are assigned to the units respectively are encrypted and are stored.

The first data processing unit is a BD JVM BD J virtual machine . The BD JVM is set as a virtual machine which is a virtual hardware environment for executing the BD J application recorded in the disk .

The second data processing unit is an AACS layer . The AACS layer is set as a data processing unit for performing a data process according to the AACS standard such as a process of acquiring an ID recorded in the disk treatment of information with high security and data transformation in a content copying process.

In this way when a process of copying content recorded in the disk to another medium is performed the BD JVM as an execution area of the BD J application recorded in the disk and the AACS layer as an execution area of a program for performing the processes according to the AACS standard are established to transmit and receive process requests and process results therebetween.

In order to transmit and receive process requests and process results between the BD J application and the AACS layer an API Application Programming Interface is used. The API is a set of functions for performing various processes necessary for the content copying process. The API is recorded in the BD J application or other areas which can be read by the information processing device . A specific example of the API will be described in detail later.

The information processing device executes the BD J application in the BD JVM communicates with the management server and performs the process of acquiring the copy permission information and the like.

When the content stored in the disk is copied to a second recording medium it is necessary to transform the content or the usage control information usage rule depending on the medium as a copy destination. This process is performed in the program executing area AACS layer for performing the processes according to the AACS standard.

The BD J application is a program for executing processes necessary for the content copying process and is executed in the BD JVM of the information processing device . The following processes are performed as the processes employing the BD J application 

 e a process of acquiring copy permission information from the server a check process a process of outputting the copy permission information to a recording controller 

 f a process of monitoring the content copying process which is performed by the recording controller and

 g a process of monitoring a process of writing data downloaded from the server which is performed by the recording controller.

As described above the BD J application may be constructed by a single application program but may also be constructed by a combination of plural BD J applications performing specific processes. For example the processes of a to g may be performed by plural BD J applications.

The process of the BD J application will be described now with reference to . The BD J application is started in the BD JVM established in the information processing device in step S shown in .

At the time of performing the process a guide picture as a user interface such as a menu provided from the BD J application is displayed on the display of the information processing device . A series of processes for performing the content copying process managed copy is started by a user s instruction.

The BD J application first accesses the management server using the server URI included in the managed copy management file MCMF in accordance with the user s instruction. At this time a content ID corresponding to the content to be copied is transmitted to the management server .

In step S the management server generates a permitted process list which is list data of processes permitted for the content and transmits the generated permitted process list to the information processing device on the basis of the content ID received from the information processing device . For example the permitted process list is a list including information on whether the copying of the content is permitted and information on the fee of the copy process.

The information processing device receives the permitted process list from the management server and displays the permitted process list on the display in step S so as to allow a user to select a process to be performed.

When the user selects a process to be performed the information processing device performs a payment process by transmitting payment data to the management server . For example the user inputs the data necessary for the payment such as a credit card number to the payment picture and transmits the payment data. Then in step S the management server permits the process and transmits the copy permission information to the information processing device .

The information processing device sends the copy permission information received from the management server to the AACS layer . The AACS layer performs the process of step S and the processes subsequent thereto. The AACS layer performs a process of transforming the management data read from the disk into management data based on the medium type of the second recording medium such as a hard disk an R RE disk and a flash memory as a copy destination. For example a process of adding an encryption key unit key corresponding to the copied content or a process of transforming the usage control information the content certificate and the like to data corresponding to the copied content. The information necessary for transforming the data is included in the copy permission information . The transformed management data is recorded in the second recording medium .

In step S the information processing device reads the encrypted content recorded in the disk and outputs content copy data having been subjected to a data transformation such as a format transformation. In this way the copied data of the content recorded in the disk is recorded as the encrypted content in the second recording medium . The management data recorded in the second recording medium includes the usage control information the content certificate the MKB the CPS unit key file and the token corresponding to the content recorded in the second recording medium .

At the time of performing the content copying process the information processing device and the management server may perform a process of confirming the medium identifier serial number of the second recording medium and a process of signing the medium identifier with a secret key of the management server to generate a token. This token may be included in the management data. The management data including the token and the like is indicated by the management data in the management server in . The management data CP data recorded in the second recording medium may include the token information.

This content copying process has been roughly described with reference to . As described above the content copying process is performed using the BD J application and the program executed in the AACS layer. Therefore the necessary information needs to be transmitted and received between the BD J application and the program executed in the AACS layer. The API which defines various processes is employed in this process.

Plural process examples which are performed by the information processing device according to the embodiment of the invention using a server will be described now with reference to . The following two processes are shown in 

Process Example 1 a process of allowing the information processing device user device to download content A from the server and to store the downloaded content in the local memory unit and

Process Example 1 corresponds to the content downloading process corresponding to the EST Electric Sell Through described with reference to b of .

Process Example 2 corresponds to the MC Managed Copy described with reference to and is a process of acquiring copy permission information from the server and copying content between mediums.

The ROM disk having content such as a movie recorded thereon is first mounted on the information processing device . A program recorded in the ROM disk is then executed by the data processing unit to perform a download process of acquiring content A from the server . The program is a BD J application program which is a Java registered trademark program corresponding to the BD standard when the ROM disk is the Blu ray Disc registered trademark .

The data processing unit transmits a content download request to the server in accordance with the program . The server provides content A to the information processing device in response to the request. The data processing unit of the information processing device stores content A downloaded from the server in a local memory unit in the device for example the local memory unit constituted by a hard disk or the like.

At the time of downloading the content from the server the following process may be performed concurrently. That is the information processing device transmits the ID device binding ID of the information processing device or a random number binding nonce to the server . The server signs the data with a secret key of the server to generate server authentication information token and provides the server authentication information to the information processing device .

When the downloaded content is used by the information processing device the server authentication information token is verified to confirm that the acquired server authentication information token is valid. Only when this confirmation is made the decoding and reproducing of the downloaded content is permitted. By this setting the usage of the downloaded content is permitted to only a specific device information processing device .

Process Example 2 shown in will be described now. This process is a process of copying content B stored in the disk to the local memory unit . Content B is content stored in the ROM disk and is content to be subjected to usage control. Therefore at the time of performing the copy process it is necessary to acquire the copy permission information from the server .

The program for performing this serial copy process is a program for example BD J application stored for example in the ROM disk . The program is different from the program recorded in the ROM disk in Process Example 1 shown in . The program is a program for performing the content downloading process and the program is a program for performing the content copying process. The different programs may be stored in the ROM disk .

At the time of performing the copy process on the condition that the copy permission information is acquired from the server that is the managed copy MC process the data processing unit of the information processing device reads and executes the program BD J from the ROM disk . The data processing unit performs a series of processes such as a process of reading a medium ID recorded in the ROM disk a process of transmitting the medium ID to the server and a process of acquiring the copy permission information from the server in accordance with the program . After these processes are performed the process of copying the content recorded in the ROM disk to the local memory unit is performed.

In this way various content such as the content downloaded from the server and the copied content from the ROM disk that is the content copied in the managed copy MC process performed under the control of the server by acquiring the copy permission information from the server is recorded in the local memory unit .

The copied content and the downloaded content are divided into the units of titles and are stored in the directories and . By this division and setting in the units of titles data can be selected and copied at the time of performing the copy process on another medium.

However it is not preferable that the process of reproducing the content recorded in the local memory unit can only be performed using the data recorded in the local memory unit. It is preferable that it should be necessary to use data recorded in an internal memory of the information processing device other than the local memory unit. This is because the data recorded in the local memory unit such as a hard disk can be copied to another medium and non permitted usage of the content could be encouraged when the content can be reproduced using only the copied data.

An example of data stored in the local memory unit and the memory in the information processing device will be described with reference to and the subsequent drawings. Plural examples of data storage will be described now in two patterns of A an example of data storage where the content downloaded from the server is stored in the local memory unit see and B an example of data storage where the content copied from another medium is stored in the local memory unit see .

The data processing unit of the information processing device performs a process of recording the encrypted content downloaded from the server or the encrypted content copied from the medium in the local memory unit. The data processing unit makes a data communication with the server which is performed along with the recording process or performs a key block process such as the MKB. The data processing unit performs a content reproducing process accompanied with the process of decoding the encrypted content or the process of confirming the validity by using the data stored in the local memory unit and the data stored in the secure memory at the time of performing a process of reproducing the encrypted content recorded in the local memory unit.

The example A of data storage where the content downloaded from the server is stored in the local memory unit will be first described with reference to .

In the example shown in a device key set a device binding ID and a binding nonce are stored in the secure memory .

The device key set is a key set established to correspond to the information processing device as a device. That is the device key set is a key set specific to an information processing device as a device or set of plural information processing devices. This device key set is used to generate a decoding key at the time of decoding the encrypted content stored in the local memory unit . This device key set needs to be managed in a secrecy required system.

The device binding ID is an identifier specific to the information processing device as a device or a set of plural information processing devices. The binding nonce is random number information and is generated and stored in the secure memory by the information processing device for example at the time of downloading the content from the server .

The device binding ID and the binding nonce are data that must be transmitted to the server in order to acquire the server authentication information token from the server at the time of downloading the content from the server . The device binding ID and the binding nonce need to be managed in a system with anti falsification integrity required .

In this example three pieces of data of the device key set the device binding ID and the binding nonce are stored in the secure memory other than the local memory unit . The device key set or the device binding ID may be stored at the time of manufacturing the information processing device or may be acquired and stored from a server or a medium providing the data. When the data is acquired from the server or the medium it is necessary to have high security to prevent leakage.

When requesting the downloading of content from the server the information processing device transmits the device binding ID and the binding nonce stored in the secure memory to the server .

The server generates the server authentication information token by signing the data with the secret key and transmits the server authentication information to the information processing device . The information processing device stores the server authentication information token in the local memory unit . The server authentication information token in the local memory unit is shown in .

As shown in the drawing the server transmits a CPS unit key file a CPS unit usage control information file an encrypted content an MKB and a content certificate to the information processing device at the time of downloading the content.

The CPS unit key file is a file storing key used to decode the CPS units of the encrypted content or a key used to generate the keys.

The CPS unit usage control information file is a file storing usage control information of the CPS units of the encrypted content .

The encrypted content is an entity of the content to be reproduced and is divided into units CPS units as a usage unit.

The content certificate is used to confirm the validity of the encrypted content . The information processing device confirms the validity of the encrypted content using the content certificate at the time of reproducing the encrypted content . By this process the reproduction of the content is permitted on condition that the validity of the encrypted content is confirmed.

The information processing device stores the data transmitted from the server in the local memory unit . That is the following data is stored in the local memory unit shown in a CPS unit key file a CPS unit usage control information file an encrypted content an MKB and a content certificate . The server authentication information token is recorded in addition to these data.

At the time of reproducing the encrypted content the process including the process of confirming the validity of the encrypted content and the process of decoding the encrypted content is performed using all the data stored in the local memory unit and the device key set stored in the secure memory .

In this example the data stored in the secure memory includes the following data a device key set used to generate a key for decoding the encrypted content and a device binding ID and a binding nonce used to acquire authentication information from the server which are stored in the secure memory.

Another example of data where the content downloaded from the server is stored in the local memory unit and the device key set is not necessary will be described now with reference to .

In a server providing download content and an information processing device including a local memory unit storing the download content and a secure memory are shown.

In the example shown in a volume unique key and content management data AACS data are stored in the secure memory . These data are provided from the server . That is in the example shown in the information processing device needs to store the device key set and the device binding ID in the secure memory in advance but the storage of the data is not required in the example shown in . The information processing device can receive the volume unique key and the content management data AACS data from the server and store the received data in the secure memory at the time of downloading the content from the server .

Specific data of the volume unique key and the content management data AACS data will be described with reference to .

The volume unique key is set as a unique key in the title unit of the downloaded content or the copied content. This key is key information used to decode the encrypted content of the corresponding title. The volume unique key is also encrypted and is decoded for use.

In a in an example of data in which the volume unique key is correlated with the title number is shown. The correlated data is stored in the secure memory . At the time of reproducing the content the title is designated the content correlated with the designated title is selected and the volume unique key is selectively used depending on the title.

When the download content is acquired from the server a disk storing one type of content is fitted into the information processing device and the download process is performed for example using a program read from the disk. The volume unique key or the volume ID is a volume unique key or a volume ID set to correspond to the content title of the disk. When content is copied from the disk and recorded in the local memory unit the volume unique key or the volume ID corresponding to the content title of the disk storing the content is recorded as storage data of the secure memory. In a in an example where volume unique keys corresponding to the titles of various disks are registered is shown.

In an setting example of title numbers the copy content MC content is set when the first bit is 0 the download content EST content is set when the first beat is 1 and the directory names or sub directory names of the local memory unit storing the content are set in the second bit and the subsequent bits. The correspondence between the title numbers and the content becomes clear by this setting.

As shown in b in the content management data AACS data includes a title number a volume ID a PMSN Prerecorded Media Serial Number and an anti falsification code.

The PMSN Prerecorded Media Serial Number is an ID specific to the medium disk and is an ID set in the ROM disk storing the content. The PMSN corresponds to the ID of the ROM disk used to download the content or the ID of the ROM disk as a copy source when the content is copied.

The anti falsification code is data for verifying the falsification of the title number the volume ID and the PMSN.

In this process example the volume unique key and the content management data AACS data are stored in the secure memory shown in . The volume unique key needs to be managed in a system requiring secrecy. The content management data AACS data needs to be managed in a system with anti falsification integrity required .

The volume unique key and the content management data AACS data are both data used to reproduce the encrypted content stored in the local memory unit . These data include data necessary for generating a key used to decode the encrypted content or for performing the validity confirming process. When the data included in the content management data AACS data is used it should be necessarily confirmed that no falsification is made therein using falsified verifying data. The data can be used after the absence of falsification is confirmed.

When the information processing device requests the download content from the server the server transmits as data to be stored in the local memory unit of the information processing device the CPS unit key file the CPS unit usage control information file and the encrypted content as shown in the drawing.

The server transmits the volume unique key and the content management data AACS data as data to be stored in the secure memory of the information processing device .

The CPS unit key file is a file storing key used to decode the CPS units of the encrypted content or a key used to generate the keys.

The CPS unit usage control information file is a file storing usage control information of the CPS units of the encrypted content .

The encrypted content is an entity of the content to be reproduced and is divided into units CPS units as a usage unit.

In this process example the MKB and the content certificate stored in the local memory unit in the process example having been described with reference to are not included in the data provided from the server. In this example the data need not be stored in the local memory unit.

The information processing device stores the data transmitted from the server in the local memory unit or the secure memory . That is the following data are stored in the local memory unit shown in a CPS unit key file a CPS unit usage control information file and an encrypted content . A volume unique key and a content management data AACS data are stored in the secure memory .

At the time of reproducing the encrypted content processes using all the data stored in the local memory unit and the data stored in the secure memory are performed.

In the process example shown in the data necessary for the process of reproducing the encrypted content acquired by download is provided from the server . In the configuration having been described with reference to only a specific information processing device storing the device key set in advance can use the download content. However in the configuration shown in any device can use the download content not just the device having the specific data.

 B The example of data storage where the content copied from another medium is stored in the local memory unit will be described now with reference to .

In a disk storing an encrypted content to be copied and an information processing device including a local memory unit in which the encrypted content of the disk is copied and stored are shown. The information processing device includes a secure memory as an internal memory.

In the example shown in content management data AACS data a device key set and a volume unique key are stored in the secure memory .

The content management data AACS data is the same content management data as described with reference to . As shown in b in the title number the volume ID the PMSN Prerecorded Media Serial Number and the anti falsification code are set therein as corresponding data.

As the content management data AACS data the volume ID and the medium ID PMSN stored in the disk storing the encrypted content to be copied are read and stored in the secure memory by the information processing device .

The device key set is recorded in the information processing device in advance. Alternatively the device key set may be acquired from a server or a medium providing the device key set. However when the device key set is acquired from the server or the medium it is necessary to secure the security thereof and to prevent the leakage thereof.

The volume unique key is generated by a data process using the medium key acquired from the volume ID stored in the disk and the MKB stored in the disk . As shown in the drawing the information processing device performs the MKB process in step S to generate the volume unique key and stores the generated volume unique key in the secure memory .

The content management data AACS data stored in the secure memory needs to be managed in a system with anti falsification integrity required . Both the device key set and the volume unique key need to be managed in a system requiring secrecy.

When the information processing device copies the content from the disk the following data recorded in the disk are read and recorded in the local memory unit of the information processing device a content certificate a CPS unit key file a CPS unit usage control information file and an encrypted content .

A content certificate a CPS unit key file a CPS unit usage control information file and an encrypted content are stored in the local memory unit shown in .

The information processing device reads the volume ID and the medium ID PMSN from the disk generates the content management data AACS data see b in including the read data and stores the generated content management data in the secure memory .

In step S the information processing device reads the MKB from the disk and acquires the medium key from the MKB using the device key of the device key set read from the secure memory . The information processing device generates the volume unique key by a data process encryption process using the acquired medium key and the volume ID read from the disk and stores the generated volume unique key in the secure memory .

At the time of reproducing the encrypted content stored in the local memory unit the processes accompanied with the process of confirming the validity of the encrypted content or the decoding process using the data stored in the local memory unit and the secure memory are performed.

Similarly to shows the example of data storage B where the content copied from another medium is stored in the local memory unit. Similarly to in a disk storing an encrypted content to be copied and an information processing device including a local memory unit in which the encrypted content of the disk is copied and stored are shown. The information processing device includes a secure memory as an internal memory.

In the example shown in a volume ID a medium ID PMSN and a device key set are stored in the secure memory . In the example described with reference to the content management data AACS data is stored. The content management data AACS data is data including the volume ID and the medium ID PMSN as described with reference to b in and falsification verifying data or the like is added to the data. In the example shown in such preparation of the data is not performed but the volume ID and the medium ID recorded in the disk are stored in the secure memory without any change.

The device key set is recorded in the information processing device in advance. Alternatively the device key set may be acquired from a server or a medium providing the device key set. However when the device key set is acquired from the server or the medium it is necessary to secure the security thereof and to prevent the leakage thereof.

The volume ID and the medium ID stored in the secure memory need to be managed in an system with anti falsification integrity required . The device key set needs to be managed in a system requiring secrecy.

When the information processing device copies the content from the disk the following data recorded in the disk are read and recorded in the local memory unit of the information processing device a content certificate an MKB a CPS unit key file a CPS unit usage control information file and an encrypted content .

A content certificate an MKB a CPS unit key file a CPS unit usage control information file and an encrypted content are stored in the local memory unit shown in .

The information processing device reads the volume ID and the medium ID PMSN from the disk and stores the read data in the secure memory .

Unlike the example shown in in the example shown in the MKB is stored in the local memory unit . At the time of reproducing the encrypted content stored in the local memory unit a process of acquiring the medium key using the device key included in the device key set is performed on the MKB . In addition processes accompanied with the process of confirming the validity of the encrypted content and the decoding process using the data stored in the local memory unit and the secure memory are performed.

Similarly to shows the example of data storage B where the content copied from another medium is stored in the local memory unit. In the example shown in server authentication information token which is copy permission information is acquired from a server and is stored in a local memory unit .

In the example shown in a device key set a device binding ID and a binding nonce are stored in the secure memory .

The device key set is a key set established to correspond to the information processing device as a device. That is the device key set is a key set specific to an information processing device as a device or a set of plural information processing devices. This device key set is used to generate a decoding key at the time of decoding the encrypted content stored in the local memory unit . This device key set needs to be managed in a secrecy required system.

The device binding ID is an identifier specific to the information processing device as a device or a set of plural information processing devices. The binding nonce is random number information and is generated and stored in the secure memory by the information processing device for example at the time of acquiring the server authentication information token from the server . The device binding ID and the binding nonce are data which should be transmitted to the server in order to acquire the server authentication information token from the server . The device binding ID and the binding nonce need to be managed in a system with anti falsification integrity required .

In this example three pieces of data of the device key set the device binding ID and the binding nonce are stored in the secure memory other than the local memory unit . The device key set or the device binding ID may be stored at the time of manufacturing the information processing device or may be acquired and stored from a server or a medium providing the data. When the data is acquired from the server or the medium it is necessary to have high security to prevent leakage.

When copying the content from the disk and storing the copied content in the local memory unit the information processing device transmits the device binding ID and the binding nonce stored in the secure memory to the server .

In step S shown in the server generates the server authentication information token by signing the data with the secret key of the server and transmits the server authentication information to the information processing device . The information processing device stores the server authentication information token in the local memory unit . The server authentication information token is shown in .

The server provides a DL download content certificate which corresponds to the encrypted content copied from the disk and stored in the local memory unit to the information processing device at the time of providing the server authentication information token . The content certificate includes data for confirming the validity of the encrypted content . The information processing device stores the data received from the server in the local memory unit . The server authentication information token and the DL content certificate CC are shown in the local memory unit of .

The information processing device performs the process of copying the content from the disk after acquiring the data from the server . When performing the process of copying the content from the disk the information processing device reads the following data from the disk and records the read data in the local memory unit of the information processing device a content hash table an MKB a CPS unit key file a CPS unit usage control information file and an encrypted content .

The data of a content hash table an MKB a CPS unit key file a CPS unit usage control information file and an encrypted content are stored in the local memory unit shown in .

The content hash table is a table storing hash values of constituent data of the encrypted content. The content hash table is used to verify whether the content is valid content that was not falsified at the time of reproducing the content.

At the time of reproducing the encrypted content stored in the local memory unit the process including the process of confirming the validity of the encrypted content and the process of decoding the encrypted content is performed using all the data stored in the local memory unit and the device key set stored in the secure memory .

a device binding ID and a binding nonce used to acquire authentication information from the server which are stored in the secure memory.

As described with reference to when the download content or the copy content is stored in the local memory unit of the information processing device the data strongly requiring anti leakage or anti falsification measures is stored in the secure memory other than the local memory unit. By using this data storage configuration it is possible to prevent the content from being used even when the data stored in the local memory unit is copied to leak to another medium thereby preventing the non permitted use of content.

The invention has been hitherto described with reference to specific embodiments. However it is obvious to those skilled in the art that the embodiments can be modified in various forms without departing from the spirit and scope of the invention. That is the invention has been described exemplarily but these should not be taken as definitive. The spirit and scope of the invention can be understood from the appended claims.

A series of processes described in this specification can be performed by hardware software or a combination thereof. When the processes are performed by software a program including the process sequence can be installed in and executed by a memory of a computer assembled into exclusive hardware. Alternatively the program can be installed in and executed by a general purpose computer performing various processes. For example the program can be recorded in a recording medium in advance. The program cannot only be installed in a computer from a recording medium but may be also received through a network such as a LAN Local Area Network and the Internet and installed in a recording medium such as a built in hard disk.

The various processes described in this specification can be performed consecutively in the described order or may be performed in parallel or individually depending on the processing capability of the device performing the processes or as needed. The system in this specification is a logical set of plural devices and is not limited to a configuration in which the plural devices are disposed in the same chassis.

As described above according to the above mentioned embodiments of the invention in the configuration for storing content downloaded from a server or content copied from a medium in a local memory unit it is possible to safely store key data with high secrecy in memory other than the local memory unit. Accordingly for example even when data stored in the local memory unit is copied and leaks out it is possible to prevent the non permitted usage of the contents by preventing the data stored in the memory from being leaked out. In addition the device specific ID information and the like stored in the memory is transmitted to the server and the server authentication data is received and stored in the local memory unit. Accordingly the correlation of the content stored in the local memory unit with the device is reliably carried out.

The present application contains subject matter related to that disclosed in Japanese Priority Patent Application JP 2008 212484 filed in the Japan Patent Office on Aug. 21 2008 the entire contents of which is hereby incorporated by reference.

It should be understood by those skilled in the art that various modifications combinations sub combinations and alterations may occur depending on design requirements and other factors insofar as they are within the scope of the appended claims or the equivalents thereof.

