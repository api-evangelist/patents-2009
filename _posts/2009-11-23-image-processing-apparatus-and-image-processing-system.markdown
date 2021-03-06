---

title: Image processing apparatus and image processing system
abstract: An image processing apparatus and an image processing system are supplied capable of restraining an occurrence of failure print. The image processing apparatus connected to an image forming apparatus comprises an operation detecting section that detects operations of a document processing section; a document size obtaining section that obtains document size information; a medium size obtaining section that obtains medium size information of print mediums set in the image forming apparatus; a comparing and judging section that compares the document size information and the medium size information and judges whether or not they are consistent; an inquiring section that inquires user whether or not document size of the print object document is changed; an inputting section that inputs a change instruction of the document size; and a changing section that changes the document size information into the medium size information on the basis of the change instruction.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08630014&OS=08630014&RS=08630014
owner: Oki Data Corporation
number: 08630014
owner_city: Tokyo
owner_country: JP
publication_date: 20091123
---
The invention relates to an image processing apparatus that generates document data of print object document and generates image data of print use on the basis of the document data and an image processing system in which an image forming apparatus is connected to the image processing apparatus.

In an image processing system that is composed of an image processing apparatus such as a personal computer and an image forming apparatus such as a printer connected to the image processing apparatus until now such technology is known to prevent miss print to paper of undesignated size through detecting that paper size of a print object document and paper size of paper set in the image forming apparatus are not consistent by comparing them before print of the print object document generated in the image processing apparatus.

For example in a print system disclosed in a patent document 1 mentioned below when inconsistency of the paper size is detected a warning scene is displayed in a host computer as the image processing apparatus for urging a selection of any one of a cancel and a continuation of the print and a change of the paper size. In the warning scene when the change of the paper size is selected the host computer changes the paper size of the print object document into paper size of the paper set in the printer generates print data and transmits it to the printer.

However after the paper size of the print object document is changed there is a case that a change occurs in a paragraph position of the document and an arrangement of images so an undesirable layout is produced. However in the disclosed technology mentioned above even after the change occurs in the layout because print is executed that is exactly as it was so it results in a failure print. As a result expendable supplies such as toner paper and the like are wasted.

Therefore an image processing apparatus and an image processing system are desired capable of restraining occurrence of failure print.

It is therefore an object of the invention to provide an image processing apparatus and an image processing system that can solve the above problem.

A first aspect of the invention is to provide an image processing apparatus connected to an image forming apparatus that has a document processing section for performing a creation and an editing of document data of a print object document on the basis of document size information an instructing section for instructing to print the print object document and a converting section for converting the document data into print use image data for sending to the image forming apparatus on the basis of the instruction comprising an operation detecting section that detects an operation of the document processing section a document size obtaining section that obtains the document size information a medium size obtaining section that obtains medium size information of print mediums set in the image forming apparatus a comparing and judging section that compares the document size information and the medium size information that are obtained and judges whether or not they are consistent an inquiring section that inquires a user whether or not document size of the print object document is changed when the document size information and the medium size information are not consistent an inputting section that inputs a change instruction of the document size and a changing section that changes the document size information into the medium size information on the basis of the change instruction.

A second aspect of the invention is to provide an image processing system that includes an image forming apparatus for forming images onto print mediums and an image processing section that is connected to the image forming apparatus and has a document processing section for performing a creation and an editing of document data of a print object document on the basis of document size information a instructing section for instructing to print the print object document and a converting section for converting the document data into print use image data for sending to the image forming apparatus on the basis of the instruction wherein the image processing apparatus comprises an operation detecting section that detects operations of the document processing section a document size obtaining section that obtains the document size information a medium size obtaining section that obtains medium size information of print mediums set in the image forming apparatus a comparing and judging section that compares the document size information and the medium size information that are obtained and judges whether or not they are consistent an inquiring section that inquires a user whether or not document size of the print object document is changed when the document size information and the medium size information are not consistent an inputting section that inputs a change instruction of the document size and a changing section that changes the document size information into the medium size information on the basis of the change instruction.

According to the image processing apparatus of the present invention after an operation of the document processing section is detected document size of a print object document and medium size of print mediums set in the image forming apparatus are compared and when they are not consistent an inquiry whether or not document size is changed is executed so it is possible to change the document size into the medium size of print mediums before the print instruction. Therefore it is possible to avoid failure print and waste of expendable supplies is restrained.

The above and other objects and features of the present invention will become apparent from the following detailed description and the appended claims with reference to the accompanying drawings.

Hereinbelow it is to explain enforcement form of the present invention in detail by using figures. Here it is to explain an example in the case to apply to a printer system that is composed of a personal computer and a printer of the present invention.

A printer system as an image processing system as shown by comprises a personal computer as an image processing apparatus and a printer as an image forming apparatus. It is possible to print documents generated in the personal computer through the printer by using the printer system .

Firstly it is to explain about the personal computer that forms the printer system of the present embodiment.

In the personal computer as shown by a CPU a program storing ROM a RAM a hard disk apparatus an input I F a display I F and a printer I F are mutually connected through an address data bus .

The CPU Central Processing Unit is a center processing apparatus for performing a general control of the personal computer regards the RAM as a work region and executes all kinds of programs stored in the program storing ROM .

The program storing ROM Read Only Memory is a non volatile read only memory and stores all kinds of programs. In the personal computer of the present embodiment as shown by a document process application program an application watch program a paper size watch program an image form program and an inquiry process control program are stored in the program storing ROM .

The document process application program is an application program for executing edit storing display and print of document information composed of texts images figures and the like.

The application watch program is a program for obtaining and notifying information with respect to operations of the document process application program .

The paper size watch program is a program for obtaining paper size information representing size of paper set in the printer .

The image form program is a program for generating image data for print in the printer on the basis of document data.

The inquiry process control program is a program for executing a comparing and judging process and an inquiring process that are mentioned below.

