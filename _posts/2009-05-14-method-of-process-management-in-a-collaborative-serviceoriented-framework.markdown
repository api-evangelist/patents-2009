---

title: Method of process management in a collaborative service-oriented framework
abstract: A method for process management in a collaborative service-oriented workshop for processing objects associated with data representing real data or processes, each object including a structure for storing links to other objects. After determining at least one function and at least one piece of information enabling the execution of the at least one function, an object including at least one reference to the at least one function and the at least one piece of information is created.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08984016&OS=08984016&RS=08984016
owner: Airbus Operations S.A.S.
number: 08984016
owner_city: Toulouse
owner_country: FR
publication_date: 20090514
---
The present invention concerns information technology architectures for collaborative work and more particularly a method for process management in a collaborative service oriented workshop.

Optimization of the study and design phases for objects such as vehicles for the purpose of reducing the development costs and time generally necessitates the employment of a specific information technology environment.

For example the aerodynamic study of an aircraft involves numerous specialists working on different aspects of the same data which aspects may or may not be related to one another. These specialists generally use different information technology tools as well as different machines for execution of the processes being employed. In addition these specialists may be situated at different geographic locations.

It is therefore proving advantageous to employ an environment based on an open architecture that permits sharing of data and information technology resources especially calculating resources. Preferably such an environment should be adapted to a range of heterogeneous machines and operating systems.

It is also advantageous to use an interface that it makes it possible to access separate and different existing tools. Such a common interface should be adapted in particular to manage data that have to be exchanged between these tools as well as to permit easy selection of and access to the data.

In addition the environment preferably should permit easy adaptation to future needs such as integration of new tools management of new types of data and production of new types of results.

Furthermore there exists a need for data traceability in order to determine the origin of the produced data as well as their life cycle during the different modifications and uses in calculation or other processes.

For example there exist software applications such as SynfiniWay developed by the Fujitsu Corporation SynfiniWay and Fujitsu are trademarks that permit optimization of the execution of tasks in a heterogeneous environment. The SynfiniWay application makes it possible in particular to virtualize the global resources and to present the applications in the form of services linked by data sequences and dependences in order to automate the information technology processes.

Furthermore there exist script languages such as Python and Java Python and Java are trademarks that make it possible to automate certain tasks and to call up existing tools. Python is a high level interpreted and object oriented programming language. It may be used in numerous contexts and be adapted to numerous uses by means of specialized libraries.

For its part data traceability is generally determined by the processes that led to the data. For example in the applications of PDM type initials for Product Data Management in English terminology the user must follow predetermined processes without being able to deviate from them. The origin of a datum is therefore determined by the process that made it possible to obtain the datum.

However a centralized and optimized environment does not exist for the study and design of systems in a heterogeneous open collaborative environment.

The object of the invention is therefore a method for process management in a collaborative service oriented workshop adapted to treat objects associated with data representative of real or process data each object comprising a structure adapted to store links to other objects in memory this method comprising the following steps 

The method according to the invention therefore makes it possible to manage data independently of their inherent characteristics such as their nature their storage location and their size to permit global management thereof.

Advantageously the said at least one information item is a reference to at least one object associated with a datum used as input or as output of the said at least one function.

The method according to the invention is therefore capable of executing processes represented by objects and of establishing links between the objects associated with the executed processes and the objects associated with the real data employed by the processes or in other words for example used or produced by the processes.

According to a particular embodiment the said at least one function is a function external to the said collaborative service oriented workshop in order to use existing functions and to limit software developments. The method according to the invention therefore makes it possible to avoid maintaining several similar versions of software modules.

The method according to the invention therefore makes it possible to create objects associated with composite processes or in other words combinations of functions.

According to a particular embodiment the method additionally comprises a step of converting the said object to a function that can be executed by a module external to the said collaborative service oriented workshop thus making it possible to use the function outside the collaborative service oriented workshop without rewriting the corresponding code.

Advantageously the environment of execution of a process model is similar for the process models executed by the said collaborative service oriented workshop and for the said functions that can be executed by an external module in order to offer homogeneity of execution of the functions.

According to a particular embodiment the method additionally comprises a step of creating an object comprising at least one reference to the said function that can be executed by an external module and to at least one information item necessary for execution of the said function that can be executed by an external module.

