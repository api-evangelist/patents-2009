---

title: System and method for management of common decentralized applications data and logic
abstract: Enables a computer-assisted management of enterprise-network files of interest, and trouble-free migration of enterprise-wide business data and processes currently built and maintained in two popular tools, spreadsheets (commonly MICROSOFT® EXCEL®) and desktop/departmental databases (commonly MICROSOFT® ACCESS®). Includes:


url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08122340&OS=08122340&RS=08122340
owner: 
number: 08122340
owner_city: 
owner_country: 
publication_date: 20090902
---
This application claims the benefit of U.S. Provisional Patent Application 61 101 141 filed 29 Sep. 2008 the specification of which is hereby incorporated herein by reference.

One or more embodiments of the invention are related to the field of computer systems. More particularly but not by way of limitation one or more embodiments of the invention enable a system and method for management of common decentralized applications data and logic.

There is currently no known system or method for computer assisted management of common decentralized applications data and logic for example enterprise network files of interest which contain enterprise wide business data but which are housed in individual files spread across an organization.

Specifically enterprise wide business data and processes are currently built and maintained in two popular tools spreadsheets most commonly MICROSOFT EXCEL and desktop departmental databases most commonly MICROSOFT ACCESS . Files of these types litter business organization personal computers and yet should be coordinated to provide data integrity and centralized knowledge. This dispersed information topology limits the usefulness of the data.

Enterprise Chief Information Officers CIOs and other IT department managers often are held responsible for knowing how many files exist of certain file types for example MP3s and proprietary software executables . This is a difficult job at best as the files could be in thousands of directories spread across thousands of personal computers in a large organization.

In addition both spreadsheets such as MICROSOFT EXCEL and desktop departmental databases such as MICROSOFT ACCESS offer daunting challenges to most enterprises CIOs or IT departments as they are usually 

Difficult to inventory and understand Most spreadsheets and desktop departmental databases are designed built and maintained by business i.e. non Information Technology departments with no IT involvement or guidance. Thus most CIOs or IT managers cannot answer with any confidence any question about the number or purpose of the spreadsheets and desktop departmental databases even though these usually comprise a substantive percentage of overall enterprise information. 

Very difficult to migrate into enterprise applications After business departments develop and use spreadsheets and desktop departmental databases business department management occasionally finds inherent spreadsheet and desktop departmental database limitations primarily to do with single user limits or lack of integration with other enterprise databases to be a problem and ask their CIO or IT manager to upgrade it to support multiple users and where appropriate integrate it with other enterprise applications and data. This is often a troublesome request for a CIO or IT manager to receive as most CIO s resources are stretched thin and the effort of migrating either a spreadsheet or desktop departmental database to fit it into enterprise database and architectural standards such application development technology stacks such as .NET SQL Server or J2EE Oracle often significantly exceeds the cost of designing and building the original spreadsheet or desktop departmental database.

For at least the limitations described above there is a need for a system and method for management of common decentralized applications data and logic.

One or more embodiments of the invention enable a new system and method for management of common decentralized applications data and logic. Specifically embodiments of the invention enable a computer assisted management of enterprise network files of interest and trouble free migration of enterprise wide business data and processes currently built and maintained in two popular tools spreadsheets most commonly MICROSOFT EXCEL and desktop departmental databases most commonly MICROSOFT ACCESS .

Embodiments of the invention solve the problems outlined in the description of the related art by a system and method that includes 

A file system repository that lists each file of interest and in addition describes in detail design and intent information for each spreadsheet and desktop departmental database.

A Simplified Enterprise Application Repository SEAR also referred to herein as the Simplified Enterprise Application Meta Model configured to store descriptions of simple enterprise applications.

Utilities that read enterprise database meta data such as table definitions and store them into the SEAR.

Utilities that analyze spreadsheets and desktop departmental databases or files of any other type for example as associated with given file type extensions in the file repository and restate them as simple enterprise applications in the SEAR. Other file types include MP3 s or files of any other extension.

