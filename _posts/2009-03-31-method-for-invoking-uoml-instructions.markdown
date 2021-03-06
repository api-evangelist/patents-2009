---

title: Method for invoking UOML instructions
abstract: Embodiments of the present invention disclose a method for encapsulating Unstructured Operation Markup Language (UOML) into an Application Programming Interface (API), including: mapping an object of an UOML operation to a data type of a programming language, mapping the UOML operation to an API function prototype in the programming language, wherein an attribute or sub element of the UOML operation is mapped to a parameter of the API function prototype; wherein, when an API function is invoked, the API function issues a corresponding UOML operation instruction to a docbase management system according to the mapping relations; after an operation defined by the UOML operation instruction is executed by the docbase management system, the return result from the docbase management system is converted into a data type of the programming language by the API function. In this way, API functions in different programming languages, which correspond to the UOML, can be implemented, and the application developers of the programming languages may invoke suitable API functions directly to implement applications on the docbase management system, thus the development efficiency can be improved.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08316379&OS=08316379&RS=08316379
owner: Sursen Corp.
number: 08316379
owner_city: Beijing
owner_country: CN
publication_date: 20090331
---
This application claims the benefit and is a continuation of PCT CN2007 070132 filed Jun. 19 2007 which is the PCT filing of CN200610114649.1 filed Nov. 20 2006 all of which applications are fully incorporated herein by reference.

The present invention relates to electronic document processing technologies and particularly to a method for encapsulating Unstructured Operation Markup Language UOML into an Application Programming Interface API .

The UOML standard includes a series of docbase management system instructions defined according to a format of action object in Extensible Markup Language XML which has been explained in detail in a Chinese patent application with Application No. CN 200510131641.1. Since XML works across different platforms and with different languages the UOML standard can enable the docbase management system instructions to be exchanged across the different platforms in the different languages. However in practical applications operations on a docbase are usually controlled by using programs written in programming languages hence the programs need to parse and process UOML XML texts. If every application developer designs his her own way of parsing and processing UOML XML texts in his her programs the workload of coding will increase significantly and the efficiency of coding will drop sharply.

The objective of the present invention is to provide a method for encapsulating Unstructured Operation Markup Language UOML into an Application Programming Interface API of a programming language so as to improve the development efficiency of docbase management system application developers.

mapping the UOML operation to an API function prototype in the programming language wherein an attribute or sub element of the UOML operation is mapped to a parameter of the API function prototype 

wherein when an API function is invoked the API function issues a corresponding UOML operation instruction to a docbase management system according to the mapping relations 

after an operation defined by the UOML operation instruction is executed by the docbase management system the return result from the docbase management system is converted into a data type of the programming language by the API function.

According to the method provided by embodiments of the present invention the UOML can be encapsulated into API in the programming language. When a developer develops an application of the docbase management system with the programming language the encapsulated API in the programming language can be invoked directly therefore a lot of works on parsing the UOML can be saved and the development efficiency can be improved.

In embodiments of the present invention by utilizing the characterized format of the UOML standard i.e. action object and the internal mapping relations between UOML objects and classes or structures of programming languages the present invention provides a method for encapsulating UOML into APIs of different programming languages therefore when an application of the docbase management system is developed with a programming language the API prepared for the UOML in the programming language can be invoked directly to improve the efficiency of developers.

Step an UOML object is mapped to a composite data type of a programming language. An attribute of the UOML object is mapped to a variable of a simple data type or complex data type in the composite data type and a sub element of the UOML object is also mapped to a variable of the simple data type or complex data type in the composite data type.

Firstly a representation of the UOML object is provided in the programming language. Every UOML object is mapped to a defined composite data type by utilizing the customized definition function of composite data types in the programming language. The composite data type may include a class in object oriented language or a structure in non object oriented language. The attribute of the UOML object can be represented with the variable of the simple data type or complex data type in the composite data type e.g. a variable of INT type CHAR type or FLOAT type or an array. A sub element of the UOML object is usually an object in the UOML and the sub element of the UOML object is represented by a variable of the related composite data type defined in the programming language and corresponded to the sub element. A sub element of the UOML object which is not an object in the UOML e.g. coordinate s describing position also may be represented by a variable of the simple data type. It should be noted that the variables of the simple data type the complex data type and the composite data type may include a pointer variable.

Step an UOML operation is mapped to an API function prototype in the programming language wherein the attribute and the sub element of the UOML operation are mapped to parameters of the API function prototype.

