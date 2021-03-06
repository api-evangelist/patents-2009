---

title: Method and system for e-mail enhancement
abstract: A method for enhancing an electronic message, referred to as an e-mail, upon receiving the same in the e-mail inbox of a user, the method includes the following steps: a local application, working with the e-mail inbox and extracting a set of data contained in the incoming e-mail, sends the data set to a remote server, receives a response from the remote server, and attaches the response to the incoming e-mail; and the remote server receives the data set sent by the local application, analyzes the data so as to identify specific elements, and sends the specific elements as a reply to the local application. The invention relates to the exchange of structured information by e-mail, and in particular to scheduling appointments, contact details, and monitoring tasks to be performed.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08775534&OS=08775534&RS=08775534
owner: 
number: 08775534
owner_city: 
owner_country: 
publication_date: 20091016
---
The present invention relates to a method and a system making it possible to enhance an electronic message referred to as an e mail upon receipt thereof in a user s e mail inbox.

During about the last ten years e mail has become the foremost medium of exchange between professionals. Gradually it is replacing paper letters fax telex and telephonic conversations. E mail is a medium which can be used in a number of ways. In fact e mail is currently used to arrange meetings to give instructions to receive instructions to plan work and retrieve information about contacts etc.

However it is sometimes difficult to rapidly identify useful information which is buried within texts and annotations which are more or less useful.

Numerous systems exist for linguistic analysis which make it possible to process text in such a way as to highlight this useful information in the initial document or in a new document.

Document U.S. Pat. No. 4 965 763 describes a method for analyzing a document. This method consists of extracting parametric information from a document by identifying and targeting syntactic analysis on selected parts of this document. In fact the start and end of documents are particularly analyzed in order to identify the following parametric information author date receiver address subject etc. The information thus obtained allows a very precise classification of the analyzed documents.

Document U.S. Pat. No. 7 054 886 describes a system which allows Internet browsing in order to recover a set of information and to set up a professional database. This information is generally extracted from Web pages using an Extractor .

Document U.S. Pat. No. 7 178 099 describes a method allowing the enhancement of electronic messages referred to as e mails upon receipt thereof in an e mail inbox. This method uses a software application capable of intercepting the incoming e mail analyzing the content and the items attached to this e mail so as to produce a new document referred to as an enhanced e mail in particular in HTML format comprising said content as well as an index and other information such as for example a summary of the attached items. The content can be enhanced by incorporating colour into it so as to attract attention to certain words or other items. However with such a method the recipient of the e mail only receives their message once all the operations of analyzing the e mail s content header and attached items have been carried out. Depending on the complexity and size of the e mail and the attached items the analysis process can take a significant amount of time and considerably delay delivery of the message to the recipient. The same situation can occur due to hardware reasons the analysis is not successful which inevitably blocks the e mail.

A purpose of the present invention is to remedy the above mentioned drawbacks by proposing a novel method for analyzing e mail which is non intrusive in the e mail and does not block it as regards the user. A purpose of the invention is also a method for analyzing e mail which is efficient and rapid.

At least one of the above mentioned aims is achieved with a method for enhancing an electronic message referred to as an e mail upon receipt thereof in a user s e mail inbox. According to the invention this method comprises the following steps 

In other words the extraction of the set of data consisting in particular of simply extracting the text contained in the e mail is carried out in a machine containing the e mail inbox and different from the remote server. The latter carries out the demanding operations of identification of the specific elements i.e. the linguistic analysis.

With the method according to the invention the linguistic processing is advantageously carried out within a remote server to which significant hardware and software resources can be allocated so that this linguistic analysis is carried out rapidly and efficiently. By contrast in the systems of the prior art it is the user s processing unit which is required to do this analysis which unnecessarily slows down the set of the operations taking place within this processing unit.

According to an advantageous feature of the invention the local application and the remote server operate asynchronously so that the incoming e mail can be consulted in the e mail inbox by the user while the remote server carries out the data analysis. Therefore the incoming e mail is not blocked and its consultation by the user is not dependent on the linguistic analysis.

