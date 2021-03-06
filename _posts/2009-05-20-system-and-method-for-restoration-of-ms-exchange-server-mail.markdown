---

title: System and method for restoration of MS exchange server mail
abstract: A system, method and computer program product for restoration of MS Exchange Server mail. MS Exchange Server mail is retrieved from a virtual copy of the MS Exchange database. Virtualization is implemented by a system filter. Logs are applied to a virtualized DB in order to synchronize it with a real DB of the MS Exchange. The data located in the remote archive does not need to be copied into the real folder, because the data is made available by virtualization means. After the logs are applied, the virtualized DB is opened (without being mounted) from files from the virtual folder. From this point on, the DB of MS Exchange can be viewed and the data can be queried and retrieved from the virtualized DB. Thus, a single message or a mailbox can be retrieved very fast, as if it were being retrieved from a real MS Exchange DB.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09213697&OS=09213697&RS=09213697
owner: Acronis International GmbH
number: 09213697
owner_city: Schaffhausen
owner_country: CH
publication_date: 20090520
---
The present invention is related to restoration of a MICROSOFT Exchange Server mail and more particularly to restoration of backed up MICROSOFT Exchange server mails without actual restoration of the MICROSOFT Exchange Server database.

Electronic mail has become an invaluable application for most of the enterprises over a past decade. However initially it was difficult to implement reserve copying i.e. backup and restoration of the email related information. If the system failed some data was not recoverable thus causing significant damage to an enterprise. Therefore it is very important for an enterprise to implement effective approach for reserve copying and recovery of data without producing a significant operational overhead.

A MICROSOFT Exchange Server is a distributed database and an information exchange environment having a functionality of a mail client intended for an internal use i.e. information exchange among employees of an enterprise . Most of the critical information of the enterprise is stored in the database of the MICROSOFT Exchange Server. In order to protect this information in case of system failure or user error a regular backup of the MICROSOFT Exchange mail data is needed.

A full back up of the MICROSOFT Exchange server is a costly process. However a restoration of a single message of a group of messages or of a mail box is not conventionally possible. It can only be possible if the database DB of the MICROSOFT Exchange Server is backed up at a brick level i.e. back up of each message one by one . Typically the MICROSOFT Exchange Server DB is backed up at a DB level which makes impossible restoration of a single message or of a particular mailbox.

The brick level backup can take up to several hours while DB level backup takes dozens of minutes. However backup of the entire DB takes up a lot of resources and can be quite costly.

Therefore a method for fast and efficient restoration of the MICROSOFT Exchange Server mail without the restoration of the entire MICROSOFT Exchange Server DB is desired.

The present invention is related to a method for fast restoration of mail from the MICROSOFT Exchange Server and more particularly to restoration of backed up MICROSOFT Exchange Server mail without a restoration of the entire MICROSOFT Exchange Server database.

In exemplary embodiment a MICROSOFT Exchange Server mail is retrieved from a virtual copy of the MICROSOFT Exchange database. Virtualization is implemented by a system filter. Logs are applied to a virtualized DB in order to synchronize it with a real DB of the MICROSOFT Exchange. This can be done using de archiving of the database files or the logs can be applied to the already backed up database files by using special applications that allow working with the backed up files as if they were stored on a regular hard drive and not on a reserve storage.

The data located in the remote archive does not need to be copied into the real folder because the data is made available by virtualization means. After the logs are applied the virtualized DB is launched without being mounted from files from the virtual folder. From this point on the DB of MICROSOFT Exchange can be viewed and the data can be queried and retrieved from the DB.

Thus a single message or a mailbox can be retrieved very fast as if it were being retrieved from a real MICROSOFT Exchange DB. The data can be queried and retrieved from the virtualized DB of the MICROSOFT Exchange. The file data can be moved from the archive into the real folder while the MICROSOFT Exchange Server remains open and the database being restored is assembled.

The retrieved data is assembled into mail messages. Then the assembled messages can be stored into a virtual folder or directly into the real folder.

Additional features and advantages of the invention will be set forth in the description that follows and in part will be apparent from the description or may be learned by practice of the invention. The advantages of the invention will be realized and attained by the structure particularly pointed out in the written description and claims hereof as well as the appended drawings.

It is to be understood that both the foregoing general description and the following detailed description are exemplary and explanatory and are intended to provide further explanation of the invention as claimed.

Reference will now be made in detail to the preferred embodiments of the present invention examples of which are illustrated in the accompanying drawings.