Utilities that generate well documented and well programmed enterprise relational databases and applications from simple enterprise applications descriptions in the SEAR.

A system and method for management of common decentralized applications data and logic will now be described. In the following exemplary description numerous specific details are set forth in order to provide a more thorough understanding of embodiments of the invention. It will be apparent however to an artisan of ordinary skill that the present invention may be practiced without incorporating all aspects of the specific details described herein. In other instances specific features quantities or measurements well known to those of ordinary skill in the art have not been described in detail so as not to obscure the invention. Readers should note that although examples of the invention are set forth herein the claims and the full scope of any equivalents are what define the metes and bounds of the invention.

Enterprise Network that contains computers e.g. mainframes servers desktops laptops and other file containing computers with various files of interest including spreadsheets and desktop departmental databases wherein the computers record basic file information such as date time last modified size et cetera in the file system repository .

 Crawler utility periodically searches network directories and files for new changed or deleted erased files of interest including but not limited to spreadsheets and desktop departmental database files. Crawler passes new changed or erased spreadsheets to Spreadsheet Analyzer utility which reads spreadsheet semantic details such as worksheets cell definitions macros et cetera and stores changes into Spreadsheet Meta Model database part of Comprehensive Repository relational database . If the spreadsheet file is new Crawler sends e mail to the best guess file owner asking for more information about the new spreadsheet file s purpose history et cetera.

The Crawler utility passes new changed or erased desktop departmental databases and optionally their database data to Database Analyzer utility which reads desktop departmental database semantic details such as tables queries forms reports et cetera stores changes into Database Meta Model database which also is part of Comprehensive Repository relational database and if the desktop departmental database file is new sends e mail to the best guess file owner asking for more information about the new database file s purpose history et cetera.

A Repository Application is used by the CIO and other authorized IT staff to manage the run frequency and network reach of the Crawler utility to read analyze report on and add value to annotate information in the file system repository Spreadsheet Meta Model the Database Meta Model the Enterprise Reference Model and the Enterprise Simplified Enterprise Application Meta Model database.

When an end user opens an e mail generated by either the Spreadsheet Analyzer utility or the Database Analyzer utility the end user clicks a link in the e mail s body to add purpose and other annotation information forward the request to another person who is the file s owner or claim the file is private. In each case clicking the link automatically invokes the Repository Application for a purpose specific on line transaction to do the action requested.

An Enterprise Database Upload utility periodically searches the Enterprise Development Database structure part of the Centrally Managed Enterprise Architecture for created modified or dropped tables and other relational database objects and stores changes into a Simplified Enterprise Simplified Enterprise Application Meta Model database which also is part of the Comprehensive Repository relational database.

A Spreadsheet Synthesis utility reads the Spreadsheet Meta Model database determines helped by Repository Application annotations as necessary each spreadsheet s equivalent applications semantic or meaning and saves or updates that meaning as an enhanced spreadsheet applications definition in the Simplified Enterprise Simplified Enterprise Application Meta Model database. Where appropriate the enhanced spreadsheet application definition reflects if it maintains its own data or also already existing enterprise data i.e. that which has been analyzed and stored by the Enterprise Database Upload utility .

A Database Synthesis utility reads the Database Meta Model database determines helped by Repository Application annotations as necessary each desktop departmental database s equivalent applications semantic or meaning and saves or updates that meaning as an enhanced desktop departmental database applications definition in the Simplified Enterprise Simplified Enterprise Application Meta Model database. Where appropriate the enhanced desktop departmental database application definition reflects if it maintains its own data or also already existing enterprise data i.e. that which has been analyzed and stored by the Enterprise Database Upload utility .

