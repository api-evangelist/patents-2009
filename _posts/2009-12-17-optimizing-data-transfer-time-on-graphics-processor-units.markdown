---

title: Optimizing data transfer time on graphics processor units
abstract: Disclosed are methods and systems for optimizing data transfer time in a graphics processor unit. The methods and systems involve receiving a user request to perform online analytical processing computation, the user request comprising axes dimensions and filter dimensions associated with a visualization for an online analytical computation cube, identifying one or more slices of the online analytical processing cube based on the user request, transferring the one or more identified slices to a second memory, performing the online analytical processing computation for the one or more identified slices at the graphics processor unit and retrieving a result of the online analytical processing computation from the second memory.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08965866&OS=08965866&RS=08965866
owner: Business Objects Software Limited
number: 08965866
owner_city: Dublin
owner_country: IE
publication_date: 20091217
---
The field generally relates to data transfer time optimization and more specifically to online analytical processing OLAP computations on graphics processor units GPU .

A GPU is a specialized processor. It serves as a co processor to a central processing unit CPU assisting to create graphics for display. A GPU normally has a highly parallel structure efficient floating point operations and dedicated memory making it suitable for creating three dimensional graphics. GPUs have been used to do more than create graphics. In OLAP there is an increasing demand for near real time interactive visualization of analytical data using in memory analysis techniques. Most performance enhancing techniques in multi dimensional databases involve pre aggregation. That is aggregation or sub aggregation are stored which enable response times to queries. Generally a GPU is used for performing OLAP computations as GPUs are suited for repetitive calculations required in OLAP. However GPU has a limited memory and it is not possible to fit a cube in the memory of the GPU. Hence every time an OLAP computation is to be performed the contents of the cube or its in memory portion has to be transferred to the memory of the GPU and the result has to be transferred back after the computation. When this is done in a near real time interactive visualization scenario the time taken for data transfer to the GPU starts dominating the actual time for the computation thus negating much of the advantage in making the calculations in the GPU. Hence it is important to reduce the data transfer time to get maximum interactivity from the visualization.

Disclosed are methods and systems for optimizing data transfer time. The methods and systems involve receiving a user request to perform online analytical processing computation the user request comprising axes dimensions and filter dimensions associated with a visualization for an online analytical processing cube identifying one or more slices of the online analytical processing cube based on the user request transferring the one or more identified slices to a second memory performing the online analytical processing computation for the one or more identified slices at a GPU and retrieving a result of the online analytical processing computation from the second memory.

In one embodiment the online analytical processing cube is stored in a first memory of a computer system. The second memory is a memory in the GPU. An OLAP application may be used to retrieve data from the OLAP cube.

These and other benefits and features of embodiments of the invention will be apparent upon consideration of the following detailed description of preferred embodiments thereof presented in connection with the following drawings.

Embodiments of techniques for optimizing data transfer time on graphics processor units are described herein. In the following description numerous specific details are set forth to provide a thorough understanding of embodiments of the invention. One skilled in the relevant art will recognize however that the invention can be practiced without one or more of the specific details or with other methods components materials etc. In other instances well known structures materials or operations are not shown or described in detail to avoid obscuring aspects of the invention.

Reference throughout this specification to one embodiment this embodiment and similar phrases means that a particular feature structure or characteristic described in connection with the embodiment is included in at least one embodiment of the present invention. Thus the appearances of these phrases in various places throughout this specification are not necessarily all referring to the same embodiment. Furthermore the particular features structures or characteristics may be combined in any suitable manner in one or more embodiments.

OLAP refers to a type of data source and associated tools. Business intelligence tools include OLAP tools. OLAP generally refers to a technique of providing fast analysis of shared multi dimensional information stored in a database. OLAP systems are used for report generation and are suited to ad hoc analyses. An OLAP cube normally includes several dimensions and measures. The data in an OLAP data source is multi dimensional and is partially or fully pre aggregated. Also called cubes or hyper cubes these data sources provide a conceptual view of data including full support for hierarchies and multiple hierarchies. The multi dimensional schema means redundant information is stored but it allows for users to initiate queries without the need to know how the data is organized. Also OLAP data sources can have faster response times than relational databases. This framework also finds use because it is a logical way to analyze businesses and organizations. In some OLAP tools the data is arranged in a schema which simulates a multi dimensional schema. The results of an OLAP query are often displayed in a cross tabulation or cross tab. In a cross tab the dimensions form the rows and columns of the matrix while the measures are the values. There are a number of commercially available OLAP tools including SAP BusinessObjects Voyager which is available from SAP Americas of Palo Alto Calif. US.

A dimension represents a group of one or more enumerable business objects like products people financial elements and time. A dimension may be hierarchical e.g. time includes years quarters months and days. A business object need not relate to a commercial enterprise as such and can be related to governance social science engineering science and the like. A measure is a quantity as ascertained by comparison with a standard usually denoted in some metric for example units sold and dollars. A measure such as sales revenue can be displayed for dimension customer product and geography. A measure may be a quantity that is determined by comparison with a standard usually denoted in some metric like units sold . A measure may be a resultant of an aggregation of identical measures for a dimension. For instance measure revenue may be displayed for dimension time . Here the measure describes an aggregation of all the revenues for all the years. A measure can also be displayed as a value for each of the members within a dimension. A value may be described as a quantity for example numeric quantity . For instance for the attribute sales revenue 1000 the value is 1000 .