The RAM Random Access Memory is a volatile memory and is a primary storage device used as a work region when programs are executed through the CPU .

The hard disk apparatus is a secondary storage device capable of reading and writing larger amount of data than the program storing ROM and the RAM and stores document file that is storing destination of document information those edit and print are executed by using the document process application program other necessary data and the like as a storing section.

Moreover it is also possible to adopt a structure that stores respective programs stored in the program storing ROM that is the document process application program the application watch program the paper size watch program the image form program and the inquiry process control program in the hard disk apparatus .

The inputting apparatus as shown by is composed of a keyboard and a mouse in the present embodiment and performs input of all kinds of input information and selection information on the basis of operations of a user.

The display is capable of displaying a plurality of windows and performs display of an inquiry scene and a paper size warning scene that are mentioned below.

The personal computer as an image processing apparatus as shown by includes a document process application section a paper size watching section an image forming section and an inquiring process controlling section .

The document process application section as shown by is composed of an edition processing section an application watching section for watching an operation of the edition processing section and an instructing section for performing a print instruction to the edition processing section .

The edition processing section is a processing section which operates when the document process application program is executed through the CPU and performs a document process such as a new creation edit and the like of document information as a document processing section. For example the edition processing section reads out one or plural document information from a document file in the hard disk apparatus converts the document information into document data that is in the form of an inner process and performs respective processes for display print and the like on the basis of the document data. Further the edition processing section perform edit of the read out document information performs creation of new document information and then stores the edited or newly created document information in the document file. Furthermore the edition processing section transmits a document that is an object of a print process that is the document data of the print object document to the image forming section . The document that is an object of the document process by the edition processing section is generically called a process object document.

The application watching section as shown by has a setting section an operation detecting section an application information obtaining section and an application information notifying section . The application watching section corresponds to the application watch program as a function extension module of the document process application section is a plug in which operates in the inside of respective processes executed in the CPU . The application watching section through performing communication with the edition processing section by using an API Application Programming Interface opened through the edition processing section watches an operation of the edition processing section and notifies the paper size watching section of it.

The setting section with respect to a process object document in the document process of the edition processing section performs a setting of document size information. Here the document size information is data representing paper size of the document corresponding to the document information.

The operation detecting section performs communication with the edition processing section and detects that the following respective operations such as a document file open operation a new document creation operation a paper setting change operation a document selection operation and a window activation operation are performed in the document process application section containing the edition processing section . Next it is to explain the respective operations detected by the operation detecting section . Moreover the respective operations detected by the operation detecting section are generically called document process operations.

The document file open operation corresponds to an operation in which a document file stored in the hard disk apparatus is opened through the edition processing section that is a document file is registered and a corresponding window is displayed on the display for the first time.

The new document creation operation represents an operation in which new document information is created by the edition processing section .

The paper setting change operation represents an operation in which document size information is set by the setting section with respect to the process object document that is in a document process through the edition processing section .

The document selection operation is an operation in which a process object document is selected in the document process application section . The document process application section is capable of executing parallel document processes with respect to a plurality of process object documents. On executing the parallel document processes each window corresponding to respective process object documents is respectively displayed on the display of the personal computer a user operates the inputting apparatus so as to select any one of process object document. The document process application section selects any one of process object document on the basis of the input from the inputting apparatus the edition processing section executes a document process with respect to the selected process object document. The operation detecting section detects the operation in which the process object document is selected as the document selection operation.

The window activation operation represents an operation in which a window corresponding to the document process application section is activated among respective windows displayed on the display . On displaying a plurality of windows on the display windows those are objects of input and operation through the inputting apparatus are called as active windows and the other windows are regarded as non active windows. The window activation operation corresponds to an operation in which any one of window is switched from non active window to active window. The document process application section executes the window activation operation on the basis of the input from the inputting apparatus .

The operation detecting section after detected the document process operation mentioned above performs an instruction for the application information obtaining section to obtain application information. The operation detecting section notifies the application information obtaining section of the obtainment instruction and detection operation names representing kinds of the detected operations. Moreover with respect to respective operations mentioned above the detection operation names sent to the application information obtaining section through the operation detecting section are respectively document file open new document creation paper setting change document selection and window activation .

The application information obtaining section on the basis of the obtainment instruction from the operation detection section performs communication with the edition processing section to obtain application information. Here the application information obtained through the application information obtaining section is composed of a process ID of a process corresponding to a operation detected by the operation detecting section a detection operation name representing a kind of the detected operation a document name as document discrimination information of a process object document and document size information of the process object document. The application information obtaining section notifies the application information obtaining section of the obtained application information.

The application information notifying section notifies the inquiring process controlling section of the application information obtained by the application information obtaining section .

The paper size watching section as shown by includes a demand transmitting section and a paper size receiving section . The paper size watching section corresponds to the paper size watch program performs communication with the printer through the printer I F to obtain paper size information of paper set in the printer .

The demand transmitting section transmits a transmission demand of paper size information to the printer on the basis of an obtainment demand mentioned below from the image forming section or the inquiring process controlling section . Further the demand transmitting section notifies the paper size receiving section of obtainment demand source information representing that the obtainment demand source is any one of the image forming section and the inquiring process controlling section .

The paper size receiving section as a medium size receiving section and a medium size obtaining section receives paper tray information containing paper size information as medium size information from the printer and obtains paper size information. Then the paper size receiving section notifies the image forming section or the inquiring process controlling section of the obtained paper size information on the basis of the obtainment demand source information informed from the demand transmitting section .

The image forming section as shown by includes a reception detecting section an identifying section a paper size judging section a notifying section an inputting section and a converting section . The image forming section corresponds to the image form program receives document data from the document process application section and generates image data for print in the printer .

The reception detecting section detects a receiving of document data from the document process application section and performs an obtainment demand for the paper size watching section in order to obtain paper size information from the printer .