According to the UOML standard an operation may support a plurality of objects so it should be taken into consideration whether the programming language supports function polymorphism when the UOML operation is converted into an API function prototype in the programming language. If the programming language does not support the function polymorphism an individual API function prototype shall be defined for every object of the operation if the programming language supports the function polymorphism only one API function prototype may be defined for all objects of the operation and the objects are indicated by different parameter types in the function prototype. The attribute and sub element of the UOML operation are mapped to the parameters of the API function prototype. When an object oriented language is adopted the API function may be defined as a member function of a class when the attribute or sub element of the operation is a member variable of the class the member function prototype may exclude the related parameter and the member variable may be referenced directly in the function body. Obviously all attributes and sub elements of the operation can be mapped to parameters of the function prototype just like in non object oriented language.

Step according to the operation corresponding to the function prototype and the parameters of the function prototype the operation of the API function is converted into an UOML operation and the UOML operation is executed in the body of the API function in the programming language and then the return result of the UOML operation is converted into a return value of a type in the programming language.

In the body of the API function in the programming language UOML operation instructions are generated according to the mapping relation between the function prototype and the UOML operation and the relation between the parameters of the function and the attribute and sub element of the UOML operation. The operation instructions are sent to the docbase management system and after executing the operation instructions the docbase management system returns an executing result. Since the result returned from the docbase management system is in the UOML format so the return result shall be converted into a return value of a type in the programming language.

Programming languages usually includes object oriented languages and non object oriented languages. The processes of encapsulating UOML into APIs in different programming languages differ slightly from each other because of different characteristics of the different programming languages.

The process of encapsulating UOML into an API in an object oriented language is explained hereinafter taking C as an example of the object oriented language.

Step an UOML object is mapped to a class of an object oriented language. An attribute of the UOML object is mapped to a variable of a simple data type or complex data type in the class and a sub element of the UOML object is mapped to a variable of class type or simple data type in the class.

Taking an UOML document object as an example a class UOML Doc is firstly defined in C to correspond to the UOML document object. The class can be derived from a base class or be derived from none of base classes. Or a base class is firstly defined for all UOML objects 

When the class UOML Doc which is mapped to the UOML document object is defined the sub elements of the UOML document object are mapped to member variables in the UOML Doc class. The sub elements of the UOML document object include metadata pageset fontinfo etc. Different sub elements are usually mapped to different classes e.g. metadata is represented by UOML Meta class pageset is represented by UOML Page class and fontinfo is represented by UOML FontInfo class. Therefore the sub elements of the UOML document object are mapped to certain member variables in the UOML Doc class definition UOML Meta metadata UOML Page pageset and UOML FontInfo fontinfo. The sub element pageset can also be represented with an array of UOML Page. Since the UOML document object does not have any attribute the process of mapping attributes to member variables will not be performed.

Similarly an UOML Page class can be defined for an UOML page object. The attributes of the UOML page object e.g. resolution size rotation log etc. are represented by member variables of integer or float type during the definition of the UOML Page class and the sub elements of the UOML page object e.g. GS metadata are also represented by member variables in the UOML Page class.

In this way classes may be defined in the object oriented language for all UOML objects. The UOML objects includes UOML DOCBASE UOML DOCSET UOML DOC UOML PAGE UOML LAYER UOML OBJGROUP UOML TEXT UOML IMAGE UOML LINE UOML BEIZER UOML ARC UOML PATH UOML SRCFILE UOML BACKCOLOR UOML COLOR UOML ROP UOML CHARSIZE UOML TYPEFACE UOML ROLE UOML PRIV etc. Those skilled in the art may define the classes according to the foregoing explanation and no further description will be given herein.

Step an UOML operation is mapped to a member function of the class in the object oriented language and the attribute and sub element of the UOML operation are mapped to parameters of the member function of the class.

For example operations on the UOML document object such as UOML OPEN and UOML CLOSE are mapped to corresponding member functions i.e. Open and Close in the UOML Doc class. The location information of the document which is an attribute of the operation UOML OPEN is regarded as the parameter of the member function i.e. Open Open char szDocPath . The handle of the document object which is a sub element of the operation UOML CLOSE is regarded as the parameter of the member function Close .

Other UOML operations such as UOML GET UOML SET UOML INSERT UOML DELETE and UOML QUERY can also be mapped to member functions in the class in a similar process.

Step in the body of the member function the operation corresponding to the function is converted into an UOML operation and the return result of the UOML operation is converted in to a return value of a type in the object oriented language.

For example in the body of the member function Open char szDocPath in the UOML Doc class an invocation is converted into an UOML XML string that invokes the docbase management system and the string is then sent to the docbase management system 