The creation of processes can therefore be guided by the degree of granularity desired for traceability of the data produced and or used by the methods being employed.

Advantageously the said external function conforms with a task execution or sequencing engine thus permitting compatibility of execution of the said external function with standard tools.

Another object of the invention is a computer program comprising instructions adapted to the employment of each of the steps of the method described in the foregoing.

Data access module is connected to data management module as well as to a centralized database such as a database of Oracle type Oracle is a trademark . Data management module is connected to centralized database to execution engine and to an assembly representing distributed storage zones which can be organized in different ways such as in the form of files or databases. Execution engine is itself connected to assembly of storage zones and to process management module .

Although this architecture is particularly adapted to the design of complex objects such as aircraft the following description is based on a simple example for reasons of clarity and conciseness. This example is given for illustrative purposes.

Architecture is adapted to manipulate information technology objects representing data in the broad sense of the term since these data may be representative of a real object such as an aircraft or of a process such as an aerodynamic drag calculation process. In simplified manner the collaborative service oriented workshop works on data represented by information technology objects themselves based on metadata representing characteristic data.

The data known as framework data or FD in English terminology are therefore physical data stored in memory for example in the form of files in a storage zone . These data characterize a real object such as the grid or the structure of a chair or a process such as the steps of a furniture removal process. The size of these data is not limited and may be several hundreds of megabytes. All the data used may be stored in memory in separate physical locations.

The objects known as framework objects or FO in English terminology represent objects having a particular significance in the application sense. As indicated in the foregoing these objects are used to represent everything that can be manipulated by the collaborative service oriented workshop. The objects are based on metadata sets that may be thought of as base elements or characteristic elements. One metadata set is therefore associated with each object. Each type of metadata set may be associated with a plurality of objects. The qualification of a type of metadata set makes it possible to form an object. If for example a type of metadata set is associated with a chair one qualification of the chair forming an object may be a child s chair.

In the interests of clarity the information technology implementations of objects known as framework object proxies or FO proxies in English terminology are assimilated here with the objects themselves.

The objects include the instantiated process models known as instantiated process templates or IPT in English terminology. The instantiated process models are instances of process models or in other words process models applied to one or more objects. The process models known as process templates or PT in English terminology are generic. For example they relate to a process of constructing a room starting from several chairs and a table a process of renovating a house or a furniture removal process. The instantiated process models are represented in the form of objects and may be manipulated as such in the collaborative service oriented workshop.

The metadata known as framework metadata or FMD in English terminology correspond to particular information items of the data. They make it possible to characterize the data in order to facilitate their manipulation. One datum may be associated with a plurality of metadata sets. The metadata are advantageously stored in memory in centralized database in the form of tables or of XML files initials for Extensible Markup Language in English terminology . One type is associated here with each metadata set. The metadata comprise generic information items such as an identifier a creation date and a name of the creator and specific information items inherent to the associated datum such as the material the color or the weight of a chair. The metadata also comprise links to objects thus making it possible in particular to determine how the data were obtained and or how they have been used. These links make it possible to define data models or in other words data tree structures.

The consistency of an object is verified via the links defined in the metadata set associated with it. For example a data model of a table may be determined in such a way that a table is linked to a chair. If an object of table type is effectively associated with an object of chair type then the object of table type is said to be consistent in the sense of the data model defined via its links.

The metadata are described for example by means of a language of XML type according to the structure presented in the Annex under the heading Code excerpt 1 .

The generic part of the metadata is common to all data and it is therefore defined during employment of the collaborative service oriented workshop. Even if this part does not have any reason a priori to be modified its definition may nevertheless evolve according to the needs. However its evolution has an influence on all of the objects managed in the collaborative service oriented workshop.

The specific part of the metadata is inherent to each type of data and consequently to each type of metadata set. This part is defined by the users of the collaborative service oriented workshop. The information items of the specific part of the metadata are determined by the operations of automatic extraction that have to be performed on the data.

The generic and specific metadata are advantageously used to search for and sort data contained in the collaborative service oriented workshop.

The example given in the Annex under the heading Code excerpt 2 illustrates the description of XML type of a type of metadata used to describe a chair.

As described in the foregoing the metadata advantageously comprise a generic part and a specific part. In the present case the generic part comprises in particular the following elements 

The second part of the metadata specific to the object being manipulated in the present case a chair comprises the following attributes in this example 