The identifying section receives document data from the document process application section and identifies document size information and tray designation information that are contained in the document data. Here the tray designation information is data for designating a paper tray that is a paper feeding source of paper as a paper feeding source tray in the case of print process in the printer and is any one of lower paper tray upper paper tray and automatic selection in the present embodiment. However the tray designation information automatic selection means that the paper feeding source tray is automatically selected on the basis of the document size information.

The paper size judging section judges whether or not document size of the print object document and paper size of the paper feeding source tray are consistent on the basis of the document size information and the tray designation information that are identified by the identifying section and the paper size information that is informed from the paper size watching section . The paper size judging section when it is judged that they are not consistent that is inconsistent performs a notification instruction to the notifying section . Further when it is judged that they are consistent the paper size judging section performs a convert instruction to the converting section .

The notifying section has a function of controlling the display through the display I F and displays a paper size warning scene on the display for notifying of the inconsistency of the document size and the paper size.

On a paper size warning scene as shown by a message is displayed representing that document size of the print object document and paper size of the paper set in the paper feeding source tray of the printer are not consistent. Further the paper size warning scene as shown by has a stop selection button for selecting a stop of print and a print selection button for selecting a continuation of print.

The inputting section has a function of inputting data on the basis of the input from an input apparatus through the display I F and inputs a stop instruction for instructing a stop of print or a continuation instruction for instructing a continuation of print on the basis of a selection of user on the paper size warning scene .

The converting section converts the document data received from the document process application section into image data for print in the printer on the basis of the convert instruction from the paper size judging section or the continuation instruction from the inputting section . The converting section transmits the generated image data and the designation tray information to the printer .

The inquiring process controlling section as shown by includes a judging section a storing section an executing section a document size obtaining section a comparing and judging section an inquiring section an inputting section a changing section and an updating section . The inquiring process controlling section corresponds to the inquiry process control program and executes a comparing and judging process and an inquiring process.

The judging section judges need needlessness of a comparing and judging process on the basis of the application information informed from the document process application section and the storing section . After it is judged that the comparing and judging process is executed the judging section performs an execution instruction to the executing section .

In the storing section as shown by last inquiry time information that is time information is stored corresponding to a process ID and a document name. Here the last inquiry time information represents a last time execution time in the inquiring section . The process ID the document name and the last inquiry time information are generically called inquiry history information.

For example in the storing section that is shown in the last inquiry time information 2008 08 13 10 14 42 is stored corresponding to process ID 4712 and document name specifications.doc .

The executing section obtains document size information and paper size information on the basis of the execution instruction from the judging section and performs an obtainment instruction to the document size obtaining section and the paper size watching section in order to execute a comparing and judging process. Then the executing section after respectively received the document size information from the document size obtaining section and the paper size information from the paper size watching section transmits the document size information and the paper size information to the comparing and judging section .

Further the executing section on the basis of the judgment result informed from the comparing and judging section performs an inquiry instruction to the inquiring section and an updating instruction to the updating section and executes a notification of convert size information to the changing section and the like.

The document size obtaining section on the basis of the judgment result informed from the comparing and judging section analyzes the application information informed from the document process application section and obtains document size information. The document size obtaining section notifies the executing section of the obtained document size information.

The comparing and judging section receives document size information and paper size information from the executing section compares the document size information and the paper size information and judges whether or not they are consistent. The comparing and judging section notifies the executing section of the judgment result representing consistency inconsistency.

The inquiring section is a processing section for controlling the display through the display I F and to execute an inquiring process to a user notifies of the inconsistency of the document size and the paper size on the basis of the inquiry instruction from the executing section and displays an inquiry scene on the display for inquiring the user whether or not the document size is changed.

The inquiring section executes an API call of an OS Operation System as shown by makes to display an inquiry scene that is balloon window in the neighborhood of a display region of a task bar on the display . On the inquiry scene as shown by a message representing that document size of process object document and paper size of paper set in the printer are not consistent is displayed. Further the inquiry scene as shown by has a button for opening a balloon window and selection buttons and for changing the document size of the process object document into the paper size of the printer .

The inputting section inputs a change instruction of document size and tray designation information of a paper tray in which paper is set in order to change on the basis of the input from the inputting apparatus through the display I F .

The changing section after informed of change paper size information from the executing section transmits a change demand and change size information to the document process application section .

The updating section updates the storing section on the basis of an updating instruction from the executing section .

The printer is an image forming apparatus that receives image data from the personal computer and forms an image onto the paper as a print medium on the basis of the image data. In the present embodiment in the printer as shown by two paper trays of lower paper tray upper paper tray are set up as a paper tray section that is an accommodating section accommodating paper. Here the lower paper tray corresponds to tray designation information lower paper tray the upper paper tray corresponds to tray designation information upper paper tray .

In respective paper tray of the paper tray section that is the lower paper tray and the upper paper tray a paper guide is set up into width direction of accommodated paper that is one side of orthogonal direction with paper feeding direction. The paper guide is provided slide free by following two ditches that are set into parallel with the base of paper tray is connected with the side of the accommodated paper and regulates a position of the width direction of the paper.

Further in the printer in the inside base of the lower paper tray and the upper paper tray as shown by optics sensors and are respectively furnished. The optics sensors and detect the positions of the paper guides in respective paper trays.

Furthermore in the neighborhood of the lower paper tray and the upper paper tray as shown by hopping rollers and are respectively furnished. After the hopping roller started to rotate paper accommodated in the lower paper tray is fed every one sheet and is conveyed into an image forming section along with the rotation paper feeding rollers and . Further after the hopping roller started to rotate paper accommodated in the upper paper tray is fed every one sheet and is conveyed into the image forming section along with the rotation paper feeding rollers and .

The image forming section forms an image on the basis of image data onto the conveyed paper. Then paper on which the image is formed is ejected to an ejection tray through the rotation of an ejection roller .