Advantageously the local application can act on the e mail inbox as a plug in in other words a plug in application of the application managing the e mail inbox of the user. Communications between the local application and the remote server are of client server type.

Preferably the specific elements can comprise at least one of the elements chosen from the following group date time and location relating to a meeting contacts or tasks.

Moreover according to the invention the response transmitted by the remote server can contain a structured representation of the specific elements. This representation can be of a graphic textual or other type. It can be an index comprising the specific elements ranked in categories optionally highlighting certain elements by underlining or colouring. Advantageously the specific elements are formatted in predefined formats depending on their nature.

According to an embodiment of the invention the local application can produce an item attached to the incoming e mail based on the response transmitted by the remote server.

As a variant it is the remote server which directly incorporates the specific elements into a document in the form of an attached item that the local application attaches to the incoming e mail.

According to an advantageous embodiment of the invention the local application produces and transmits a unique identifier to the remote server at the same time as the set of data. More precisely this unique identifier can identify the user identify the incoming e mail and or comprise an IP address making it possible to locate the local application.

Generally this method according to the invention allows the content of an e mail to be enhanced by creating attached items repeating the information present in the text of the e mail in a structured manner.

Advantageously the attachment to the incoming e mail is a document in HTML format containing at least one hypertext link. For that reason the user may or may or not validate the proposed structuring. He can also click on a hypertext link in order to access the Web or recover additional information from the remote server.

Preferably said set of data comprises the text contained in the body and the header of the incoming e mail as well as the nature of this incoming e mail.

According to another aspect of the invention a system is proposed for enhancing an electronic message referred to as an e mail upon receipt thereof in an e mail inbox contained in a processing unit this system implementing the method as defined previously.

According to the invention the processing unit comprises a local application acting on the e mail inbox which is capable of extracting a set of data contained in the incoming e mail transmitting said set of data to a remote server receiving a response originating from the remote server and attaching this response in the form of an attachment to said incoming e mail.

The remote server is capable of receiving the set of data transmitted by the local application analyzing the data so as to identify the specific elements and transmitting these specific elements as a response to the local application.

Such an arrangement facilitates in particular updates which can be carried out directly on the remote server once and for all for several local applications.

In a system is shown comprising a processing unit capable of connecting to a remote server via a communication network of Internet type. The processing unit is a desktop computer or a laptop computer provided with the hardware and software means necessary for accessing the communication network and making the human machine interface possible. It is driven by an operating system which manages and coordinates different applications and hardware. In particular the processing unit comprises an e mail management application such as for example Outlook or another.

According to the invention the processing unit also comprises a local application such as a plug in which can take the form of an additional application or add in incorporated into the different e mail management applications such as Outlook. The local application can also be presented in the form of a GreaseMonkey script for Google s Webmail application Gmail .

The remote server is provided with conventional hardware and software means for correct operation within a communication network. Advantageously it also comprises a linguistic analysis module in particular as disclosed in one of the documents of the prior art indicated above.

The architecture implemented in the system according to the invention is therefore made up of two distinct components 

The role of the remote server is to offer an entry point in the form of Web Service using SOAP or REST architecture which makes it possible 

Preferably the communication between the application software and the remote server is of asynchronous type so as not to block the operation of the e mail management application such as Outlook or another. In when the e mail arrives the local application recovers the text in the e mail without blocking the normal processing of this e mail by the e mail management application. With the current capacities of communication networks transmissions and occur rapidly and to the extent that the remote server is also rapid this round trip and with processing inside the remote server occurs in a very short period of time.

The architecture according to the invention allows the remote server to be provided with hardware and software resources which are powerful in comparison with what it is possible to install in a single user s processing unit . The calculating capacity within the remote server is optimized so that linguistic analyses can be carried out rapidly and efficiently.

The processing carried out within the remote server makes it possible amongst other things to format the useful information according to a predetermined model.

Of course the invention is not limited to the examples which have just been described and numerous adjustments can be made to these examples without exceeding the scope of the invention.

