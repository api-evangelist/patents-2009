---

title: Data dependence analyzer, information processor, data dependence analysis method and program
abstract: A data dependence analyzer includes: inter-process communication detection means which, on the basis of a processing content of inter-process communication performed for transferring data to be copied between resources, detects the inter-process communication; access detection means which successively detects an access event to the data in the resource due to the process; recording means which, for each of the access events detected by the access detection means, records the access target data in the access event; and analysis means which, among the access target data recorded by the recording means, searches data respectively corresponding to the copy source and the copy destination of the data transferred through the inter-process communication detected by the inter-process communication detection means and imparts a dependence relationship between the searched data.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09027123&OS=09027123&RS=09027123
owner: NEC Corporation
number: 09027123
owner_city: Tokyo
owner_country: JP
publication_date: 20091125
---
This application is the National Phase of PCT JP2009 069837 tiled Nov. 25 2011 which claims priority to Japanese Application No. 2008 312242 tiled Dec. 8 2008 the disclosures of which are hereby incorporated by reference in their entirety.

Various kinds of information are exchanged on an IT Information Technology system and it is important to suitably monitor or manage the flow of these kinds of information according to the degree of confidentiality of the information.

When the flow of the data is insufficiently monitored information leakage occurs. It is possible to simply exchange information by using for example an USB Universal Serial Bus memory but information leakage occurs for example when the USB memory is lost.

In order to prevent such information leakage a so called DLP Data Loss Prevention tool described in Non Patent Literature 1 monitors information leakage on the basis of the degree of similarity of data which are exchanged. In particular a system using the DLP tool prevents information leakage in such a manner that a feature of information having high confidentiality is written in the policy beforehand so as to detect that the data having feature are written to a USB memory or attached to an e mail to be transmitted to an untrusted destination.

Non Patent Literature 2 proposes a method for hooking a system call and tracking not only a file input output and network I O Input Output but also inter process communication using a memory map.

Further an access management system described in Patent Literature 1 collects as logs events of file input output and network input output occurring in a PC Personal Computer . In the logs operations such as an input output of a file a change of a file name writing to a USB memory and network communication performed during a process are recorded so as to be associated with time the name of the process and a user name. By checking the logs the access management system can track the original name of the file written to the USB memory the copy source of the file and the like so as to monitor or prevent the leakage of information.

Patent Literature 2 discloses a method in which a computer reads a filter program used to monitor a user s operation for application software and detects data transfer between the applications so as to thereby prevent unauthorized inter process communication. With this method the computer can obtain the dependence relationship between data transferred only through inter process communication for transferring the data between applications. However in this method the computer needs to create a filter program for each piece of application software.

Here the dependence relationship between data means a relationship between a certain data and the other data all or part of the certain data being formed by copying all or part of the other data.

Patent Literature 3 discloses a method which monitors a user s operation for application software and detects the state of the application software and which performs analysis by combining the operation and the state. With this method the computer can comparatively accurately track not only the inter process communication but also the flow of information inside the process so as to obtain an accurate dependence relationship between data. However in this method the computer needs to acquire a file in which a rule for detecting the state of each piece of application software is written.

Non Patent Literature 1 Carelessness causes information leakage to outside August 2008 pp. 58 69 Nikkei NETWORK

Non Patent Literature 2 SAMUEL T. KING and PETER M. CHEN Backtracking Intrusions ACM Transactions on Computer Systems Vol. 23 No. 1 February 2005

However an excessive dependence relationship is likely to be acquired by the method described in Non Patent Literature 1 Non Patent Literature 2 or Patent Literature 1.

Here the excessive dependence relationship means a case where even though data are not copied the data are deteifflined to have a dependence relationship.

For example during drag and drop during drag operation in Windows registered trademark inter process communication IPC is intermittently performed between the process of the drag source and the process pointed by the mouse cursor. However in this IPC the communication is performed to determine the shape of mouse cursor and there is no substantial flow of information.

