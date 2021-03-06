---

title: Computer system for controlling backups using wide area network
abstract: One of a backup apparatus and a storage system performs control to store backup data in a storage system which belongs to an organization and/or location different from an organization and/or location to which a storage-target storage system for original data belongs, based on information (P) and/or (Q) below: (P) information relating to original data, and information relating to backup data, which is a copy of the original data; (Q) information indicating an organization and/or location to which each storage system belongs.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08745342&OS=08745342&RS=08745342
owner: Hitachi Ltd.
number: 08745342
owner_city: Tokyo
owner_country: JP
publication_date: 20090924
---
Technology of this type includes for example technology for sending backup data to any of a plurality of storage controllers from a backup apparatus that is coupled to a wide area network the Internet for example . For example the backup apparatus disclosed in Patent Literature 1 determines a combination of a backup target file and a backup medium for storing the target file on the basis of a description file describing file location and capacity of the backup target file and a definition file describing the location and capacity of the backup medium and stores the target file in the backup medium paired with the target file.

Furthermore in the case of backups using a wide area network an online storage system provided by a PaaS Platform as a Service vendor for example is adopted as a system for storing backup data. PaaS vendors include for example Amazon which provides the Amazon Simple Storage Service Amazon S3 .

Storing original data and backup data a copy of the original data in an online storage system provided by the same PaaS vendor is undesirable. This is because should a problem arise with the PaaS vendor the PaaS vendor files for bankruptcy for example both the original data and the backup data will likely be unusable.

Furthermore storage of the original data and backup data in an online storage system in the same location is undesirable. This is because should a disaster occur at this location both the original data and the backup data would likely be lost.

Hence an object of the present invention is to enable a user to use one of the original data and the backup data even if a problem should arise with the organization and or if a disaster should occur at its location.

One of a backup apparatus and a storage system which are coupled to a wide area network performs control to store backup data in a storage system hereinafter second storage system which belongs to an organization and or location different from an organization and or location to which a storage target storage system for original data hereinafter first storage system belongs based on information P and or Q below 

More specifically for example the storage system may comprise a communication interface for performing communications via a wide area network a storage apparatus and a controller coupled to the communication interface and the storage apparatus. In this case the controller performs control to store backup data in the second storage system which belongs to an organization and or location different from an organization and or location to which the first storage system belongs based on the P and or Q information. The controller may also include a CPU and memory. In this case the CPU is able to perform the aforementioned processing by executing a program that is read from the memory. The program may be a program acquired from a program source a portable storage medium such as a CD ROM or a remote server for example . The controller may include a hardware circuit instead of or in addition to the CPU and memory. Furthermore the so called storage apparatus may be a storage apparatus described in the subsequent embodiment or a physical storage device a hard disk or flash memory for example .

Furthermore for example the backup apparatus may comprise a communication interface for performing communications via the wide area network a storage apparatus and a controller coupled to the communication interface and the storage apparatus. In this case the controller performs control to store backup data in a second storage system which belongs to an organization and or location different from an organization and or location to which the first storage system belongs based on the P and or Q information. The controller may include a CPU and a memory or may include a hardware circuit instead of or in addition to the CPU and memory.

Note that the control to store backup data in the second storage system may involve storing the backup data in the second storage system or presenting the second storage system to the user as a backup data data storage target.

Furthermore the backup data may be a backup data copy in which case the backup data constituting the source of the backup data may be the original data.

Furthermore the location may be a country unit for example or a smaller unit than a country a state ward or city for example .

The present invention enables the user to use one of the original data and the backup data even if a problem should arise with the organization and or if a disaster should occur at its location.

In all of the following embodiments it is assumed that storage systems are provided by PaaS vendors and that SaaS Software as a Service vendors who use the PaaS vendors are present. A SaaS vendor uses an online storage system of a PaaS vendor and provides online storage which is a data storage region by assigning to it a new value for the software. An example of a SaaS vendor is Dropbox which uses Amazon S3 and allows data to be easily stored in an online storage system using software.

Suppose that SaaS vendors typically use highly reliable low cost PaaS vendors. A situation may therefore arise where a plurality of SaaS vendors use the same PaaS vendor. Hence even though a user of a backup apparatus may employ as a storage target for backup data a second SaaS vendor different from a first SaaS vendor and used as a storage target for original data backup data will likely be stored in a storage system of a PaaS vendor belonging to the same organization and or location as the storage system storing the original data.

When first and second SaaS vendors use a PaaS vendor belonging to the same location and a large scale disaster occurs at this location resulting in damage involving data loss at the PaaS vendor both the original data and the backup data will be lost.

Furthermore in a case where the first and second SaaS vendors use a PaaS vendor belonging to the same organization and the PaaS vendor goes bankrupt the user will likely no longer be able to use both the original data and the backup data.

The computer system of the embodiments hereinbelow makes it possible to avoid storing backup data in the storage system provided by a PaaS vendor that belongs to the same organization and or location as the organization and or location of a PaaS vendor providing a storage system where the original data is stored. Consequently even if the PaaS vendor goes bankrupt or a disaster befalls the location to which a plurality of PaaS vendors belong the user is able to use one of the original data and backup data.

Several embodiments of the present invention will be described hereinbelow with reference to the drawings. Note that in the following description when the subject of processing is a program the processing is actually executed by a processor that runs the program.

In the first embodiment by using a UUID Universally Unique Identifier of a file saved in a storage system at a PaaS site it is possible to avoid storing a backup file copy of an original file in the same storage system as a storage system where the original file is stored. Access hereinbelow refers to processing for both data reading and data writing if not otherwise specified.

The computer system comprises a user site a SaaS site and a PaaS site . Each site is coupled to the Internet . shows three SaaS sites A B and C but the number of SaaS sites may be a number higher or lower than three. Furthermore shows two PaaS sites A and B but the number of PaaS sites may be a number greater than two. When referring to any of the three SaaS sites or either of the two PaaS sites hereinbelow alphabetic characters will be assigned to the SaaS sites and PaaS sites.

The user site has a server hereinafter user server . The user server is an example of a backup apparatus. The user server generates original files by executing an application program refer to . The user server also performs backups of the original files.

The SaaS sites have a SaaS vendor server hereinafter SaaS server . The SaaS server supplies an online storage system provided by the PaaS vendor to the user server .

The online storage system of the PaaS vendor is at the PaaS site . The online storage system stores original files and or backup files. The online storage system includes a server hereinafter PaaS server and a storage apparatus coupled to the PaaS server .

The user server comprises a backend interface a CPU Central Processing Unit a memory main memory for example and a network interface . The CPU manages a logical unit hereinafter LU .

The backend interface is a device allowing the CPU to access a physical storage device hard disk or flash memory for example that holds the LU .

The LU stores programs not shown . When the user server starts up programs are read by the CPU from the LU to the memory . The LU may be a logical storage device that is supplied using RAID Redundant Arrays of Inexpensive Disks technology from a plurality of physical storage devices for example. Furthermore one or more physical storage devices may be adopted instead of the LU . The same is also true for LU and LU described subsequently.

