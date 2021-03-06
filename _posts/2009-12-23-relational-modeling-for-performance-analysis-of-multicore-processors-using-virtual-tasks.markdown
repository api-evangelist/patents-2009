---

title: Relational modeling for performance analysis of multi-core processors using virtual tasks
abstract: A relational model may be used to encode primitives for each of a plurality of threads in a multi-core processor. The primitives may include tasks and parameters, such as buffers. Implicitly created tasks, like set render target, may be visualized by associating those implicitly created tasks with actual coded tasks.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08850404&OS=08850404&RS=08850404
owner: Intel Corporation
number: 08850404
owner_city: Santa Clara
owner_country: US
publication_date: 20091223
---
This relates generally to multi core processors and particularly to performance analysis of multi core machines.

Modern general purpose and graphics processors may include one or more cores. These processors may run a large number of threads. Therefore analyzing the performance of a processor may involve a complex undertaking given the number of tasks and the number of different threads that may be running.

Conventionally a trace is a graphical depiction of a temporal sequence between tasks running on a processor. Software based trace analysis enables a software designer to understand the sequence of operations between tasks.

In accordance with some embodiments of the present invention relationships other than temporal sequencing may be visualized between chunks of code called tasks. A task is any common unit of work for scheduling and execution. It can be any portion of code with a beginning and an end. Its duration may be defined as a number of cycles to execute the task.

Traces are links between tasks. A relational model gives the relationship between tasks in terms of parent to child sibling dependency and producer and consumer. Other relationships may also be used.

The parent child relationship exists between a first task and a second task spawned by the first task. A dependency exists between a first and a second task when the first task depends on the second task to execute. A producer consumer relationship means that a first task creates data and places it in a buffer and a second task consumes that data from the buffer.

A primitive is any entity that is a party to a relationship. A task is one type of primitive. Another primitive is called a parameter. A parameter may be a buffer a name value pair a string or any kind of normal data type or structure that has a relationship to a task. Other primitives may also be used.

Referring to the performance analysis tool may include a control which may be a processor. The processor may be a multi core processor. In one embodiment it may be a graphics processor and in one embodiment it may be a single instruction multiple data SIMD multi core processor. The control is coupled to a memory which may store a graphical user interface or front end of the tool a number of sequences or application program interfaces APIs which encode the primitives and the relationships between primitives and a library which provides the toolbox of features that can be utilized. The control may be coupled to an input output to allow the user to input information and to receive an output. A display may be used to visualize the relationships between primitives including tasks.

The performance analysis tool is used by software developers to enhance the performance of their software by understanding the relationships between primitives such as tasks within that software. By understanding these relationships the software developer can understand how to improve the software performance.

Generally the software developer develops two versions of the code. One version of the code is the code which merely executes the desired function such as a game. The other version of the code includes within it the APIs which create the visualizations of the primitive relationships in some embodiments while in other embodiments binary outputs can be used without visualizations for further analysis . The version of the code with the APIs is called the instrumented code. Streaming the instrumented code to the front end graphical user interface enables the designer to see what is going on in the code. It shows the threads that are running in the code the tasks within the threads and most importantly the functional relationships between those tasks.

Referring to the sequence implemented by the application program interfaces begins by receiving the selection of a thread as indicated in block . Next a primitive identifier is selected as indicated in block . The identifier is registered in block . Then the identifier is assigned to a primitive in block .

At this point the designer then enters the relationships between a selected primitive and other primitives. The selected primitive is called the this primitive and the primitives that the this primitive has relationships with are called the that primitives.

In some embodiments the sequence automatically implies a number of relationships beyond those entered by the designer. For example if a first task is the parent of a second task it is implied that the second task is the child of the parent. Similarly if a first task is related to a second task and the second task is related to a third task it is implied that the first and third tasks are also related and the nature of the relationship can be implied. This may be referred to as transitive relationships or relationships that are implied from other relationships. The use of transitive relationships in some embodiments reduces the data entry burden on the user. In addition there may be one to N or fan out relationships. For example a single parent may spawn any number of children and all of those children do not need to be separately encoded in some embodiments.

In addition the sequence provides time stamps for each of the primitive identifiers. It also provides the time when any task begins and ends as an output. Thus in one embodiment it can display a series of threads as rows in a chart. Each row may include the sequence of tasks in the thread. In addition nested tasks may be indicated as well by visualization such as showing the nested task as extending out of the task within which it executes. A user can click on a particular task and in response to the selection of the task its relationships may be graphically displayed.

As opposed to tracing systems which are time based the system may be relationship based. The temporal relationship between tasks and different buffers is less important than the relationships between them. In some embodiments relationships within tasks are shown even where their relative timing is not in some embodiments. Thus within the thread the time sequence of tasks may be illustrated but the temporal sequence of tasks in different threads may not be displayed in some embodiments. In some embodiments functional as opposed to temporal relationships may be visualized. A functional relationship is any relationship other than the temporal sequence between tasks.