An Enterprise Applications Generator utility reads the Simplified Enterprise Simplified Enterprise Application Meta Model database including annotations where applicable and generates RDBMS Relational Database Management System DDL Data Definition Language used to create alter and drop tables et cetera and DML Data Manipulation Language used to insert modify and erase applications data in the enterprise s preferred RDBMS environment such as Oracle or SQL Server to extend the Enterprise Database . The Enterprise Applications Generator utility also generates well documented applications logic code compiles that code and deploys appropriate applications modules into the enterprise s Applications Logic Files and Development Applications Tools both part of the Centrally Managed Enterprise Architecture in the enterprise s preferred applications technology such as .NET and J2EE .

The Repository Application also is used by the CIO file owners line of business managers and other authorized staff to read analyze report on and add value to annotate information in the Simplified Enterprise Simplified Enterprise Application Meta Model database and on demand to run the Spreadsheet Synthesis utility the Database Synthesis utility the Enterprise Database Upload utility and the Enterprise Applications Generator utility. Crawler spreadsheet analyzer database analyzer spreadsheet synthesis utility database synthesis utility Enterprise database upload utility enterprise application generator repository application development application tools can run on any computer and or in Enterprise Network or in any other computer that can couple with Enterprise Network as long as the computer is configured with enough memory and with sufficient processing power and network bandwidth to run these computational entities. In one or more embodiments of the invention these computational entities may run on a plurality of computers selected from Enterprise Network or from a plurality of computers that may be coupled with Enterprise Network or any combination thereof. In addition all of the databases or data storage elements shown in including the file system repository enterprise data model spreadsheet meta model database meta model Simplified Enterprise Application Meta Model Enterprise Development database and Enterprise Application Files may be implemented with any memory element capable of storing and retrieving information including but not limited to a file system or database or any other element so configured. One skilled in the art will recognize that memory storage elements that host these elements may be coupled with any computer in Enterprise Network or coupled with any computer that may itself be coupled with Enterprise Network for example.

An Enterprise Network contains computers with various files of interesting including spreadsheets and desktop departmental databases also see for more detail.

The Crawler utility initiation module reads from the file system repository the list of file extensions such as .xls .xlsx et cetera to find databases and spreadsheets of interest associated with these file extensions.

The Crawler utility scope module reads from the file system repository the list of domains servers disks and directories and their current known owners to search and the list of already known files of interest with their previously found last modify dates and times sizes checksums CRCs et cetera.

The Crawler utility initial match module verifies continued existence of each to be searched domain server and disk and flags in the file system repository any it cannot find or search.

The Crawler utility directory search module finds all directories and sub directories in in scope domains servers and disks compares it to previously found directories and sub directories adds new directory and subdirectory records to the file system repository inheriting owner from parent directories disks et cetera and marks in the file system repository as no longer there any missing but expected directories and sub directories.

The Crawler utility file search module finds all files of interest in found directories and sub directories compares each to previously found directories files including last modify date and time size CRC et cetera adds new file records to the file system repository inheriting owner from parent directory disk et cetera updates the file system repository where last modify date and time size or CRC do not match and marks in the file system repository as no longer there any missing but expected files of interest. If a file of interest is new or changed and is either a spreadsheet or desktop departmental database the file search module reads its content into memory for passing to the next step .

If a new or changed file is a spreadsheet the Crawler utility spreadsheet file match module passes it to the Spreadsheet Analyzer utility see for details .

If a new or changed file is a desktop departmental database the Crawler utility database file match module passes it to the Database Analyzer utility see for details .

The Crawler utility completion module updates the file system repository with a record of its successful completion.

The Crawler utility periodically searches network directories and files for new changed or erased files of interest in this case spreadsheets and for new or changed spreadsheets see calls the Spreadsheet Analyzer analysis module .

The Spreadsheet Analyzer analysis module calls standard open spreadsheet APIs for example Microsoft Excel APIs to determine spreadsheet details for the spreadsheet s workbook worksheets rows columns cells charts et cetera the analysis module then adds Spreadsheet Meta Data detail to the Spreadsheet Meta Model database first erasing prior data for the spreadsheet if the spreadsheet is changed rather than new . When done the analysis module calls the Spreadsheet Analyzer notification module .