The printer as shown by is composed of a mechanism section and a mechanism controlling section for controlling the mechanism section .

In the mechanism controlling section as shown by a CPU a program storing ROM a RAM a mechanism section I F and an outside transmitting and receiving I F are mutually connected through an address data bus .

The CPU is a center processing apparatus for performing a general control of the printer regards the RAM as a work region and executes all kinds of programs stored in the program storing ROM .

The program storing ROM is a non volatile read only memory and stores a data expansion program and a paper size obtainment program in the present embodiment as shown by .

The paper size obtainment program is a program for obtaining paper size information representing paper size of paper accommodated in the paper tray section .

The RAM is a volatile memory and is used as a work region when all kinds of programs are executed through the CPU .

The mechanism section I F is an interface section for performing communication with the mechanism section .

The outside transmitting and receiving I F is an interface section for performing communication with the personal computer .

The printer as an image forming apparatus as shown by comprises a mechanism section and a mechanism controlling section .

The mechanism controlling section as shown by includes a printer transmitting section a data expanding section a paper size obtaining section and a printer transmitting section .

The printer transmitting section receives image data and tray designation information from the personal computer . Further the printer transmitting section as a demand receiving section receives a transmission demand of paper size information from the personal computer .

The data expanding section is a processing section that operates by executing the data expansion program through the CPU receives image data and tray designation information from the printer transmitting section and performs an expanding process of the image data. The expanded image data and the tray designation information are sent to the mechanism section .

The paper size obtaining section corresponds to the paper size obtainment program and performs a detection instruction to the mechanism section on the basis of a transmission demand from the personal computer in order to obtain paper size information. Then the paper size obtaining section after received guide position information from the mechanism section obtains paper size information on the basis of the guide position information and generates paper tray information. The generated paper tray information is sent to the printer transmitting section .

The paper size obtaining section obtains paper size information of paper set in respective paper trays on the basis of the guide position information. That is the paper size obtaining section obtains paper size information of paper set in the lower paper tray on the basis of the guide position information detected from the lower paper tray . Further the paper size obtaining section obtains paper size information of paper set in the upper paper tray on the basis of the guide position information detected from the upper paper tray . Then the paper size obtaining section generates paper tray information containing the paper size information.

For example paper tray information shown by is composed of paper size information A4 corresponding to the lower paper tray and paper size information B5 corresponding to the upper paper tray . That is in the printer paper of A4 size is set in the lower paper tray paper of B5 size is set in the upper paper tray .

The printer transmitting section transmits paper tray information formed from paper size information of the paper tray section to the personal computer as a paper size transmitting section.

The mechanism section as shown by includes an image forming section a paper feeding section a paper tray section and a paper size detecting section .

The image forming section forms an image onto the paper on the basis of image data received from the mechanism controlling section .

The paper feeding section performs a paper feeding from the paper tray section to the image forming section on the basis of the tray designation information received from the mechanism controlling section . The paper feeding section judges that a paper feeding source tray is any one of the lower paper tray and the upper paper tray on the basis of the tray designation information rotates and drives respective rollers in order to feed paper from the paper feeding source tray to the image forming section .

The paper size detecting section contains optics sensors and and obtains guide position information by respectively detecting the position of the paper guide in respective paper tray of the paper tray section on the basis of a detection instruction from the mechanism controlling section . The paper size detecting section transmits the obtained guide position information to the mechanism controlling section .

Firstly it is to explain operation of the personal computer in the case that a document process operation is detected through the operation detecting section by using flow charts shown by and .

In the document process application section the operation detecting section of the application watching section performs communication with the edition processing section after detected an operation of any one of a document file open operation a new document creation operation a paper setting change operation a document selection operation and a window activation operation that is a document process operation Step S performs an obtainment instruction to the application information obtaining section and notifies of a detection operation name.

The application information obtaining section obtains application information from the edition processing section on the basis of the obtainment instruction from the operation detecting section Step S . The application information obtaining section obtains a process ID a document name of a process object document and document size information and generates application information along with a detection operation name informed from the operation detecting section . Then the application information obtaining section notifies the application information notifying section of the application information.

The application information notifying section notifies the inquiring process controlling section of the application information informed from the application information obtaining section Step S .

After the application information is informed from the document process application section the judging section of the inquiring process controlling section performs a need needlessness judgment about whether or not a comparing and judging process of document size of the process object document and paper size of paper set in the printer is executed Step S . It is to explain about details of the need needlessness judging process in the judging section by using .

In the personal computer after application information is informed from the document process application section to the inquiring process controlling section the judging section firstly obtains a detection operation name from the informed application information Step S . The judging section obtains any one of document file open new document creation paper setting change document selection and window activation as the detection operation name.

Next the judging section judges whether or not the obtained detection operation name is any one of document selection and window activation Step S .

When the detection operation name is not any one of document selection and window activation but any one of document file open new document creation and paper setting change Step S the judging section judges that the comparing and judging process is executed Step S and performs an execution instruction to the executing section Step S .

When the detection operation name is any one of document selection and window activation the judging section further obtains a process ID and a document name from the application information Step S . The judging section obtains for example process ID 4712 and document name specifications.doc from the application information.

Continuously the judging section refers to the storing section and judges whether or not inquiry history information corresponding to the obtained process ID and the obtained document name is stored Step S .

In the storing section shown by the process ID 4712 and the document name specifications.doc are stored. At this time the judging section judges that the corresponding inquiry history information is stored Step S and obtains last inquiry time information Step S . The judging section obtains the last inquiry time information 2008 08 13 10 14 42 corresponding to the process ID 4712 and the document name specifications.doc from the storing section .

Further the judging section obtains present time information representing a time of present. Then the judging section judges whether or not a fixed time has been passed from a time in which the inquiring section executes the last time inquiring process on the basis of the obtained last inquiry time information and the obtained present time information Step S .