In one embodiment each task may be represented by a rectangle whose length in the x direction is a function of how long it takes to execute. In some embodiments a mouse click and drag technique can be used to select a number of tasks to display the relationships between those selected tasks and any other tasks.

Thus as a simple example referring to there are four primitives including three tasks and and one parameter in the form of a buffer . The arrows and show the relationships between the tasks. For example the vertex task may place its results in the buffer and those results may be used by the task . Thus the task is the producer and the task is the consumer. Since the vertex task was created by the draw task the arrow indicates that the vertex task is the child of the draw task . Similarly the pixel task depends on the vertex task to execute and therefore the dependency is indicated by the arrow . Thus in some cases there may be multiple relationships between tasks. In addition there may be multiple object types.

Returning to after assigning the identifier to the primitive in block the relationships for this primitive are then entered as indicated in block . While a manual technique is described herein automatic techniques are also contemplated wherein code analysis results in automatic entry of relationships without user intervention.

Then in diamond a check determines whether there are any more primitives to encode. If so the flow iterates. Otherwise a check at diamond determines whether there are more threads to encode. If so the flow iterates. Otherwise the flow ends.

In this case the user has selected a parent task B in the second thread. In response thereto the visualization of the parent child relationship is automatically generated. Namely arrows extend from task B to a series of tasks C in the third thread which are children of the task B. Moreover arrows extend from the task C in the third thread thereon to task C in the fourth thread which are grandchildren of the parent task B.

In some graphics applications such as rendering passes the techniques described heretofore would not enable task visualization. However the rendering pass may be a useful measure of work performed by a program and may be a desirable tool for profiling at an application developer level.

Because the graphics application program interface does not contain an explicit function that actually represents a rendering pass it would not be coded using the techniques described heretofore because the rendering pass is implicitly created during a series of API calls. Thus such an implicitly created task may be visualized using a virtual task. As a more concrete example the following example of calls may be made in the Direct X API 

With the regular task the time stamp of the begin and end calls is recorded since the duration of the task may be of interest. However in the example with the set render target above the actual task is over as soon as it is done rather it is a place holder for real work that will be done later.

To give a virtual task actual duration other non implicitly created or actual coded tasks may be associated with the virtual task. For example when a draw call task is created that draw call task is a child of the actual virtual task. With this concept of a virtual task the duration of a set render target may be given a duration presenting the user with a list of render target virtual tasks and computing their duration based on all of their related tasks.

Then the virtual tasks may be visualized in a time line as represented in by using the minimum and maximum of its child task. From the parent child relations the visualization shown in may result. For example the underlying task of rendering the target one may be drawn as a child of draw and draw and render target two may be shown as a child of draw . Thus the render target and render target get a duration even though the duration is basically the duration of the associated draw calls such as draw and draw in the case of set render target and draw in the case of set render target .

The virtual tasks may also be useful for showing more information about complex tasks so that basic profiling can be done without detailed information. In the render target example only the virtual task render target render target may be shown in an application run as shown in . With a large number of threads this may be more clear than the depiction shown in in some cases. For example with 128 different threads each of which itself contains hundreds of thousands of tasks the set render target executes the longest and set render target is likely dependent on set render target s completion. This insight can enable the designer to either stop profiling and immediately take action perhaps by allowing set render targets and to co execute or by optimizing set render target now that it is known that it is a time consumer.

Referring to the sequence for entering a virtual task may be a module or a part of an API shown in . Initially the virtual task is begun as indicated in block as if it were a real task. Then also as if the virtual task was a real task a current task identifier is set in block . Next the task is associated with another task in block . For example the set render target virtual task may be associated with one or more draw calls as illustrated for example in . This association provides a virtual task duration. Finally the virtual task is ended block .

In short virtual tasks may be useful for building profiling tools for complex highly parallel software. Without them the profiling tool may not be able to show anything more than the mechanism executing an API which may prevent gaining simple and critical performance insights in some cases. Using virtual tasks an abstraction is obtained that allows such issues to be more clear from the start enabling more productive and efficient top down profiling in some embodiments.

The graphics processing techniques described herein may be implemented in various hardware architectures. For example graphics functionality may be integrated within a chipset. Alternatively a discrete graphics processor may be used. As still another embodiment the graphics functions may be implemented by a general purpose processor including a multi core processor.

References throughout this specification to one embodiment or an embodiment mean that a particular feature structure or characteristic described in connection with the embodiment is included in at least one implementation encompassed within the present invention. Thus appearances of the phrase one embodiment or in an embodiment are not necessarily referring to the same embodiment. Furthermore the particular features structures or characteristics may be instituted in other suitable forms other than the particular embodiment illustrated and all such forms may be encompassed within the claims of the present application.

While the present invention has been described with respect to a limited number of embodiments those skilled in the art will appreciate numerous modifications and variations therefrom. It is intended that the appended claims cover all such modifications and variations as fall within the true spirit and scope of this present invention.