The Spreadsheet Analyzer notification module generates an e mail to the most likely spreadsheet owner see the e mail offers the most likely file owner determined via the directory or sub directory and history of other files found in that directory or sub directory the choice of clicking a link to provide more information about the spreadsheet such as its purpose suggest another person as the owner or declare the spreadsheet private. 

If the e mail recipient clicks a link doing so automatically starts the Repository Application with the appropriate on line transaction see to add details reassign ownership or declare the spreadsheet private.

An Enterprise Network contains computers with various files of interesting including desktop departmental databases.

The Crawler utility periodically searches network directories and files for new changed or erased files of interest in this case desktop departmental databases and for new or changed desktop departmental databases calls the Database Analyzer analysis module .

The Database Analyzer analysis module calls standard open desktop departmental database APIs such as Microsoft Access APIs to determine desktop departmental database details for that database s tables columns queries update transactions reports et cetera the analysis module then adds Database Meta Data detail to the Database Meta Model database first erasing prior data for the desktop departmental database if the desktop departmental database is changed rather than new . When done the analysis module calls the Database Analyzer notification module .

The Database Analyzer notification module generates an e mail to the most likely desktop departmental database owner see the e mail offers the most likely file owner determined via the directory or sub directory and history of other files found in that directory or sub directory the choice of clicking a link to provide more information about the desktop departmental database such as its purpose suggest another person as the owner or declare the spreadsheet private. 

If the e mail recipient clicks a link doing so automatically starts the Repository Application with the appropriate on line transaction to add details reassign ownership or declare the desktop departmental database private.

FIG. A Table groups lists of groups of related tables in the Comprehensive Repository database see and FileSystem group tables tables that describe an Enterprise Network see .

FIG. B FileObject table shows column level details of this key FileSystem group table s design see . This table describes a file of interest in an Enterprise Network see .

FIG. C Spreadsheet Meta Model group tables tables that describe a spreadsheet such as an Excel spreadsheet found in an Enterprise Network see .

FIG. D Database Meta Model group tables tables that describe a desktop departmental application such as an Access database found in an Enterprise Network see .

Simple applications synthesized by the Spreadsheet Synthesizer see from spreadsheets such as Excel spreadsheets.

Simple applications synthesized by the Database Synthesizer see from desktop departmental databases such as Access databases.

FIG. G Enterprise Definition Model see table describes the structure of one or more organizations including for example relationships between organizations and staff members and responsibilities held by staff members.

The Repository Application includes transactions and reports to view and maintain contents of the Comprehensive Repository . Once such transaction is the AnnotateFile on line transaction .

The AnnotateFile on line transaction lets a file owner in this example the author of a new spreadsheet add details reassign ownership or declare a file private i.e. for the use only of the owner .

AnnotateFile shows and allows changes to the file s name directory or sub directory tree primary purpose whether it s private and who is the file s owner . In addition the file s owner can list general purpose notes and add miscellaneous details .

The Spreadsheet Analyzer utility see generates e mails notifying the most likely owner of the spreadsheet that it analyzed.

The Database Analyzer utility also see generates e mails notifying the most likely owner of the desktop departmental database that it analyzed.

The e mail s body text specifies the most likely owner s first name file name in question and disk and directory sub directory tree .

The e mail includes a link asking for details about this new spreadsheet this link s HTML automatically invokes the Repository Application AnnotateFile transaction see letting the owner add purpose et cetera for the spreadsheet.

The e mail includes a link asking for the recipient s best guess at to the correct owner of this new spreadsheet i.e. the e mail recipient turns out not to be the owner but knows who is this link s HTML automatically invokes the Repository Application ReassignOwners transaction letting the recipient specify who is likely the spreadsheet s owner.

The e mail includes a link asking for verification that this new spreadsheet is owned by the e mail s recipient but is private this link s HTML automatically invokes the Repository Application AnnotateFile transaction letting the owner explicitly state that the spreadsheet is private and add details if desired.

An IT specialist uses the Repository Application to find a desktop departmental database in the Database Meta Model database and request running of the Database Synthesis utility .

