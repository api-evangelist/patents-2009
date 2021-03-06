---

title: Reuse of document print attributes
abstract: An information processing apparatus includes a storing unit configured to store, in a storage device, print setting information including a hierarchical structure of a document and a print attribute associated with a hierarchical level of the document, and a setting unit configured to, when the print attribute in the print setting information stored in the storage device is applied to a selected document, compare a hierarchical structure of the selected document and the hierarchical structure of the print setting information and to set a print attribute to an appropriate hierarchical level of the selected document based on a comparison result and the print attribute of the print setting information.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08368926&OS=08368926&RS=08368926
owner: Canon Kabushiki Kaisha
number: 08368926
owner_city: Tokyo
owner_country: JP
publication_date: 20090218
---
The present invention relates to an information processing apparatus an information processing method and a computer readable storage medium.

Microsoft has announced a plan to support an extended markup language XML paper specification XPS which is a new XML based document format by Windows Vista XML Paper Specification Overview search results as of Feb. 15 2008 . An XPS document has a document format including three hierarchical levels called FixedDocumentSequence FixedDocument and FixedPage. XML documents containing print attributes referred to as print tickets can be associated with nodes of each hierarchical level. Print Ticket and Print Capabilities Support in Windows Printer Drivers search results as of Feb. 15 2008 . A job level print ticket is associated with FixedDocumentSequence. Further a document level print ticket is associated with FixedDocument1. Further a page level print ticket is associated with FixedPage1.

Since the print ticket can be specified for each node of each hierarchical level an XPS document can change for example an output size for each FixedPage or stapling setting for each FixedDocument. As mentioned in XML Paper Specification Overview the XPS document has an aspect of a print spooler format used during printing and another aspect of an ordinary document. Regarding the document aspect the XPS document can be used as a document format for publishing and distributing various documents in the same manner as a page description format PDF file. As described above the XPS document can retain a print ticket for each node of the hierarchical levels and as a result it is possible to create and distribute XPS documents associated with print attributes.

Further the XPS document includes an exception setting function which allows a user to specify different print attribute settings for each page in addition to print attribute settings for an entire job. For example in a case where a user creates a document including a plurality of sections the user may desire to use colored paper for first pages of the sections and white paper for the rest of the pages. In such a case the user makes a setting to use white paper for the entire job and use colored paper only for the first page of each section that is different from the print attribute settings for the entire job. Specifying the different print attribute settings is not limited to a paper type color to be used. There are cases in which a user may desire other kinds of setting for example a paper size one sided two sided printing finishing and color settings for a specific page or a range of pages to be different from the print attribute settings of the entire job. Refer to Japanese Patent Application Laid Open No. 2004 110638 and Japanese Patent Application Laid Open No. 2005 250606 .

When different print attribute settings are set for each page in a printer driver or an application following procedures are often used.

Further in a printer driver a print template function is installed which exports and applies favorite print attributes to other documents. With regard to a printing method such as a DEVMODE printing and a job definition format JDF printing which can output print attribute settings for the entire job together with the exception setting in one file the print template function can be realized such that the print attributes are exported as one file stored in a printer driver and applied to a target document in such printing methods.

However in a case of printing an XPS document since the print attributes are associated with each of the hierarchical levels the print attributes are output as a plurality of files if they are directly exported. Further it is difficult to identify the page which the print attribute is associated with so that the print template function cannot be realized.

The present invention is directed to allow reuse of a print attribute of a document having a hierarchical structure so that a user can easily set the print attribute to the document having the hierarchical structure.

According to an aspect of the present invention an information processing apparatus includes a storing unit configured to store in a storage device print setting information including a hierarchical structure of a document and a print attribute associated with a hierarchical level of the document and a setting unit configured to when the print attribute in the print setting information stored in the storage device is applied to a selected document compare a hierarchical structure of the selected document and the hierarchical structure of the print setting information and to set a print attribute to an appropriate hierarchical level of the selected document based on a comparison result and the print attribute of the print setting information.

According to another aspect of the present invention a method for processing information in an information processing apparatus includes storing in a storage device print setting information including a hierarchical structure of a document and a print attribute associated with a hierarchical level of the document and when the print attribute in the print setting information stored in the storage device is applied to a selected document comparing a hierarchical structure of the selected document and the hierarchical structure of the print setting information and setting a print attribute to an appropriate hierarchical level of the selected document based on a comparison result and the print attribute of the print setting information.