Furthermore the controller is provided by the CPU and the memory . However instead of or in addition to programs being executed by a processor such as the CPU the controller may be implemented by hardware. The same is also true for at least one of the PaaS server the SaaS server and a storage controller which is described subsequently.

The PaaS server includes a backend interface a CPU a memory a network interface and a network interface . The LU is managed by the CPU .

Although not shown in figures programs are stored in the LU . When the PaaS server starts up programs are read from the LU to the memory by the CPU .

The network interface is a device coupled to the storage apparatus via a fibre channel cable for example.

The storage apparatus comprises a storage controller and one or more physical storage devices hard disks for example upon which LU are based. shows two LU but the number of LU may be a number higher or lower than two. When either of the two LU is referred to hereinbelow alphabetic characters will be assigned to the LU.

The network interface is a device coupled to the PaaS server via the fibre channel cable for example.

The CPU executes a program not shown hereinafter access control program which is stored in the memory and controls access to the LU from the PaaS server for example.

The memory is a memory used as a cache for data constituting the files storing the access control program.

A plurality of physical storage devices supporting the plurality of LU for example are coupled to the backend interface . As a result the CPU is able to access the LU .

The SaaS server has the same composition as the user server except that the programs stored in the LU and memory differ from the programs stored in the LU and the memory and the information tables for example stored in the memory differs from the information tables for example stored in the memory . Details will be provided subsequently.

The memory stores a backup program a schedule program a SaaS client program an application program a SaaS management table a schedule management table a backup management table and a file management table . The information may also be stored in a format other than table format.

The schedule program is a program for executing the backup program according to a schedule configured by the user.

The SaaS client program is a program for accessing online storage provided by the SaaS server program from the backup program and the application program .

The application program is a program that executes the work of a user and generates original files. The original files generated by the application program are stored in the storage apparatus of the PaaS sites via the SaaS sites .

The SaaS management table is a table that includes information relating to the SaaS site which is the storage target for the original file written by the application program and information relating to the SaaS sites which are storage target candidates for the backup file written by the backup program .

The schedule management table is a table that includes information relating to schedules according to which the schedule program runs the backup program .

The backup management table is a table that includes information relating to backup files and information relating to online storage serving as the backup target.

The file management table is a table that includes information relating to all the files created by the application program or the backup program .

The memory stores a PaaS server program an organization management table a file management table a PaaS management table and a WEBDAV Web based Distributed Authoring and Versioning property management table .

A PaaS server program is a program providing a function for saving files in the storage apparatus via the Internet a function for deleting files from the storage apparatus and a function for reading files from the storage apparatus .

The organization management table is a table that includes information relating to the organizations of the SaaS vendor.

The file management table is a table that includes information including UUIDs relating to all the files that the PaaS server program has saved in the storage apparatus .

The PaaS management table is a table that includes information relating to the PaaS sites serving as backup file storage target candidates when a file is judged by the PaaS server program to be a backup file.

The WEBDAV property management table is a table that includes information relating to WEBDAV properties.

The memory stores the SaaS server program the PaaS client program the PaaS management table the organization management table and the file management table .

The SaaS server program is a program that provides a function for saving files in online storage provided by the PaaS sites via the Internet a function for deleting files from the online storage and a function for reading files from the online storage.

The PaaS client program is a program for accessing the online storage provided by the PaaS server program from the SaaS server program .

The PaaS management table is a table that includes information relating to PaaS sites serving as file storage target candidates when the PaaS server program returns an error in saving a file in response to a file save request from the SaaS server program .

The organization management table is a table that includes information relating to the organizations of the PaaS vendor.

The file management table is a table that includes information relating to all files saved in the PaaS sites by the SaaS server program .

The detailed processing of each of the above programs will be described subsequently using flowcharts. Details on the various management tables will be provided subsequently.

The SaaS management table includes a SaaS ID an organization name a storage location and an IP address for each of the SaaS sites managed by the user server .

The storage location is the location of the last storage apparatus where the SaaS vendor saved a file. This table item is used in a third embodiment.

The IP address is the IP address for accessing the SaaS server typically the IP address of the SaaS server .

The mount point is the name of the drive where the online storage supplied by the SaaS vendor is mounted in the SaaS server .

The organization name and the IP address are registered in the SaaS management table by being input by the administrator of the user site hereinafter user administrator via a SaaS site registration screen not shown that is provided by the backup program using a management terminal not shown referred to hereinafter as user management terminal at the user site for example. The SaaS ID is generated by the backup program when a pairing of the organization name and the IP address is registered and the SaaS ID is registered in the SaaS management table in association with this pairing for example. In cases where the SaaS site used is known beforehand the user administrator configures a mount point by using the file system of the PaaS server before using the application program and the backup program for example. The mount point is registered in the SaaS management table by the backup program at this time for example.

The schedule management table includes for each backup schedule a schedule ID a schedule name and a start time .

The start time is the time when the backup is started. The schedule program runs the backup program when the start time is reached. The start time may indicate the date time day or period when the backup is executed for example.

The schedule name and the start time are registered in the schedule management table by being input by the user administrator via the schedule registration screen not shown provided by the schedule program using the user management terminal for example. The schedule ID is generated by the schedule program when a pairing of the schedule name and the start time is registered for example the schedule ID being registered in the schedule management table in association with this pairing.

The backup management table includes an ID a backup source a backup target and a schedule ID for each backup set. A backup set is a combination of a backup source a backup target and a backup schedule.

The ID is an ID for identifying combinations of the backup source the backup target and the schedule ID .

The backup source is information indicating the file directory or drive backed up by the backup program .

The backup target is information indicating a target directory or drive in which the data of the backup source is saved by backup processing the initial value of the directory or drive for example .

The backup source the backup target and the schedule ID are registered in the backup management table by being input by the user administrator via a backup registration screen not shown provided by the backup program using the user management terminal for example. The backup ID is generated by the backup program when a combination of the backup source the backup target and the schedule ID are registered for example the backup ID being registered in the backup management table in association with this combination.

The file management table includes for each file a local ID a file name a UUID and the SaaS ID . The local ID is an ID uniquely identifying a file.

The UUID is a unique ID that is allocated to a file by a file system not shown when the file is saved in the storage apparatus of the PaaS site .

The file name is registered by the file system when the application program or the backup program creates a file for example. The UUID is registered after being acquired from a PaaS site when a backup is performed by the backup program . This will be described in detail subsequently using . A SaaS ID is registered by the file system when a file is created for example by using the SaaS management table to specify the SaaS ID from the file name and the mount point .

The organization management table includes an organization name a storage location and an IP address .

The organization name is the name of the vendor PaaS vendor operating the PaaS site with the PaaS server in which the organization management table is stored.

The storage location is the location of the last storage apparatus in which the PaaS vendor saved the file. This table item is used in the third embodiment.

The IP address is an IP address for accessing the PaaS server storing the organization management table .

