---

title: Printing method to load filter dynamically and recordable medium with program to execute the printing method and host apparatus
abstract: A printing method which dynamically loads a filter, a recordable medium with a program to execute the printing method, and a host apparatus. The printing method uses filter setting information having at least one filter corresponding to a print option of a print document, the printing method can include selecting a print option, changing the filter setting information corresponding to the print option, and applying the printing option according to the changed filter setting information and transmitting print data.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08502995&OS=08502995&RS=08502995
owner: Samsung Electronic Co., Ltd.
number: 08502995
owner_city: Suwon-si
owner_country: KR
publication_date: 20090304
---
This application claims priority from Korean Patent Application No. 10 2008 0027105 filed on Mar. 24 2008 in the Korean Intellectual Property Office the disclosure of which is incorporated herein by reference in its entirety.

Apparatuses and methods consistent with the present general inventive concept relate to a printing method recordable medium and host apparatus and more particularly to a printing method to load a filter dynamically a recordable medium with a program to execute the printing method and a host apparatus.

Recently Microsoft has unveiled concepts on a new XPS XML Paper Specification file format to replace existing EMF files and an XPS based print driver to print in the XPS file format.

From the GDI print path if a print command is sent through a Win32 application for original data a spooler spools the original data into an enhanced meta file EMF . The EMF file is rendered into a GDI Graphic Device Interface function supplied by Windows OS by a GDI rendering engine of a GDI based printer driver . The rendered EMF file is rendered into a PDL Page Description Language by a PDL conversion transmitter to be recognized by the printer and then transmitted to the printer . Therefore the printer finally prints the file. Here PDL includes PCL Printer Command Language developed by HP and PS PostScript developed by Adobe.

From the XPS print path if a print command is sent through .Net Framework 3.0 based WPF Windows Presentation Foundation application for original data a spooler spools the original data into an XPS file format. A filter pipeline administrator reads a filter setting file and loads a first filter a second filter and an nth filter in sequence written in the filter setting file to process the XPS spool file . The XPS spool file processed by the nth filter is transmitted to the printer to be printed.

Here OS provides a GDI to XPS converter to convert the original data into the XPS spool file to thereby print the original data written from the Win32 application along the OXS print path. Conversely an XPS to GDI converter is also provided to convert the original data into GDI to thereby print the original data written from the WPF application along the GDI print path.

To embody the foregoing XPS print path an XPS printer driver is required and the detailed configuration thereof is as shown in .

The XPS printer driver includes a Version 3 driver and a filter pipeline administrator . The Version 3 driver includes a conversion render module to convert the original data written from the Win32 application using a GDI print API Application Programming Interface into an XPS spool file and a setting module to receive printer setting information.

The filter pipeline administrator reads a filter setting file and loads the first filter and second filter to nth filter in sequence corresponding to a filter description written in the filter setting file . The respective filters and process the XPS spool file according to a principle set during programming. The processed XPS spool file is transmitted to the printer to be printed.

As shown therein four filter descriptions A of watermark overlay N up and render are written in sequence in the filter setting file .

The filter pipeline administrator reads the filter setting file and loads watermark overlay N up and render filters corresponding to the filter description A in sequence to process an XPS spool file . More specifically the filter pipeline administrator loads the watermark filter first. The watermark filter outputs an XPS spool file watermarked from the XPS spool file . The watermarked XPS spool file is inputted to the next overlay filter . The XPS spool file inputted by the overlay filter is used to output an overlaid XPS spool file. Likewise as the XPS spool file passes through the filter pipeline including a series of filters and each of the filters and processes the XPS spool file . Here the render filter converts the inputted XPS file into a PDL required by the printer . Then the converted PDL data are transmitted to the printer to be printed.

However the conventional filter setting file has the fixed filter description A and filters are loaded to process print options even though a user did not select the print option.

If the render filter is fixed in the filter setting file the XPS spool file passes through the render filter to increase the printing job time even though the printer supports the XPS spool file format and the PDL conversion is not necessary.