The identifier or address of a metadata set makes it possible to retrieve the data with which it is associated.

The qualification of a metadata set representing a chair may be in particular child or adult making it possible to end up with two different objects.

In the same way it is possible to define metadata and objects for tables. During importation of an object defining a table it is possible to define at the level of a data model that this object is consistent only if it is linked to at least one object of chair type. Such a relation between objects is defined by the links defined in the metadata. These links may also be represented in XML format or in a table. During importation of an object of table type links of data model type must be established between the object of table type and the objects of chair type in order to make this object consistent with the data model defined in this way.

Alternatively the metadata may be represented in the form of tables. For example a table may be associated with each type of datum. The columns of the table represent the metadata while each of its rows represents an object. Table 1 presented in the Annex illustrates a simplified example of representation of a type of metadata set that can be associated with data of chair type. It should be noted here that the links are not included in the table representing the metadata. According to this example the links are stored in memory in a table of links.

A table of links may be represented for example in the form of the table presented in the Annex as Table 2 in which each column represents a pair of identifiers of objects between which a link is established.

Thus the information items stored in memory in the metadata tables and in the table of links make it possible to manipulate all of the present and future data of the collaborative service oriented workshop as well as to construct data models.

It may be noted here that the representation of metadata in the form of tables is equivalent to an XML representation and that it is possible to use a conversion tool to switch from one representation to another.

Representation of data characterizing physical objects or processes is therefore achieved at several levels 

It should be noted here that according to this structure it is not necessary to employ synchronization methods in the collaborative service oriented workshop.

Data access module makes it possible in particular for a user to access in selective and centralized manner metadata stored in memory in centralized database especially in order to visualize these metadata to construct views on these metadata permitting effective sorting over all of the data accessible in the collaborative service oriented workshop as well as to follow if necessary the links uniting certain of these data.

Module also makes it possible to record metadata in centralized database . Thus it is possible for a user to enter metadata via a man machine interface MMI in order to specify information items that would not appear in the data stored in memory in storage zones . To access and record metadata the user interface may use in particular requests of SQL type initials for Structured Query Language in English terminology . This manual recording of metadata proves advantageous with regard to addition of specific information items that are not amenable to automatic extraction from the datum during importation of the object into the workshop.

Similarly data access module makes it possible for a user to access in selective and centralized manner the data stored in memory in storage zones via data management module as well as to record data. To access and record data the user interface advantageously uses specific APIs initials for Application Programming Interface in English terminology and web services.

Data manager is used as interface between data access module centralized database storage zones and execution engine adapted in particular to apply processes to data. Data manager also makes it possible to control the access rights of the users.

According to a particular embodiment data manager is composed of a client part and a server part. The client part may be implemented in a language of Python type to make it possible to access web services accessible in the server part. All the standard functions of data management such as importation exportation publication collaboration and management of rights are preferably available. This list is not exhaustive. All of the functions used in the course of the life cycle of the datum are available via this API.

The server part may be implemented for example in language of the Java or Python type to permit interfacing with the different databases and storage zones. Advantageously this part is also in charge of the mechanisms for extracting metadata from data stored in memory in distributed storage zones to centralized database containing the metadata.

Execution engine permits the execution of processes by way of process models based for example on discipline specific applications. An interface between execution engine and storage zones permits access directly or via an API to the data during the execution of processes. Execution engine is preferably linked to a calculation grid for example of SynfiniWay type which manages the submission of different processes on a distributed infrastructure as well as the movement of data during execution.

Preferably execution engine also comprises an interface with applications using flows of jobs workflows in English terminology such as the ModelCenter applications ModelCenter is a trademark or SynfiniWay or in other words task execution or sequencing engines.

Process manager permits the creation of high level workflows known as composite processes which encapsulate unitary treatments. These workflows may be subjected to parametric studies and to studies of sensitivities to parameters and may permit the creation of behavior models. These functionalities may therefore be used in connection with multidisciplinary optimization studies.

Thus the treatment of non unitary processes or in other words processes relying on several different functions is managed by the process manager in such a way for example that they are decomposed into unitary processes which are then executed by the execution engine.

Data are created in the different databases not illustrated by means for example of a file interface or of an interface of Corba type acronym for Common Object Request Broker Architecture in English terminology Corba is a trademark .