After it is judged that the fixed time has been passed Step S the judging section judges that the comparing and judging process is executed Step S and performs an execution instruction to the executing section Step S . Thus the need needlessness judging process is completed in the personal computer .

In the step when it is judged that the fixed time has not been passed the judging section judges that the comparing and judging process is not executed Step S . Thus the need needlessness judging process is completed in the personal computer .

Further in the step when inquiry history information corresponding to the obtained process ID and the obtained document name is not stored in the storing section the judging section judges that the comparing and judging process is executed Step S and performs the execution instruction to the executing section Step S . Thus the need needlessness judging process is completed in the personal computer .

As stated above after the document process operation is detected and the inquiring process with respect to the same process is executed the comparing and judging process of document size and paper size is executed excluding when the fixed time has not been passed.

Returning to after the need needlessness judging process is executed by the judging section Step S and the execution instruction is performed Step S the executing section performs an obtainment instruction to the document size obtaining section and the paper size watching section in order to obtain document size information and paper size information.

The document size obtaining section obtains document size information from the application information received from the document process application section on the basis of the obtainment instruction and notifies the executing section of it Step S . The document size obtaining section obtains for example document size information letter and notifies the executing section of it.

Further the demand transmitting section of the paper size watching section transmits the printer of a transmission demand of paper size information on the basis of the obtainment instruction from the inquiring process controlling section Step S . At this time the demand transmitting section notifies the paper size receiving section of the obtainment demand source information representing that the obtainment demand source is the inquiring process controlling section .

Then after the paper tray information is received from the printer Step S the paper size receiving section obtains paper size information from the paper tray information Step S . For example after the paper tray information shown by is received the paper size receiving section notifies the inquiring process controlling section of the obtained paper size information on the basis of the obtainment demand source information.

Next the executing section transmits the document size information informed from the document size obtaining section and the paper size information informed from paper size watching section to the comparing and judging section . Then the comparing and judging section compares the document size information and the paper size information and judges whether or not they are consistent Step S .

When the document size information and the paper size information are consistent the comparing and judging section judges that paper of the paper size that is consistent with the document size is set in any one of paper tray of the printer . Thus the inquiry controlling process is completed in the personal computer .

When the document size information is letter and the paper size information includes A4 and B5 the comparing and judging section judges that the document size information and the paper size information are not consistent that is inconsistent Step S . Then the comparing and judging section notifies the executing section of the judgment result representing inconsistency.

Continuously the executing section with respect to the inquiring section notifies of the document size information and the paper size information and performs an inquiry instruction.

The inquiring section after received the inquiry instruction from the executing section displays an inquiry scene on the display in order to inquire a user whether or not document size of process object document is changed into the paper size of paper set in the printer Step S . On the display on the basis of a control of the inquiring section as shown by a balloon window of the inquiry scene is displayed in the neighborhood of the task bar .

Further the executing section with respect to the updating section notifies of a process ID and a document name and performs an updating instruction of the storing section . On the basis of the updating instruction the updating section updates the storing section Step S . It is to explain details of an updating process of the storing section through the updating section by using .

In the personal computer after the executing section with respect to the updating section notifies of the process ID and the document name notifies of process ID and document name and performs an updating instruction of the storing section Step S the updating section firstly judges whether or not inquiry history information corresponding to the informed process ID and the informed document name is stored in the storing section in order to update the storing section on the basis of the updating instruction Step S .

For example after the process ID 4712 and the document name specifications.doc are informed the updating section judges that inquiry history information corresponding to the storing section is stored Step S . Continuously the updating section obtains present time information and rewrites the last inquiry time information 2008 08 13 10 14 42 corresponding to the process ID 4712 and the document name specifications.doc into the obtained present time information Step S . Thus the updating process is completed in the personal computer .

When the inquiry history information corresponding to the process ID and the document name is not stored in the storing section Step S the updating section obtains present time information newly creates inquiry history information on the basis of the informed process ID the informed document name and the obtained present time information and stores the inquiry history information in the storing section Step S . Thus the updating process is completed in the personal computer .

As stated above after the inquiring process is executed inquiry history information representing an execution history is updated.

Returning to on the inquiry scene displayed on the display as shown by the selection buttons and for changing document size into paper size are provided. Respective selection buttons and respectively correspond to the lower paper tray and the upper paper tray of the printer . That is the selection button corresponds to a change from document size information letter to paper size information A4 and the selection button corresponds to a change from document size information letter to paper size information B5 .

On the display of the inquiry scene when a user selects a button by operating the inputting apparatus or any one of button is not selected even if a fixed time is passed the inquiring section stops the display of the inquiry scene on the basis of an instruction from the executing section . That is on the display the balloon window of the inquiry scene is closed. Thus the inquiry controlling process is completed in the personal computer .

After the document size is changed the user operates the inputting apparatus on the display of the inquiry scene and selects any one of the selection buttons and . On the basis of the selection the inputting section inputs the change instruction of document size and tray designation information Step S . For example when the selection button is selected the inputting section inputs the change instruction and tray designation information designating the lower paper tray .

After the change instruction and the tray designation information are inputted the executing section notifies the changing section of paper size information corresponding to the inputted tray designation information as change size information Step S . For example the executing section notifies the changing section of change size information A4 . Then the changing section transmits the change demand and the change size information to the document process application section .

After the document process application section received the change demand and the change size information from the inquiring process controlling section the setting section with respect to the process object document in the document process through the edition processing section changes setting of the document size information into the change size information Step S . Thus the inquiry controlling process is completed in the personal computer .

As stated above when the document size of the process object document in the document process is not consistent with the paper size of paper set in the printer the inquiring process is executed that inquires a user whether or not document size is made to be consistent with the paper size.

Next it is to explain an operation of the personal computer when a print instruction is performed through the instructing section by using flow charts shown by and .