If a printer does not support the XPS spool file format the render filter should be present. However if the filter setting file is fixed to have no render filter the printer may not print the file. Particularly considering office environment where a plurality of host apparatuses and printers are connected in a network some printers may not be used as the filter description of the render filter is fixed in the filter setting file.

The present general inventive concept provides a printing method to dynamically change filters according to a print option a recordable medium with a program to execute the printing method and a host apparatus.

The present general inventive concept also provides a printing method which reduces print time a recordable medium with a program to execute the printing method and a host apparatus.

The present general inventive concept also provides a printing method that performs a print operation even if a data format recognizable by an image forming apparatus changes a recordable medium with a program to execute the printing method and a host apparatus.

Additional aspects and utilities of the present general inventive concept will be set forth in part in the description which follows and in part will be obvious from the description or may be learned by practice of the general inventive concept.

Embodiments of the present general inventive concept can be achieved by providing a printing method which uses filter setting information having at least one filter corresponding to a print option of a print document and an XPS printer driver the printing method including selecting the print option changing the filter setting information corresponding to the print option and applying the printing option according to the changed filter setting information and transmitting print data.

The printing method may further include restoring the filter setting information after the print operation.

The changing the filter setting information may include initializing the filter setting information and changing the filter setting information according to at least one filter corresponding to the selected print option.

The printing method may further include displaying changed content of the filter setting information.

The printing method may further include determining whether an image forming apparatus to which the print data is to be transmitted is able to print the print data.

The printing method may further include changing the print data to be printed by the image forming apparatus if the image forming apparatus is unable to print.

The printing method may further include displaying print unavailability if an image forming apparatus to which the print data is to be transmitted is not able to print the print data.

Embodiments of the present general inventive concept can also be achieved by providing a recordable medium with a computer program to execute a printing method the printing method which uses filter setting information having at least one filter corresponding to a print option of a print document and an XPS print driver and includes selecting the print option changing the filter setting information corresponding to the print option and applying the printing option according to the changed filter setting information and transmitting print data.

Embodiments of the present general inventive concept can also be achieved by providing a host apparatus which has an interface to be connected with an image forming apparatus the host apparatus including an input unit to receive a print option a storage unit which stores therein an application program to write a print document and filter setting information and a controller which changes the filter setting information to have at least one filter corresponding to the inputted print option generates print data about the print document according to the changed filter setting information and transmits the generated print data to the image forming apparatus through the interface if a print command is sent for the print document.

The controller can restore the filter setting information after the print data are transmitted to the image forming apparatus.

The controller initializes the filter setting information when changing the filter setting information and changes the filter setting information according to at least one filter corresponding to the selected print option.

The host apparatus further includes a display unit wherein the controller controls the display unit to display changed content of the filter setting information.

The controller can change the print data to be printed by the image forming apparatus if the print data are not printable by the image forming apparatus.

The host apparatus may further include a display unit wherein the controller displays print unavailability on the display unit if the print data are not printable by the image forming apparatus.

Reference will now be made in detail to the embodiments of the present general inventive concept examples of which are illustrated in the accompanying drawings wherein like reference numerals refer to like elements throughout. The embodiments are described below so as to explain the present general inventive concept by referring to the figures.

A printing method a recordable medium with a program to execute the printing method and a host apparatus according to exemplary embodiments will be described in detail with reference to accompanying drawings.

The host apparatus according to the present embodiment includes an input unit a display unit a storage unit a host interface and a controller .

The input unit includes an input means such as for example a mouse and a keyboard to receive a user input.

The display unit includes a display device such as for example a CRT monitor and an LCD monitor. The display unit displays a UI user interface thereon to select a print option.

The storage unit includes a storage medium such as for example a hard disk flash memory and RAM to read and write. The storage unit stores therein an XPS spool file and a filter setting file .

The storage unit may store therein an application program such as WPF Windows Presentation Foundation application or WIN application to write a print document.