A mechanism for extraction transformation and loading known as ETL initials for Extract Transform and Load in English terminology is then employed in order to extract the metadata from data stored in memory in storage zones . They are stored in centralized database . This database therefore collects the information items of the physical data created in the different distributed storage zones .

It should be noted here that the extraction mechanism is employed when the data are created modified or deleted. It is specific to each type of data and metadata.

A qualification function makes it possible to qualify the extracted metadata to form objects that can be stored in memory in centralized database . Following qualification verification of the consistency of the object is performed. This consistency may be assured via links which may or may not be stored in memory together with the metadata which links may be of different natures such as the version the configuration the data model and the user.

A set of links between objects defining a data model may be used to determine links between several objects. The links are associated with metadata. As described in the foregoing they are stored in memory with the latter or in separate manner for example in a table of links stored in memory in centralized database .

The links make it possible to establish at a later time the traceability of the data or in other words the traceability between the different data produced or used during execution of processes. Several types of links exist especially the following 

The set of these links placed in pairs makes it possible to obtain the traceability carried by the datum the data contain all of the histories especially as regards the execution of processes the version the configuration the users and the models.

In this way it is possible to construct complete trees of objects linked to one another by metadata and specific links. In the example of the chair and the table a tree making it possible to know the metadata color and location of the table verifies the data model linking it to chairs having a specific color as metadata. In this way it is possible to reconstruct gradually complete trees for obtaining data.

It should be noted here that the data models or in other words the data tree structures are specific to the data being manipulated in the collaborative service oriented workshop. However although the data models may be derived from links between the objects they do not exist as such in the collaborative service oriented workshop. They are implicitly created during the definition of objects or in other words metadata sets corresponding to particular data types.

As illustrated in a function of data manager makes it possible to access links and objects in order to form a view of consistent objects or in other words a view presenting the relations between objects which view may be transmitted to a user in the form of data model views .

Similarly the user may visualize objects and relations in the form of object views and of relation views such as lists.

Thus according to this embodiment the user or in other words the client part of data manager has available the following three types of views 

A description of XML type of objects of object proxy type containing all of the metadata associated with each datum is advantageously created for use for example by execution engine in order to access the data stored in memory in storage zones in the course of execution of processes.

After a first object has been selected step for example via a man machine interface a link to a second object contained in this first object is accessed step . Then a link to a third object contained in this second object is accessed step in order to make it possible to establish a link between the first and the third object step or between the data associated with the first object and those associated with the third object.

Alternatively a link to a third object contained in the first object is accessed step in order to make it possible to establish a link between the second and third object step or between the data associated with the second object and those associated with the third object.

As suggested by the dashed arrow these steps may be repeated iteratively in order to determine a data tree wherein the leaves represent the data or the objects associated with the data and the branches represent the links between the data or between the objects associated with the data .

Instantiated process model is analyzed in a syntax analyzer of XML type known as XML parser in English terminology in order to extract from it the information items that permit execution of the process. In particular the parameters the code and the information items concerning the data necessary for execution of the process are extracted from the XML document. Similarly the data used by the process forming the inputs of the process are retrieved by means of links to the objects in question. All of the information items necessary for execution of the process and extracted from the XML document are transmitted to core of the execution engine.

The code of instantiated process model or in other words the data associated with the object representing the instantiated process model corresponds to instructions that can be directly executed by the execution engine to instructions that can be executed via a specific interface for example of code of Python type or to external functions or modules called on by the execution engine such as ModelCenter functions.

The execution of the process associated with instantiated process model may lead to creation of new objects forming the output of the process. These objects are treated in the same way as the objects described in the foregoing. In particular metadata and links stored in memory in centralized database as well as data stored in storage zones are associated with these objects. Alternatively or in complementary manner the input of the process may be modified in the course of execution thereof. The modified inputs forming an output of the process are known as inputs outputs.

Core of the execution engine preferably relies on an execution environment also known as execution context of the instantiated process module. The purpose of the execution environment is in particular to preserve a history of execution of the process to make the data accessible in the format of the execution engine for example in the form of objects of Python type to monitor the execution of the process and to furnish the interfaces necessary for execution of external modules in the core of the execution engine.

When a process is executed and in particular when new objects are created one or more links is are automatically created in the metadata associated with the data used by the process inputs outputs and inputs outputs as well as in the metadata associated with the instantiated process model.