Further features and aspects of the present invention will become apparent from the following detailed description of exemplary embodiments with reference to the attached drawings.

Various exemplary embodiments features and aspects of the invention will be described in detail below with reference to the drawings.

Referring to the printing system includes a client PC and a client PC which are examples of an information processing apparatus or a computer and a printer that can communicate each other via a network i.e. a communication medium. Two similarly configured client PCs and are illustrated to indicate that there is a plurality of client PCs on the network. Hereinafter only the client PC will be used to describe the present exemplary embodiment.

A plurality of applications for creating documents and a printer driver for outputting application data to the printer are installed in the client PC . Functions other than the printer driver such as a hot folder for outputting the application data to the printer can be installed in the client PC as long as the functions can set print attributes.

Referring to a central processing unit CPU controls each of the processes performed by the client PC. A read only memory ROM is non rewritable and stores programs and data related to each of the processes performed by the client PC. A random access memory RAM is rewritable and electrically stores temporary data related to each of the processes performed by the client PC.

The client PC stores programs and data temporary data and application data related to each of the processes performed by the client PC in a hard disk drive HDD .

An input device is a keyboard and a pointing device for inputting an instruction to the client PC. A display device displays an operation status of the client PC and information output from each program operating on the client PC.

A network interface I F connects to a local area network LAN and the Internet via the network and exchanges information with external devices. An external device I F connects to external storage devices. The above described devices are connected to each other via a system bus and exchange data.

The CPU realizes functions or processes of an operating system OS or the printer driver to be described below by executing processes based on programs that correspond to the OS and the printer driver stored in the HDD .

The printer driver displays on the display device a GUI an operating screen or a tab sheet which has a display screen structure suitable for a user to instruct an output operation such as printing by the printer . The printer driver sets setting parameters of print attributes print attributes desired by the user according to a user key operation. Further the printer driver performs control to transmit the set print attributes to a transmission destination or an output destination device such as a printer via a communication medium e.g. a network together with an image data document data or a document desired by the user.

Further the printer driver displays a GUI for setting the print attributes on the display device according to the user key operation. When the user issues an instruction to display a tab sheet related to a printer by the key operation on the GUI the printer driver displays the tab sheet related to the printer on the display device .

Referring to a printer driver window which is a tab sheet for setting the print attributes includes a transmission destination selection column for selecting a target output destination. The user selects a desired output destination transmission destination device in the present system via the transmission destination selection column displayed on the screen.

A page setting control is used to select a page to be output from a job. The user uses the page setting control to determine which page in image data created by application software operating on the client computer is to be output. The printer driver thus allows the user to select a page to be printed out in the output destination device e.g. a printer in the present system via the page setting control displayed on the screen. Further the printer driver allows the user to print all pages or a specific page using the page setting control .

A copy number setting control is used to specify a number of copies of the job to be printed out by the output destination device e.g. the printer in the present system. The user can increase or decrease the number of copies by moving a cursor to the copy number setting control and clicking on one of arrows of a scroll bar set on the copy number setting control .

A property key is used to specify detailed settings of the output destination device selected in the transmission destination selection column . When the user presses the property key i.e. inputs a cue the printer driver responds and performs control to display on the display device various detail screens illustrated in . After the user finishes specifying the desired settings via the various operation screens illustrated in printing can be started according to the settings desired by the user by pressing an OK button . On the other hand the user can cancel the settings by pressing a close key . As a result the printer driver discards the previous user settings and terminates displaying the printer driver window .

The GUI includes tab sheets such as page settings finishing paper supply print quality and the like. The user can set various detailed print output conditions related to page settings finishing paper supply and print quality by pressing on the tab sheets. The user presses a key or the tab sheet using an input device such as a pointing device.

The user selects favorite print attribute settings that the user wants to use from a previously registered favorite settings list via a favorite settings portion . When the user selects the favorite the printer driver automatically sets the print attributes associated with the favorite as the current print attributes and also sets the print attributes on the screen.