The organization name and the IP address are registered in the organization management table by being input by the administrator of the PaaS site hereinafter PaaS administrator via an organization registration screen not shown provided by the PaaS server program using a management terminal not shown hereinafter PaaS management terminal in the PaaS site .

The file management table includes for each file a path name a file name a UUID an extended UUID and a WEBDAV pointer .

The UUID is a unique ID allocated to the file by the file system when the file is saved in the storage apparatus .

The extended UUID is an ID based on the UUID of the file created during a file backup by the backup program . The extended UUID includes the UUID of the backup source file and a backup identifier identifying the file as a backup file for example.

A PaaS ID is registered by the file system when a file is created for example by using the PaaS management table to specify a PaaS ID see from the path name the file name and the mount point . When another PaaS site is not being used a value a hyphen for example signifying that another PaaS site is not used is registered as the PaaS ID for example. The path name the file name the UUID and the WEBDAV pointer are indicated to the file system by the PaaS server program when a file is created for example and registered. The extended UUID is registered by the PaaS server program which receives the extended UUID sent from the backup program when a backed up file is saved in the storage apparatus for example. In cases where files written from a plurality of SaaS sites or Paas sites are managed although not illustrated this can be implemented by registering a user ID which corresponds to each written file in the file management table . When communication with the PaaS site starts authentication is performed using the user ID of the SaaS site or PaaS site that issued a communication start request and file association is performed using the user ID.

The PaaS management table includes for each PaaS site managed by the PaaS server a PaaS ID an organization name a storage location and an IP address .

PaaS ID is an ID for identifying a combination of the organization name the storage location and the IP address of another PaaS site .

The organization name is the name of the vendor of another PaaS site hereinafter other PaaS site from the PaaS site hereinafter own PaaS site where the PaaS management table is stored. The other PaaS site is a PaaS site that is used as another storage target PaaS site when a file owing to its identical UUID is not saved in the storage apparatus of the own PaaS site .

The storage location is the location of the last storage apparatus where the PaaS vendor saved the file. This table item is used in the third embodiment.

The mount point is the name of the drive where the online storage provided by the PaaS vendor is mounted on the server .

The organization name and the IP address are registered in the PaaS management table by being input by the PaaS administrator via a PaaS site registration screen not shown provided by the PaaS server program using the PaaS management terminal for example. In cases where the PaaS site used is known beforehand the PaaS administrator configures a mount point by using the file system of the PaaS server for example. The mount point is registered in the PaaS management table by the file system at this time for example.

The PaaS management table includes for each PaaS site managed by the SaaS server a PaaS ID an organization name a storage location an IP address and a mount point .

The PaaS ID is an ID for uniquely identifying a combination of the organization name the storage location the IP address and the mount point of a PaaS site .

The storage location is the location of the last storage apparatus where the PaaS vendor saved the file. This table item is used in the third embodiment.

The mount point is the name of the drive where the online storage provided by the PaaS vendor is mounted on the server .

The organization name and the IP address serving as the connection target of the registered PaaS site are registered in the PaaS management table by being input by the SaaS site administrator hereinafter SaaS administrator via a PaaS site registration screen not shown provided by the SaaS server program by using a management terminal at the SaaS site not shown hereinafter the SaaS management terminal for example. The PaaS ID is generated by the SaaS server program when a pairing of the organization name and the IP address is registered for example and registered in the PaaS management table in association with this pairing. When the PaaS site used is known beforehand the SaaS administrator configures a mount point by using the file system of the server before using the SaaS server program for example. The mount point is registered in the PaaS management table by the SaaS server program at this time for example.

The organization management table is composed by an organization name a storage location and an IP address .

The organization name is the name of the vendor SaaS vendor operating the SaaS site which stores the organization management table .

The storage location is the location of the last storage apparatus where the SaaS vendor saves the file. This table item is used in the third embodiment.

The IP address is an IP address for accessing the server of the SaaS site storing the organization management table .

The organization name and the IP address are registered in the organization management table by being input by a SaaS administrator via an organization registration screen not shown provided by the SaaS server program by using the SaaS management terminal for example.

The file management table includes for each file a local ID a path name a file name a UUID an extended UUID and a PaaS ID .

The UUID is a unique ID that is allocated to the file by the file system when the file is saved in the storage apparatus of the PaaS site .

The local ID the path name the file name and the PaaS ID are registered by the SaaS server program when a file is created for example. The UUID is registered by the SaaS server program when a response to a UUID request of the backup program is received by the SaaS server program from the PaaS server program for example. The extended UUID is registered by the SaaS server program when the SaaS server program receives the extended UUID from the backup program for example. The PaaS ID is registered by the file system when a file is created for example by using the PaaS management table to specify the PaaS ID from the path name the file name and the mount point . When the PaaS site used is known beforehand the SaaS administrator configures a mount point by using the file system of the server before using the SaaS server program for example. The mount point is registered in the file management table by the SaaS server program at this time for example. In cases where files written from a plurality of user sites are managed although not illustrated this can be implemented by registering a user ID which corresponds to each written file in the file management table . When communication with the SaaS site starts authentication is performed using the user ID of the user site that issued a communication start request and file association is performed using the user ID.

In this embodiment the WEBDAV standard as defined under RFC 4918 for example is extended so that UUIDs can be acquired from the PaaS server . A UUID item is added as a file property.

As shown in the backup program sends a file UUID request to the SaaS server in XML eXtensible Markup Language format for example by using the WEBDAV PROPFIND method. The SaaS server sends the UUID request to the PaaS server .

After receiving the UUID request the PaaS server sends a UUID which is a Multi Status file property to the SaaS server in XML format as a response as shown in . The SaaS server sends a response to the user site that issued the request.

A file creation request is used by extending the MKCOL method of the WEBDAV standard for example. The file name thus created is designated as a first parameter of the MKCOL method and the extended UUID is designated as the second parameter thereof.

The backup program uses the MKCOL method for example when the file creation request is sent to the SaaS site for backup processing.

After receiving the file creation request the PaaS server sends Created in to the request source as a response for example.

SaaS site registration processing at the user site is executed as initial processing by a user administrator before the file creation processing by the application program and the backup program is executed.

The user administrator activates the SaaS registration screen of the backup program and inputs the organization name and IP address of the SaaS site step .

PaaS site registration processing at the SaaS site is executed as initial processing by a SaaS administrator before the SaaS server program provides online storage services.

The SaaS administrator activates the PaaS registration screen of the SaaS server program and inputs the organization name and IP address of the PaaS site step .

The PaaS site registration processing at the PaaS site is executed as initial processing by a PaaS administrator before the PaaS server program provides online storage services.

The PaaS administrator activates the PaaS registration screen of the PaaS server program and inputs the organization name and IP address of the PaaS site step .

New file creation processing is executed when a new file is created by the application program and the backup program . In new file creation processing an empty file with no data content is created. Here an example of new file creation processing in which the backup program uses a known WEBDAV standard for backup processing will be described.

The backup program receives a backup ID as a parameter when run by the schedule program and thus identifies the backup being executed.