In the method described in Non Patent Literature 1 Non Patent Literature 2 or Patent Literature 3 a dependence relationship is produced irrespective of the content of IPC. Thus even in such a case where there is no substantial flow of information it is determined by the method that there is a dependence relationship. This results in a problem in which many excessive dependence relationships are acquired and thereby data cannot be accurately tracked.

The computers described in Patent Literatures 2 and 3 need to create a filter program or a state detection rule for each piece of application software. For this reason in the techniques much labor and time are required for tracking data and hence it is difficult to track the flow of the data. Further there is a problem in which some data cannot be detected by the filter program and the like and hence it is difficult to track the flow of the data.

An object of the present invention is to provide a technique which enables the flow of data to be easily and accurately tracked.

To this end a data dependence analyzer according to the present invention includes inter process communication detection means which on the basis of processing content of inter process communication detects the inter process communication performed for transferring data to be copied between resources access detection means which successively detects an access event to access the data in the resource during the process recording means which for each of the access events detected by the access detection means records the access target data in the access event and analysis means which among the access target data recorded by the recording means searches data respectively corresponding to the copy source and the copy destination of the data transferred through the inter process communication detected by the inter process communication detection means and imparts a dependence relationship between the searched data.

A data dependence analysis method according to the present invention is a method in which on the basis of processing content of inter process communication inter process communication detection means detects the inter process communication performed for transferring data to be copied between resources in which access detection means successively detects an access event to access the data in the resource during the process in which for each of the access events detected by the access detection means recording means records the access target data in the access event and in which among access target data recorded by the recording means analysis means searches data respectively corresponding to the copy source and the copy destination of the data transferred through the inter process communication detected by the inter process communication detection means and imparts a dependence relationship between the searched data.

A program according to the present invention is a program for executing an inter process communication detection procedure for on the basis of processing content of inter process communication detecting the inter process communication perfoimed for transferring data to be copied between resources an access detection procedure for successively detecting an access event to access the data in the resource during the process a recording procedure for for each of the access events detected by the access detection means recording the access target data in the access event and an analysis procedure for among access target data recorded by the recording means searching data respectively corresponding to the copy source and the copy destination of the data transferred through the inter process communication detected by the inter process communication detection means and imparting a dependence relationship between the searched data.

According to the present invention the data dependence analyzer detects inter process communication performed for transferring data to be copied between resources on the basis of the processing content of the inter process communication. Thus the data dependence analyzer can detect the copy of the data without performing complicated operations such as an operation to create the filter program and the state detection rule for each application and hence can easily track the flow of the data. Further the data dependence analyzer imparts the dependence relationship between the data respectively corresponding to the copy destination and the copy source of the data transferred through the detected inter process communication and hence can accurately track the flow of the data.

Exemplary embodiments according to the present invention will be described in detail with reference to the accompanying drawings.

Monitoring unit includes IPC monitoring unit IPC analysis unit IO monitoring unit and log creation unit . For example monitoring unit is included in a part of an operating system OS . More specifically monitoring unit can be realized by a method of expanding a kernel such as a device driver and a system call hook of the OS. Monitoring unit may also be realized so as to operate not in the kernel mode but in a user mode such as the application programming interface API hook.

IPC monitoring unit monitors detects inter process communication hereinafter referred to as IPC . The inter process communication is perfolined by using for example a named pipe a LPC Local Procedure Call or a shared memory. IPC monitoring unit monitors the IPC by opening the named pipe the LPC the shared memory and the like by transmitting data to them and by mediating a system call for receiving data from them. IPC monitoring unit notifies to IPC analysis unit the type of protocol of the detected IPC and the processing content of the IP

IPC analysis unit determines whether the detected IPC is performed to transfer data to be copied between resources.