The storage unit stores therein an Operating System OS not shown to support an operation of the application program . The WPF application operates in Windows Vista OS of Microsoft and may operate if .Net Framework 3.0 is installed in Windows XP or Windows 2003 OS. The Windows Vista and Windows XP and Windows 2003 having the .Net Framework 3.0 support the XPS print path as a new print architecture.

The XPS spool file may be stored in the storage unit in two cases. First if a print command is sent through the WPF application the WPF application generates data of print documents in an XPS document format. Then the XPS spool file is stored in the storage unit . The XPS document format is defined in XPS XML Paper Specification and the XPS document format conforms to the XPS spool file format.

Second if a print command is sent through the Win32 application for a print document a spooler converts data of GDI based print document written in the Win32 application into the XPS spool file by using a GDI to XPS conversion module of the OS.

That is the XPS spool file may be generated by the conversion module not only when the print command is sent through the WPF application but also through the WIN32 application.

The generated XPS spool file includes original data written from the application program a print option for the original data and setting information of an image forming apparatus connected to the host apparatus . Here the print option which is included in the XPS spool file also includes a print option selectively inputted by a user through the input unit .

The filter setting file includes filter information about at least one of first filter to nth filter to be loaded by a spool file processor of the controller to be described later . Here the filter information includes a filter description B such as a name of a filter to be loaded. The filter setting file may be called filter setting information.

The controller changes the filter setting file to have at least one filter corresponding to the print option inputted through the input unit if a print command is sent through the application program for the print document.

More specifically the controller changes the filter description B of the filter setting file according to the print option inputted by the input unit . Then the filter description B of the filter setting file is changed dynamically corresponding to the print option selected by a user and the data do not need to pass through unnecessary filters. Thus more efficient print is available and print time can be reduced.

In some cases the controller may control the display unit to display a detail of the changed filter setting file .

If necessary the controller may initialize the filter setting file not to have the filter description B when changing the filter setting file . Then the controller may determine the selected print option and add filter information corresponding to the determined print option to the initialized filter setting file to thereby change the filter setting file .

The controller generates print data of the print document according to the changed filter setting information and transmits the generated print data to the connected image forming apparatus through a host interface .

More specifically the controller loads at least one of the filters and according to the changed filter setting file and controls the XPS spool file of the print document to pass through the loaded filters and to thereby generate print data. The controller transmits the generated print data to a printer interface of the image forming apparatus through the host interface .

The print data are the XPS spool file which has passed through the filters and to be processed and may include spool data and data having print option information inputted through the input unit .

If the image forming apparatus does not support the XPS spool file the print data may be converted into a PDL Page Description Language another format supported by the image forming apparatus through a render filter in to be described later .

The controller may store the original filter setting file in the storage unit before the filter description B is changed. After the XPS spool file is completely printed the controller may restore the stored filter setting file. More specifically the controller removes the filter setting file having the changed filter description B and restores the original filter setting file not shown . Here the original filter setting file not shown may be additionally stored in another storage space of the storage unit and then the changed filter setting file may be removed before the additionally stored original filter setting file is moved to the original position. Otherwise a name of the original filter setting file not shown may be changed temporarily and then it can be changed into the original name after the completion of a print operation. Further other known methods may be employed to avoid Microsoft s Windows Hardware Quality Labs WHQL certification.

If a printer driver has a WHQL certification it should receive certification again when information such as file size and date are changed causing an inconvenience in using the printer driver. Thus the filter setting file which has changed to efficiently execute the XPS spool file may be removed after the completion of the print operation and the original filter setting file may be restored to thereby avoid issues related to the WHQL certification.

The original filter setting file is restored after the completion of the print operation but it may be restored if the filter setting file is not needed any more even though not physically after the completion of the print operation. For example if print data of the print document are transmitted to the image forming apparatus if the filter processes the XPS spool file or if the XPS spool file passes through the filter pipeline the filter setting file is not required anymore.

Meanwhile the controller includes a spool file processor to process data of the print document according to the print option.

More specifically the controller includes the spool file processor to process the XPS spool file of the print document according to the print option.