The backup program specifies the backup source file original file indicated by the backup source corresponding to the ID by referring to the backup management table using the received backup ID as a search key and specifies the backup target indicated by the backup target and corresponding to the ID . For example the path name of the newly created file is the backup target and the file name of the newly created file is the file name of the backup source .

The backup program registers the file name of the created file in the file management table and sends a file creation request including the path name and the file name to the SaaS client program step .

The SaaS client program receives the file creation request and specifies the file name from the request step .

The SaaS client program uses the file management table to specify the SaaS ID corresponding to the specified file name. The SaaS client program refers to the SaaS management table and specifies the IP address corresponding to the specified SaaS ID step .

The SaaS client program uses the specified IP address to send a file creation request to the SaaS server program of the SaaS site step . The file creation request includes the file name specified in step .

The SaaS server program receives a file creation request and sends the request to the PaaS client program step .

The PaaS client program receives the file creation request and specifies the file name from the request step .

The PaaS client program refers to the file management table and specifies the PaaS ID corresponding to the specified file name. The PaaS client program specifies the IP address corresponding to the specified PaaS ID from the PaaS management table step .

The PaaS client program uses the specified IP address to send a file creation request to the PaaS server program of the PaaS site step .

The PaaS server program receives the file creation request creates an empty file in response to the received file creation request and creates a UUID on the basis of a parameter file name for example included in the request step .

The PaaS server program registers the UUID thus created and registers the path name and the file name acquired from the file creation request in the file management table step .

The PaaS server program sends a success response indicating that the file creation request has succeeded to the PaaS client program which was the request source transmission source of the file creation request step .

The PaaS client program receives the success response and sends the received success response to the request source SaaS server program step .

Upon receiving the success response the SaaS server program registers the path name and the file name of the created file and the PaaS ID of the PaaS site which succeeded in saving the file to the file management table step .

The SaaS client program receives the success response and sends the received success response to the backup program step .

File write processing is processing in which data is written to a newly created empty file file with no data content .

Processing such as file write processing read processing and UUID acquisition processing is sent to the PaaS site via the SaaS site from the backup program of the user site in the same way as the new file creation processing illustrated in . Hence similar processing will not be described hereinbelow since the focus of the description will be on differences.

File write processing is executed when the application program and the backup program write a file. Here an example of file write processing in which the backup program uses a known WEBDAV standard for backup processing will be described.

The backup program sends a file write request including the path name of the file to be written the file name and write data for example the file data read by the read processing in original file data to the SaaS client program step .

The SaaS client program receives the file write request and sends the request to the PaaS server program via the SaaS site . Specifically the same processing as for steps to in is carried out steps to .

The PaaS server program receives the write request and writes the data of the received request to a file specified by the received request step .

The PaaS server program sends a success response to the backup program of the user site via the SaaS site and the write processing ends. More specifically the same processing is performed as in steps and in steps to step . Note that as can be seen in a comparison with the SaaS server program does not update the file management table in steps to .

The file read processing is executed when the application program and the backup program read a file. Here an example of file read processing in which the backup program uses a known WEBDAV standard for backup processing is described.

The backup program specifies the name of the file to be read from the backup source of the backup management table step .

The backup program sends a file read request which includes the path name and the file name of the file to be read to the SaaS client program .

The SaaS client program sends the file read request to the PaaS server program via the SaaS site . More specifically the same processing as in steps to in is carried out steps to .

The PaaS server program sends the read data file data as a success response to the backup program of the user site via the SaaS site and the read processing ends. More specifically the same processing as in steps and in is carried out steps to . Note that as can be seen in comparison with the SaaS server program does not update the file management table in steps to .

XaaS selection processing is a general name for SaaS selection processing at the user site PaaS selection processing at a SaaS site and PaaS selection processing at a PaaS site in other words substituting S or P for X . This processing is executed by each program as a subroutine.

The backup target registered in the backup management table is the default backup target for example. Here SaaS selection processing at the user site will be described by way of example.

The backup program specifies a drive name indicated by the backup target in a row selected from the backup management table . The backup program specifies the mount point of the drive with the specified drive name from the SaaS management table and specifies the SaaS ID corresponding to the specified mount point from the SaaS management table . The backup program judges whether or not a SaaS ID not selected in the backup processing being executed by the SaaS ID excluding the specified SaaS ID default SaaS ID is in the SaaS management table step . Although not illustrated this judgment can be implemented by adding a column of flags indicating whether a SaaS has been selected to the SaaS management table for example. The backup program judges that there are no unselected SaaS IDs when the flags of SaaS IDs for which the mount point is registered are all 1 . The backup program judges that there is an unselected SaaS ID when there is a flag at 0 for a SaaS ID for which the mount point is registered. Whenever the backup program starts file backup processing the backup program registers 1 for a default SaaS ID and registers 0 for all other SaaS IDs.

In cases where it is judged that there is an unselected SaaS ID the backup program registers a 1 for a flag indicating whether the SaaS corresponding to the unselected SaaS ID has been selected selects the unselected SaaS ID in the SaaS management table and sends the unselected SaaS ID to a calling program step .

When it is judged that there is no unselected SaaS ID the backup program sends an error indicating that there is no selectable SaaS ID to the calling program step .

This XaaS selection processing is selection processing for the PaaS ID at the SaaS site and selection processing for the PaaS ID at the PaaS site .

File UUID acquisition processing is executed when the backup program acquires the UUID of a backup source file from a PaaS site.

The backup program acquires the backup source of the backup management table and specifies the name of the file from which the UUID was acquired from the backup source step .

The backup program sends a UUID request see to the PaaS server program via the SaaS site steps to step .

The PaaS server program acquires the UUID corresponding to the file name in the UUID request from the file management table step .

The PaaS server program sends the UUID to the backup program of the user site via the SaaS site as a success response see and the UUID acquisition processing ends steps to . Here the SaaS server program changes the UUID in the file management table to the UUID received in response step . Likewise the SaaS client program changes the UUID of the file management table to the UUID received in response step .

The WEBDAV property management table is created during file creation. The logic address where data is registered to establish an association with the file is registered in the WEBDAV pointer in the file management table .

The property name constituting a WEBDAV property is determined under the WEBDAV standard. In this embodiment a property name such as UUID for example is added to extend the property name.

The value is the value of the property name . For example a file creation date and time is registered as the property name creationdate and the file display name is registered as the property name displayname . The UUID registered in the file management table is stored as the UUID .

This processing is processing of the backup program which is executed by the schedule program at the backup start time. Hereinafter a backup schedule with this start time will be referred to as the target schedule in the description of .

The backup program reads the backup source file in the read processing in step . The backup source file is a file indicated by the backup source corresponding to the target schedule ID.

The backup program acquires the UUID of the read backup source file in the UUID acquisition processing of step .

The backup program creates an extended UUID by adding a backup identifier to the acquired UUID step .

The backup program sends a new file creation request directed toward the backup target corresponding to the target schedule ID and including the extended UUID hereinafter called a new backup file creation request see to the SaaS site by using the IP address for the SaaS ID corresponding to the backup source file step .