In the document process application section after the instructing section performs the print instruction in the edition processing section Step S the edition processing section regards a process object document in the document process as a print object document and transmits document data of the print object document to the image forming section .

In the image forming section after the document data is received Step S the identifying section identifies document size information and tray designation information in which the received document data is contained Step S . The identifying section identifies for example document size information letter and tray designation information automatic selection . Then the identifying section notifies the paper size judging section of the identified document size information and the identified tray designation information.

Further the reception detecting section detects a receiving of the document data and performs an obtainment instruction of paper size information to the paper size watching section .

In the paper size watching section the demand transmitting section transmits a transmission instruction of paper size information to the printer on the basis of the obtainment instruction from the image forming section Step S . Further the demand transmitting section notifies the paper size receiving section of the obtainment demand source information representing that the obtainment demand source is the image forming section .

Then after paper tray information is received from the printer Step S the paper size receiving section obtains paper size information corresponding to respective tray designation information from paper tray information Step S and notifies the image forming section of the paper size information on the basis of the obtainment demand source information. The paper size receiving section obtains for example paper size information A4 corresponding to tray designation information lower paper tray and obtains paper size information B5 corresponding to tray designation information upper paper tray and then notifies the image forming section of them.

Continuously the paper size judging section judges whether or not document size of a print object document and paper size of paper feeding source tray are consistent Step S . The paper size judging section compares document size information informed from the identifying section and paper size information corresponding to tray designation information informed from the identifying section in respective paper size information informed from the paper size watching section and then judges whether or not they are consistent. Further when automatic selection is informed as tray designation information the paper size judging section respectively compares document size information and respective paper size information and then judges whether or not they are consistent.

For example after document size information letter and tray designation information automatic selection are identified and paper size information A4 and B5 are informed the paper size judging section judges that the document size information and the paper size information are not consistent that is inconsistent Step S . Then the paper size judging section with respect to the notifying section notifies of the document size information and the paper size information and performs a notification instruction.

The notifying section displays the paper size warning scene containing the document size information and the paper size information on the display on the basis of the notification instruction from the paper size judging section Step S .

On the display of the paper size warning scene after user selects a stop selection button by operating the inputting apparatus the inputting section inputs a stop instruction Step S . Thus the print instructing process is completed in the personal computer .

On the paper size warning scene after a print selection button is selected the inputting section inputs a continuation instruction Step S . On the basis of the continuation instruction the converting section converts the document data received from the document process application section into image data for print Step S .

Continuously the converting section transmits the converted image data and the tray designation information identified by the identifying section to the printer Step S . Thus the print instructing process is completed in the personal computer .

In the Step S after it is judged that the document size information and the paper size information are consistent the paper size judging section performs a convert instruction in the converting section . On the basis of the convert instruction the converting section converts document data into image data Step S and transmits the image data and tray designation information to the printer Step S . Thus the print instructing process is completed in the personal computer .

As stated above when document size of a print object document and paper size of paper feeding source tray are not consistent a paper size warning scene is displayed on the display in order to make a user select a print stop or a print continuation.

Firstly it is to explain an operation of the printer in the case to receive a transmission demand of paper size information from the personal computer by following . Moreover in the paper tray section of the printer paper of A4 size is accommodated in the lower paper tray and paper of B5 size is accommodated in the upper paper tray .

In the printer after the printer transmitting section received a transmission demand from the personal computer Step S the transmission demand is sent to the paper size obtaining section .

Then the paper size obtaining section performs a detection instruction in the mechanism section on the basis of the transmission demand.

In the mechanism section the paper size detecting section respectively detects positions of the paper guides in the lower paper tray and the upper paper tray through the optics sensors and on the basis of the detection instruction from the mechanism controlling section and obtains respective guide position information Step S . The paper size detecting section transmits the obtained guide position information to the mechanism controlling section .

Continuously the paper size obtaining section obtains paper size information corresponding to respective paper trays on the basis of respective guide position information received from the mechanism section and generates paper tray information Step S . The paper size obtaining section obtains paper size information A4 corresponding to the lower paper tray obtains paper size information B5 corresponding to the upper paper tray as shown by and generates paper tray information. The generated paper tray information is sent to the printer transmitting section .

Then the printer transmitting section transmits the paper tray information containing the paper size information to the personal computer Step S . Thus the obtaining and transmitting process of paper size information is completed in the printer .

As stated above after positions of the paper guides of respective paper trays are detected and paper size information is obtained paper tray information containing the paper size information is generated and is sent to the personal computer .

Next it is to explain an operation of the printer in the case to receive image data for print from the personal computer by following .

In the printer after the printer transmitting section received image data and tray designation information from the personal computer Step S the image data and the tray designation information are sent to the data expanding section .

Continuously the data expanding section performs an expanding process of the image data Step S . The data expanding section transmits the expanded image data and the tray designation information to the mechanism section .

In the mechanism section the paper feeding section receives tray designation information from the mechanism controlling section selects any one of the lower paper tray and the upper paper tray as a paper feeding source tray on the basis of the tray designation information and then feed a paper from the paper feeding source tray of the paper tray section to the image forming section . Then the image forming section forms an image onto the fed paper on the basis of the image data received from the mechanism controlling section Step S . Thus the printing process is completed in the printer .

As stated above on the basis of the image data received from the personal computer an image is formed onto the paper.

A process object document shown by includes text parts graph part and the like. Here the process object document is layout adjusted in order that document size becomes letter size.

In the printer system containing a former personal computer when paper of letter size is not set in the printer if a print of the process object document shown by is instructed the personal computer changes on the basis of an instruction from a user for example document size into paper size of the printer from letter size and then is made to execute the print. The print result is shown by in the case to execute the print by changing document size into A4 size from letter size.

Because size of width direction of paper of A4 size is small comparing with paper of letter size so one part of text parts contained in the process object document of letter size extends over a plurality of lines in a print result of A4 size as shown by . At this time layout of text parts and graph part falls into disorder and then failure print is performed.

