---

title: Method and apparatus to provide location information
abstract: A method of providing location information through a navigation device, the method including: obtaining location information from the Internet; and converting the obtained location information into data that can be used in the navigation device.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08478517&OS=08478517&RS=08478517
owner: Samsung Electronics Co., Ltd.
number: 08478517
owner_city: Suwon-Si
owner_country: KR
publication_date: 20090402
---
This application claims the benefit of Korean Patent Application No. 2008 58046 filed on Jun. 19 2008 in the Korean Intellectual Property Office the disclosure of which is incorporated herein by reference.

As traffic congestion has increased so has the popularity of navigation devices. In particular navigation devices that rapidly and accurately output information about a desired target location have become especially popular. However in order to search for a route to a desired target location with such a navigation device the name or address of the desired target location has to be known in advance.

Due to the development of the IT industry communication infrastructure networks have proliferated which enable a user to rapidly obtain desired information through the Internet. Accordingly information such as recommended tourist spots and restaurants can be easily obtained through search engines or personal blogs. When a user has not decided on a desired target location or has no information about the desired target location such location information can be obtained from web pages in order to then set the desired target location on the navigation device.

However many web pages do not include detailed location information and may only include phone numbers of the desired target location. In this case a user is inconvenienced since the user has to continue to search for location information or has to call a phone number to determine the name or address of the desired target location. In addition even if web pages include detailed location information such information may not be registered to a database of the navigation device. In this case the user has to manually input the address of the desired target location into the navigation device.

According to aspects of the present invention there is provided a method of proving location information through a navigation device the method including obtaining location information from the Internet and converting the obtained location information into a format that can be used by the navigation device.

According to aspects of the present invention the obtaining of the location information may include extracting a key word that is to be used in requesting the location information from text data provided from a web page sending a request to an external server for location information related to the key word and in response to the request receiving the location information from the external server.

According to aspects of the present invention the obtaining of the location information may include a user selecting a key word that is used to request the location information from text data provided from a web page sending a request to an external server for location information that is related to the key word and in response to the request receiving the location information from the external server.

According to aspects of the present invention the method may further include ranking the received location information according to a predetermined standard outputting the received location information based on the ranking and selecting a certain portion of the output location information. The converting of the obtained location information may include converting the selected location information into a format that can be used by the navigation device.

According to aspects of the present invention the method may further include setting a target location on the navigation device using the converted location information.

According to aspects of the present invention the ranking may be determined according to the correspondence between the received location information and data provided from a web page.

According to aspects of the present invention the location information may be point of interesting POI data.

According to another aspect of the present invention there is provided a method of providing location information through a navigation device the method including searching for stored location information that relates to an input key word when the location information is not stored sending a request to an external server for location information that is related to the key word receiving the location information from the external server and converting the received location information into a format that can be used by the navigation device.

According to aspects of the present invention the method may further include ranking the converted location information according to a predetermined standard and outputting the converted location information based on the ranking.

According to aspects of the present invention the method may further include selecting some of the output location information and setting a target location on a navigation device using the selected location information.

According to another aspect of the present invention there is provided an apparatus to providing location information through a navigation device the apparatus including a location information obtaining unit to obtain location information from the Internet and a converter to convert the obtained location information into data that can be used in the navigation device.

According to another aspect of the present invention there is provided an apparatus to provide location information through a navigation device the apparatus including a determining unit to search for stored location information related to an input key word a request unit to send a request to an external server for location information related the key word if the location information is not found by the search a receiver to receive the location information from the external server in response to the request and a converter to convert the received location information into a format that can be used in the navigation device.

Additional aspects and or advantages of the invention will be set forth in part in the description which follows and in part will be obvious from the description or may be learned by practice of the invention.

Reference will now be made in detail to the exemplary embodiments of the present invention examples of which are illustrated in the accompanying drawings wherein like reference numerals refer to the like elements throughout. The exemplary embodiments are described below in order to explain the aspects of the present invention by referring to the figures.

The location information obtaining unit obtains desired location information from a web page. Hereinafter a first case where detailed location information is provided by a web page and a second case where only schematic location information is provided by a web page are separately described. The detailed location information includes information sufficient to set a location that can be used in a navigation device.

As an example of the first case where detailed location information is provided from a web page a user directly inputs a location name into a search engine which provides a web page with detailed location information. The location information obtaining unit may directly obtain the detailed location information from the web page. In this case the converter as will be described later converts the obtained detailed location information into a format and or data that can be used in the navigation device thereby expanding the navigation data.

As an example of the second case where only schematic location information is provided from the web page the user may access web pages related to a location such as blogs related to famous restaurants or famous tourist spots or personal homepages blogs. In this case geographical information about the location may not be included in the web pages. Instead simple information such as the name and the phone number of a restaurant may be included. The user can then search for the detailed location information using the simple information provided by the web pages.

Hereinafter a process of obtaining location information using the location information obtaining unit is described based the second case. The location information obtaining unit may include a request unit and a receiver .

The request unit obtains a key word from a web page and sends a request to an external server not shown for location information relating to the key word. The external server can access a database including the location information. Herein a key word refers to single key words and or key word phrases. The user may directly select a key word from the information provided from a web page. As an example it is assumed that the web page is a blog describing a famous tourist spot.

The apparatus may include an interface not shown through which a user can input and or select a key word derived from text data provided from the web page. The selected key word may relate to location information such as the name the address and or the phone number of the location.

According to another exemplary embodiment the apparatus may include an extracting unit not shown to extract the key word from the website. As an example text data provided from the web page is analyzed based on a predetermined criteria or titles of images or voice files provided from the web page are analyzed to thereby extract the key word. It is assumed that the web page provides text describing the tourist spot Bulguksa along with an image named Bulguksa.jpg . In this example the extracting unit analyzes the text and titles of the image files and thereby extracts the key word Bulguksa .