The backup program receives a response to the request from the SaaS site to which the new backup file creation request was sent step .

The backup program analyzes the received response and judges whether or not a file with a UUID identical to the UUID hereinafter called the original UUID of the backup source file has been found from the PaaS site managed by the SaaS site to which the new backup file creation request was sent step .

When a no file found judgment is made the backup program sends file data read in step to the SaaS site in which the original UUID was not found step .

On the other hand when a file found judgment is made the backup program acquires the results of executing XaaS selection processing see in order to determine the next SaaS site to which the new backup file creation request is to be sent step . The backup program then judges whether or not there is an error such as the results of the XaaS selection processing indicating that no subsequent candidate SaaS site was found step . When no error is judged the backup program executes the processing of step . When on the other hand an error is judged the backup program displays the error on a user management terminal via a GUI for example . Note that a method with which the backup program determines the SaaS site that is to serve as the backup target will be described subsequently but the user administrator may also select the backup target SaaS site .

The backup program judges whether or not files to be backed up still remain step . When it is judged that such files still remain the backup program executes the processing of step for those files to be backed up ending the backup processing upon judging that there are no more files to be backed up.

This processing is executed when the SaaS server program receives a new backup file creation request from the user site .

The SaaS server program sends a new backup file creation request to the PaaS site selected from one or more backup target candidate PaaS sites managed by the PaaS management table step .

The SaaS server program receives a response to the request from the PaaS site to which the new backup file creation request was sent .

The SaaS server program judges from the received response whether or not a file with a UUID identical to the UUID hereinafter called the original UUID of the backup source file has been found from the PaaS site managed by the PaaS site to which the request was sent step .

When a no file found judgment is made the SaaS server program sends a success response to the request to the request source SaaS site step .

When a file found judgment is made the SaaS server program acquires the results of executing XaaS selection processing see in order to determine the next PaaS site to which the new backup file creation request is to be sent step . The SaaS server program judges whether or not there is an error such as the results of the XaaS selection processing indicating that no subsequent candidate PaaS site was found . When no error is judged the SaaS server program executes the processing of step . When an error is judged the SaaS server program sends an error response to the request to the request source SaaS site step .

This processing is executed when the PaaS server program receives a new backup file creation request from the SaaS site .

The PaaS server program acquires an original UUID except for the backup identifier from the extended UUID of the received request. The PaaS server program then acquires the results of executing UUID check processing see step .

The PaaS server program judges from the acquired results whether or not a file with a UUID identical to the original UUID has been found step .

When a no file found judgment is made the PaaS server program creates a file using the path name the file name and the extended UUID included in the new backup file creation request step . The PaaS server program sends a success response to the request source SaaS site step .

When on the other hand a file found judgment is made the PaaS server program acquires the results of executing XaaS selection processing see in order to determine the next PaaS site to which the new backup file creation request is to be sent step . The PaaS server program judges whether or not there is an error such as the results of the XaaS selection processing indicating that no subsequent candidate PaaS site was found step .

When an error is judged the PaaS server program sends a request error response to the request source PaaS site step .

When no error is judged the PaaS server program sends a new backup file creation request to a PaaS site selected from one or more backup target candidate PaaS sites managed by the PaaS management table step . The PaaS server program receives a response to the request from the PaaS site step . The PaaS server program then judges from the received response whether or not a file with a UUID identical to the original UUID has been found from the PaaS site managed by the PaaS site to which the request was sent step . When a file found judgment is made the PaaS server program executes the processing of step . When a no file found judgment is made the PaaS program sends a request success response to the request source SaaS site step .

A PaaS server program compares the original UUID excluding the backup ID from the extended UUID with all the UUIDs in the file management table .

When a UUID found judgment is made the PaaS server program returns an error indicating that an identical UUID has been found step .

When a UUID not found judgment is made the PaaS server program returns a success response indicating that an identical UUID has not been found step .

As described hereinabove by acquiring the UUID of the backup source file and by checking during backup that a file with an identical UUID has not been saved at the backup target PaaS site it can be ensured that the backup file is not stored in the backup source PaaS site that has the original file. Consequently even when there is a disaster involving data loss at one PaaS site one of the original file and the backup file is not lost and remains available.

When the first embodiment above and one or more modifications of the first embodiment are considered the computer system according to the first embodiment can be implemented as follows for example.

In other words the backup apparatus user server for example adds backup identification information extended UUID for example which is identification information including original data identification information the UUID or another type of identification information may be adopted for example and information signifying a backup backup identifier for example to the backup data and sends a backup file storage request to which backup identification information was added. The storage request may be sent to the storage system via a relay apparatus such as a SaaS server or may be sent to the storage system without passing via such a relay apparatus.

A first storage system which receives the request to store the backup data to which the backup identification information was added judges in response to the received storage request whether or not identification information identical to the original data identification information in the backup identification information added to the backup data is being managed and if the judgment result is negative stores the backup data.

On the other hand when the judgment result is positive the first storage system or a relay apparatus for relaying the storage request selects a second storage system which belongs to an organization and or location different from an organization and or location to which the first storage system belongs on the basis of organization location information indicating organizations and or locations to which storage systems coupled to the first storage system or the relay apparatus belong and sends a storage request for the backup data to which the backup identification information was added to the second storage system. In other words a storage request may be sent from the first storage system to the second storage system without passing via a relay apparatus such as a SaaS server or the relay apparatus may send a storage request to the second storage system in cases where an error response is received from the first storage system.

Note that like the first storage system the second storage system may after receiving the storage request judge whether or not identification information identical to identification information included in the backup identification information added to the backup data is being managed.

Furthermore the first storage system may only judge whether or not identification information identical to original data identification information in the backup identification information is being managed only when information signifying a backup is detected from the backup identification information.

Furthermore the second storage system to which the storage request is sent may be a storage system that belongs to a location farthest from the location to which the first storage system belongs.

In addition in cases where any storage system coupled to the first storage system or the relay apparatus is a storage system identical to that of an organization and or location to which the first storage system belongs the first storage system or relay apparatus may upon receiving a storage request return an error to the backup apparatus. In this case the backup apparatus may send the storage request to a storage system or relay apparatus different from the first storage system or relay apparatus.

A second embodiment of the present invention will be described hereinbelow. In so doing differences from the first embodiment will mainly be described and points in common with the first embodiment will be described simply or omitted.

According to the second embodiment a UUID which includes a volume identifier of a file virtual machine file for example saved in the storage apparatus of the PaaS site is used to avoid saving an original file and a backup file thereof in the same storage apparatus.

A backup program does not perform backup source file UUID acquisition processing extended UUID creation processing or send a new backup file creation request including an extended UUID during a backup. The UUID of the file management table is not used.

A UUID acquired from within a virtual machine file by the file management program is registered in the extended UUID of the file management table .

A logical volume space of a virtual machine file mainly includes respective regions for an MBR a UUID an MFT empty data and user data .

The UUID is a region in which a unique ID for identifying the logical volume of the virtual machine file is stored.