When the user presses an add to favorite button the printer driver adds the print attributes displayed on the screen when the user pressed the button as a favorite to the favorite settings list. Further when the user presses an edit favorite button the printer driver opens displays a favorite settings editing screen illustrated in and allows the user to edit a setting item in the favorite settings. illustrates an example of the favorite settings editing screen. A favorite is a function for naming print setting information and registering the print setting information in the printer driver. Further the name of the favorite and the print setting information that corresponds to the name can be added and corrected by the user as necessary.

In the favorite settings editing screen illustrated in the favorite settings lists that are currently registered are displayed in a favorite settings list display portion . When the user selects a favorite setting in the favorite settings list display portion and presses a delete button the printer driver deletes the selected favorite setting. Further the user can change the name of the selected favorite setting via a name text box .

When the user presses a file read button the printer driver opens a file selection dialog and reads the favorite setting that is stored as a file and selected via the file selection dialog. The printer driver then registers the read file as the favorite settings. Otherwise the printer driver extracts print attributes of a file selected by the user via the file selection dialog and registers the extracted print attributes as the favorite settings. Further when the user presses a save button the printer driver saves the favorite settings that the user selected in the favorite settings list display portion as a file.

When the user selects presses the finishing tab on the operation screen illustrated in by a key operation the printer driver displays an operation screen illustrated in on the display device .

For example the printer driver controls the printer selected via the operation screen illustrated in to print a print target job according to a two sided printing mode which is set by the user via a setting portion in the operation screen illustrated in . Further the printer driver controls the printer to perform two sided printing based on a long side binding setting in the two sided printing mode set by the user via a setting portion . When the user presses a restore default setting button on the operation screen illustrated in the printer driver performs control to return the print setting details to initial values.

Further if the user presses an OK button the printer driver enables the user settings and returns to the screen illustrated in . On the other hand if the user presses a cancel button the printer driver cancels the user settings and returns to the screen illustrated in .

Similarly the user can press the paper supply tab and select or specify a page input bin or the like or press the print quality tab and select or specify a resolution and a halftone setting not illustrated .

A method for specifying a setting to a certain page or a range of pages more specifically a setting that is different from the settings for the entire job or a setting that is different from the default setting in the job will be described below. Specifying of a different setting to a certain page or a range of pages is referred to as specifying page exception settings .

In the special settings tab sheet illustrated in a front cover back cover button is used to set a front cover and a back cover separately from the text data. A paper insertion button is used to set a paper to be inserted separately from the text data. An exception page button is used to specify settings for a certain page or a range of pages that are different from the settings for the entire job. Further a special settings list displays a list of items that are set different from the entire job by using the above described buttons and . The special settings list includes columns indicating a page or a range of pages to which the setting is to be specified setting items and setting contents from left to right. The display in only illustrates an example and the printer driver can display the operation screen in other format and other items.

A merge list button is used to merge the list when adjacent pages or range of pages are set the same as to a group of special settings displayed in the special settings list . More specifically the user selects the adjacent settings to be merged from the special settings list and presses the merge list button . As a result the printer driver merges the special settings.

A delete button is used when the user wants to delete a setting among the group of special settings listed in the special settings list . The user first selects the setting to be deleted from the special settings list and presses the delete button then the printer driver deletes the setting.

A set button is used when the user wants to change a content of a setting in the group of special settings displayed in the special settings list . The user first selects from the special settings list the setting whose content is to be changed and presses the set button then the printer driver changes the setting.

Referring to a control is used to set a page or a range of pages to which a setting is made. If the user wants to specify a certain page the user enters the same page number to a start page and an end page to apply page exception setting so that values set by controls described below are applied only to the page.

A control is used to specify a setting that is different from the settings for the entire job to the page or the range of pages set in the control . A setting as to a media can be specified using the control . More specifically a paper type a paper size and one sided two sided printing can be set using the control .

A control is used to specify a setting that is different from the settings of the entire job to the page or the range of pages set using the control . More specifically a color mode half toning and input profile can be set using the control .

The user specifies a desired setting using the various controls illustrated in and presses an OK button so that the desired setting is applied. If the setting is to be cancelled the user presses a cancel button . Consequently the printer driver discards the setting content and ends displaying the dialog illustrated in .

As described above the user can specify the page exception setting using the special settings tab sheet illustrated in and the exception page setting dialog illustrated in . The above described page exception setting method is an example and the page exception setting can be specified using other methods.

