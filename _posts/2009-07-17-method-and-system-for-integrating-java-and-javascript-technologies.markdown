---

title: Method and system for integrating Java and JavaScript technologies
abstract: A method and system for integrating Java and JavaScript technologies is provided. An example system includes a JavaScript proxy generator and a runtime module. The JavaScript proxy generator may be configured to automatically generate a JavaScript proxy in a form of a Java application programming interface. The runtime module may be configured to call the JavaScript proxy from the Java module, pass control of execution to the JavaScript module, execute the JavaScript module to generate an output method or object, and pass control of execution to the Java module to continue execution of the Java module.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08572554&OS=08572554&RS=08572554
owner: eBay Inc.
number: 08572554
owner_city: San Jose
owner_country: US
publication_date: 20090717
---
This application relates to the technical fields of software and or hardware technology and in one example embodiment to system and method for integrating Java and JavaScript technologies.

JavaScript is a scripting language that is used for client side web development. Despite its name and while designed to look like Java JavaScript is unrelated to the Java programming language. Rather JavaScript is a dynamic weakly typed prototype based language intended to be easier for non programmers to work with. JavaScript and Java are trademarks of Sun Microsystems.

For a while now JavaScript has been a de facto client side scripting language for web pages. With the adoption of Web 2.0 for supporting rich client experience without sacrificing the easy accessibility of web application over WAN the JavaScript programming in connection with cascading style sheets CSS and Markup language has become a focal point of many web technology efforts.

A method and system for integrating Java and JavaScript technologies are described. In the following description for purposes of explanation numerous specific details are set forth in order to provide a thorough understanding of an embodiment of the present invention. It will be evident however to one skilled in the art that the present invention may be practiced without these specific details. The method and system described herein may be utilized advantageously in the context of a unified presentation framework that provides active scripting environment for computing applications such as e.g. web applications.

A JavaScript engine may be provided with a developer s platform e.g. Eclipse to accommodate run time and authoring of applications in Java on the server side. Java and JavaScript are distinct programming languages that are both used in developing web applications. The difference between these two languages may be viewed as a barrier by those developers that are versed in one of these languages but not another. A method and system are provided to make this language barrier disappear by unifying them under the Java language such that Java code can reference JavaScript and vice versa. In one embodiment the method and system may be implemented as an enhanced JavaScript engine for use with an integrated developer s environment IDE that permits authoring and debugging seamless Java JavaScript code.

In one example embodiment a JavaScript engine may be configured to cooperate with a build process or an IDE to generate automatically a typed Java application programming interface API for each authored JavaScript module. While JavaScript proxies are automatically generated for JavaScript modules created in an environment associated with an enhanced IDE an external build system may be configured to also generate JavaScript proxies for all JavaScript types from an existing JavaScript library. A typed Java API generated for a JavaScript module may be termed a JavaScript proxy. A JavaScript proxy may be called from a Java module and may return a typed output. While a JavaScript proxy is automatically generated for JavaScript modules created in an environment associated with the enhanced JavaScript engine the enhanced JavaScript engine may be configured to also generate a JavaScript proxy for a JavaScript module from an existing JavaScript library. In one example embodiment when a third party JavaScript module is encountered the enhanced JavaScript engine may first annotate the third party JavaScript module to create a definition for the third party JavaScript module and then use the definition to generate a JavaScript proxy for the annotated third party JavaScript module.

As a JavaScript proxy may be implemented as a Java API it can be called from a Java module during the execution of the Java module as any other Java API. The associated JavaScript is executed to create any object or method according to the JavaScript. It will be noted that in this scenario the JavaScript is being executed on the server and may be run in a debug mode so that any debug statement in the JavaScript module can be viewed at the source of truth i.e. at a location of a particular instruction in the JavaScript module that is being executed in a manner similar to an execution of a Java class .

An example method and system may be implemented in the context of a network environment illustrated in .

As shown in the network environment may include client systems and and a server system . The server system in one example embodiment may host an integrated developer s environment IDE . The client systems and may run respective browser applications and and may have access to the server system via a communications network . The communications network may be a public network e.g. the Internet a wireless network etc. or a private network e.g. a local area network LAN a wide area network WAN Intranet etc. . The browser application is shown as including a browser plug in termed a Java application in browser or JAB plug in . The JAB plug in in one example embodiment facilitates running Java modules and a Java based enhanced JavaScript engine inside the browser application Java modules and a Java based enhanced JavaScript engine to control the browser application and to interact with the browser application .