In the domain of OLAP there is an increasing demand for near real time interactive visualization of analytical data using in memory analysis techniques. In interactive visualization a user is able to select and view the dimensions and measures of the OLAP cube using visualization such as a cross tab or a chart. The visualizations may be two dimensional or three dimensional. The visualizations show data in a corresponding viewport. The viewport could be depicted as a data grid chart or a portion of either bounded by the available screen size or some other imposed restriction. Though OLAP cube includes several dimensions and cells once a viewport is fixed only a part of the OLAP cube is of user s interest. The selection of a viewport fixes a sub set of the dimensions as axes for the visualization. In the interactive visualization performing OLAP computations such as aggregation e.g. Sum Average Max Last on a user request is an important aspect. Aggregating a measure along one or several dimensions is the act of determining an overall value of this measure for sets of members of these dimensions. For instance Revenue could be aggregated by cities or whole countries or by days or quarters. For each dimension that governs it a measure may also specify how values are aggregated along the members of the dimension. For instance it can be specified that the measure Inventory aggregates by a sum on Geography the inventory for a given product in a country at a point in time is the sum of the inventories for all its cities and on Product the inventory for a group of products is the sum of inventories for each product in this group but aggregates on last along the time dimension the inventory for a product for the year is the inventory at the end of the last day of this year . A set of measures with same dimensionality can be grouped into a set called a Dimension of Measures which behaves just like a dimension. Together with the dimensions that define its dimensionality a Dimension of Measures defines a Cube.

For the purpose of aggregation the user may typically select two or three dimensions of the OLAP cube for analysis purposes. When the user selects three dimensions the selected dimensions are presented on a user interface screen along the x axis y axis and z axis. For example consider an OLAP cube having dimensions namely time products and geography and a measure of sales revenue. The user may select two dimensions namely products and geography as axes dimensions in a two dimensional visualization. The unselected dimension time is considered as a filter dimension. A visualization tool presents the values for products and geography as a two dimensional cross tab or chart in the viewport of the user interface. Based on the two dimensional presentation the user will be able to analyze revenues for different products in different geographic locations. The user can manipulate the controls for example to drill down to perform more detailed analysis of the sales revenue. Alternatively the user can redefine the viewport for example resize or move. When drilling down to perform more detailed analysis of the sales revenue the user can slice the OLAP cube according to his interest. A slice is a subset of a multi dimensional array corresponding to a single member for each of the dimensions not in the subset. The slice often refers to a two dimensional array selected from the OLAP cube. In this scenario the user has sliced the OLAP cube according to product and geography. The intersection of the viewport and the slice defines a view slice.

For OLAP computations GPU is suited to perform repetitive calculations involved in aggregating all the cells in a cube or sub cube in parallel. The GPU is a specialized processor meant for accelerating graphics processing on devices like personal computers game consoles and graphics workstations. These processors have massively parallel processing power and are increasingly used to implement many complex algorithms outside of the graphics domain. They usually have Single Instruction Multiple Data SIMD or Multiple Instruction stream Multiple Data stream MIMD architecture. SIMD architecture and MIMD architecture includes more than one memory which helps in speeding up the processing power. The processing power of the GPU may be combined with in memory analysis techniques to afford near real time visualization of larger cubes with more dimensions and more complex ad hoc queries.

An implementation of performing OLAP computations using a GPU will involve transferring parts of the OLAP memory cube required for an OLAP computation to a device memory in the graphics processor unit. The OLAP computation is performed in a processor of the GPU and the result obtained from the computation is made available to the CPU for example transferred back to the CPU memory. Transferring parts of the OLAP memory cube may involve transferring slices of the OLAP cube associated with the OLAP computations. In the further embodiments the CPU memory and the device memory are illustrated as first memory and second memory respectively.

Consider the user is interested in detailed analysis of product Pacross different geographic locations during a specific period of time. The user selects product and geographic location as axes dimensions and time as filter dimension. The shaded portion of the cube shows the slice which contains data of product Pacross different geographic locations according to the user selection. On applying the time Tas filter dimension the user is interested in detailed analysis of product Pin geographic location Gand for time T then the data in portion is used. This is a filtered slice.

In an embodiment a new viewport is determined if the axes dimensions are altered. When the axes dimensions are altered the viewport size increases or decreases accordingly. In another embodiment the new viewport is reloaded to the second memory. In case the viewport is increased the increased portion of the viewport is moved to the second memory.

Assuming that the OLAP cube includes products on the x axis and geography on the y axis and time on the z axis one or more slices associated with the user request is identified based on the axes dimensions the filter dimensions and the limitations imposed on the axes. In this scenario the axes dimensions are product and geography and the filter dimensions are time and distribution channel. This data can be visualized on a viewport. In this scenario the viewport is a grid of product versus geographic location. The filter dimensions can alter the values displayed on the viewport.