The empty data is a region in which logical volume formatted data is written or a region to which no data is written.

The logical composition of a virtual machine file is such that empty data of the logical volume space of the virtual machine file are stored in a compressed state for example.

This processing is activated by the PaaS server and executed before the file is written. This processing is executed by the file monitoring program at all times.

The file monitoring program detects a virtual machine file written to the file system. For example the file monitoring program monitors file extensions. More specifically in cases where a virtual machine file extension is vmvm for example when a file with a file name vmfile.vmvm is newly created the file monitoring program detects the fact that the file is a virtual machine file and monitors writing step .

The file monitoring program is capable of identifying the logical structure of a virtual file with a virtual machine file extension and of specifying the position in which the UUID is written position within the virtual machine file .

Upon detection of a virtual machine file the file monitoring program specifies the position of the UUID within the detected virtual machine file and reads the UUID . The file monitoring program then registers the read UUID in the location of the extended UUID within the file management table step . The processing of this step is executable as long as the position of the UUID is written before file writing is complete.

This processing is executed by the backup program which is run by the schedule program at the backup start time. A backup schedule with this start time will be referred to hereinbelow as target schedule in the description of .

The backup program reads the backup source file in the read processing see step . The backup source file is a file indicated by the backup source corresponding to the target schedule ID.

The backup program sends a new file creation request for the backup target indicated by the backup target corresponding to the target schedule ID to the SaaS site step .

After receiving a success response to the new file creation request the backup program sends file data to the backup target SaaS site in file write processing see step .

The backup program judges from the received response whether or not a file with a UUID identical to the UUID in the backup source virtual machine file referred to hereinafter as the original VM UUID has been found from the PaaS site managed by the SaaS site to which the request was sent step .

When a no file found judgment is made the backup program judges whether or not a file to be backed up still remains step . When a remaining file judgment is made the backup program executes the processing of step for files to be backed up. When a no remaining file judgment is made the backup program ends the backup processing.

When a file found judgment is made the backup program acquires the results of executing XaaS selection processing see in order to determine the SaaS sites to which the write request is to be sent next step . The backup program judges whether there is an error such as the results of the XaaS selection processing indicating that no subsequent candidate SaaS site was found step . When no error is judged the backup program executes the processing of step . When an error is judged the backup program displays this error on the user management terminal via a GUI for example step .

This processing is executed when the SaaS server program receives a backup file write request from the user site .

The SaaS server program sends the backup file write request to a PaaS site selected from one or more backup target candidate PaaS sites managed by the PaaS management table step .

The SaaS server program judges from the received response whether or not a file with a UUID identical to the original VM UUID has been found from the PaaS site managed by the PaaS site to which the request was sent step .

When a no file found judgment is made the SaaS server program sends a request success response to the request source SaaS site step .

When a file found judgment is made the SaaS server program acquires the results of executing the XaaS selection processing see in order to determine the next PaaS site to which the request is to be sent step . The SaaS server program judges whether or not there is an error such as the results of the XaaS selection processing indicating that no subsequent candidate PaaS site was found step . When an error is judged the SaaS server program sends a request error response to the request source SaaS site step . When no error is judged the SaaS server program executes the processing of step .

This processing is executed when the PaaS server program having received a write request from the SaaS site writes a file to the storage apparatus and when the file monitoring program then detects a virtual machine file and acquires the original VM UUID.

The PaaS server program acquires the original VM UUID as a parameter from the file monitoring program at this time.

The PaaS server program acquires the results of executing the original VMUUID check processing see step . When the virtual machine file is saved in the storage apparatus the acquired original VM UUID is registered in the extended UUID of the file management table . In step of the original VM UUID check processing the PaaS server program compares the original VM UUID with the extended UUID of the file management table .

The PaaS server program judges from the acquired results whether or not a file with an extended UUID identical to the original VM UUID has been found .

When a no file found judgment is made the PaaS server program writes file data included in the write request using the path name and file name included in the write request step . The PaaS server program registers the original VM UUID in the extended UUID of the file management table . The PaaS server program sends a success response to the request source SaaS site step .

When a file found judgment is made the PaaS server program acquires the results of executing XaaS selection processing see in order to determine the next PaaS site to which the write request is to be sent step . The PaaS server program judges whether or not there is an error such as the results of the XaaS selection processing indicating that no subsequent candidate PaaS site was found step .

When an error is judged the PaaS server program sends a request error response to the write request source PaaS site step .

When no error is judged the PaaS server program sends a backup file write request to the PaaS site selected from one or more backup target candidate PaaS sites managed by the PaaS management table step . Even when file writing is in progress because the error judgment results are obtained in the processing of step the determination of whether or not writing is complete for each file part is managed using a bitmap for example. In so doing in the processing of step the data written to the storage apparatus is read from the storage apparatus and data not yet written to the storage apparatus is read from a buffer for example whereby file data can be sent to another PaaS site without waiting for file writing to end. The PaaS server program receives a response from the PaaS site step . The PaaS server program judges from the received response whether or not a file with an extended UUID identical to the original VM UUID has been found from the PaaS sites managed by the PaaS sites to which the request was sent step .

When a file found judgment is made the PaaS server program executes the processing of step . When a no file found judgment is made the PaaS program executes the processing of step . Since it is determined that the file has been saved to another PaaS site the data of the virtual machine file is deleted from the storage apparatus of the PaaS site executing this processing and registration information of the virtual machine file is deleted from the file management table step . The PaaS server program sends a success response to the request to the write request source SaaS site step .

As described hereinabove for virtual machine file backup by checking during backup that a file with an identical UUID in the virtual machine file has not been saved in the backup target PaaS site only the internal data of the file data are used without using metadata of the file data thereby making it possible to avoid storing the backup file in the same PaaS site as the backup source PaaS site where the original file is present. Consequently even when a disaster involving data loss occurs at one PaaS site one of the original file and the backup file thereof still remains available.

When the second embodiment described above and one or more modifications of the second embodiment are considered the computer system according to the second embodiment can be implemented as follows for example.

In other words the backup apparatus adds to the backup data backup identification information extended UUID for example which is identification information including original data identification information the UUID for example and an identifier of a logical volume serving as the backup data storage target and sends a request to store the backup data to which the backup identification information was added. The storage request may be sent to the storage system via a relay apparatus such as a SaaS server or may be sent to the storage system without passing via such a relay apparatus.

After receiving the request to store the backup data to which the backup identification information was added the first storage system judges in response to the received storage request whether or not identification information identical to the identification information included in the backup identification information added to the backup data is being managed and stores the backup data when the judgment result is negative.

In cases where the judgment result is positive the first storage system or a relay apparatus for relaying the storage request selects a second storage system which belongs to an organization and or location different from an organization and or location to which the first storage system belongs on the basis of organization location information indicating the organizations and or locations to which storage systems coupled to the first storage system or relay apparatus belong and sends a storage request for backup data to which backup identification information was added to the second storage system. In other words a storage request may be sent from the first storage system to the second storage system without passing via a relay apparatus such as a SaaS server or the relay apparatus may send a storage request to the second storage system in cases where an error response is received from the first storage system.