The present invention is related to a system method and computer program product for fast restoration of backed up MICROSOFT Exchange Server mail without restoration of the entire MICROSOFT Exchange Server database that substantially obviates one or more of the disadvantages of the related art.

According to an exemplary embodiment MICROSOFT Exchange Server mail is retrieved from a virtualized MICROSOFT Exchange database. Virtualization is implemented by a system filter. For example it can be done such virtual folders as a well established construct in operating system. So BeOS included a version of virtual folders referred to as saved queries that has since influenced the development of virtual folder features in operating systems like Mac OS X WINDWOS and LINUX.

These virtual folders are populated dynamically by executing a search on the entire file system or a subset of it or by using the cached version of the search. Logs are applied to a virtualized DB in order to synchronize it with a real DB of the MICROSOFT Exchange. The DB logs reflect changes that happened to the DB files during backup. The DB logs are also backed up and the backed up logs can be applied to the backed up database files. Thus a state of the DB at any time can be made available.

This can be done using de archiving of the database files or the logs can be applied to the already backed up database files by using special applications that allow working with the backed up files as if they were stored on a regular hard drive and not on a reserve storage. The data located in the remote archive does not need to be copied into the real folder because the data is made available by virtualization means such as the Mounting Point Manager utility which puts archive data into a virtual folder.

After the logs are applied the DB is opened without being mounted from files from the virtual folder. The virtual folder is a directory where the virtualized archived database files are stored. A database can be assembled from the files located in the virtual folder. From this point on the DB of MICROSOFT Exchange can be viewed and the data can be queried and retrieved from the virtualized DB. Thus a single message or a mailbox can be retrieved very fast as if it were being retrieved from a real MICROSOFT Exchange DB.

The data can be queried and retrieved from the virtualized DB of the MICROSOFT Exchange. The retrieved data can be assembled into mail messages. Then the assembled messages can be stored into a virtual folder directly into the real folder or to a MICROSOFT Exchange mailbox.

According to the exemplary embodiment in order to be virtualized the MICROSOFT Exchange DB needs to be backed up at DB level in a very short time. illustrates a flowchart of a method for rapid backup of a MICROSOFT Exchange Server database in accordance with the exemplary embodiment

The process of reserve on line copying i.e. run time backup of the MICROSOFT Exchange Server is started by launching a reserve copying application. This application calls a Web Storage System Service WSS service indicating the desired type of reserve copying. Then the backup process is started at step by marking a synchronization point of the backup.

A this point the WSS informs an Exchange Server Engine ESE that it is in a reserve copying mode and an empty correction file .PAT is created at step for each database being backed up. Note that in the exemplary embodiment during the process of an online backup the database is open for access and transactions can still be recorded in the database. If a transaction invokes an operation for an already copied database file .edb over the point of the reserve copying i.e. a flag in .edb file indicating what is already copied and what is not yet copied the page before the reserve copying point is written into a correction file .PAT .

A separate .PAT file for each backed up database is used. When the ESE is placed into a reserve copying mode a new log file is open. For example if a log file edb.log is currently open it is closed and renamed at step in order to correspond to a latest set of transactions. Then a new file edb.log is created at step .

Then at step a list of files for backup is requested from the MICROSOFT Exchange Server. At step the files from a list requested at step i.e. a current storing group are copied into the backup archive. The database pages are ordered at step by creating a correction file .PAT for each database and writing the database header into the correction file.

The pages are grouped into fragments of 64 KB each i.e. 16 4 KB pages and loaded into an operating memory. The operations corresponding to each copied database .edb file are written into the correction file i.e. .PAT file at step . Then the ESE checks a checksum for each page in order to confirm the integrity of data at step .

A checksum can be in a form of a hash string consisting of 4 byte segments. Such a hash string is generated and added to each page of the database for controlling the integrity of the page. The original checksum of the page is compared to a checksum of the page read into a RAM. Thus it is verified that the data read out of the database and the data written into the database are identical.

MICROSOFT Exchange database page has the first 82 bytes allocated for page headers and flags indicating page type as well as information about the data types contained in the page. When the page is loaded into memory the checksum is calculated and a page number is verified. If the checksum does not match the original checksum this means that the page is corrupted. The ESE in this case will return an error the database will be suspended and information about the corrupted page is recorded in the transaction log.