Before a process is executed the metadata associated with the instantiated process model comprise references to the objects associated with the data to be used but do not contain any link. The links are therefore created in each object when the process is executed.

For example when a process uses a datum to product a result the following links are created in the course of execution of the process 

Depending on the nature of the executable code and the implementation of the collaborative service oriented workshop the executable code is executed by the collaborative service oriented workshop or by an external application. By way of illustration the executable code is executed in this case by the collaborative service oriented workshop if it is of Python type and by an external application if it is for example of ModelCenter MC type.

The execution of functions external to the collaborative service oriented workshop is achieved according to a mechanism of encapsulation of external functions in process models. illustrates an example of encapsulation of a ModelCenter model in a process model.

If the executable code is of Python type the data necessary for execution of the code comprising in particular the references to input and output data as well as to the execution environment are formatted according to the Python format module . The process formatted in this way is then encapsulated module in a process model that can be manipulated by the collaborative service oriented workshop as a standard object module . As illustrated by the arrow connecting module to module the process model uses the Python interface when the process must be executed.

Similarly if the executable code is of ModelCenter type the data necessary for execution of the code comprising in particular the references to input and output data as well as to the execution environment are encapsulated according to the ModelCenter format module . The process formatted in this way is then encapsulated module in a process model that can be manipulated by the collaborative service oriented workshop as a standard object module . Once again as illustrated by the arrow connecting module to module the process model uses the appropriate interface which in this case is the ModelCenter interface when the process must be executed in order to permit execution of the process outside the collaborative service oriented workshop.

By means of a man machine interface or in other words an interface between modules and and between modules and in this case the instantiation of the process model may be achieved after encapsulation of the process.

The objective of encapsulation is in particular to adapt the process models according to a predetermined format. In particular the encapsulation makes it possible to check the validity of data to determine the necessary parameters and impose default values on missing parameters and to copy and or generate the appropriate code. Optionally the encapsulation also makes it possible to define execution directives or in other words to define for example what are the machines on which the processes or certain parts of processes must be executed.

The encapsulation of external functions in a process model is preferably achieved by means of the following XML sections 

Thus a process model can call up a function external to the collaborative service oriented workshop. By virtue of the structure of the objects associated with the process models and in particular the links traceability of the data used as input or output of process models that call up external functions is possible.

Similarly it is also possible to encapsulate process models in external functions for example in ModelCenter models. Thus process models developed in the collaborative service oriented workshop may be used directly by external applications. Via this mechanism it is possible to use and to link process models to other external functions while preserving during execution not only the use of data managed in the collaborative service oriented workshop but also the associated traceability.

The execution of process models starting from an external application is achieved by the neutral execution module of the integration layer of the collaborative service oriented workshop known as SRUN used to execute the instantiated process models.

In this way a process model can encapsulate external functions and be encapsulated in external functions.

In this double encapsulation mechanism the degree of traceability of data is therefore determined by the functions executed by the collaborative service oriented workshop and by external applications.

By way of illustration if a process model A of the collaborative service oriented workshop calls up functions B C and D where B and C are process models of the collaborative service oriented workshop and D is a ModelCenter model that itself calls up functions E and F where E is an external function and F is an encapsulated process model of the collaborative service oriented workshop it is possible to follow the links between B C and D but not between E and F simply between the input of E and the output of F executed outside the collaborative service oriented workshop. In this way it is possible to determine the level of granularity desired for traceability of the data.

As indicated in the foregoing the data associated with objects characterizing instantiated process models may be represented in the form of files for example in the form of a file of XML type. The descriptions of process models advantageously comprise several sections specific to each type of information item.

The process models may themselves be composed of process sub models which may be stored in memory in sections of process models. The process sub models in this case are references to process models accessible in the collaborative service oriented workshop. In this way it is possible to create composite process models that reference several unitary process models or process models that themselves are composite.

The section relating to the inputs the outputs the inputs outputs and the parameters of an instantiated process model comprises for example the name the type and the category. Other items of information may be associated with the inputs the outputs the inputs outputs and the parameters of an instantiated process model such as the type of user concerned a description and a help feature. One section is used for each input output input output and parameter.