The spool file processor forms a filter pipeline which includes the filters and loaded corresponding to the filter description B written in the filter setting file . More specifically the filter description B of the filter setting file is changed by the controller before the filters and are loaded by the spool file processor and the filters and corresponding to the changed filter description B are loaded. The filters and are loaded in sequence as written in the filter description B and process the XPS spool file according to assigned functions.

The filters and may include at least one of a watermark filter to process a watermark print option an overlay filter to process an overlay print option an N up filter to process an N up print option a poster filter to process a poster print option and a render filter to convert an XPS file format into a PCL Printer Control Language to be recognized by the image forming apparatus and a PDL Paper Description Language such as PS PostScript .

The overlay print option is used to overlay contents of two original documents in one page while the poster print option is used to enlarge the original data in 2 2 or 4 4 to print the data. The N up print option is used to print a plurality of pages of the original data in one page.

The spool file processor may include a filter pipeline administrator refer to of Microsoft. Any element can be a spool file processor as long as it loads a filter for independent processing and enables each filter to process a spool file.

The XPS spool file which is processed by the nth filter is transmitted to the image forming apparatus through the host interface . The host interface may include one of a parallel port and a USB port. The host interface may have a network interface card to be connected to the Internet.

The image forming apparatus receives the processed XPS spool file through the printer interface . The printer controller controls a printing unit to print the received XPS spool file .

It is assumed that a user selects to insert the term CONFIDENTIAL for the watermark print option and not for the overlay print option . The printer driver UI may provide a preview screen .

Once the watermark print option is selected the filter description about filters processing other print options is removed from the filter description B and the filter description about the watermark filter only exists.

The spool file processor loads the watermark filter according to the changed filter setting file . The watermark filter watermarks the XPS spool file .

Therefore the file does not pass through the unnecessary filters and more efficient environment with shorter print time may be available.

Elements which are different from those according to the previous exemplary embodiments will be described only.

A controller may change a filter description B of a filter setting file according to a print option selected through an input unit .

The controller may determine whether the image forming apparatus connected through a host interface and a printer interface supports an XPS spool file.

To briefly describe the determination process the controller requests the image forming apparatus about a supported file format the image forming apparatus reads information stored in a ROM not shown and transmits the information to the host apparatus . Then the controller may determine the supported file format with the response information transmitted by the image forming apparatus with respect to the request.

Whether the image forming apparatus supports the XPS spool file may be determined not only when a print command is sent but also whenever as required. For example if a user executes a printer driver program or if a predetermined time elapses the controller may determine periodically whether the image forming apparatus supports the XPS spool file.

If it is determined that the image forming apparatus does not support the XPS spool file i.e. if the print data in an XPS spool file format may not be printed by the image forming apparatus the controller can control the display unit to display the result.

If it is determined that the image forming apparatus supports the XPS spool file the controller changes a filter description about the render filter of the filter setting file .

More specifically if the image forming apparatus supports the XPS spool file the controller removes the filter description B about the render filter from the filter setting file . If the image forming apparatus does not support the XPS spool file the controller adds the filter description B about the render filter to the filter setting file .

The spool file processor loads the render filter by the changed filter setting file . The loaded render filter converts the XPS spool file into a PDL supported by the image forming apparatus .

Thus even if the image forming apparatus is changed and the supported file format is changed accordingly the filter setting file may be dynamically changed corresponding thereto to provide a more efficient print environment.

As delay of print time due to the unnecessary application of the render filter is prevented print time may be reduced.

The function of the controllers and may be realized by a printer driver or by being added to the existing elements as necessary. The controllers and may be realized by an additional application program. The controllers and may be realized in hardware such as an additional chip instead of software.

Hereinafter printing methods according to exemplary embodiments of the present general inventive concept will be described with reference to .

As shown in printing method according to an exemplary embodiment selects a print option operation S . Then a print command is sent through the WIN32 program or WPF application operation S .