The Database Synthesis utility upload module reads details including owner provided annotations and complete desktop departmental database details tables columns queries reports update transactions et cetera from the Database Meta Model database and reads existing applications database details schemas tables columns et cetera from the Simplified Enterprise Application Meta Model database .

The Database Synthesis utility synthesis module uses the data gathered by the upload module to determine the most likely combination of RDBMS tables already existing and new new on line transactions new reports et cetera that would replace the original desktop departmental database. Except for desktop departmental database versus production database transformations most desktop departmental database reports become production reports and most desktop departmental database queries update transactions et cetera become production on line transactions capable of updates queries et cetera.

The Database Synthesis utility database design module adds designs for new RDBMS tables columns et cetera to the Simplified Enterprise Application Meta Model database .

The Database Synthesis utility transaction design module adds designs for new transactions screens regions fields buttons logic et cetera to the Simplified Enterprise Application Meta Model database .

The Database Synthesis utility report design module adds designs for new reports titles headers footers regions fields buttons calculations et cetera to the Simplified Enterprise Application Meta Model database .

An IT specialist uses the Repository Application to review fine tune or erase the desktop departmental database s newly created production components in the Simplified Enterprise Application Meta Model database .

The Enterprise Database Upload utility initiates and runs the Enterprise Database Upload startup module which reads the list of supported and applicable development database instances and schemas from the Simplified Enterprise Application Meta Model database .

The Enterprise Database Upload analysis module reads the list of known development database objects such as tables and columns from the Simplified Enterprise Application Meta Model database reads the active dictionary in the Enterprise Development Database for actual enterprise database tables columns et cetera and creates a list of differences such as new tables and columns and changed column definitions.

The Enterprise Database Upload differences module reads domain information matching new and changed tables and columns from Simplified Enterprise Application Meta Model database determines best guess new meta meta model content updates adds or modifies corresponding content in the Simplified Enterprise Application Meta Model database and where needed generates informative e mails to responsible IT staff asking for additional information.

When responsible IT staff open generated e mails and click their links the Repository Application automatically starts and displays the relevant content update transaction for example TableDetails or ColumnDetails transactions so that the IT staff member can add specialized information such as suggested column help text to display on generated transactions.

An IT specialist uses the Repository Application to find a spreadsheet in the Spreadsheet Meta Model database and request running of the Spreadsheet Synthesis utility .

The Spreadsheet Synthesis utility upload module reads details including owner provided annotations and complete spreadsheet details workbook worksheets rows columns cells charts et cetera from the Spreadsheet Meta Model database and reads existing applications database details schemas tables columns et cetera from the Simplified Enterprise Application Meta Model database .

The Spreadsheet Synthesis utility synthesis module uses the data gathered by the upload module to determine the most likely combination of RDBMS tables already existing and new new on line transactions and new reports that would perform the same business function as the original spreadsheet see .

The Spreadsheet Synthesis utility database design module adds designs for new RDBMS tables columns et cetera to the Simplified Enterprise Application Meta Model database .

The Spreadsheet Synthesis utility transaction design module adds designs for new transactions screens regions fields buttons logic et cetera to the Simplified Enterprise Application Meta Model database .

The Spreadsheet Synthesis utility report design module adds designs for new reports titles headers footers regions fields buttons calculations et cetera to the Simplified Enterprise Application Meta Model database .

An IT specialist uses the Repository Application to review fine tune or erase the spreadsheet s newly created production components in the Simplified Enterprise Application Meta Model database .

A spreadsheet is analyzed by the Spreadsheet Analyzer utility and placed into the Spreadsheet Meta Model see .

The spreadsheet has a table listing trades in this table in particular there is a Buy Sell column with values of B for Buy and S for Sell and a Market price column whose value is derived copied from the corresponding Market price value in the Equity table .

The Spreadsheet Synthesizer reviews complete analyzed spreadsheet content and already existing tables including in this case an already existing Equities table with columns EquityID and EquityCode in the Enterprise Simplified Enterprise Application Meta Model database see .