Note that the ESE does not cure page corruption but only notifies about corrupted pages. The page corruption takes place at the point when data is written onto a disk. In most cases corruption of database pages is caused by equipment or device driver failure. It is important to make sure that the drivers are updated and the latest versions are used.

Comparing the checksums prevents storing corrupted data. Thus a successfully created reserve copy of the MICROSOFT Exchange Server database is guaranteed to be not corrupted since each individual page is checked prior to copying it into a reserve database. After verification of the checksums at step a list of log files .log that are needed to be backed up is requested from the MICROSOFT Exchange Server at step . Then at step the logs and correction files are copied into the backup.

Then the logs are truncated or deleted at step when a new generation of files is created at the beginning of reserve copying. Also old correction files are erased from the disk at step . Then the reserve files are closed the ESE goes into a normal mode of operation and the reserve copying is completed at step .

A virtual folder is used for virtualizing data from the MICROSOFT Exchange DB archive and for restoring mails to a real folder . Note that the archive can implemented on remote location. A virtual folder denotes an organizing principle for files and folders that is not dependent on their physical location in a folder. Instead they can consist of scripts or other mechanisms that coalesce results from a data store which may be a database or a custom index and presents them visually in the format in which folder views are presented. Files and folders of DB of the MICROSOFT Exchange are not stored in a virtual folder since physically a virtual folder is just a file storing a search query. Any attempt to store a file of folder in a virtual folder depending on the implementation is redirected to some physical store.

Then the content of the virtual folder is implemented as a DB of the MICROSOFT Exchange i.e. virtualized DB . The data can be queried and retrieved from the DB of the MICROSOFT Exchange. The retrieved data can be assembled into messages using for example Mail Application Programming Interface MAPI . Then the restored messages can be stored into a virtual folder or directly into the real folder or into the MICROSOFT Exchange mailbox . The MAPI is an application that works with mail systems. The MAPI allows to receive and send messages as well as to attach files or other objects to the messages.

Virtualization of the archived files of the remote archive in the virtual folder with the subsequent application of the backed up logs allows using the backed up database files for requesting data from the DB and for assembling messages from the retrieved data with a subsequent restoration of the messages into the real folder or into the MICROSOFT Exchange mailbox .

This can be done using de archiving of the database files or the logs can be applied to the already backed up database files by using special applications that allow working with the backed up files as if they were stored on a regular hard drive and not on a reserve storage. In this case data located in the remote archive does not need to be copied into the real folder because the data is made available by virtualization means such as a Mounting Point Manager.

For example recordation in MICROSOFT Exchange Server 2000 2003 can be allowed from one location. Tracking log files is stored in the folder Exchsrvr YourServerName.log where YourServerName is the name of the MICROSOFT Exchange Server. Each day a new file can be created with a name yyyymmdd.log where yyyymmdd is a date of file creation.

After the logs are applied at step the database is opened using files from the virtual folder at step . Note that the database is not mounted at step . The mounting of the DB is not necessary because it is time consuming and it is not necessary to work with mails from DB as usual. By opening a DB it is possible to extract all necessary information from a DB. From this point on the DB of MICROSOFT Exchange can be viewed and the data can be queried and retrieved from the DB at step .

DB data retrieval commands can be similar to the commands i.e. queries for an SQL server. For example 

In this case the data for a recipient having an email address qwerty qwerty.qw will be retrieved from the virtualized DB. The data can have special variables assigned for storing the data. For example A can be assigned for recipient s address B for message subject and C for message content. The email messages can be created from the assigned variables in the form of separate files.

According to the exemplary embodiment any type of a search filter can be used on the virtualized DB. For example in order to prevent retrieval of spam messages the filter can use special parameters such as message subject message content sender s name message recipient etc. It can also use message attributes such as date of creation and date of receipt. Certain information of the message content can be used for filtering as well. For example if the content has some embedded advertisement it can be filtered out based on particular words or phrases.

The message parameters can be changed using special commands. Thus a message subject and the message content can be changed for example for changing the message status i.e. level of importance urgency status etc. 

In step the selected data can be assembled into email message using the MAPI. Then the assembled message can be stored in the virtual folder or directly in the real folder.

An example illustrating creation of an email message using the data retrieved from the DB and saved into the assigned variables A B C is provided below 

In this example the recipient s address is taken from the variable A the message subject is taken from the variable B and the message content is taken from the variable C. Then the message can be saved using the command MAPISaveMail in step . Alternatively the message can be saved in the original location of this mail into the MICROSOFT Exchange mailbox in step . The virtual folder can be dismounted at step .