On the other hand in the printer system of the present embodiment document size of the process object document is changed from letter into A4 and then the print result is shown by in the case to execute the print.

According to the personal computer of the present embodiment because a change of document size is executed in the document process through the document process application section for example after character size of texts contained in the text parts of the process object document is changed through instructing to print it is possible to obtain a print result containing text parts and a graph part as shown by .

As stated above the personal computer of the present embodiment after detected an operation of the document process application section executes a comparing and judging process of process object document size and paper size of paper set in the printer . Then when paper of the same size as the document size is not set in the printer a user is inquired whether or not document size is changed document size is changed into paper size in the printer on the basis of the instruction from user. Therefore it is possible to restrain the occurrence of failure print caused by inconsistency between document size and paper size. Because the comparing and judging process is executed before the print instruction so even when document size is changed and the layout of the process object document falls into disorder it is possible for a user to confirm and because it is possible to amend through the document process application section so a restraint effect of the failure print is improved.

Further in the personal computer of the present embodiment because it is possible to prevent repeating to execute inquiring processes with respect to the same process object document in a short time by setting a storing section for storing history information of inquiring processes so unnecessary process cost is reduced and then the convenience is improved.

Moreover in the present embodiment the application watching section is explained as a plug in that operates in the inside of a process of the document process application section . However the present invention is not limited in the case. For example it is possible to obtain a form of outside program that performs an operation detection through watching access operations to document file.

A printer system of the present embodiment is composed of a personal computer and a printer . Such structure as a searching section and an application information demanding section are added in the personal computer and such structure as an installation detecting section is added in the printer are different from that of embodiment 1.

Moreover in the present embodiment the same structure as the embodiment 1 is shown by the same mark and the detailed explanations about them are omitted.

The printer as an image forming apparatus as shown by comprises a mechanism section and a mechanism controlling section .

The mechanism section as shown by includes an image forming section a paper feeding section a paper tray section a paper size detecting section and an installation detecting section .

The installation detecting section after any one of the lower paper tray and the upper paper tray is drawn out in the paper tray section if it is installed again detects the installation and then notifies the mechanism controlling section of it.

The mechanism controlling section as shown by FIG. includes a printer transmitting section a data expanding section a paper size obtaining section and a printer transmitting section .

The paper size obtaining section performs a detection instruction to the mechanism section on the basis of a transmission demand from the personal computer . Then the paper size obtaining section receives guide position information from the mechanism section obtains paper size information on the basis of the guide position information and generate paper tray information as shown by .

Further the paper size obtaining section after informed of the installation of the paper tray section from the mechanism section performs a detection instruction to the mechanism section obtains paper size information and generates paper tray information. Then the paper size obtaining section generates a paper change flag for informing of the installation of the paper tray section that is a change of paper in the paper tray section and then adds it to paper tray information.

The paper size obtaining section obtains for example A4 and B5 as paper size information corresponding to respective paper trays on the basis of the guide position information. Further the paper size obtaining section generates a paper change flag 1 as installation information representing installation of the paper tray section . Then the paper size obtaining section adds the generated paper change flag 1 to respective obtained paper size information A4 and B5 as shown by and generates paper tray information.

The personal computer as an image processing apparatus as shown by includes a document process application section a paper size watching section an image forming section and an inquiring process controlling section .

The document process application section as shown by is composed of an edition processing section an application watching section and an instructing section .

The application watching section as shown by has a setting section an operation detecting section an application information obtaining section and an application information notifying section .

The application information obtaining section on the basis of the obtainment instruction performs communication with the edition processing section and obtains application information. Further the application information obtaining section obtains application information on the basis of the obtainment instruction from the inquiring process controlling section . The application information obtaining section notifies the application information notifying section of the obtained application information.

The paper size watching section as shown by includes a demand transmitting section and a paper size receiving section .

The paper size receiving section as a medium size receiving section and a medium size obtaining section receives paper tray information from the printer and obtains paper size information. The paper size receiving section when the paper change flag is not added to the received paper tray information performs a notification of the obtained paper size information on the basis of obtainment demand source information informed from the demand transmitting section . Further the paper size receiving section as a convert detecting section when the paper change flag is added to the paper tray information detects a change of paper set in the printer and then notifies the inquiring process controlling section of the paper change information representing the change of paper and the obtained paper size information.

The inquiring process controlling section as shown by includes a judging section a storing section an executing section a document size obtaining section a comparing and judging section an inquiring section an inputting section a changing section a updating section a searching section and an application information demanding section .

The executing section performs an obtainment instruction to the document size obtaining section and the paper size watching section on the basis of an execution instruction from the judging section . Then the executing section transmits the document size information and the paper size information to the comparing and judging section to execute a comparing and judging process. Further the executing section on the basis of a judgment result from the comparing and judging section executes an inquiry instruction to the inquiring section an updating instruction to the updating section a notification of change size information to the changing section and the like.

Furthermore the executing section after received the paper change information and the paper size information from the paper size watching section performs a search instruction to the searching section .

The searching section searches respective windows displayed on the display specifies an active window that is a window in operation and obtains a process ID of a program corresponding to the window. The searching section performs an obtainment of the process ID by using an API of OS.

Further the searching section obtains process information of a program corresponding to the process on the basis of the obtained process ID. The searching section performs an obtainment of process information by using the API of OS. Then the searching section refers to the obtained process information and then judges whether or not the process is a process in starting in the document process application section .

The application information demanding section performs an obtainment instruction of application information with respect to the document process application section .

In the present embodiment firstly it is to explain an operation of the printer by using a flow chart shown by .

The operation of the printer is the same as that of embodiment 1 in the case to receive a transmission demand of paper size information or image data for print from the personal computer so explanations are omitted. Here it is to explain an operation of the printer in the case that the installation of the paper tray section is detected.