Consider the user analyzing revenue earned from the online sales for the first quarter of 2008. One or more slices associated with the aggregation are identified. In this scenario the slices of the OLAP cube contain data of a c and e illustrated above. The slices are visualized in a viewport to obtain corresponding view slices. The size of the view slices is limited to the viewport area. The viewport area is determined based on the axes dimensions filter dimensions and the set of limitations imposed on the axes dimensions. According to this scenario the view slices will contain sales revenue for product keyboard for geographic location USA according to the OLAP cube data a c and e . A memory with capacity equal to the size of the view slice is allocated in the second memory. The identified view slices are transferred to the second memory. The addresses of the identified slices are stored in lookup data structure. The lookup data structure may include but is not limited to a hash map table Translation Look Ahead Buffer TLB and the like. The user request for aggregation is transferred along with the identified slices. At a processor of the GPU the aggregation request is computed. The result obtained from the aggregation computation request is stored in the second memory. The result of the aggregation request is retrieved from the second memory and is displayed on the viewport of the graphical user interface. In an embodiment the slices are identified for each filter dimension. For example the above explained scenario includes two filter dimensions namely time and distribution channel. The slices are identified based on both time and distribution channel as well.

In an embodiment when the user requests for an aggregation only the slice addresses are sent to the second memory provided its address is available in the lookup data structure. If the address is not available in the lookup data structure the slice is transferred to the second memory. This involves only a fraction of the data transfer time than the time required for transferring complete slices. The GPU de references the slice addresses to fetch the slices from the device memory itself. The whole computation is done in the GPU and only the result is sent back to the first memory. Assuming 32 bit addresses and slice size of 400 cells each containing 32 bit data the savings in data transfer time is 1 400.

A second portion of viewport displays data of a view slice associated with a user request to view the sales revenue of product keyboard according to geographic location USA for the first quarter of the year 2008 on applying retail sales as a filter dimension.

Some embodiments of the invention may include the above described methods being written as one or more software components. These components and the functionality associated with each may be used by client server distributed or peer computer systems. These components may be written in a computer language corresponding to one or more programming languages such as functional declarative procedural object oriented lower level languages and the like. They may be linked to other components via various application programming interfaces and then compiled into one complete application for a server or a client. Alternatively the components maybe implemented in server and client applications. Further these components may be linked together via various distributed programming protocols. Some example embodiments of the invention may include remote procedure calls being used to implement one or more of these components across a distributed programming environment. For example a logic level may reside on a first computer system that is remotely located from a second computer system containing an interface level e.g. a graphical user interface . These first and second computer systems can be configured in a server client peer to peer or some other configuration. The clients can vary in complexity from mobile and handheld devices to thin clients and on to thick clients or even other servers.

The above illustrated software components are tangibly stored on a computer readable medium as instructions. The term computer readable medium should be taken to include a single medium or multiple media that stores one or more sets of instructions. The term computer readable medium should be taken to include any physical article that is capable of undergoing a set of physical changes to physically store encode or otherwise carry a set of instructions for execution by a computer system which causes the computer system to perform any of the methods or process steps described represented or illustrated herein. Examples of computer readable media include but are not limited to magnetic media such as hard disks floppy disks and magnetic tape optical media such as CD ROMs DVDs and holographic devices magneto optical media and hardware devices that are specially configured to store and execute such as application specific integrated circuits ASICs programmable logic devices PLDs and ROM and RAM devices. Examples of computer readable instructions include computer code such as produced by a compiler and files containing higher level code that are executed by a computer using an interpreter. For example an embodiment of the invention may be implemented using Java C or other object oriented programming language and development tools. Another embodiment of the invention may be implemented in hard wired circuitry in place of or in combination with computer readable software instructions.

A data source is an information resource. Data sources include sources of data that enable data storage and retrieval. Data sources may include databases such as relational transactional hierarchical multi dimensional e.g. OLAP object oriented databases and the like. Further data sources include tabular data e.g. spreadsheets delimited text files data tagged with a markup language e.g. XML data transactional data unstructured data e.g. text files screen scrapings hierarchical data e.g. data in a file system XML data files a plurality of reports and any other data source accessible through an established protocol such as Open DataBase Connectivity ODBC produced by an underlying software system e.g. ERP system and the like. Data sources may also include a data source where the data is not tangibly stored or otherwise ephemeral such as data streams broadcast data and the like. These data sources can include associated data foundations semantic layers management systems security systems and so on.

The above descriptions and illustrations of embodiments of the invention including what is described in the Abstract is not intended to be exhaustive or to limit the invention to the precise forms disclosed. While specific embodiments of and examples for the invention are described herein for illustrative purposes various equivalent modifications are possible within the scope of the invention as those skilled in the relevant art will recognize. These modifications can be made to the invention in light of the above detailed description. Rather the scope of the invention is to be determined by the following claims which are to be interpreted in accordance with established doctrines of claim construction.