After the print command the filter setting file is read operation S and the filter setting information is changed corresponding to the selected print option operation S . More specifically the filter description included in the filter setting file is changed.

Then the print option applies according to the changed filter setting information to transmit print data to the image forming apparatus operation S .

The filter description is dynamically changed according to the selected print option and the filters processing the unselected print option are not loaded. Thus more efficient print environment may be provided and print time may be reduced.

Referring to a printing method according to another exemplary embodiment will be described. Repetitive description will be avoided.

The printing method according to the present exemplary embodiment further includes an operation of storing an original filter setting file before change operation S and an operation of restoring the original filter setting file after the print data are printed operation S .

First a print option is selected operation S . Then a print command is sent through the WIN32 application or WPF application operation S .

The filter setting file is read operation S . It is determined whether the filter description to process the selected print option is written in the filter setting file operation S . An operation of initializing the filter setting file to remove all contents of the filter setting file may be inserted between the operations S and S.

If it is determined that the filter description is not written a filter description about a filter to process the print option is written in the filter setting file operation S .

If it is determined that the filter description is written operation S it is further determined whether all the print options selected by a user have been checked operation S . More specifically it is determined whether the filter description corresponding to the selected print option is reflected in the filter setting file operation S .

If it is determined that the all the print options are checked the filter setting file is read again operation S .

If it is determined that all the print options are not checked operations S to S are repeated until all the print options are checked.

After the filter setting file is read again it is determined whether the image forming apparatus supports the XPS spool file operation S .

If it is determined that the image forming apparatus supports the XPS spool file the filter description about the render filter is removed from the filter setting file operation S . Here the term remove means that the filter description is removed from the filter setting file if the filter description about the render filter is included in the filter setting file and absence is maintained if the filter description is not included therein.

If it is determined that the image forming apparatus does not support the XPS spool file a filter description about the render filter is added to the filter setting file S. Here the term add means that not only the filter description is additionally written in the filter setting file if the filter description about the render filter is not included in the filter setting file but also the filter description about the render filter is maintained if it is included in the filter setting file.

After reflecting the render filter description to the filter setting file according to the XPS spool file support of the image forming apparatus the reflected filter setting file is stored operation S .

Then the XPS spool file is generated operation S . It is determined whether the filter setting file has the filter description operation S .

If it is determined that the filter description exists at least one filter is loaded corresponding to the filter description to process the XPS spool file operation S .

If it is determined that the filter description does not exist the XPS spool file is transmitted to the image forming apparatus while the operation of loading the filter and processing the XPS spool file is skipped operation S . Here there may be no selected option and no filter description if the image forming apparatus supports the XPS spool file. As the XPS spool file may be directly transmitted to the image forming apparatus without being sent through the filters the printing speed is much faster.

At operation S the data transmitted to the image forming apparatus is a spool file which is print data including spool data and information about the selected print option. However if the image forming apparatus may not print the print data having the print option i.e. if the XPS spool file may not be printed the print data are converted into the PDL format data by the render filter and then transmitted to the image forming apparatus to be printed.

The printing method according to the present embodiment may further include an operation of displaying print unavailability of the print data as required.

Meanwhile the print data which is transmitted to the image forming apparatus is printed on a print medium by a printing unit of the image forming apparatus operation S .

The foregoing printing method may provide more efficient printing environment such as reducing load to the host apparatus since the filters are changed dynamically depending on print options and XPS spool file supported by the image forming apparatus and the unnecessary filter is not loaded.

As described above the printing method recordable medium and host apparatus provide the following effects.

First as a filter is dynamically changed by a print option a more efficient printing environment may be secured. Particularly as an unnecessary filter is not loaded load to the host apparatus may be reduced.

Third data can be printed even if an image forming apparatus is changed and a data format recognizable by the image forming apparatus is changed accordingly.

Although a few exemplary embodiments of the present general inventive concept have been shown and described it will be appreciated by those skilled in the art that changes may be made in these embodiments without departing from the principles and spirit of the general inventive concept the scope of which is defined in the appended claims and their equivalents.