Note that after receiving the storage request the second storage system may perform a judgment of whether identification information identical to the identification information included in the backup identification information added to the backup data is being managed in the same way as the first storage system.

Furthermore the second storage system to which the storage request is sent may be a storage system that belongs to a location farthest from the location to which the first storage system belongs.

In addition in cases where any storage system coupled to the first storage system or the relay apparatus is a storage system identical to that of an organization and or location to which the first storage system belongs the first storage system or relay apparatus may upon receiving a storage request return an error to the backup apparatus. In this case the backup apparatus may send the storage request to a storage system or relay apparatus different from the first storage system or relay apparatus.

In Embodiment 3 the SaaS server supplies information relating to the location and organization to which the SaaS vendor providing the SaaS server belongs to the user server via an API. Likewise the PaaS server supplies information relating to the location and organization to which the PaaS vendor providing the PaaS server belongs to the user server via an API. The user server checks for an overlap between the backup source and backup target on the basis of the information relating to the locations and organizations. Consequently the organization and location of the backup target can be made different from the organization and location of the backup source.

Differences from the second embodiment and the first embodiment will mainly be described hereinbelow and points in common with the second embodiment and the first embodiment will be described simply or omitted.

In this embodiment the backup program executed by the user server judges whether there is an overlap between the backup source and the backup target.

The programs and information shown in are stored in the memory in the user server. A backup program judges whether or not there is an overlap between the backup source and the backup target. A SaaS client program performs access to an API.

In the memory see within the PaaS server the PaaS server program is a HTTP Hypertext Transfer Protocol or SOAP REST Simple Object Access Protocol Representational State Transfer program or similar. The PaaS server program has a function for reading the organization name and the storage location from the table shown in and responding via an API for example.

In the memory see within the SaaS server the SaaS server program is an HTTP or SOAP REST program or similar. The SaaS server program has a function for reading the organization name and the storage location from the table shown in and responding via an API for example.

Note that the following tables are used in embodiment 3 a SaaS management table a schedule management table a backup management table a file management table the UUID part is unused an organization management table an PaaS site file management table the UUID parts are unused a PaaS site PaaS management table a SaaS site PaaS management table a SaaS site organization management table and a SaaS site file management table .

The backup program performs backup processing in on the basis of the backup schedule see . According to organization location check processing is performed before starting a backup in other words before starting the processing shown in step in . Note that according to when step yields YES the processing returns to step whereas in this embodiment according to when step yields YES the processing returns to step .

 Step The backup program acquires from the backup source file original file the SaaS ID corresponding to the file name see of the file. The backup program acquires the IP address corresponding to the acquired SaaS ID from a SaaS management table . The backup program uses an API to acquire information organization name and storage location relating to the PaaS site managed by the SaaS server from the SaaS server on the basis of the acquired IP address . Note that the PaaS server program and the SaaS server program each use an API when returning the organization name and the storage location information location information . Examples of APIs in this embodiment are shown in . These APIs perform access using the HTTP protocol as illustrated earlier in a user server or SaaS server returns a return value including organization name and storage location information under a GET environment.html instruction.

 Step The backup program acquires a SaaS ID of the SaaS site that is the default backup target of the backup target file. The backup program acquires the IP address corresponding to the acquired SaaS ID from the SaaS management table . The backup program acquires information organization name and location information relating to the PaaS site managed by the SaaS server from the SaaS server using an API on the basis of the acquired IP address . Note that the PaaS server program and the SaaS server program each use an API when returning organization name and storage location information location information .

 Step Based on information acquired in steps and a backup program performs a comparison to determine whether there is a match between the organization and location to which the PaaS site storing the original file belongs and the organization and location to which the PaaS site storing the backup file belongs this judgment may also be performed for only the organization or the location . This comparison may be performed in order starting with the location farthest from the location to which the PaaS belongs and where the original file is stored. Thus the farthest location is easily selected resulting in a reduced likelihood of data loss caused by a large scale disaster.

 Step The backup program judges whether a match is obtained from the results of the comparison in step .

 Step When the result of the judgment of step is a match the backup program selects a SaaS site different from the SaaS server SaaS site in step as the backup target the detailed steps are shown in .

After the organization location check processing the backup file is written. The backup file write target is the PaaS site hereinafter called the target PaaS site at this stage acquired in step in cases where step yields no match . A backup file write request is sent to the SaaS site in step and sent to the target PaaS site from the SaaS site.

When the third embodiment above and one or more modifications of the third embodiment are considered the computer system according to the third embodiment can be implemented as follows for example.

The backup apparatus acquires organization location information indicating organizations and or locations to which two or more storage systems among a plurality of storage systems belong. More specifically for example the backup apparatus sends an acquisition request for storage system related organization location information to all managed relay apparatuses SaaS servers for example . After receiving the acquisition request the storage systems send storage system related organization location information for example organization name and or storage location information to the relay apparatus which sent the acquisition request. Furthermore if a storage system manages another storage system the former sends an acquisition request to the other storage system. Consequently the storage system receives organization location information relating to the other storage system from the other storage system if a further storage system is coupled directly or indirectly to the other storage system the other storage system receives organization location information relating to the further storage system . The storage systems send the received organization location information to the relay apparatus that sent the acquisition request. The relay apparatus sends the organization location information received from the storage system to the backup apparatus. In this way the backup apparatus is able to acquire organization location information relating to all the storage systems.

Furthermore on the basis of organization location information for a plurality of storage systems the backup apparatus specifies one or more second storage systems which belong to an organization and or location different from the organization and or location to which the storage system storing the original data belongs and is able to display the specified one or more second storage systems as recommended backup data storage targets. The backup apparatus is able to send a backup data storage request to a second storage system selected by the user from one or more second storage systems or to a relay apparatus coupled to the selected second storage system.

Note that among one or more second storage systems a second storage system belonging to a location farthest from the location to which the first storage system belongs is most recommended.

Furthermore the backup apparatus may perform organization location information acquisition when performing a backup of the original data.

In addition the backup apparatus may receive a storage system address IP address for example from each relay apparatus instead of acquiring the organization location information of the storage system from the relay apparatuses and may acquire organization location information directly from the storage systems using these addresses. An embodiment in which communication takes place via the SaaS site has been described. However if the PaaS management table is managed by the user site and the requests to the SaaS sites and the processing by the SaaS sites is performed by the PaaS sites a case where files are stored in the PaaS sites directly without passing via the SaaS sites can also be adopted. The storage system storing the original data may be in a local network to which the backup apparatus is coupled. In this case values configured by the administrator of the user site using the backup program prior to backup processing are employed for organization location information of the storage system where the original data is stored.

A fourth embodiment of the present invention will be described hereinbelow. In so doing differences from the first embodiment will mainly be described and points in common with the first embodiment will be described simply or omitted.

The storage apparatus of the PaaS site may be NAS Network Attached Storage and have a RAIN Redundant Array of Inexpensive Nodes configuration.