A control is used to set a paper supply option to be installed and a control is used to set a paper discharge option to be installed. The user specifies a desired setting using the various controls illustrated in and presses an OK button so that the desired setting is applied. If the setting is to be cancelled the user presses a cancel button . The printer driver then discards the setting content and returns to the screen illustrated in .

The printer driver includes a user I F driver and a graphic driver . The user I F driver displays a user interface UI and saves settings. The graphic driver converts a print rendering instruction received from the application program via the OS into a code that can be interpreted by the printer. If the application program instructs a setting of a print attribute via the OS the user I F driver displays the print attribute setting dialog and the tab sheets illustrated in on the display device .

The print attributes set by the user via the user I F driver are stored in a printer driver setting storage area within a storage area which is controlled by the OS . Further the user I F driver the graphic driver and the application program can access the printer driver setting storage area via the OS and read the print attributes set by the user.

Further a communication I F of the client PC and a communication I F of the printer are connected by a communication medium such as a network. The graphic driver can transmit print data to the printer via the OS . Further the graphic driver can acquire configuration information and status information about the printer via the OS .

A process flow in which the user selects a print menu from an application menu sets print attributes on the printer driver and performs printing will be describe below.

In step S the application program calls an application programming interface API of the OS and instructs the printer driver to display a tab sheet for setting the print attributes. At this time the application program obtains an area in a memory for storing the print attributes i.e. a print attribute setting area and designates the print attribute setting area to the API. When the instruction is received the OS instructs the printer driver to display the tab sheet for setting the print attributes.

In step S upon receiving the instruction the user I F driver in the printer driver displays the tab sheet for setting the print attributes illustrated in .

In step S the printer driver acquires setting values related to the print attributes set in the tab sheet or the dialog illustrated in described above. The set print attributes are fixed when the user presses the OK button in the tab sheet illustrated in after the user sets the print attributes.

When the user presses the OK button in step S the user I F driver in the printer driver stores the setting values related to the print attributes set by the user in the print attribute setting area instructed by the API call in step S. As a result the print attributes are set and the setting values related to the print attributes are stored.

In step S the application program calls the API of the OS and instructs the printer driver to start printing. In this process the printer driver may once display the tab sheet for setting the print attributes illustrated in . Before instructing print start the application program designates the print attribute setting area in the memory to the API in the OS . Upon receiving the print instruction the OS instructs the printer driver to start printing.

In step S the graphic driver in the printer driver reads out the setting values of the print attributes stored in the print attribute setting area designated in the print start instruction. The graphic driver then generates a print attribute setting code and transmits the generated code to the printer to instruct printing.

In step S the graphics driver which received the print rendering instruction via the OS converts the print rendering instruction to a print code that can be interpreted by the printer and transmits the print code to the printer .

In step S the printer renders the received print rendering code and performs printing. Then the print job is completed.

A problem which arises when a favorite function of the printer driver is applied to a document which has a hierarchical structure as illustrated in will be describe below. illustrates an example of a document which has a hierarchical structure.

A conventional favorite function previously stores a print attribute group associated with a favorite name and when the favorite name is selected the favorite function applies settings of the print attribute group associated with the favorite name. The print attribute group can include various print attributes but does not include a hierarchical structure of a document hierarchical structure information . Therefore if a favorite print attribute group is applied to the document which has the hierarchical structure as illustrated in using the conventional favorite function the printer driver cannot determine to which hierarchical level the favorite print attribute group is set. Thus the favorite print attribute group cannot be applied to the document.

To solve such a problem a method for registering print attributes of an XPS document as a favorite from the printer driver and a process for applying the print attributes of the XPS document registered as the favorite to other XPS documents will be described below.

In a case where the user registers an XPS document as a template using the screen illustrated in the user presses a file read button and the printer driver allows the user to select an XPS file in addition to a print attribute file. If the user selects both the XPS file and the print attribute file the printer driver reads and stores the XPS document including the print attributes and the hierarchical structure of the XPS file as the template.

According to the present exemplary embodiment the XPS document in which the print attributes are associated with the hierarchical structure as illustrated in is registered as the favorite and the favorite print attributes can be applied to other XPS documents. When the favorite print attributes are applied to the other XPS documents the exception print attributes that are associated with the hierarchical structure parts can also be applied as the print attributes to the other XPS documents based on processes illustrated in flowcharts of to be described below. Examples in which the favorite is applied to the XPS documents which have a plurality of types of the hierarchical structures will be described below.