In the printer the installation detecting section after detected the installation of the paper tray section Step S notifies the mechanism controlling section of it.

Continuously the paper size obtaining section performs a detection instruction to the mechanism section .

In the mechanism section the paper size detecting section on the basis of the detection instruction from the mechanism controlling section obtains guide position information by respectively detecting positions of the paper guides in the lower paper tray and the upper paper tray through the optics sensors and and then transmits it to the mechanism controlling section Step S .

Continuously the paper size obtaining section on the basis of respective guide position information received from the mechanism section obtains respective paper size information as shown by and generates paper tray information Step S .

Further the paper size obtaining section generates a paper change flag 1 as shown by and adds the paper change flag to the paper tray information Step S . Then the paper size obtaining section transmits the paper tray information to the printer transmitting section .

Next the printer transmitting section transmits the paper tray information composed of the paper size information and the paper change flag to the personal computer Step S . Thus the generating and transmitting process of paper tray information is completed in the printer .

As stated above after the installation of the paper tray section is detected and paper size information corresponding to respective paper trays is obtained paper tray information is generated by adding a paper change flag and is sent to the personal computer .

Next it is to explain an operation of the personal computer of the present embodiment by following a flow chart shown by and .

Because the operation of the personal computer in the case that a document process operation is detected is the same as that of embodiment 1 so explanations are omitted. In the present embodiment it is to explain an operation of the personal computer in the case to receive paper tray information from the printer .

In the personal computer the paper size receiving section of the paper size watching section after received paper tray information from the printer Step S the paper size receiving section judges whether or not a paper change flag is added to the paper tray information Step S . When the paper change flag is not added the personal computer completes the process.

For example as shown by when a paper change flag is added to paper tray information Step S the paper size receiving section obtains respective paper size information from the paper tray information Step S . The paper size receiving section notifies the inquiring process controlling section of the obtained respective paper size information and paper change information.

The executing section of the inquiring process controlling section after received the paper change information and the paper size information from the paper size watching section performs a search instruction to the searching section .

Continuously the searching section obtains a process ID of a program in starting in the active window Step S .

Next the searching section obtains process information on the basis of the obtained process ID Step S .

Then the searching section refers to the obtained process information and judges whether or not the process is a process in starting in the document process application section Step S . After it is judged that the process is not a process of the document process application section the personal computer completes the process.

After it is judged that the process is a process of the document process application section Step S the searching section notifies the application information demanding section of the process ID. Then the application information demanding section performs an obtainment instruction of application information with respect to the document process application section Step S .

In the application watching section of the document process application section the application information obtaining section obtains application information from the edition processing section on the basis of the obtainment instruction from the inquiring process controlling section Step S . The application information obtaining section notifies the application information notifying section of the obtained application information.

Then the application information notifying section notifies the inquiring process controlling section of the informed application information Step S .

After the application information is informed from the document process application section the judging section of the inquiring process controlling section performs a need needlessness judgment about whether or not a comparing and judging process of document size of a process object document and paper size of paper set in the printer is executed Step S . Because the flow of need needlessness judging process in the judging section is the same as that of embodiment 1 so explanations are omitted.

After the need needlessness judging process is executed through the judging section Step S and an execution instruction is performed Step S the executing section performs an obtainment instruction to the document size obtaining section in order to obtain document size information.

The document size obtaining section obtains document size information from the application information received from the document process application section on the basis of the obtainment instruction and then notifies the executing section of it.

Then the executing section transmits the document size information informed from the document size obtaining section along with the paper change information and the paper size information that are informed from the paper size watching section to the comparing and judging section . Then the comparing and judging section compares the document size information with the paper size information and judges whether or not they are consistent that is performs a comparing and judging process Step S .

When document size information is consistent with paper size information the comparing and judging section judges that paper of paper size that is consistent with document size is set in any one of paper tray of the printer . Thus the inquiry controlling process is completed in the personal computer .

When it is judged that document size information and paper size information are not consistent that is inconsistent Step S the comparing and judging section notifies the executing section of the judgment result representing inconsistency.

Then the executing section informs of document size information and paper size information with respect to the inquiring section and then performs an inquiry instruction.

The inquiring section displays an inquiry scene on the display on the basis of the inquiry instruction from the executing section Step S .

Further the executing section informs of a process ID and a document name with respect to the updating section and then performs an updating instruction. On the basis of the updating instruction the updating section updates the storing section Step S .

On the display of the inquiry scene when any one of the selection buttons and is selected the inputting section inputs a change instruction of document size and tray designation information Step S . On the basis of the input the executing section notifies the changing section of paper size information corresponding to the inputted tray designation information as change size information Step S . Then the changing section transmits a change demand and the change size information to the document process application section .

After the document process application section receives the change demand and the change size information from the inquiring process controlling section the setting section changes a setting of document size information into the change size information with respect to the process object document Step S . Thus the inquiry controlling process is completed in the personal computer .

As stated above after a paper change is detected in the printer a comparing and judging process of document size of a process object document in the document process through the document process application section and paper size of the printer is executed when they are not consistent the inquiring process is executed.

Further because the operation of the personal computer is the same as that of embodiment 1 in the case that the print instruction is performed through the instructing section so explanations are omitted.

As stated above according to the printer system of the present embodiment because the printer after detected the installation of the paper tray section is capable of obtaining paper size information of the paper tray section and informing the personal computer of it it is possible for the personal computer to detect the inconsistency of document size and paper size not only when a document process operation is detected but also when a paper change is detected. Therefore it becomes possible to further restrain the occurrence of the failure print.

In respective embodiments stated above a printer is adopted as an image forming apparatus that is connected to an image processing apparatus. However the present invention is not limited in the case. For example it is also possible to adopt MFP that has both FAX function and scanner function.

The present invention is not limited to the foregoing embodiments but many modifications and variations are possible within the spirit and scope of the appended claims of the invention.