A method for obtaining the IPC performed to transfer the data to be copied between the resources will be described in detail. IPC analysis unit acquires the type of communication protocol that is used by the IPC and the processing contents of the IPC using the protocol. This is because in some cases data are not copied that depend upon the type of protocol and content of the IPC and because when the dependence relationships between data are obtained for all the IPC the dependence relationships are excessively obtained.

By using a determination rule based on the type of the protocol and the processing content IPC analysis unit analyzes data flowing through the channel of the IPC and thereby determines whether the data have been copied between resources. The determination rule is described on the basis of the expert s determination about whether an explicit information flow exists between the communication source and the communication destination of the IPC which are commonly used between processes.

Here the resource means a device in computer to and from which device information can be inputted and outputted by the user s operation and includes for example a file in a hard disk or a removable media and a network connection. The network connection includes data transmission based on for example FTP File Transfer Protocol HTTP Hyper Text Transfer Protocol SMTP Send Mail Transfer Protocol and the like.

In the case of a classic communication protocol IPC analysis unit determines the dependence relationship on the basis of the type of command transmitted through the protocol the argument of the command and the like processing contents . Further in the case where the protocol of IPC is RPC Remote Procedure Call IPC analysis unit determines the dependence relationship on the basis of the name of a procedure and the argument and the like of the procedure processing procedure . Alternatively in the case where the protocol of IPC is a COM Component Object Model method call IPC analysis unit determines the dependence relationship on the basis of an interface name a method name the argument and the like of the method processing content .

When acquiring the processing contents IPC analysis unit temporarily stores a system call relating to the IPC each time the system call is issued. This is because one IPC having a certain function is realized by a series of system calls being issued a plurality of times. Further when one IPC having a certain function is completed IPC analysis unit reconstructs and acquires the processing contents communication contents of the IPC from the temporarily stored processing content.

For example communication through a named pipe is client server type communication and hence there is a case where IPC having a function is realized by communication through the named pipe being made a plurality of times. In this case IPC analysis unit temporarily stores the content of a series of communication through the named pipe.

The LPC is one of the IPC mechanisms in the WINDOWS registered trademark operating system and is a client server type communication similar to communication through the named pipe. Also in this case IPC analysis unit temporarily stores the content of a series of communication made through the named pipe. In particular the size of data to be transmitted is limited in the LP Thus when a data having a large data size is transmitted the data is transmitted by the LPC and by the shared memory. In this case when reconstructing the content of the IPC communication IPC analysis unit reconstructs the content of LPC communication together with the content of the shared memory.

IO monitoring unit monitors an access to a resource by a process. IO monitoring unit detects the access by mediating a system call for opening a file and a network socket and by mediating communication to a file system driver and a network driver from an OS kernel.

Log creation unit creates a log in which an access event to access a resource detected by IO monitoring unit and an IPC event detected by IPC analysis unit are recorded. The details of the recorded contents of the log will be described below.

Log created by log creation unit is stored in storage unit . Storage unit is a storage medium such as for example a hard disk. By using a known technique for preventing log tampering storage unit may prevent tampering of log by a user.

On the basis of the content recorded in log analysis unit analyzes the dependence relationship between data respectively set as access targets at the access events. In other words for the data set as targets access targets at the respective access events analysis unit determines at which of the access events the mutually dependent data are respectively set as the targets.

More specifically analysis unit sets one of the files data as a search target from among the targets of the access events. Analysis unit searches all of events the target of which is the search target file and the type of which is write . The event satisfying the conditions is set as event Z.

When there is no corresponding event Z analysis unit determines that there is no file depending on the search target file.

When there is corresponding event Z analysis unit searches all events which are generated before event Z and which are read event hereinafter referred to as event W having the same process name as that of event Z.

Then analysis unit determines whether there is an IPC event which is generated before event Z and which has the process name of event Z as the target. The event satisfying this condition is set as event W.

When there is an event W analysis unit searches all read events W which are generated before event W and which have the same process name as that of event W. Analysis unit determines that the search target file depends on the target of the searched event W.