The section relating to the execution context of an instantiated process model comprises a classification section specifying the tools used during execution of the instantiated process model. The section relating to the execution context of an instantiated process model also comprises a section for context creation making it possible to store the execution context of the instantiated process model in memory as well as a section for current execution context specifying the configuration to be used to execute the process and making it possible to store the choices to be effected by the calculation grid controller in memory. The section relating to the execution context of an instantiated process model may also comprise an execution server section to specify the configuration of the calculation grid chosen during instantiation of the process model as well as an execution report section filled out at the end of execution of the process and containing for example an error code or art specific information items relating to the execution of the process. The attributes of the sections of creation of context and of current execution context are for example the following 

The section relating to the data of an instantiated process model is provided in order to store in memory the private data of the process model that are available during execution of the process. This section may itself comprise sections such as sections specific to particular processes such as processes of the ModelCenter type.

The section relating to the code of an instantiated process model comprises the code of the process to be executed. The attributes of this section are for example the language used such as the Python language the version of the code and if necessary comments.

Furthermore an instantiated process model may comprise a description of the list of available servers and or of servers preferred for execution of the process.

The links represented in solid bold lines represent inclusion the links in solid lines represent the notion of importation and the links in dashed lines represent the implicit notion of importation.

The extensions of PT type Process Template are associated with process models or in other words with the execution engine the extensions of DM type Data Management are associated with data or in other words with the data manager and the extensions of MC type are associated with ModelCenter or in other words with a particular process manager.

As illustrated a process model comprises a plurality of subassemblies to which in the present case correspond to sections for inputs for outputs for parameters for servers for the execution context for data and for the code respectively. The sections linked to the inputs to the outputs and to the parameters themselves comprise arguments .

The process model implicitly comprises the information items relating to specific models to such as the EDMG models initials for Editeur De Mod le G n ralis Generalized Model Editor ModelCenter and Excel Excel is a trademark . The ModelCenter model of the process model receives information items from a particular model .

It is noted here that the Excel model uses a reference to the function to be used for example a URL initials for Uniform Resource Locator in English terminology while the ModelCenter is included in the process model by virtue of encapsulation.

The data specified in Sections and are obtained from objects which themselves comprise links and to other objects.

Thus references to are associated with the generic process model while the set of references corresponds to an instantiated process model. It nevertheless should be noted here that parameters may also be modified manually by the user.

Instantiated process model is analyzed first of all step in order to check its validity by means of a predetermined XML diagram . If it is not valid execution of the process is stopped and another instantiated process model may be treated. If the instantiated process model is valid the information items contained in this model are extracted step .

The extraction of information items makes it possible in particular to determine execution context configuration as well as execution environment which in particular may comprise the inputs the outputs the inputs outputs the parameters and or the data inherent to the instantiated process model. According to a preferred embodiment execution context configuration and the execution environment are determined according to the Python format.

The execution context configuration is then checked according to the validity of the execution domain step . In fact the creator of a process has the option of specifying a validity domain for example a specific software version. If a user wishes to use a different version he may be prompted or forced to change his choice since the validity condition of the execution domain is not satisfied. If the configuration is not valid execution of the process is stopped and another instantiated process model may be treated.

If the configuration is valid the conditions on the inputs and the inputs outputs are verified step . During instantiation of the process it may be that the user referenced an object that cannot be used in this process because it does not satisfy the conditions defined by the creator of the process. In the given example concerning the table and the chair the furniture removal process may have as a condition for example a specific color of the chair. If the user chooses a chair of a different color the furniture removal process cannot take place. If the conditions on the inputs and the inputs outputs are not valid execution of the process is stopped and another instantiated process model may be treated.

If the conditions on the inputs and the inputs outputs are valid execution of the process proceeds according to the code of the instantiated process model step or in other words according to the data associated with the object representing the instantiated process model.

The code of the instantiated process model is then executed step . In general the core of the execution module known as SRUN loads the inputs the inputs outputs as well as the Python modules necessary for execution of the code into memory. If necessary a distributed execution environment based on the capacities of the SRUN execution module may be employed.

In the case of composite instantiated process models the SRUN execution module creates instances of process sub models in memory and executes them successively as unitary instantiated process models. Coherence between the different unitary processes is then assured by the engine that executes the flow of jobs or workflow.

