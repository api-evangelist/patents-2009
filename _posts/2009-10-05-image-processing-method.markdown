---

title: Image processing method
abstract: There is provided a method for image processing to transfer scanned data of a document read by an image reading apparatus to an application which is operated in an information processing apparatus connected to the image reading apparatus. The method includes obtaining an execution path of an application which is currently operated in the information processing apparatus, and transferring the scanned data to the image reading apparatus by using the execution path.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08345302&OS=08345302&RS=08345302
owner: Canon Kabushiki Kaisha
number: 08345302
owner_city: Tokyo
owner_country: JP
publication_date: 20091005
---
The present invention relates to an image processing method for transferring scanned image data by a desired application.

As discussed in Japanese Patent Application Laid Open No. 10 275209 a system has conventionally been known which simply analyses read image data to determine an adaptive application program and instructs a device to start the determined adaptive application program.

Japanese Patent Application Laid Open No. 2000 316065 discusses a system that scans data from a user interface of a peripheral device to transfer scanned data to a selected application.

In these conventional examples when the selected application basically processes text data an image is converted into an appropriate text file.

However the system discussed in Japanese Patent Application Laid Open No. 10 275209 automatically determines an application to be started according to a type of image data obtained by analysis hence depending on a result of the analysis the data is not always transferred to an application desired by a user.

In the system discussed in Japanese Patent Application Laid Open No. 2000 316065 a host computer and the peripheral device communicate with each other about application information and an application installed in the host computer is displayed on the peripheral device side for selection. Thus the peripheral device has to select an application of a transfer destination of the data each time.

The present invention is directed to a method that can properly display scanned data on an application of a transfer destination.

According to an aspect of the present invention there is provided a method for image processing to transfer scanned data of a document read by an image reading apparatus to an application which is operated in an information processing apparatus connected to the image reading apparatus. The method includes obtaining an execution path of an application which is currently operated in the information processing apparatus and transferring the scanned data to the image reading apparatus by using the execution path.

According to another aspect of the present invention there is provided a computer readable storage medium which stores a program for causing an information processing apparatus to execute a method for image processing to transfer scanned data of a document read by an image reading apparatus to an application which is currently operated in the information processing apparatus connected to the image reading apparatus.

According to an exemplary embodiment of the present invention read scanned data can be displayed by an application intended by a user without designating any application to be started to display the scanned data. As a result convenience can be greatly improved.

Further according to the exemplary embodiment the scanned data can be displayed by the application intended by the user without changing any designated contents which are displayed by other applications. As a result convenience can be greatly improved.

The scanned data is converted into data according to a display capability e.g. supporting only text data only image data or both of an application of a transfer destination and transferred. Thus the scanned data can be properly displayed on the application.

Further features and aspects of the present invention will become apparent from the following detailed description of exemplary embodiments with reference to the attached drawings.

Various exemplary embodiments features and aspects of the invention will be described in detail below with reference to the drawings.

The information processing apparatus is an example of an image processing apparatus that performs scanning in a reading apparatus including an image reading function and displays scanned data of a read document by an application of a host computer. In other words the information processing apparatus may be a host personal computer PC and implements a method for performing scanning in the reading apparatus including the image reading function and displaying scanned data by the application of the host computer. The image processing apparatus is connected to a scanner . The image processing apparatus includes a central processing unit CPU a primary storage device a secondary storage device an interface I F unit an input device an output device and a system bus .

The scanner includes a CPU a read only memory ROM a random access memory RAM a communication unit a display unit a reading control unit an operation unit and a system bus .

The CPU performs calculation determination or control of data or a command and execution of a program stored in the primary storage device . The primary storage device is mainly configured by a memory for loading and storing a program or the like stored in the secondary storage device .

The secondary storage device is for example a hard disk. In the first exemplary embodiment a program is stored in the secondary storage device and loaded to the primary storage device to be executed by the CPU . The I F unit is for example a universal serial bus USB interface for communicating with a scanner which includes a reading function.

The input device is for example a mouse a keyboard or a controller. The output device is for example a display. The system bus is a transmission path for transferring a command or data between the CPU and the I F unit the output device or the storage devices and . The scanner is connected to the information processing apparatus via the I F unit .