In this case as shown in a PaaS server divides a write target file into chunks namely a file a a file b and a file c and stores these chunks by distributing them between a plurality of storage apparatuses A to C. Here the PaaS server may generate parity data for file and store the parity data in a storage apparatus D to enable recovery of the file even when one storage apparatus stops operating due to damage. The number of divisions of the file in which the parity data is included may be equal to or less than the number of storage apparatus constituting the RAIN. A case with fewer divisions will be described by way of example hereinafter. Note that fragments to of the file will be referred to hereinafter as file chunks and that file chunks file fragment data and parity data will be referred to generally as subdata .

The memory stores a RAIN program a storage management table a node management table and a file management table . The RAID program performs file division parity data generation and file storage in the LU .

The storage management table is a table that has information relating to the storage apparatus including the table . The table includes for example a storage ID an IP address and a storage location .

The IP address is an IP address used to communicate with the storage apparatus in order to store data.

The storage location is information indicating the location where the storage apparatus is installed. The value of the storage location may be the name of a country or continent for example.

The node management table includes a storage ID an IP address and a storage location for each storage apparatus node capable of communicating with the storage apparatus holding the table . The storage ID corresponds to the storage ID of the storage apparatus . The IP address corresponds to the IP address of the storage apparatus. The storage location corresponds to the storage location of the storage apparatus.

The node management table is created when the PaaS administrator registers a storage apparatus that is to serve as a component in the RAIN configuration.

The file management table includes for each subdata item a local ID a chunk ID a path name a file name a storage ID a type a UUID and an extended UUID .

The storage ID is corresponds to the storage ID of the storage apparatus where the subdata is stored.

The type is information for identifying whether the subdata is a file chunk or parity data. A file chunk is registered as data while parity data is registered as parity .

The extended UUID is an ID similar to the extended UUID the same extended UUID being registered for the same file name .

In this embodiment when the storage apparatus has a NAS RAIN configuration the RAIN program is able to perform the processing of the PaaS server program . In cases where a file is stored discretely between storage apparatuses the RAIN program stores the file chunks and parity data so that the storage IDs of the storage apparatuses storing these data are all different. When a backup file has a UUID identical to the UUID of the original file in an extended UUID the RAIN program stores the file chunks and parity data of the backup file so that the storage ID of the storage apparatus storing this data and the storage ID of the storage apparatus storing the file chunks and parity data of the original file are completely different. Thus one of the original file and the backup file can be preserved even when data are lost at the same time due to damage from two storage apparatuses constituting the RAIN.

Note that the RAIN program may also store file chunks and parity data of the backup file so that instead of the storage ID the storage location corresponding to the file chunks and file data of the backup file is completely different from the storage location corresponding to the file chunks and parity data of the original file. Thus one of the original file and the backup file can be preserved even when data are lost at the same time due to a large scale disaster from two storage apparatuses that constitute the RAIN and belong to the same location.

As a storage apparatus for storing backup subdata file chunks and parity data of the backup file corresponding to the original subdata file chunks and parity data of the original file a storage apparatus which belongs to a storage location farthest from the storage location of the storage system storing the original subdata may be selected. Consequently there is an increased likelihood of preserving one of the original file and the backup file even if a region wide large scale disaster should occur.

Depending on the RAID level of the RAIN configuration for N where N is an integral number storage apparatuses the storage ID and the storage location of the storage apparatus storing the original subdata and the storage ID and the storage location of the storage apparatus storing the backup subdata may be identical. For example depending on the RAID level a file can be recovered even when one or more storage apparatuses are damaged where N is the maximum number of storage apparatuses in which damage may occur. More specifically when the RAID level is RAID5 N 1 and when the RAID level is RAID6 N 2 for example.

In cases where the RAIN program carries out the processing in an error is not returned when an identical UUID exists but an error is returned when it is not possible to make the storage ID of the subdata of the original file completely different from the storage ID of the subdata of the backup file or when it is not possible to make all the storage location information location information different.

The user server or SaaS server may also store a plurality of subdata based on an original file and a plurality of subdata based on a backup file such that the subdata are distributed between a plurality of storage systems at a plurality of PaaS sites. In this case a predetermined number of second storage systems N second storage systems corresponding to the RAID level of the RAIN configuration for example among a plurality of second storage systems where a plurality of subdata based on the backup file are stored are storage systems belonging to organizations and or locations different from organizations and or locations to which a plurality of first storage systems storing a plurality of subdata based on the original file respectively belong.

A fifth embodiment of the present invention will be described hereinbelow. In so doing differences from the first embodiment will mainly be described and points in common with the first embodiment will be described simply or omitted.

Suppose that a user site PaaS site A PaaS site B PaaS site C SaaS site A and SaaS site B exist for example. The user server in the user site is coupled to a SaaS server A in the SaaS site A and to a SaaS server B in the SaaS site B. The SaaS server A is coupled to a PaaS server A in the PaaS site A and to a PaaS server B in the PaaS site B. The PaaS server A is coupled to a PaaS server C in the PaaS site C. The SaaS server B is coupled to the PaaS server B.

In this configuration suppose that the PaaS site A has been unable to store a backup file sent to the PaaS site A. In this case the routes that may be selected as the route for storing the backup file are as follows starting with the highest ranking route first 

In other words the smaller the number of hops number of communications a route has the higher its ranking. That is route R1 is a route via which communication is performed from PaaS site A to PaaS site C backup file transfer for example in other words a route for which the number of hops is 1 . Route R2 is a route via which communication is performed from PaaS site A to SaaS site A and from SaaS site A to PaaS site B in other words a route for which the number of hops is 2 . Route R3 is a route via which communication is performed from PaaS site A to the user site from the user site to SaaS site B and from SaaS site B to PaaS site B in other words a route for which the number of hops is 3 . Hence R1 has the highest ranking while R3 has the lowest ranking. Therefore in concrete terms when the present embodiment is applied to the first and second embodiments for example the PaaS server A is configured to transfer a backup file via route R1. When the backup file cannot be stored via route R1 when the PaaS server C is damaged for example the PaaS server A stores the backup file via route R2. When the backup file cannot be stored via route R2 either when the PaaS server C is damaged for example the PaaS server A sends an error response. The error response is received by the user site via the SaaS server A. Upon receiving this error response the backup program executed by the user server stores the backup file via route R3.

Furthermore when the present embodiment is applied to the third embodiment for example the backup program executed by the user server may display recommended storage targets in accordance with the aforementioned ranking order.

Several embodiments of the present invention have been described hereinabove but the present invention is not limited to these embodiments. It is understood that a variety of modifications are possible within a scope not departing from the spirit of the present invention.

For example the SaaS site need not feature in any of the above embodiments. In other words a file may be stored in the PaaS site from the user site without passing via the SaaS site . In this case the PaaS client program and the PaaS management table may be stored in the memory in the user server .

In addition two or more of the first to fifth embodiments may be combined. At least one of the following combinations to P may be adopted for example 