A mail can be created and saved to a pointed to folder but also this mail can be created and sent to addressee with using a command MAPISendDocuments if files are attached to a mail or this mail can be sent with using a command MAPISendMail .

The virtualized and opened DB can be used for extracting information about addressee or about all addressees about parameters and content of mail from DB. Also a mail can be deleted from the virtualized DB after that all mails can be restored to pointed place. Such a method can be used for example for the restoration of mail messages without restoring those messages which contain spam.

Note that other mail servers for example AFTERLOGIC XMail Server APACHE JAMES COMMUNIGATE PRO ICEWARP Mail Server COURIER Mail Server ESERV EXIM HMAIL Server HULA and others can be used instead of MICROSOFT Exchange Server.

Those of ordinary skill in the art will appreciate that the proposed message allows for fast and efficient retrieval of the MICROSOFT Exchange mail without restoration of the entire MICROSOFT Exchange DB.

With reference to an exemplary system for implementing the invention includes a general purpose computing device in the form of a computer or a server or the like including a processing unit a system memory and a system bus that couples various system components including the system memory to the processing unit .

The system bus may be any of several types of bus structures including a memory bus or memory controller a peripheral bus and a local bus using any of a variety of bus architectures. The system memory includes read only memory ROM and random access memory RAM .

A basic input output system BIOS containing the basic routines that help to transfer information between elements within the personal computer such as during start up is stored in ROM . The personal computer may further include a hard disk drive for reading from and writing to a hard disk not shown a magnetic disk drive for reading from or writing to a removable magnetic disk and an optical disk drive for reading from or writing to a removable optical disk such as a CD ROM DVD ROM or other optical media.

The hard disk drive magnetic disk drive and optical disk drive are connected to the system bus by a hard disk drive interface a magnetic disk drive interface and an optical drive interface respectively. The drives and their associated computer readable media provide non volatile storage of computer readable instructions data structures program modules and other data for the personal computer .

Although the exemplary environment described herein employs a hard disk a removable magnetic disk and a removable optical disk it should be appreciated by those skilled in the art that other types of computer readable media that can store data that is accessible by a computer such as magnetic cassettes flash memory cards digital video disks Bernoulli cartridges random access memories RAMs read only memories ROMs and the like may also be used in the exemplary operating environment.

A number of program modules may be stored on the hard disk magnetic disk optical disk ROM or RAM including an operating system preferably Windows 2000 . The computer includes a file system associated with or included within the operating system such as the Windows NT File System NTFS one or more application programs other program modules and program data .

A user may enter commands and information into the personal computer through input devices such as a keyboard and pointing device . Other input devices not shown may include a microphone joystick game pad satellite dish scanner or the like. These and other input devices are often connected to the processing unit through a serial port interface that is coupled to the system bus but may be connected by other interfaces such as a parallel port game port or universal serial bus USB . A monitor or other type of display device is also connected to the system bus via an interface such as a video adapter . In addition to the monitor personal computers typically include other peripheral output devices not shown such as speakers and printers.

A data storage device such as a hard disk drive a magnetic tape or other type of storage device is also connected to the system bus via an interface such as a host adapter via a connection interface such as Integrated Drive Electronics IDE Advanced Technology Attachment ATA Ultra ATA Small Computer System Interface SCSI SATA Serial SCSI and the like.

The computer may operate in a networked environment using logical connections to one or more remote computers . The remote computer or computers may be another personal computer a server a router a network PC a peer device or other common network node and typically includes many or all of the elements described above relative to the personal computer . It may further include a memory storage device . The logical connections include a local area network LAN and a wide area network WAN . Such networking environments are commonplace in offices enterprise wide computer networks Intranets and the Internet.

When used in a LAN networking environment the personal computer is connected to the local area network through a network interface or adapter . When used in a WAN networking environment the personal computer typically includes a modem or other means for establishing communications over the wide area network such as the Internet.

The modem which may be internal or external is connected to the system bus via the serial port interface . In a networked environment program modules depicted relative to the personal computer or portions thereof may be stored in the remote memory storage device. It will be appreciated that the network connections shown are exemplary and other means of establishing a communications link between the computers may be used.

Having thus described a preferred embodiment it should be apparent to those skilled in the art that certain advantages of the described method and apparatus have been achieved. It should also be appreciated that various modifications adaptations and alternative embodiments thereof may be made within the scope and spirit of the present invention. The invention is further defined by the following claims.