The integrated developer s environment IDE in one example embodiment is equipped with an enhanced JavaScript engine . The enhanced JavaScript engine may be Java based and may be configured to facilitate integration of Java and JavaScript. The Java based JavaScript engine in one example embodiment enables both Java and JavaScript modules to be executed and to interact with each other seamlessly inside a server side Java application. An example system that may be provided as part of the IDE is illustrated in .

The JavaScript proxy generator may be configured to generate automatically a JavaScript proxy for a third party JavaScript module. In one embodiment the JavaScript proxy generator includes a JavaScript annotation module . The JavaScript annotation module may be configured to annotate the third party JavaScript module in order to create a definition for the third party JavaScript module and then use the definition to generate a JavaScript proxy for the annotated third party JavaScript module.

The system may further include a runtime module configured to call a JavaScript proxy associated with a JavaScript module from a Java module and responsive to the calling pass control to the JavaScript module. The runtime module in one embodiment is implemented as an executable in a JavaScript engine that provides Java like object oriented type support dynamic type loading and ordered static type initialization. The runtime module may then execute the JavaScript module and pass control to the Java module in order to continue execution of the Java module. A debugger may also be provided with the system . The debugger may be implemented as an integrated debugger for both Java and JavaScript modules to debug Java modules as well as JavaScript modules accessed via the JavaScript proxy. Also shown in is a Java to JavaScript translation module configured to translate content of Java modules into JavaScript statements. An example method for integrating Java and JavaScript technologies can be described with reference to .

As shown in the method commences at operation when the source JavaScript detector of detects a JavaScript module. At operation the JavaScript proxy generator of automatically generates a JavaScript proxy corresponding to the JavaScript module. The generated JavaScript proxy may correspond e.g. to a JavaScript object literal to a JavaScript native array to a native JavaScript function to a JavaScript function created in a proprietary JavaScript based language or to a browser data object model DOM . Examples of JavaScript proxies that correspond to various types of JavaScript modules are illustrated below in .

Returning to execution of a Java module that includes a call to a JavaScript proxy commences at operation . At operation the runtime module of detects a call to the JavaScript proxy. The execution control is then passed to the JavaScript module that corresponds to the JavaScript proxy at operation . After the instructions present in the JavaScript module are executed the execution control is returned to Java module at operation . A schematic diagram of a Java module launching the execution of a JavaScript module that may be viewed as corresponding to operations and is shown in .

As shown in a Java module A block includes a call to a JavaScript proxy B. During the execution of the Java module A when a call to the JavaScript proxy B is encountered the execution control is passed to the JavaScript module B block . The JavaScript module B is shown as including a call to a Java module C block . When a call to the Java module C is encountered the execution control is passed to the JavaScript module B. Upon completion of the execution of instructions present in the Java module C the execution control is returned to the Java module A block .

An example system for integrating Java and JavaScript technologies has been termed VJET. VJET blurs the language boundary between JavaScript and Java such that developers can code JavaScript using Java JavaScript or a combination of both with complete interoperability. Described below are example modules that can be provided as part of VJET.

To support the best of Java language features for JavaScript. VJET uses structural and comment annotation based type definition for bring in Java language concept to JavaScript such as the concepts listed below.

VJET Abstract Syntax Tree JST analogous to Java AST represents Java like types and semantics in addition to JavaScript language constructs.

VJET runtime bootstrap can be loaded in any standard JavaScript engine to enable VJET typed JavaScript. Some example features of the VJET JavaScript runtime library are listed below.

VJET JavaScript to Java API in one embodiment enables existing JavaScript to be accessed from Java naturally.

VJET JavaScript Library integration provides support external type definition to integrate third party non VJET JavaScript library.

VJET core Java library is set of Java API for accessing JavaScript types and functions from Java language such as JS global functions JS native types e.g. array object literal function browser DOM and convenient DOM operations and functional programming extension. The functional programming extension may support the following features.

All commonly used Java data types in JDK Java Development Kit have been made available in JavaScript by VJET via its Java to JavaScript translation.

An enhanced execution environment to run and debug authored Java and JavaScript code in their native language form is provided. The custom Java type loader and pluggable Java JavaScript type converters provided with VJET automatically bridge types and instances from two different languages. VJET enhanced scripting service supports interoperability between Java and JavaScript and blurs the boundary between the Java and JavaScript languages. In Active Programming mode Java types are loaded and executed in their authored forms Java or JavaScript while naturally interacting with other JavaScript types and objects. Under Active Programming mode native JavaScript types can live in the Java space via proxies and Java objects can live in the script space with object identity preserved across language boundaries.