In this way analysis unit investigates the dependence relationship for all the files data described in the log and outputs analysis result in which the dependence relationships between the data are described.

 Type is the type of event detected by IO monitoring unit or IPC analysis unit . The event detected by IO monitoring unit is an access event to access a resource and is the reading read or the like from the resource or the writing to the resource write or the like . The event detected by IO monitoring unit is an IPC event ipc for transferring the copied data.

 Process name is an identifier uniquely assigned to the process performed at the event. When the detected event is an IPC event the name of a process as a communication source is recorded.

When the detected event is an access event target is access target data. When the detected event is an IPC event target is a process as a communication destination.

Next operation of computer of the present exemplary embodiment will be described. is a flow chart showing the operation of computer . This operation is started when a predetermined application is executed. Referring to IPC monitoring unit acquires the type of protocol used in the detected IPC step S . IPC monitoring unit performs communication content acquisition processing step S . On the basis of the type of protocol and the processing content of the detected IPC IPC analysis unit detects IPC performed to transfer data to be copied between resources step S .

IO monitoring unit detects an access event to access the resource step S . Log creation unit creates log in which the access event to access the resource and the IPC event performed to copy the data are recorded and stores log in storage unit step S .

Analysis unit reads log and performs analysis processing step S . Computer ends the operation after step S.

If the IPC is not completed NO in step S IPC monitoring unit returns to step S. If the IPC is completed YES in step S IPC monitoring unit restructures the temporarily stored processing content communication content of the IPC and notifies the restructured processing content to IPC analysis unit step S . IPC monitoring unit ends the communication content acquisition processing after step S.

In the case where the protocol of the communication contents is the COM method call and where the interface name of the method is IDataObject and the name of the method is QueryGetData it is determined that no dependence relationship between data is produced by this IPC communication false step S . This method call is issued when the mouse cursor enters inside the window of the drop destination during drag and drop processing based on OLE and hence does not have a function of transmitting information held by the drag source process to the drag destination process. Therefore this method call produces no dependence relationship between data.

When the protocol of the communication contents does not meet any of the rules in steps S and S it is determined that a dependence relationship between data is produced by this IPC communication true . This is to prevent the omission of detection of a dependence relationship which may be produced and which cannot be detected even by the determination rules created by experts.

When event Z is recorded YES in step S analysis unit searches read event W which is generated before event Z and which is associated with the same process name as that of event Z. Analysis unit adds searched event W to set Y step S . Set Y is a set of events whose targets are respectively set to data having dependence relationships with file X.

Analysis unit determines whether IPC event W which is generated before event Z and which is associated with the same process name as that of event Z is recorded step S .

When event W is recorded YES in step S analysis unit sets event W as event Z step S and returns to step S.

When event W is not recorded in step S No in step S analysis unit determines that file X depends on the targets of the events included in set Y and imparts dependence relationships to these data so as to write the imparted dependence relationships in analysis result step S .

When event Z is not recorded NO in step S analysis unit determines that there is no file dependent from file X step S .

After step S or step S analysis unit determines whether all the files are searched step S . When all the files are not searched NO in step S analysis unit returns to step S. When all the files are searched YES in step S analysis unit ends the analysis processing.

Subsequently the results of the operation of computer at the time when this file operation is performed will be described by taking an example of user s file operation. to are figures showing a series of file operations performed by a user. Referring to files of aaa.txt bbb.doc and ccdoc are stored in computer and

processes of WORDPAD registered trademark word processor and WINWORD registered trademark word processor are started. Here the user performed an operation of reading the file aaa.txt in the process WORDPAD registered trademark word processor. 

Then as shown in the user performed an operation of reading the file bbb.doc in the process of WINWORD registered trademark word processor. 

Referring to the user opened one more execution screen of WINWORD registered trademark word processor and performed an operation of reading the file ccc.doc in the process of WINWORD registered trademark word processor. 