If multiple key words are extracted from a web page the extracted key words are displayed so that the user may select one of the key words. Once the key word is selected the request unit sends a request to an external server for location information relating to the key word. As an example the request unit transmits the key word to an open application programming interface API which searches for related location information. The open API searches the database run by the external server for the location information related to the key word.

The receiver receives the location information which corresponds to the request from the external receiver. The received location information may include detailed location information or may include location information that can be used to obtain the detailed location information such as a name a phone number and or an address. When different types of location information are received a list including the different types of location information may be generated and displayed. Then the user may make at least one selection from the list. An apparatus to provide location information which outputs the list of the received location information will be described with reference to .

The converter converts the received location information into a format that can be used in the navigation device. The location information may be point of interesting POI data used by a web page. The converter may convert the POI data into POI data suitable for use in a navigation device.

The apparatus may further include a target location setting unit not shown . The target location setting unit may automatically use the converted location information to set a target location on a navigation device. However the target location setting unit is not required in all aspects of the present invention. According to other exemplary embodiments the converted location information is stored in a database of a navigation device and when the user selects the location information related to the target location the converted location information may be used to set the target location.

The order determining unit ranks the location information received from an external server not shown according to a predetermined standard. As an example the ranking of the received location information is output can be determined according to the correspondence between the location information received from the external server and data provided from a web page. The order determining unit will be described more fully with reference to .

The outputting unit outputs a list of the location information which is organized according to the determined ranking. As an example the outputting unit displays location information having a higher correspondence on the upper portion of a display device not shown and the outputting unit displays the location information having a lower correspondence on the lower portion of the display device. That is the more relevant location information location information having a higher probability of being selected by a user is displayed on the upper portion of the display device.

The user makes a selection from the list using the interface unit . The converter then converts the selected location information into a format that can be used in a navigation device. However according to another exemplary embodiment the converter can convert all of the received location information into a format that can be used in the navigation device and can then store the converted location information.

In operation S the order of outputting the location information is determined according to the determined correspondence. That is the location information is ranked and output according to the determined correspondence. According to another exemplary embodiment some information such as the names of image files and or highlighted words is given more weight more than other information. Therefore if a block of text includes a word corresponding to the specific information the block of text is ranked higher than other blocks of text.

In the user selects the Saemaeul restaurant as the key word to be used in obtaining location information. The method of selecting the key word may vary according to various embodiments. As an example the user may directly input Saemaeul restaurant into a key word field or may press a specific button while a cursor is on a specific word to select the key word. When the user selects Saemaeul restaurant and then right clicks a keyword search pop up window appears for example. When the user clicks the menu called keyword search the word Saemaeul restaurant is entered as the key word.

According to another exemplary embodiment information provided from a web page is analyzed to extract a key word or one or more extracted key words are displayed so that the user may make manually select a key word. When the user selects the key word the apparatus to provide location information sends a request to an external server for location information that is related to the selected key word.

In the apparatus to provide location information receives the corresponding location information from the external server. That is the location information related to the Saemaeul restaurant is received and is then displayed to the user. In the current exemplary embodiment a list is displayed that includes various related pieces of location information i.e. a name an address and a phone number.

In the user selects the desired location information from the list. The apparatus to provide location information converts the selected location information into a format that can be used in a navigation device. In detail the converted location information may be automatically stored in a database of a navigation device or may be stored in a user selected location. According to another exemplary embodiment the converted location information may be automatically set as a target location in a navigation device.

The location information received from the external server is ranked according to a predetermined standard. As an example the received location information and the data provided from the web page are compared to each other and the location information having the highest correspondence is determined to be the location information with the highest probability for user selection and is output accordingly. In operation the obtained location information is converted into a format that can be used in a navigation device.

When a user inputs a key word related to a target location the determining unit searches for location information related to the key word a database of the navigation device. If the location information is stored in the database a target location is set using the stored location information and the navigation device searches for a route to the target location. When the location information is not stored in the database the request unit sends a request to an external server for the location information.

Once the receiver receives the location information from the external server the converter converts the received location information into a format that can be used by the navigation device. The apparatus may further include at least one of an order determining unit not shown an outputting unit not shown and an interface unit not shown . The outputting unit may be a display unit.

The order determining unit ranks the converted location information according to a predetermined standard. The outputting unit outputs a list of the location information based on the ranking. A user makes a selection from the list using the interface unit. The user selects the location information through the interface unit.

The apparatus may further include a target location determining unit not shown . The target location determining unit can set the user selected location information as the target location in the navigation device.

If the location information is not stored operation S is performed. Then in operation S a location information request is sent to an external server using the key word.

In operation S location information which corresponds to the request is received from the external server. In operation S the received location information is converted into a format that can be used in a navigation device.

Aspects of the present invention can also be embodied as computer readable codes on a computer readable recording medium. Also codes and code segments to accomplish the present invention can be easily construed by programmers skilled in the art to which the present invention pertains. The computer readable recording medium is any data storage device that can store data which can be thereafter read by a computer system or computer code processing apparatus. Examples of the computer readable recording medium include read only memory ROM random access memory RAM CD ROMs magnetic tapes floppy disks and optical data storage devices. The computer readable recording medium can also be distributed over network coupled computer systems so that the computer readable code is stored and executed in a distributed fashion. Aspects of the present invention may also be realized as a data signal embodied in a carrier wave and comprising a program readable by a computer and transmittable over the Internet.

Although a few exemplary embodiments of the present invention have been shown and described it would be appreciated by those skilled in the art that changes may be made in these exemplary embodiments without departing from the principles and spirit of the invention the scope of which is defined in the claims and their equivalents.