The CPU includes a microprocessor that controls the RAM the communication unit the display unit the reading control unit and the operation unit according to a program stored in the ROM . The RAM stores scanned image data sent from the reading control unit .

The communication unit communicates with the information processing apparatus when the data stored in the RAM or button event information is sent to the information processing apparatus or conversely when a command for controlling the scanner from is received from the information processing apparatus .

The reading control unit includes a direct memory access DMA controller an image processing integrated circuit IC a complementary metal oxide semiconductor CMOS logic IC or the like and converts the scanned image data into multi valued or binarized data to sequentially send them to the RAM .

The display unit includes a light emitting diode LED or the like and displays a status during operation setting or an operation of the scanner. The operation unit includes a power switch a reset switch an operation selection button a scan button and the like and can be freely operated by a user.

The user interface displays an event selection section an operation setting section and a start application setting section .

The event selection section selects and sets an operation according to a button even. A user can select various events such as store in a Joint Photographic Experts Group JPEG format store in a portable document format PDF format transfer to an application and the like.

The operation setting section is used for setting an operation for the event selected by the event selection section when the button event is received from the scanner .

The start application setting section is displayed when an even of OPEN BY APPLICATION is selected in the event selection section and used for setting an application to which the scanned image data is transferred. This setting is set in an active application.

The CPU issues a scan start event from a peripheral device to the host computer and starts a utility for scanning using a scanner driver that can control a reading operation of the peripheral device. The CPU determines whether the scan start event starts up the utility.

The scanner reads an image using the scanner driver according to reading setting when the scan start event is issued.

The CPU obtains an execution path of an application which is active in the information processing apparatus when the scan start event is issued.

In step S the information processing apparatus detects an event that an OPEN BY APPLICATION event is selected by the operation unit of the scanner and sent from the communication unit .

In step S the information processing apparatus starts the utility using a service of an operating system OS or the like. The utility determines whether the event is for opening an application. A content of the event is obtained by using an application programming interface API of the OS or the like. A tool for obtaining an event may be used in place of using the service or the API of the OS.

If the event is different from the OPEN BY APPLICATION event NO in step S then in step S processing based on a content set by the event selection section of for example processing corresponding to an event for scanning and storing data in a PDF format and attaching the data to E MAIL is executed.

If the event is determined as the OPEN BY APPLICATION YES in step S then in step S the utility obtains an execution path of a currently active application using APIs of a plurality of OSs. For example when an OS is Windows registered trademark the utility first obtains a handle of the active window and obtains process ID that has created the window from the window handle.

Alternatively the utility obtains a handle of a forefront window and obtains class information of the window. If the class information is about a class of a target to which data stored by the utility is transferred a process ID is obtained from the window handle. If the class information is about a class other than a target to which the data stored by the utility is transferred a handle of a window which is at a back of the forefront window is obtained to execute similar processing.

The utility obtains all pieces of process information by a snapshot and compares them with the ID of the process that has created the active window. The utility obtains a path of the application from the process information matched with the process ID.

In place of obtaining the handle of the active window the utility may execute the following. A list of window handles is obtained from the OS and when the window handles can be obtained in stacked order of windows the window handle which is obtained first can be used as a handle of a currently active window.

When all applications that have been started are minimized and it is determined that there is no currently active application or when a desk top screen is currently displayed an active application is determined as follows. In such a case a window on a top of Z order that indicates stacked order of windows obtainable using the API of the OS is regarded as the active application.

When a dynamic link library DLL of the system is obtained as an execution path the DLL cannot be started because it is not an application. Thus an active application is determined using a handle of a window second highest in the Z order.

In addition to the above methods if an API which can acquire a path of a currently active application is prepared on the OS side the API may be used. A method for determining a path of an active application is not limited to the above.

In step S the scanner performs scanning via the scanner driver based on the content set by the operation setting section of .

After completion of the scanning in step S a transfer format of the scanned data is determined. The determination is executed by displaying a dialog to cause the user to select a format. If an application has performed the determination of the transfer format before a previous result is stored and processing can be continued according to the previous selection result without displaying any dialog. The transfer format may be stored beforehand in a database for each application. When an application of a transfer destination is determined a transfer format corresponding to the application may be determined by reading from the database.