The Spreadsheet Synthesizer defines in the Enterprise Simplified Enterprise Application Meta Model database see two new tables MarketPrices with a foreign key to the already existing Equities table and Trades with foreign keys both to Equities and MarketPrices.

The Spreadsheet Synthesizer defines in the Enterprise Simplified Enterprise Application Meta Model database see two new on line transactions MaintainMarketPrices with fields Equity and Market price and EnterTrades with fields Date Equity Buy Sell Shares Price and Commission .

The Spreadsheet Synthesizer defines in the Enterprise Simplified Enterprise Application Meta Model database see a charting report summarizing profit and loss by calendar month. In one or more embodiments defining the above objects for example adds rows to the following tables see DataObject DataObjectRelationship EnterpriseApplication EnterpriseApplicationObject EnterpriseApplicationObjectEvent EnterpriseApplicationObjectMiscellaneousDetail EnterpriseApplicationObjectNote EnterpriseDomain FunctionObject FunctionObjectInvocation FunctionObjectInvocationParameter FunctionObjectParameter InterfaceObject InterfaceObjectRelationship MenuObject and MenuObjectDetail. Although these field names in the table are provided in an exemplary manner one skilled in the art will recognize that variations of these names or fields are in keeping with the spirit of the invention so long as the spreadsheet synthesizer can describe the information that it is supplied with in a manner that allows for the description of objects in the Enterprise Simplified Enterprise Application Meta Model database. The same holds true with any synthesizer component implemented with embodiments of the invention including the database synthesizer for example.

In one table a database administrator or developer has modified one column and added another column .

When the Enterprise Database Upload utility next runs it compares Enterprise Development Database tables and columns with details in the Simplified Enterprise Application Meta Model DataObject table .

Since two development tables and are unchanged the Enterprise Database Upload utility leaves their corresponding data and in the DataObject table unchanged.

Since one development table has a changed column and a new column the Enterprise Database Upload utility updates the corresponding detail row in the DataObject table for the changed column and adds a new column definition row for the new column .

Since one development table has been added with four columns the Enterprise Database Upload utility adds one new table definition row and four new column definition rows to corresponding data that corresponds to table .

An IT specialist uses the Repository Application to find an application originating as either a spreadsheet or desktop departmental database in the Simplified Enterprise Application Meta Model and run the Enterprise Applications Generator utility .

The Enterprise Applications Generator content module reads the Simplified Enterprise Application Meta Model for new and changed applications content tables columns transactions reports et cetera .

The Enterprise Applications Generator database module generates and runs DDL SQL Data Definition Language and DML SQL Data Manipulation Language to add new tables add new columns to existing tables and convert tables with changed columns as necessary then runs that DDL and DML in the Development Database in the Enterprise Development Run Time Environment . One skilled in the art will recognize that any type of database language or commands associated with a given database language can be utilized so long as the desired tables and columns are created modified or deleted as desired.

The Enterprise Applications Generator transaction module generates depending on site standards enterprise business objects such as J2EE EJB s .NET objects et cetera programmatic source code for all new transactions implied by the underlying spreadsheet or desktop departmental database and adds them into various source files in the Development File System within the Enterprise Development Run Time Environment .

The Enterprise Applications Generator report module generates depending on site standards Crystal Excel et cetera programmatic source code for all new reports implied by the underlying spreadsheet or desktop departmental database and adds them into various other source files in the Development File System within the Enterprise Development Run Time Environment .

The Enterprise Applications Generator invocation module compiles transaction and report programmatic source code for all new reports and transactions creates run time or executable files adds them into various files in the Development File System within the Enterprise Development Run Time Environment then invokes or executes those run time or executable files to run the resulting application .

While the invention herein disclosed has been described by means of specific embodiments and applications thereof numerous modifications and variations could be made thereto by those skilled in the art without departing from the scope of the invention set forth in the claims.