A case where the XPS document illustrated in is applied as the favorite to an XPS document which has a hierarchical structure illustrated in will be described. illustrates an example of a document which has a hierarchical structure. The printer driver acquires the hierarchical structure from the XPS document illustrated in and compares the acquired hierarchical structure with the hierarchical structure of the XPS document to be applied as the favorite. The hierarchical structure including hierarchical structure parts to is similar to the hierarchical structure of the XPS document to be applied which includes the hierarchical structure parts to . Therefore the printer driver applies the print tickets to to the corresponding hierarchical structure parts in the XPS document illustrated in .

A case where the XPS document illustrated in is applied as the favorite to an XPS document which has a hierarchical structure illustrated in will be described. illustrates an example of a document which has a hierarchical structure. The printer driver acquires the hierarchical structure from the XPS document illustrated in FIG. . The printer driver then compares the acquired hierarchical structure with the hierarchical structure of the XPS document to be applied as the favorite which includes the hierarchical structure parts to . Consequently the hierarchical structure including hierarchical structure parts to of the XPS document illustrated in lacks the hierarchical structure part that corresponds to the hierarchical structure part which is the second page of the second section. Therefore the printer driver does not apply the print ticket which is specified to the hierarchical structure part to the XPS document which has the hierarchical structure illustrated in . Instead the print driver applies the print tickets to to the corresponding hierarchical structure parts in the XPS document which has the hierarchical structure illustrated in . illustrates an example in which the favorite XPS document illustrated in is applied to the XPS document illustrated in .

A case where the XPS document illustrated in is applied as the favorite to an XPS document which has a hierarchical structure illustrated in will be described. illustrates an example of a document which has a hierarchical structure. The printer driver acquires the hierarchical structure from the XPS document illustrated in . The printer driver then compares the acquired hierarchical structure with the hierarchical structure of the XPS document to be applied as the favorite.

The hierarchical structure illustrated in including hierarchical structure parts to is different from the hierarchical structure parts to of the XPS document to be applied in that a number of the hierarchical structure part corresponding to the third page of the second section is greater. Therefore the printer driver applies the print tickets to to the corresponding hierarchical structure parts. Further the printer driver applies the print attributes associated with an upper level hierarchical structure part of the hierarchical structure part to the hierarchical structure part since a print ticket is not specified to the hierarchical structure part the print ticket specified to the hierarchical structure part which is on a further upper level is applied to the hierarchical structure part . illustrates an example of applying the favorite XPS document illustrated in to the XPS document illustrated in .

Further a case where the XPS document illustrated in is applied as the favorite to an XPS document which has a hierarchical structure illustrated in will be described. illustrates an example of a document which has a hierarchical structure. The printer driver acquires the hierarchical structure from the XPS document illustrated in . The printer driver then compares the acquired hierarchical structure with the hierarchical structure of the XPS document to be applied as the favorite which includes the hierarchical structure parts to . Consequently the hierarchical structure illustrated in which includes hierarchical structure parts to does not include the hierarchical structure part corresponding to the hierarchical structure part illustrated in that corresponds to the second page of the second section. Therefore the printer driver does not apply the print ticket specified to the hierarchical structure part .

Further the hierarchical structure parts to are different from the hierarchical structure parts to to be applied as the favorite in that a number of the hierarchical structure parts and corresponding to the third section in the XPS document is greater. Therefore the printer driver applies the print attributes specified to the upper level hierarchical structure part the print ticket to be applied to the hierarchical structure to the hierarchical structure parts and . Further the printer driver applies the print tickets to to the corresponding hierarchical structure parts. illustrates an example in which the favorite XPS document illustrated in is applied to the XPS document illustrated in .

In step S the printer driver acquires the XPS document which is associated with the favorite name selected by the user.

In step S the printer driver acquires a hierarchical structure to be referred to as hierarchical structure information K and print attributes from the XPS document acquired in step S.

In step S the printer driver acquires hierarchical structure information K from the XPS file to which the favorite print attributes will be applied.

In step S the printer driver applies the print attributes of FixedDocumentSequence in the hierarchical structure information K to the FixedDocumentSequence in the hierarchical structure information K.