In step S if the transfer data format is only for image data YES in step S then in step S the active application obtained in step S is started using the scanned data as a command line argument. At this point to notify the application of the transfer destination of the on going transfer of the scanned data the application is started by a command line argument in which a parameter of the scanned data is added in addition to the path of the scanned data.

An example of a command line can be described as follows c programfiles microsoft office office12 winword. Exe i c Image0001.bmp c Image0002.bmp . Microsoft is a registered trademark.

In step S if the transfer data format is determined to be only for text data YES in step S then in step S the utility converts the scanned data into text data. As a method for conversion into text data a method for extracting a text area by executing OCR processing for the scanned data or the like can be used. There are no particular restrictions on a method for conversion into text.

In step S the data converted into the text data is stored and the scanned data is discarded. In other words the scanned data is not necessary after it is converted into the text data and hence removed from the secondary storage device .

In step S the utility designates a path of the text data stored in step S as a command line argument and starts the active application obtained in step S.

If determination is NO in both of steps S and S the transfer data format is determined to be for both image data and text data. In step S the utility converts the scanned data into text data. In step S the utility stores the text data in the secondary storage device .

In step S the utility transfers the scanned data and the text data stored in step S as command line arguments to the active application obtained in step S to be executed.

At this point to notify the application of the transfer destination of the on going transfer of the image data a parameter of the image format is added in addition to the execution path to start the command line.

In the processing method of the first exemplary embodiment the transfer format of the scanned data is determined by user s selection on the dialog. However in the second exemplary embodiment the transfer format is automatically determined without causing the user to select it on the dialog.

Steps S to S S S to S and S to S are similar to those of the flowchart of of the first exemplary embodiment and hence description thereof will be omitted.

In step S scanned image data is separated into an image area and a character area. An arbitrary method may be used for the separation processing. In the second exemplary embodiment an image area and a character area are discriminated from each other based on values obtained by conventional fast Fourier transformation.

In step S if only an image area is detected or no character area is detected YES in step S it is determined that the scanned data includes only image data. In step S the image data is transferred to an active application.

In step S if only a character area is detected YES in step S it is determined that the scanned data includes only text data and processing in steps S to S are executed. In this case if an active application cannot process text data the text data is converted into image data to be sent.

If determination is NO in both steps S and S it is determined that the scanned data includes both image data and text data and processing in steps S to S are executed. In this case if an active application cannot process the image data only the text data is transferred. If an active application cannot process the text data the text data is converted into image data to be transferred.

A recording storage medium which stores program codes programs of software for realizing the functions of the above described exemplary embodiments may be supplied to a system or an apparatus and a computer CPU or micro processing unit MPU of the system or the apparatus may read the program codes stored in the recoding medium to execute them. In this case the program codes read from the recording medium realize the functions of the first and second exemplary embodiments and the recording medium storing the program codes constitutes the present invention.

The recording medium for supplying the program codes can include for example a flexible disk a hard disk an optical disk a magneto optical disk a compact disc CD ROM a CD readable CD R a magnetic tape a nonvolatile memory card a ROM and a DVD.

Based on instructions of the program codes read from the recording medium by the computer the operating system OS or the like running on the computer can execute a part or all of actual processing to realize the functions of the exemplary embodiments. This case is included in the present invention.

The program codes read from the recording medium are written in a function extension board inserted into the computer or a function extension unit connected to the computer. Then based on instructions of the program codes a CPU or the like disposed in the function extension board or the function extension unit can execute a part or all of actual processing to realize the functions of the exemplary embodiments. This case is included in the present invention.

An image processing apparatus including a peripheral device and a computer formed integrally whose configuration can realize the functions of the exemplary embodiments is also included in the present invention.

While the present invention has been described with reference to exemplary embodiments it is to be understood that the invention is not limited to the disclosed exemplary embodiments. The scope of the following claims is to be accorded the broadest interpretation so as to encompass all such modifications and equivalent structures and functions.

This application claims the benefit of Japanese Patent Application No. 2008 260436 filed on Oct. 7 2008 which is hereby incorporated by reference herein in its entirety.