The interoperability of Java and JavaScript using VJET enables a seamless integration of Java Junit testing framework for JavaScript testing.

VJET integrated debugger is a fully unified debugger for both Java and JavaScript language. It provides seamless debugging across language boundary and permits developers to step in out Java JavaScript naturally in the same debugger session.

Compiler liked service to perform semantic validation for JavaScript files based on type space and all enabled semantic validation rules.

VJET Aggregation Module provides utility functions to produce aggregated JavaScript from those individual JavaScript definitions based on their type dependencies without manual intervention.

As most advanced Java IDEs VJET IDE supports complete development environment for authoring running and debugging VJET JavaScript authored in either Java or JavaScript language .

Java to JavaScript and JavaScript to Java API translation services can be utilized beneficially to integrate with IDE to perform auto translation when source of truth was modified and saved to integrate with build script to perform translation based on configuration control and to perform on the fly translation in debug mode when the source code has been modified.

Third party non VJET library integration may be performed as separate step. For example coded separate abstract VJET types may be coded to represent external types based their documentation or meta data definition. This step may be automated via e.g. code generation tools if there is standard meta data definition such as XML definition.

Via JavaNativeProxy normal server side application could also leverage existing client side logic written in JavaScript in order to perform server side logic.

In a traditional client side JavaScript engine such ase.g. a JavaScript engine that may reside in a browser only JavaScript form will be presented and Java code will be executed in its translated JavaScript form. In VJET extended JavaScript engine a user may choose to run all code in JavaScript form e.g. translated code from Java or in the authored form e.g. Java or JavaScript .

Below are some example Java modules that may be utilized in a system for integrating Java and JavaScript technologies.

Examples 1 and 2 below include Java code for Creating Java API from JavaScript. Example 1 shows a type definition for a Java API corresponding to a JavaScript module. Example 2 illustrates code generation of a Java native proxy from a JavaScript module resulting in a JavaScript native proxy.

Examples 3 and 4 below illustrate extension techniques for functional programming that integrate JavaScript modules and Java modules.

The Java code examples reproduced above may be run and debugged in their current form utilizing the enhanced JavaScript engine in an IDE. The Java code reproduced above can interact with native JavaScript objects seamlessly. Those Java objects can be created and accessed by either JavaScript code or Java code.

The techniques described herein in some embodiments may be used advantageously to provide strongly typed API for accessing native JavaScript objects and functions as well as execution and debugging environment to run Java code and JavaScript code with a blurred language boundary.

The example computer system includes a processor e.g. a central processing unit CPU a graphics processing unit GPU or both a main memory and a static memory which communicate with each other via a bus . The computer system may further include a video display unit e.g. a liquid crystal display LCD or a cathode ray tube CRT . The computer system also includes an alpha numeric input device e.g. a keyboard a user interface UI navigation device e.g. a cursor control device a disk drive unit a signal generation device e.g. a speaker and a network interface device .

The disk drive unit includes a machine readable medium on which is stored one or more sets of instructions and data structures e.g. software embodying or utilized by any one or more of the methodologies or functions described herein. The software may also reside completely or at least partially within the main memory and or within the processor during execution thereof by the computer system with the main memory and the processor also constituting machine readable media.

The software may further be transmitted or received over a network via the network interface device utilizing any one of a number of well known transfer protocols e.g. Hyper Text Transfer Protocol HTTP .

While the machine readable medium is shown in an example embodiment to be a single medium the term machine readable medium should be taken to include a single medium or multiple media e.g. a centralized or distributed database and or associated caches and servers that store the one or more sets of instructions. The term machine readable medium shall also be taken to include any medium that is capable of storing and encoding a set of instructions for execution by the machine and that cause the machine to perform any one or more of the methodologies of embodiments of the present invention or that is capable of storing and encoding data structures utilized by or associated with such a set of instructions. The term machine readable medium shall accordingly be taken to include but not be limited to solid state memories optical and magnetic media. Such media may also include without limitation hard disks floppy disks flash memory cards digital video disks random access memory RAMs read only memory ROMs and the like.

The embodiments described herein may be implemented in an operating environment comprising software installed on a computer in hardware or in a combination of software and hardware.

Thus a method and system for integrating Java and JavaScript technologies has been described. Although embodiments have been described with reference to specific example embodiments it will be evident that various modifications and changes may be made to these embodiments without departing from the broader spirit and scope of the inventive subject matter. Accordingly the specification and drawings are to be regarded in an illustrative rather than a restrictive sense.