Referring to the user dragged the file ccc.doc read into the process WINWORD registered trademark word processor and dropped the file to the process execution screen WORDPAD registered trademark word processor so as to make the data of the filed copied.

Finally the user stored in a resource by setting the read files aaa.txt ccc.doc as a file ddd.doc in the process WORDPAD registered trademark word processor. 

When these file operations are perfoimed computer records access events and IPC events in log as shown in step S . Specifically when the files are read from

resources in the processes of WORDPAD registered trademark word processor and WINWORD registered trademark word processor as shown in and those access events are recorded in time series order.

Subsequently in during the drag operation of the file IPC is intermittently performed between the drag source process and the drag destination process currently pointed by the mouse cursor. However there is no substantial flow of information in this IPC and hence the IPC events during this period are not recorded in the log. Since when the file is dropped in the data is copied between the resources the IPC event is recorded.

Finally as shown in when the files are written in the resource in the process WORDPAD registered trademark word processor the access events are recorded in time series order.

files aaa.txt bbb.doc and a ccc.doc through the processes WORDPAD registered trademark word processor and WINWORD registered trademark word processor. That is the file ddd.doc file depends on the files aaa.txt bbb.doc and ccdoc .

As described above according to the present exemplary embodiment since computer data dependence analyzer detects on the basis of the processing contents communication between processes performed for transferring data to be copied between resources computer can detect the copy of the data without performing complicated operations such as operations to create a filter program and a state detection rule for each application and can easily track the flow of data. Further the data dependence analyzer imparts a dependence relationship between data respectively corresponding to the copy destination and the copy source of data transferred by the detected inter process communication and hence can accurately track the flow of the data.

Further on the basis of the type of protocol used in inter process communication and processing content of the inter process communication the data dependence analyzer detects inter process communication performed to transfer data to be copied on the basis of the processing content of the inter process communication. Thus the data dependence analyzer can exclude inter process communication performed by using a protocol that does not transfer copied data with the result that the data can be accurately tracked.

Analysis unit associates a read event with a write event via an event during the detected inter process communication and defines a dependence relationship of the copied data by setting the read data as a copy source and the written data as a copy destination. Thus even when data are copied via the inter process communication the copied data can be accurately tracked.

A second exemplary embodiment according to the present invention will be described. Computer of the present exemplary embodiment is different from computer of the first exemplary embodiment in that computer further obtains a degree of dependence relationship.

In step S IPC analysis unit acquires IPC through which data is copied between resources and also acquires the data size of the copied data.

When it is not possible to determine the presence of dependence relationship IPC analysis unit returns 2 for safety step S .

In step S analysis unit multiplies the data size corresponding to event Z by the data size corresponding to event W and sets the value obtained by the multiplication as degree of dependence of event W.

In step S analysis unit calculates the degree of dependence of event Z when event W is set as event Z.

As described above according to the present exemplary embodiment computer evaluates an event having a larger target data size as having a higher degree of dependence and hence can grasp the strength of dependence relationship between data. Computer can further increase the efficiency of data tracking by preferentially tracking data having a strong dependence relationship.

A third exemplary embodiment according to the present invention will be described. is a block diagram showing a configuration of computer of the present exemplary embodiment. Referring to computer is different from computer of the first exemplary embodiment in that monitoring unit further includes dynamic information flow analysis unit .

By using definition information in which a system call for initiating reading from a resource by a process and a system call for initiating writing to a resource by the process are defined dynamic information flow analysis unit checks the transfer of data in the process until the data read from the resource to the process is written out by the process.

Dynamic infoimation flow analysis unit checks the transfer of data in the process by using the method described in Non Patent Literature 3 Feng Qin Cheng Wang Zhenmin Li and Ho seop Kim Yuanyuan Zhou and Youfeng Wu LIFT A Low Overhead Practical Information Flow Tracking System for Detecting Security Attacks ACM IEEE International Symposium on Microarchitecture MICRO 06 2006 or Non Patent Literature 4 Prateek Saxena R. Sekar and Varun Puranik Efficient Fine Grained Binary Instrumentation with Applications to Taint Tracking ACM IEEE International Symposium on Code Generation and Optimization 2008 .