In step S the printer driver acquires the first FixedDocument of the hierarchical structure information K and the first FixedDocument of the hierarchical structure information K.

In step S the printer driver compares the two FixedDocuments acquired in step S. If the printer driver determines that both FixedDocuments exist as a result of the comparison BOTH EXIST in step S the process proceeds to step S. On the other hand if the printer driver determines that the FixedDocument exists only in the hierarchical structure information K ONLY K EXISTS in step S the process proceeds to step S. Further if the printer driver determines that the FixedDocument exists only in the hierarchical structure information K ONLY K EXISTS in step S the process proceeds to step S.

In step S the printer driver applies sets the print attributes of the FixedDocument in the hierarchical structure information K to the FixedDocument in the hierarchical structure information K.

In step S the printer driver applies the print attributes to Fixedpage which belongs to a lower level of the FixedDocument in the hierarchical structure information K. Hereinafter the FixedDocument in the hierarchical structure information K will be referred to as the FixedDocument D and the FixedDocument in the hierarchical structure information K will be referred to as the FixedDocument D. The process performed in step S will be described in detail below with reference to .

In step S the printer driver applies the print attributes of the FixedDocumentSequence in the hierarchical structure information K as the print attributes of the FixedDocument D.

In step S the printer driver acquires subsequent FixedDocuments in the hierarchical structure information K and the hierarchical structure information K respectively.

In step S the printer driver confirms the two FixedDocuments acquired in step S and determines whether the subsequent FixedDocument exists in either of the hierarchical structure information K and the hierarchical structure information K. If the printer driver determines that the subsequent FixedDocument exists in either the hierarchical structure information K or hierarchical structure information K YES in step S the process returns to step S. If the printer driver determines that there is no subsequent FixedDocument in either the hierarchical structure information K or the hierarchical structure information K NO in step S the process ends.

In step S the printer driver acquires the first FixedPage of the FixedDocument D and the first FixedPage of the FixedDocument D respectively.

In step S the printer driver compares the two FixedPages acquired in step S. As a result of comparison if the printer driver determines that both FixedPages exist BOTH EXIST in step S the process proceeds to step S. If the printer driver determines that the FixedPage exists only in the FixedDocument D ONLY D EXISTS in step S the process proceeds to step S. Further if the printer driver determines that the FixedPage exists only in the FixedDocument D ONLY D EXISTS in step S the process proceeds to step S.

In step S the printer driver applies the print attributes of the FixedPage in the FixedDocument D to the FixedPage in the FixedDocument D.

In step S the printer driver applies the print attributes of the FixedDocument D to the FixedPage in the FixedDocument D.

In step S the printer driver acquires subsequent FixedPages in the FixedDocument D and the FixedDocument D respectively.

In step S the printer driver confirms the two FixedPages acquired in step S and determines whether the subsequent FixedPage exists in either of the FixedDocument D or FixedDocument D. If the printer driver determines that the subsequent FixedPage exists in either of the FixedDocument D or FixedDocument D YES in step S the process returns to step S. On the other hand if the printer driver determines that there is no subsequent page in both of the Fixed Document D and Fixed Document D NO in step S the process ends.

Another method for registering the favorite will be described below as a second exemplary embodiment of the present invention.

When the user registers an XPS document as a template using the screen illustrated in the user presses the file read button and the printer driver allows the user to select an XPS file in addition to a print attribute file. If the user selects both the print attribute file and the XPS file the printer driver performs the process illustrated in . Further the printer driver acquires the hierarchical structure information and the print tickets associated with each of the hierarchical structure parts from the XPS document. The printer driver then stores the acquired hierarchical structure information and print tickets by associating them with the favorite name.

In step S the printer driver allows the user to select an XPS document to be registered as the favorite and acquires a path to the XPS document.

In step S the printer driver acquires the hierarchical structure information from the XPS document selected in step S.

In step S the printer driver acquires the print ticket from the XPS document selected in step S. When the print ticket is acquired the printer driver acquires information indicating the hierarchical structure part to which the acquired print ticket belongs to.

In step S the printer driver stores the hierarchical structure information acquired in step S and the print ticket acquired in S in a memory by associating them with a registration name of the favorite.