During the execution of the process the script containing the code is executed in the corresponding execution environment possibly on a machine different from that of the data manager according to the choice of calculation grid manager. Preferably the mechanisms that permit execution of the process in secure manner are used to read and write the physical data to store the history of execution of the process in memory and to store data temporarily in memory.

After execution of the script or in other words the process the execution engine transmits the outputs to the appropriate domain and stores the execution report in memory.

Similarly the object corresponding to data may be combined with an object of dining room type linked to data and with an object of bed type linked to data in an instantiated furniture removal process in order to create an object of inhabited house type linked to data . In this case the metadata linked to data indicate the inhabited state as well as the number of rooms and windows.

The example given in the Annex under the reference Code excerpt 3 illustrates a simplified example of metadata associated with the data of before execution of the renovation process.

As indicated in this example the metadata comprise generic information items especially the type and name of the object as well as the link for accessing the corresponding datum and specific information items in this case the state the number of windows and the number of rooms. It should be noted that the metadata are of the IN type meaning that they do not correspond to data created by an instantiated process model.

The renovation process model that can be used to treat the foregoing example representing a house in ruins may be described generically in the way presented in the Annex under the reference Code excerpt 4 .

This process model has as input an object of house type and creates as output another object of house type. This process model may be instantiated to contain in particular references to objects associated with data and of . The instantiated process model is then for example that given in the Annex under the reference Code excerpt .

As indicated the instantiated process model additionally comprises execution parameters the identification of the execution machine the application configuration used and the execution history links between the objects associated with data and with instantiated process model and between the objects associated with instantiated process model and data .

After execution of the process corresponding to this instantiated process model the metadata linked to data are modified in order to add a history link permitting traceability of the data. After execution of the process therefore the metadata associated with data may be represented in the way given in the Annex under the reference Code excerpt 6 .

As indicated in this example a link was created between the objects associated with data and with instantiated process model . Thus by means of the object associated with instantiated process model it is possible to establish a link between the objects associated with data and .

Similarly after execution of the process data as well as the metadata associated with them including the links are created. The metadata associated with data may then be represented in the way given in the Annex under the reference Code excerpt 7 .

As in the foregoing a link was created between the object associated with data and the object associated with instantiated process model . Thus by means of the object associated with instantiated process model it is possible to establish the link existing between data and . It should be noted that the metadata in this case are of the OUT type meaning that they correspond to data created by an instantiated process model in the collaborative service oriented workshop.

In the same way a second process model may be created and instantiated to treat data and in order to create data and the associated object. When the second instantiated process model characterizing a furniture removal process is executed the metadata associated with data are modified in order to integrate the link induced by execution of instantiated process model . The metadata associated with data may then be expressed in the form given in the Annex under the reference Code excerpt 8 .

The link created between the object associated with data and the object associated with instantiated process model makes it possible by means of this object to establish the link between the objects associated with data and .

Furthermore data as well as the associated object are created during execution of second instantiated process model . The associated metadata may be represented in the form given in the Annex under the reference Code excerpt 9 .

The link created between the object associated with data and the object associated with instantiated process model makes it possible by means of this object to determine the links between the objects associated with data and between the objects associated with data and as well as between the objects associated with data and .

A device adapted to employ part of the invention is illustrated in . Device is for example a microcomputer a computer or a workstation.

The communication bus permits communication and interoperability between the different elements included in device or connected thereto. The representation of the bus is not limitative and in particular the central unit is capable of communicating instructions to any element of device directly or via another element of device .

The executable code of each program allowing the programmable device to employ the processes according to the invention may be stored for example on hard disk or in read only memory .

According to one variant memory card may contain data as well as the executable code of the aforesaid programs which code will be stored on hard disk once it has been read by device .

According to another variant it will be possible for the executable code of the programs to be received at least partly via interface to be stored in a manner identical to that described in the foregoing.

More generally it will be possible for the program or programs to be loaded into one of the storage means of device before being executed.

Central unit will command and direct the execution of the instructions or portions of software code of the program or programs according to the invention which instructions are stored on hard disk or in read only memory or else in the other aforesaid storage elements. During boot up the program or programs stored in a non volatile memory such as hard disk or read only memory are transferred into random access memory which then contains the executable code of at least part of the program or programs according to the invention as well as registers for storing in memory the variables and parameters necessary for employment of the invention.

Naturally to satisfy specific needs a person skilled in the area of the invention will be able to apply modifications in the foregoing description.