More specifically dynamic information flow analysis unit determines whether data on a certain memory depends on data on another memory by associating a memory with a tag representing what information is currently stored in the memory and by making a process execute codes that are embedded in the process and configured to propagate the tag in correspondence with memory operation processing performed by the process. With this method when a system call reads data to a memory buffer from a certain resource A dynamic information flow analysis unit adds a tag corresponding to resource A to the memory buffer. Then in the case where the tag is propagated according to the processing of the data on the memory buffer and where the contents on the memory buffer are eventually written in another resource B by a system call when the tag corresponding to resource A is added to the memory buffer dynamic information flow analysis unit outputs information representing that resource B is dependent on resource A.

In the present exemplary embodiment for IPC determined by IPC analysis unit as having a dependence relationship dynamic infoimation flow analysis unit also makes the tag propagate between an input to the IPC and an output from the IP

When the data is outputted to a resource or process serving as an output destination target in the writing event to the resource or the IPC event log creation unit specifies from the tag notified from dynamic information flow analysis unit the resource or process dependence source from which the data is originated. Then log creation unit records in log not only the type and target of each of the events but also the resource as the dependence source of the event.

When searching a file dependent from search target file X analysis unit searches a file whose type is write and whose target is file ZX. When there is no corresponding file analysis unit determines that there is no file depending on file X. When there is a corresponding file analysis unit determines that the dependence source file recorded in association with the file is the dependence source of file X.

After step S dynamic information flow analysis unit checks the transfer of data in the process and outputs information for specifying the resource dependent from the target of IPC or the process step S . In each event log creation unit records the target and the resource as the dependence source in association with the type of the event step .

When event Z the type of which is write and the target of which is file X is recorded in log YES in step S analysis unit adds the file dependent from event Z to set Y step S . After step S analysis unit performs step S.

As described above according to the present exemplary embodiment on the basis of the definition information in which for the system call for initiating the writing of data the argument of the transfer source of the data is defined computer further records as a copy source access target data set by the argument of the transfer source in association with the written access target data. Thus the flow of data can be easily tracked.

For example in relating to the first exemplary embodiment three files aaa.txt bbb.doc ccdoc are acquired as dependence sources for the search target file ccdoc .

However in in the present exemplary embodiment only two files aaa.txt ccdoc are acquired as dependence sources of the same target ccdoc . This is because computer detects the data transfer between processes in the first exemplary embodiment but does not detect the data transfer in the process data transfer between a memory and a memory buffer and the like . For this reason computer of the first exemplary embodiment also sets as the dependence source the file bbb.doc which is not actually dependent on the search target file ccdoc and hence acquires an excessive dependence relationship as compared with the present exemplary embodiment.

However in the present exemplary embodiment computer lb can specify the source of the drag and drop operation by using dynamic information flow analysis unit so as to further suppress the excessive production of dependence relationship. Thus even in the case where the number of resources having dependence relationships is increased in accordance with the progress of editing data computer can accurately track the data.

A fourth exemplary embodiment according to the present invention will be described. is a block diagram showing a configuration of computer of the present exemplary embodiment. Referring to computer is different from computer of the first exemplary embodiment in that computer lc further includes security level determination unit in monitoring unit .

Security level determination unit determines the security level level of confidentiality of a resource as a target of reading.

As for the reference of the determination for example security level determination unit determines that the security level of a file stored in a specified directory is higher than the security level of a file not stored in the specified directory. Further security level determination unit determines the degree of security level according to the content of a read file as described in

When searching a read source file corresponding to a search target file analysis unit sets as a dependence source only a file having a security level lower than that of the search target file.

When there is event Z YES in step S analysis unit searches read event W which is generated before event Z and which is associated with the same process name as that of event Z step S . Then when the security level of searched event W is lower than the security level of event Z analysis unit adds event W to set Y step S 