The favorite which is registered by the present exemplary embodiment is different from the favorite applied to the XPS document by the process described with reference to in the previous exemplary embodiment in that the hierarchical structure information and the print ticket are associated with the registered favorite. As a consequence it is not necessary to acquire the hierarchical structure information and print tickets from the XPS document. Therefore step S illustrated in does not have to be performed. Otherwise the processes in the present exemplary embodiment are similar to the processes in the previous exemplary embodiment.

According to the present exemplary embodiment the printer driver stores only minimum information necessary to apply the favorite instead of storing the XPS document itself as in the previous exemplary embodiment. Therefore a processing speed can be improved and a storage amount can be reduced.

According to a third exemplary embodiment of the present invention print attributes that are not associated with hierarchical structure information can be applied to a FixedDocumentSequence when a favorite is applied. The favorite can be registered by any of the above described methods.

When the user selects the favorite to be applied the printer driver allows the user to select two files that correspond to an entire setting and to an exception setting. The printer driver allows the user to select print attributes of formats other than that of the XPS document as the entire setting. Further the printer driver allows the user to select only the XPS document as the exception setting. If the user selects the XPS document as the exception setting and does not specify any setting to the entire setting the printer driver displays the file name of the XPS document specified as the exception setting in an entire settings column on the operation screen. Further the printer driver uses the print ticket of the FixedDocumentSequence in the XPS document specified in the exception setting as the entire setting.

The printer driver performs a process according to the flowchart illustrated in for applying the above described settings. However the process of step S is different from the previous exemplary embodiments. In step S illustrated in the printer driver acquires the print ticket print attributes of the FixedDocumentSequence in the favorite XPS document. The printer driver then applies the acquired print ticket to the FixedDocumentSequence of the XPS document to which the favorite be applied.

On the other hand according to the present exemplary embodiment if the file specified to the entire setting is different from the file specified to the exception setting the printer driver applies the print attributes specified to the entire setting to the FixedDocumentSequence of the XPS document to which the favorite is applied. Further the printer driver applies the print ticket of the FixedDocumentSequence in the XPS document specified to the exception setting to the FixedDocumentSequence in the XPS document to which the favorite be applied.

According to the present exemplary embodiment the print attributes that are not associated with the hierarchical structure information can be applied to the FixedDocumentSequence together with the existing favorites. As a result resources of the favorites can be efficiently used.

The present invention can be achieved by providing a computer readable storage medium or a computer readable recording medium which stores software program code for implementing functions of the above described exemplary embodiments to a system or an apparatus. The program code stored in the computer readable storage medium can be read and executed by a computer central processing unit CPU or micro processing unit MPU of the system or the apparatus. In this case the program code read from the computer readable storage medium realizes the functions of the exemplary embodiments of the present invention and the computer readable storage medium which stores the program code constitutes the present invention.

Furthermore the functions of the above described exemplary embodiments can be realized not only by executing the program code read by the CPU but also by performing a part or the whole of processes by an operating system OS or the like working on a computer according to instructions of the program code.

Furthermore the program code read from the computer readable storage medium can be stored in a memory equipped in a function expansion card inserted in or a function expansion unit connected to the computer of the system or the apparatus and a CPU in the function expansion card or the function expansion unit can execute a part or the whole of processes according to the instructions of the program code to realize the functions of the above described exemplary embodiments.

In a case where the present invention is applied to the computer readable storage medium the program code that corresponds to the flowcharts illustrated in the figures of the above described exemplary embodiments are stored in the computer readable storage medium.

According to the above describe exemplary embodiments print attributes including exception settings can be registered from an XPS document as a print template. Therefore the print template can be applied to other XPS documents. As a result print attributes of an XPS document in which complex print attributes have been set can be re used so that setting print attributes can be simplified. More specifically a user can reuse print attributes of a document which has a hierarchical structure so that the user can easily set the print attributes to a document which has a hierarchical structure.

According to the present invention print attributes of a document having a hierarchical structure can be reused so that a user can easily set print attributes to a document which has a hierarchical structure.

While the present invention has been described with reference to exemplary embodiments it is to be understood that the invention is not limited to the disclosed exemplary embodiments. The scope of the following claims is to be accorded the broadest interpretation so as to encompass all modifications equivalent structures and functions.

This application claims priority from Japanese Patent Application No. 2008 048533 filed Feb. 28 2008 which is hereby incorporated by reference herein in its entirety.