Upon receipt of the request represented by the UOML XML string the docbase management system performs the Open operation. If the document is successfully opened an XML string will be returned. In the body of the function Open an UOML Doc object is constructed according to the received string and is returned as the return value of the function.

The process of encapsulating UOML into the API in the object oriented language is explained above with reference to C as an example. It is obviously that the process can also be applied to other object oriented languages such as Object C Delphi Java Python Ruby etc.

The process of encapsulating UOML into an API in a non object oriented language is explained hereinafter taking the programming language C as an example of the non object oriented language.

Step an UOML object is mapped to a structure of a non object oriented language. An attribute of the UOML object is mapped to a variable of a simple data type or complex data type in the structure and a sub element of the UOML object is mapped to a variable of structure type or simple data type in the structure.

Taking an UOML document object as an example a structure struct UOML Doc is firstly defined in C to correspond to the UOML document object.

After the structure struct UOML Doc is defined for the UOML document object the sub element of the UOML document object is mapped to a member variable in the structure struct UOML Doc. The UOML document object has sub elements including metadata pageset fontinfo etc. The structures mapped to the sub elements are defined as follows metadata is represented by the structure struct UOML Meta pageset is represented by the structure struct UOML Page and fontinfo is represented by the structure struct UOML FontInfo. Therefore the sub elements of the UOML document object correspond to certain member variables i.e. struct UOML Meta metadata struct UOML Page pageset struct UOML FontInfo fontinfo in the definition of the structure struct UOML Doc. The sub element pageset can also be represented with an array of struct UOML Page. Since the UOML document object does not have any attribute the process of mapping attributes to member variables will not be performed.

Similarly a structure struct UOML Page can be defined for an UOML page object. The attributes of the UOML page object e.g. resolution size rotation log etc. are represented by member variables of integer or float type during the definition of the structure struct UOML Page and the sub elements of the UOML page object e.g. GS metadata are also represented by member variables in the structure struct UOML Page.

In this way structures may be defined in the non object oriented language for all UOML objects. The UOML objects includes UOML DOCBASE UOML DOCSET UOML DOC UOML PAGE UOML LAYER UOML OBJGROUP UOML TEXT UOML IMAGE UOML LINE UOML BEIZER UOML ARC UOML PATH UOML SRCFILE UOML BACKCOLOR UOML COLOR ROP UOML CHARSIZE UOML TYPEFACE UOML ROLE UOML PRIV etc. Those skilled in the art may define the structures according to the foregoing explanation and no further description will be given herein.

Step an UOML operation is mapped to a global function prototype in the non object oriented language and the attribute and the sub element of the UOML operation are mapped to parameters of the function prototype.

Also taking the UOML document object as an example API function prototypes such as struct UOML Doc UOML Doc Open char szDocPath and void UOML Doc Close HANDLE hDocHandle are defined for operations on the UOML document object such as UOML OPEN and UOML CLOSE.

The location information of the document which is an attribute of the operation UOML OPEN is regarded as the parameter of the API function UOML Doc Open i.e. szDocPath. the handle of the document object which is a sub element of the operation UOML CLOSE is regarded as the parameter of the API function UOML Doc Close i.e. hDocHandle.

Other UOML operations such as UOML GET UOML SET UOML INSERT UOML DELETE UOML QUERY can also be mapped to API function prototypes in such way.

Step in the body of the function the operation corresponding to the function is converted into an UOML operation and the return result of the UOML operation is converted in to a return value of a type in the non object oriented language.

For example in the body of the API function UOML Doc Open char szDocPath an invocation is converted into an UOML XML string that invokes the docbase management system and the string is then sent to the docbase management system 

Upon receipt of the request represented by the UOML XML string the docbase management system performs the Open operation. If the document is successfully opened an XML string will be returned. In the body of the function UOML Doc Open an UOML Doc object is constructed according to the received string and is returned as the return value of the function.

The process of encapsulating UOML into the API in the non object oriented language is explained above with reference to the language C as an example. It is obviously that the process can also be applied to other non object oriented languages such as TCL Pascal Perl etc.

According to the method of the present invention the UOML can be encapsulated into the API in the programming language. When a developer develops an application of the docbase management system with the programming language the encapsulated API in the programming language can be invoked directly therefore a lot of works on parsing the UOML can be saved and the development efficiency can be improved.

The foregoing are only preferred embodiments of the present invention and are not for use in limiting this invention any modification equivalent replacement or improvement made under the spirit and principles of this invention is included in the protection scope of this invention.