As described above according to the present exemplary embodiment security level determination unit acquires the security level of a resource serving as a read source and analysis unit acquires only the dependence relationship between files having security levels that are not lower than a predetermined value. Thus the operation to acquire the dependence relationship between files having a comparatively low security level is eliminated so that computer can further increase the efficiency of data tracking.

A fifth exemplary embodiment according to the present invention will be described. The configuration of computer of the present exemplary embodiment is the same as computer of the fourth exemplary embodiment except that log creation unit does not record an access event whose security level is not higher than a predetermined value.

After step S log creation unit eliminates a record of an event whose security level is lower than a predetermined value and records only an access event whose security level is not lower than the predetermined value step S .

As described above according to the present exemplary embodiment only important events whose security level is high are noted and hence the efficiency of data tracking is improved. Further computer can suppress the size of log .

A sixth exemplary embodiment according to the present invention will be described. is a block diagram showing a configuration of computer le of the present exemplary embodiment. Referring to computer le is different from computer lc of the fourth exemplary embodiment in that computer further includes IO mediation unit .

Security level determination unit further acquires the security level of a resource as a data write destination.

In the determination of the security level of the resource as the data write destination security level determination unit sets the security level of a specific storage apparatus such as for example a USB Universal Serial Bus memory to a level that is lower than the security level of the other storage apparatus. Further security level determination unit determines that the security level of a specific directory is higher or lower than the security level of the other directory. Security level determination unit determines that the security level of HTTPS Hypertext Transfer Protocol over Secure Socket layer transmission to a specified server is higher than the security level of HTTPS transmission to an unspecified server.

In the case where IO mediation unit mediates write IO to a resource when the security level of the resource as the write destination is lower than the security level of the read source dependence source of the write destination IO mediation unit inhibits the write operation by making the issuance of the system call unsuccessful.

When no read process was performed No in step S or after step S security level determination unit determines whether a write process of writing the read data has been performed step S . When the write process is performed YES in step S security level determination unit acquires the security level of the write destination step S .

IO mediation unit determines whether the security level of the resource as the write destination is higher than the security level of the resource as the read source step S .

When the security level of the resource as the write destination is higher than the security level of the resource as the read source YES in step S 

IO mediation unit permits the writing of the data to the resource as the write destination step S . After step S computer ends IO mediation processing.

Note that the present exemplary embodiment is configured such that only confidential information is prevented from flowing to the outside but may also be configured such that the security level of the user is also defined and only the user who is authorized to read confidential information can read the confidential information. This is achieved for example by such a configuration in which the security level of a user is assigned to a process opened by the user and in which IO mediation unit inhibits the reading from a resource whose security level higher than the security level of the process. Thereby even when the user tries to perform reading from a resource whose security level is higher than the user s security level the user cannot perform reading from the resource and hence the confidential information is prevented from being disclosed to the user.

As described above according to the present exemplary embodiment when the security level of a resource as a read source is higher than the security level of a resource as a write destination IO mediation unit inhibits the writing to the resource. Thus it is possible to prevent data having high confidentiality high security level from being written to a resource having low confidentiality low security level .

As described in Non Patent Literature 1 tools for inhibiting the writing of a file having high confidentiality to a USB memory have been put into practical use but these tools are not properly operated in the case where the contents of a file are modified by encryption or the like to the extent that the confidentiality of the file cannot be determined. On the other hand computer of the present exemplary embodiment tracks the exchange of data between processes and hence the writing of the file can be correctly inhibited on the basis of the security level before the file is modified to the extent that the confidentiality of the file cannot be determined.

The possibility that the system becomes unstable by making the issuance of the system call unsuccessful is low. Since the system call for initiating file opening or network connection often fails due to lack of file permission a network connection error or the like suitable processing at the time of the failure of the system call is usually written in the application side. However the system call for initiating IPC fails less frequently than these kinds of system calls and hence processing at the time of the failure of the system call for initiating IPC is not suitably written in the application side in many cases. Therefore when the system call for initiating IPC is made to fail the operation of an existing application may become unstable for example application software crashes .

However the present exemplary embodiment includes the feature in which access to a file of a process and the access to a network are controlled but the control of IPC is not performed. As a result the present exemplary embodiment can prevent leakage of confidential data while minimizing the possibility of unstable operation of an existing application.

A seventh exemplary embodiment according to the present invention will be described. is a block diagram showing a configuration of computer lf of the present exemplary embodiment. Referring to computer is different from computer of the first exemplary embodiment in that computer further includes encryption unit decryption unit and key management unit .

In the case where when data is written to a resource the security level of the resource as the write destination is not lower than a predetermined value encryption unit encrypts the target data by using an encryption key corresponding to the security level.

Decryption unit determines whether the data read from the resource is encrypted. For example when a specific header is added to an encrypted file or an encrypted network packet decryption unit checks the header of the read data and thereby determines whether the read data is encrypted. When the read data is encrypted decryption unit acquires a key from key management unit to decrypt the read data.

Computer of the present exemplary embodiment performs IO mediation processing step S before step S similarly to the sixth exemplary embodiment.

When no read process was performed NO in step S or after step S decryption unit determines whether a write process has been performed step S . When a write process was performed YES in step S encryption unit performs encryption processing step S . When no write process is performed NO in step S or after step S computer ends IO mediation processing.

When the data is encrypted YES in step S decryption unit acquires a key from key management unit and decrypts the data by using the key step S . Then decryption unit sets the security level of the data to 1 step S .

When the data is not encrypted NO in step S decryption unit sets the security level of the data to 0 step S . After steps S and S decryption unit ends the decryption processing.

When the security level is 1 YES in step S encryption unit acquires a key from key management unit and encrypts the target data step S . When the security level is not 1 NO in step S or after step S encryption unit ends the encryption processing.

Note that in order to avoid complication the present exemplary embodiment is described as having a configuration in which all of the confidential resources are encrypted by using the same key managed by key management unit . However encryption unit may be configured to encrypt each of the data by using an individual key produced at random. Further it may also be configured such that a public key encryption system is used to allow only decryption unit to use a confidential key.

Further in the present exemplary embodiment the security level is divided into two stages 0 and 1 but the security level may be divided into three or more stages. In this case computer lf needs only to record in the header the information corresponding to the security level so as to change the key according to the security level.

Further the present exemplary embodiment is configured only to prevent confidential information from flowing in plain text to the outside. The present exemplary embodiment may also be configured such that the user s security level is also defined and such that only the user authorized to read confidential information can read the confidential information. For example the present exemplary embodiment may be configured such that the security level of a user is assigned to a process opened by the user and such that decryption unit prevents a key corresponding to a security level that is higher than the security level of the process from being assigned to the user. Thereby even when the user tries to perform reading from a resource of a security level that is higher than the security level of the user the user cannot perform the reading from the resource. Thus it is possible to prevent the disclosure of confidential information to the user.

As described above according to the present exemplary embodiment computer encrypts and writes confidential information. Thus even when the confidential information is leaked to the outside by USB memory a mail or the like the confidentiality of the data can be maintained as long as the key has not been leaked.

A similar technique can be realized by a so called ERM Enterprise Rights Management DRM Digital Rights Management tool such as IRM Information Rights

Management embedded in MICROSOFT OFFICE 2003 registered trademark . However the ERM DRM tool is realized by embedding in application software the processing for realizing the above described operations and hence the application software in which the processing can be embedded is limited. On the other hand computer of the present exemplary embodiment operates independently of application software.

Note that each of the above described exemplary embodiments is configured such that computer performs both the recording of logs and the analysis of dependence relationship but may also be configured such that as shown in separate apparatuses and respectively perform the recording of logs and the analysis of dependence relationship.

