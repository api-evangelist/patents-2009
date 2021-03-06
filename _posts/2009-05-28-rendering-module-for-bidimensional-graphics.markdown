---

title: Rendering module for bidimensional graphics
abstract: The disclosure relates to a graphics module for rendering a bidimensional scene on a display screen comprising a graphics pipeline of the sort-middle type, said graphics pipeline comprising: a first processing module configured to clip a span-type input primitive received from a rasterizer module into sub-span type primitives to be associated to respective macro-blocks corresponding to portions of the screen, and to store said sub-span type primitives in a scene buffer; a second processing module configured to reconstruct the span-type input primitive starting from said sub-span type primitives, the second processing module being further intended to implement a culling operation of sub-span type primitives of the occluded type.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08411094&OS=08411094&RS=08411094
owner: STMicroelectronics S.r.l.
number: 08411094
owner_city: Agrate Brianza
owner_country: IT
publication_date: 20090528
---
The present disclosure relates to a rendering module for bidimensional 2D graphics and particularly having a graphic processing chain or in an equivalent manner a graphics pipeline for the rendering of bidimensional scenes.

Computerized graphics is the technique of generating images on a hardware device such as for example a screen or a printer via a computer. The generation of images or objects to be represented on a display device is usually referred to as rendering.

In the field of bidimensional 2D graphics a 2D graphics pipeline for the rendering of images is known which is based on a data processing approach in a so called immediate mode immediate mode rendering pipeline or briefly IMR pipeline .

By immediate mode data processing is meant as stated an immediate processing of data i.e. in the order in which they are received by the 2D graphics pipeline and a contextual rendering of the data processed on the bidimensional display surface. As it can be inferred in an immediate mode approach each object to be displayed is processed and rendered on the screen independently from the other objects of the scene.

The IMR type 2D graphics pipeline has as a drawback to result to be not very efficient in terms of band loading and costs in the case that operations intended both to improve the quality of the scenes to be displayed and intended to reduce the working load of the same graphics pipeline are implemented. Such drawbacks may negatively impact the performance of a graphic application using the IMR type 2D graphics pipeline.

The present disclosure provides a 2D graphics pipeline of an alternative type to the above mentioned IMR type 2D graphics pipeline In some embodiments the present disclosure may at least partially reduce the drawbacks thereof particularly as regards the band loading and memory loading of the graphics pipeline and the performance of the graphic application in which the same graphics pipeline is employed.

In one embodiment of the present disclosure a graphics module is provided for rendering a bidimensional scene on a display screen. In one such embodiment the graphics module includes a sort middle graphics pipeline the sort middle graphics pipeline including a scene buffer a first processing module configured to clip a span type input primitive received from a rasterizer module into sub span type primitives to be associated with respective macro blocks corresponding to portions of the display screen and to store said sub span type primitives in the scene buffer and a second processing module configured to reconstruct starting from the sub span type primitives the span type input primitive the second processing module being further configured to cull occluded sub span type primitives of the sub span type primitives.

The graphics system of is for example an encoding decoding apparatus for digital television also known as set top box but in accordance with other embodiments of the disclosure it can be another graphics system such as a mobile telephone a PDA Personal Digital Assistant palmtop a multimedia device with a VGA type screen e.g. terrestrial digital receiver DVIX readers or MP3 reader a computer for example a personal computer a gaming device for example PS3 and so on.

The encoding decoding apparatus is preferably of the HDTV type i.e. for the application in the high definition television HDTV .

The encoding decoding apparatus for digital television is configured to receive an encoded input data flow DATIN video and or audio data from an outer antenna ANT in order to provide a corresponding encoded data flow DATOUT to a television apparatus TV provided with at least one display screen DISP and operatively connected to the encoding decoding apparatus .

In more detail the encoding decoding apparatus comprises a central processing unit CPU for example a microprocessor or a microcontroller operatively connected to a primary system memory MEM .

The encoding decoding apparatus further comprises an input output device IN OUT operatively connected to and controlled by the central processing unit CPU in order to receive the encoded input data flow DATIN.

In addition the encoding decoding apparatus comprises an electronic device AH prearranged for the encryption decryption of digital data. In more detail the electronic device is a hardware accelerator operating under the control of the central processing unit in order to decrypt the decoded data flow DATIN received by the input output device . Particularly the hardware accelerator is configured to receive activation signals by the central processing unit to decrypt the data flow DATIN and to send decrypted data DAT to an audio video decoder AU VID adapted to provide under the control of the central processing unit to which it is operatively connected the encoded data flow DATOUT to the television apparatus .

The audio video decoder comprises the rendering graphics module or simply graphics module already mentioned before which results to be operatively connected to and controlled by the central processing unit .

The graphics module is configured to implement a set of functions of the graphics type to render a 2D graphics scene the description of which is received in input by the encoding decoding apparatus through the outer antenna then displayed on the display screen of the television apparatus optionally overlapping the 2D graphics scene obtained with the encoded data flow DATOUT sending the result to the television apparatus .

Preferably the graphics module is a graphics engine configured to render digital images by relieving the central processing unit of additional working loads. To the purposes of the present disclosure by graphics engine is meant a device capable of hardware and or software rendering not by means of the performance by the central processing unit but through the performance by another co processor such as for example a digital signal processor DSP. The terms graphics accelerator or graphics co processor also usually employed in the computerized graphics field are completely equivalent to the term graphics engine.

Alternatively the graphics module can be a graphics processing unit GPU in which the rendering functions are performed on the basis of software instructions performed by a dedicated processor such as a DSP and on the basis of hardware instructions performed by a specifically designed hardware logic. In accordance with a further embodiment some or all of the rendering functions are performed by the central processing unit .

Particularly the graphics module in accordance with the example of the disclosure is intended to render 2D images based on a data processing approach in a so called delayed mode. Furthermore the graphics module is preferably so configured as to result to meet the OpenVG open standard promoted within a panel called Khronos known in the literature.

By data processing through a delayed mode approach is meant a data processing comprising a first processing of the data received in input by the graphics module and the storing of the processed data in a memory internal to the graphics module and following a special command received from the graphics application a second processing intended to display the scene on the screen on the basis of the previously processed and rendered data. It is noted that in a delayed mode approach the data are typically processed in a different order compared to that in which they are acquired by the graphics module strictly depending on the graphics application.

It is noted that the processing of the data based on a delayed mode approach is known in 3D three dimensional graphics and is at the base of the sort middle rendering hardware architecture SMR per se known to those skilled in the 3D graphics and also known as tile based rendering architecture.

In light of what has been stated above by graphics module is meant a graphics pipeline of the sort middle type for the rendering of bidimensional scenes.

Now with reference to the graphics module comprises a drive or driver module DRV a first 2D graphics GFX pipeline hereinafter graphics pipeline and a second 2D filtering pipeline hereinafter filtering pipeline.

The driver module is a driver module in compliance with the OpenVG OpenVG Driver 2D standard per se known having standard interface tasks and configured to receive commands from programs for example Application Programming Interface API running on the central processing unit and to translate said commands into specialized commands for the graphics pipeline and or the filtering pipeline .

The pieces of information which can be generated by the driver module comprise a reference 2D geometric entity primitive referred to as a path hereinafter simply path a context of a scene to be rendered hereinafter simply context particularly the context organization reflects the one defined by the OpenVG standard a reference digital bitmap image of the VG Vector Graphics image type hereinafter simply VG bitmap image.

As it is known to those of ordinary skill in the art a path is a reference geometric entity of the 2D graphics which is meant as a set of commands of the plotting type to be provided to the 2D graphics pipeline to define the stroke of a 2D bidimensional primitive. Particularly a 2D scene can be defined as a set of VG bitmap images and paths to which one or more contexts are associated. Such set is sent to the graphics pipeline configured to compose or better render the 2D scene on the display screen . Each path exploits a logic mechanism of the plotting type which concretizes in plotting a stroke of the 2D primitive which is described by the path from a starting point to an endpoint.

To this aim it shall be further noticed that a path complying with the OpenVG standard comprises a first command or segment array data command or segment representative of the graphics or movement to be plotted and a second array of data representative of the X Y coordinates of the endpoint in which the graphics or movement ends and for some commands representative of one or more control points according to the particular command. It shall be noted that the starting point is to be considered as implicit at the first command it has coordinates equal to the conventional origin of the surface on which the graphics is to be plotted and for the successive commands it has from time to time revised coordinates and equal to that of the endpoint of the last performed command. The data of the second array are processed in parallel with the data of the first array according to the command defined therein.

The exemplary set of the main commands which can be indicated in a path comprises MOVE TO LINE TO QUAD BEZIER TO CUBIC BEZIER TO ARC TO. The data corresponding to the endpoint coordinates are to be associated to each command.

For example the path command MOVE TO data X Y implies a skip from the starting point or origin implicitly reached at the current stage of the computation for example with coordinates X Y to the endpoint with coordinates X and Y. The command MOVE TO involves a shift on the surface but it does not involve any stroke plotting on the same surface. The path command LINE TO data X Y involves plotting a line from the starting point for example the origin to the specified endpoint X Y the path command ARC TO data X X involves plotting a segment of arc from the starting point to the endpoint X Y .

For example the path command QUAD BEZIER TO data X Y X Y involves plotting a degree 2 Bezier curve exactly quadratic passing between the starting point and the endpoint X Y . The datum X Y represents the control point and it allows defining for example the particular shape of the Bezier curve to be plotted.

Referring back to the pieces of information provided by the driver module by context is meant a set of instructions and or pieces of information provided by the OpenVG 2D graphics application for the rendering of a scene typically intended to the 2D graphics pipeline. Some instructions typically included in a 2D context are for example instructions intended to the processing module path i.e. path fill path stroke width type of perspective transformation to be associated to the processing path module paint type anti aliasing type type of associated VG bitmap image type of blending equation and so on.

Finally the piece of information of the VG bitmap image type by which is meant a set of adjacent pixels each having a given color also results to be generable by the driver module . The bitmap image is such as to be received in input by the 2D graphics pipeline and to be plotted rendered directly on the screen following a mapping operation optionally a perspective one.

Referring back to the graphics module of it shall be noted that the graphics pipeline is so configured as to receive from the driver module pieces of information such as path context and VG bitmap images and a further DRAW PATH or DRAW IMAGE command which indicates to the same pipeline whether the entity to be processed is a path or a VG bitmap image.

Instead the filtering pipeline is so configured as to receive from the driver module only context and VG bitmap images. Unlike the graphics pipeline therefore the filtering pipeline is not arranged to receive in input geometric entities of the path type.

It shall be pointed out that as it will be reaffirmed also herein below the 2D graphics pipeline is internally configured to process path type entities and not VG bitmap images therefore in the case that the entity to be rendered is exactly a VG bitmap image the driver module is configured to transform the VG bitmap image into an equivalent path. Particularly the VG bitmap image is preferably transformed into four commands particularly of the LINE TO type the path of which will represent exactly the outer edge stroke of the VG bitmap image to be plotted.

This transformation which can be performed by the driver module advantageously allows a user not having to necessarily provide a path corresponding to the VG bitmap image but to be able to directly provide bitmap images to the graphics module by preferably prearranging only one driver module both for the graphics pipeline prearranged to accept both path and VG bitmap images and for the filtering pipeline of the graphics module prearranged to accept only VG bitmap images .

The graphics pipeline comprises a path stage PS a rasterizer module RM a first processing module binner a second processing module parser a scene buffer a fragment processor FP a macro block memory module OnChip memory OCM a frame buffer e.g. of the display .

The path stage per se known to those skilled in the 2D graphics art is so configured as to receive in input an input path P from the driver module shown for the sake of clarity also in and to provide a simplified output path P to the rasterizer module . The input path P results to be a so called high level path since it comprises all the possible commands described before which a path can define. The output path P results to be a so called low level path and as stated simplified compared to the input path P since it comprises only commands of the MOVE TO or LINE TO type. The simplified path P is usually also referred to as edge hereinafter also simply EDGE.

It shall be noted that preferably the path stage is in turn a micro pipeline comprising a series of processing modules not shown in each of which is configured to concur to the generation of the simplified output path P starting from the input path P according to the context provided by the driver module .

For example the path stage comprises a per se known tessellator module so configured as to transform the input path P into the output path P . The output path P also comprises a series of commands typically implicit of the plotting type only LINE TO MOVE TO with the data being associated to data representative of surface or screen coordinates. By surface coordinates is meant coordinates which can be mapped directly into pixels on the screen.

It shall be noted that the path stage is so configured as to process the input path P as a function of the instructions included in the context provided by the driver module for example a path fill instruction or a path stroke width instruction. Both the instructions indicated above are well known to those of ordinary skill in the field.

Particularly if the context comprises the path fill instruction the path stage results to be prearranged to provide the output path P to the rasterizer module as generated by the tessellator module since the path fill operation is performed by the rasterizer module . Instead in the case where the context comprises the path stroke width instruction the path stage results to be intended to perform a path P width operation on the output path P generated by the tessellator module by means of convolution and width operations on the basis of a piece of information about the width provided by the context in combination with the path stroke width operation. In this scenery the path stage results to be arranged to provide a further output path P to the rasterizer module as a result of the output path P width.

Therefore the path stage according to the instructions contained in the context results to be configured to provide the stroke type P or P on which the fill operation is to be performed to the rasterizer module . Furthermore the path stage results to be arranged to carry out for example a path projection operation on the final screen through a transformation matrix.

The rasterizer module is a 2D AET Active Edge Table Rasteriser rasterization module per se known which results to be operatively associated to the path stage and so configured as to receive therefrom the simplified output path P or the further output path P EDGE in surface or display coordinates and to provide in output generally more low level graphics entities of the span S type hereinafter simply referred to as spans.

As it is known to those of ordinary skill in 2D graphics by span is meant a set of horizontally adjacent fragments of the screen having the same coverage compared to the simplified path P or P in input from the rasterizer module . By fragment is meant a set of pixel pieces of information comprising a set of attributes for each pixel such as for example color and coordinate values. By coverage is meant the percentage of fragment overlap compared to the simplified path P or P . The coverage value or coverage is defined as a number ranging between 0 and 1.

A fragment completely included within the path has a total overlap relative to it therefore a coverage percentage of 100 by definition coverage value 1 . Instead a fragment which is at the level of the path P or P stroke has compared to it a partial overlap therefore a coverage percentage below 100 by definition coverage value

With reference to an example of span generation by the rasterizer module will be now described. A display screen SCH for example the display of the television apparatus is illustrated as being divided into a plurality of fragments F. The rasterizer module is so configured as to generate a plurality of spans by grouping adjacent fragments having the same coverage value on the basis of the assessment of how many fragments are partially or completely overlapped to a simplified path P P received from the path module . In the example of the simplified path is an ellipse typically described at a high level as a path P consisting in two commands of the arc type . It is reaffirmed that the rasterizer module is not configured to receive in input an ellipse as such represented directly by the path P but a simplified path P EDGE i.e. a set of rectilinear segments representative of an approximation of the ellipse.

The spans which can be generated by the rasterizer module can be of two types internal span i.e. a set of mutually adjacent fragments internally overlapped to the ellipse coverage value equal to 1 border span i.e. a set of adjacent fragments partially overlapped to the ellipse same coverage value less than 1 . It is pointed out that in the case of an elliptical shaped path it is very unlikely that border spans comprising more than an individual fragment are generated.

In the example of six internal spans can be identified si comprising 7 fragments si comprising 13 fragments si comprising 16 fragments si comprising 16 fragments si comprising 13 fragments si comprising 8 fragments and forty three border spans some of them being indicated with the reference sb each comprising an individual fragment.

The rasterizer module is arranged to define the span type primitive through a data set comprising a first datum YLINEA representative of the screen line to which the span belongs a second datum XSTART representative of the column in which the first span fragment is located a third datum SIZE width representative of the span size in terms of the number of adjacent fragments starting from the second datum XSTART. With reference to the first internal span si of it results to be defined by the rasterizer module with the data set YLINEA 3 XSTART 9 SIZE 7.

Again with reference to the first processing module is so configured as to clip the span type input primitive received from the rasterizer module into sub span type primitives each of which is associated with a macro block of the display screen SCH.

Particularly the first processing module is arranged to know from the context provided by the 2D graphics application a piece of information representative of the size of each macro block into which the display screen on which the scene is to be rendered is able to be clipped.

By definition a macro block is a screen portion having size N M where each of N and M preferably powers of two represents a number of pixels preset by the context of the 2D graphics application. The N M macro block size is to be considered as fixed since it is a static characteristic of the end hardware architecture graphics system to which the graphics module is intended.

Contextually to the span type input primitives and the size of a macro block the binner module is so configured as to receive a piece of information relative only to the sub context of the fragment processor .

The first processing module results to be configured to store in the memory buffer the pieces of information relative to the sub span type primitives and the relative sub context on the basis of the acquired size of the individual macro block according to an organization of the memory area corresponding to the memory buffer defined by a specific data structure which will be discussed herein below.

Particularly the first processing module once the piece of information indicative of the size N M of the individual macro block has been acquired is so configured as to generate a data structure of the display list type associated to each macro block of the scene to be rendered such as to organize the data storage within the scene buffer in a compact manner therefore in a particularly advantageous manner.

An example of a list type data structure indicated with the reference LST is shown in . The list type data structure LST is preferably a dynamic array of the scene buffer comprising an array of display list headers DLH and a plurality of display lists DL arrays. Each display list array of the plurality DL is organized in mutually concatenated memory portions or chunks of a fixed size.

Each element of the array of display list headers DLH represents an address of a memory portion of the scene buffer in which the first portion of the display list DL is included.

The array of display list headers DLH is typically allocated in an initial portion of the memory area corresponding to the scene buffer . The number of elements D of the header array representative of the length of the array of display list header DLH is computed by the first processing module by implementing the following relationship ceiling ceiling 1.0 

As defined by the relationship 1.0 the value D is as a function of the dimensions of the individual macro block N M and the resolution of the display screen W H . It shall be noted that the screen resolution W H is to be intended as the current resolution of the screen at the moment when the first processing module implements the relationship 1.0. In fact the screen resolution could vary in accordance with the rendering surface associated to the graphics pipeline in particular moments of the computation. As regards the computation as such it is pointed out that the command ceiling represents a rounding up to the nearest higher integer compared to the division operation indicated in brackets.

By way of example by supposing that the macro block has a fixed size equal to 64 32 and the graphics pipeline is configured to render a scene on a screen having a current size equal to 800 600 the number of elements of the array of display list header array therefore also the display list number is equal to D ceiling 800 64 ceiling 600 32 13 19 247.

As regards an individual display list each portion of a display list comprises a fixed number of list elements DLE in the example of equal to 10 and a pointer NC to the memory address of the scene buffer in which the display list portion of the same display list is allocated. The first processing module is so configured as to associate the newly generated display list portion to the pointer NC of a display list portion preceding the memory address of the scene buffer in which it is allocated. This type of organization is dynamic since advantageously in the case where a display list DL is complete the first processing module is so configured as to generate a new display list portion to be successively concatenated to the last generated display list portion.

This organization of the scene buffer into concatenated display list portions allows the first processing module to efficiently store display lists since it is possible to load the display lists from an external memory not shown in the Figures into a local buffer scene buffer .

A display list element DLE is for example a 32 bit data structure in which the most significant 4 bits are representative of an operative code to a maximum of 16 different operative codes definable while the remaining 28 bits are representative of semantics in accordance with the operative code which they are associated to.

It shall be noted that the type of operative code discriminates the type of display list element. For example in the case where the operative code is a pointer to a memory address in which a given context which had been previously stored is allocated the remaining 28 bits are used to store the above mentioned memory address. According to another example the operative code can indicate a sub span type primitive clipped span and the remaining 28 bits are used to store data relative to the sub span. Another example of an operative code can be relative to the encoding of a per se known macro block masking operation. In this case the remaining 28 bits indicate the type of masking operation. Other examples of operative code can be memory buffer or macro block clearing operations. In this case the 28 bits indicate the relative memory area to be cleared.

Furthermore the first processing module is configured following the generation of the data structure of the display list type to store a sub context associated to the instruction DRAW which it can receive from the graphics application through the driver module .

It shall be noted that the very sub context to be stored in the scene buffer is the one which can be associated to the individual fragment processor .

Furthermore it shall be considered that since a same sub context can be shared by different span type input primitives it is stored in the scene buffer only once and it is associated to each span type primitive by using a respective display list element of the display list structure comprising a pointing operative code and an address of the scene buffer memory area in which the shared sub context is allocated.

It shall be further noticed that the sub context associated to the fragment processor is provided by the OpenVG specifics therefore the maximum size thereof is a piece of information known a priori to the 2D graphics pipeline.

Referring back to the first processing module it comprises a first local write memory buffer to locally store the sub context.

The first processing module is advantageously configured to locally store in a compact representation thereof the sub context in the first local write memory buffer and subsequently once the sub context has been locally acquired to transfer and store the sub context in the scene buffer through an individual access to an external memory. The use of the local write memory buffer is advantageous since the context size is not known a priori.

It shall be noted that the size of the compacted sub context may vary as a function of the values of the same context. In fact as it is known in the OpenVG standard a path or a VG bitmap image can be rendered with the addition of several options such as for example the definition of a specific image for a particular primitive.

Contextually the first processing module is arranged to store a memory address in an internal register of its own not shown in the Figures which is representative of the scene buffer memory area in which the sub context is stored. Furthermore the first processing module is configured to associate this address to each span which it will receive from the rasterizer module.

In addition it shall be noted that the first processing module is intended to first acquire the sub context and next the span type primitives. This advantageously allows to the first processing module associating the reference sub context to each span type input primitive and storing this piece of information in each of the display lists of each macro block intersecting the span type input primitive.

It is reaffirmed that the first processing module is so configured as to receive from the rasterizer module the span type input primitives generated in accordance with the path type primitive to be rendered. Particularly such span type input primitives are sent to the first processing module according to an increasing line order from the i th line to the i 1 th line .

With reference now to it shall be considered for example a portion of the display screen SCH divided into eight macro blocks M M each of which is of size 4 4. It is reaffirmed that the size of the individual macro blocks is fixed since it is defined a priori at the system level and it is expressed in numbers of fragments.

The first processing module is so configured as to conventionally associate the coordinates 0 0 at the lower left hand corner of the screen SCH portion and to associate to each line of screen fragments a progressive reference numeral starting from the bottom line 0 . . . line 4 line 5 line 6 . . . and to each column a progressive index starting from the left . . . 6 7 . . . 11 12 . . . .

Upon receiving the span type input primitive S the first processing module is so configured as to clip the span type input primitive S into one or more sub span type primitives hereinafter for the sake of briefness simply sub spans in accordance to the relevant macro blocks which the span type input primitive overlaps.

By definition a sub span type primitive is a portion of a span type primitive univocally associated to one and only one macro block of the display screen and the pieces of information referred thereto are inserted within the display list structure associated to such macro block.

With reference to since the span type input primitive s overlaps a first macro block M a second macro block M and a third macro block M the first processing module results to be adapted to clip the input span S into a first sub span SP defined within the first macro block M a second sub span SP defined within the second macro block M and a third sub span SP defined within the third macro block M.

Consequently the first processing module is so configured as to store the pieces of information relative to the first sub span SP within the display list data structure associated to the first macro block M the pieces of information relative to the second sub span SP within the display list data structure associated to the second macro block M the pieces of information relative to the third sub span SP within the display list data structure associated to the third macro block M. The operations implemented by the first processing module to organize the display list data structure so as to store the sub spans will be described herein below.

Furthermore the first processing module is arranged to store in each display list data structure associated to the respective macro block before the storing of the pieces of information of the corresponding sub span also a reference pointer or memory address to the compacted sub context of the fragment processor .

As regards the storing of a sub span within the respective display list data structure it shall be considered that a sub span represents a display list element. Particularly the 28 bits dedicated to the data of the display list element in the case of sub spans can be organized for example as follows 

28 s bits dedicated to store a sub span offset value. By sub span offset is meant the distance in terms of the fragment number of the first fragment of the sub span from the relative origin of the individual macro block conventionally the fragment at the higher left hand corner of the macro block .

With reference again to the example of it is pointed out that the XSTART YLINEA and SIZE data set of the span type input primitive S are indicated with reference to the coordinates of the whole screen. Thereby it follows that being XSTART equal to 6 YLINEA equal to 6 and SIZE equal to 7 the input span S has a starting point of screen coordinates 6 6 and an endpoint of screen coordinates 12 6 . It is reaffirmed that conventionally the origin of the coordinate system is the lower left hand corner.

On the basis of these pieces of information the first processing module is so configured as to compute an identifier IDP of the screen macro block which includes the starting point of the span S and an identifier IDA of the screen macro block including the endpoint of the span S by implementing the following relationship ID 1.1 

in which ID represents the identifier to be computed N M represent the macro block dimensions X Y are the coordinates of the starting or endpoint of the span the containing macro block identifier of which is to be computed NML is the number of macro blocks per line in the example of equal to 4 .

In the example of the identifier IDI of the macro block having size 4 4 including the starting point with coordinates 6 6 of the span S is computed by implementing the relationship 1.1 as follows 

The identifier IDF of the macro block including the endpoint with coordinates 12 6 of the span S is calculated by implementing the relationship 1.1 as follows 

Once the identifier of the macro block M which includes the starting point of the span S and the identifier of the macro block M which includes the endpoint of the span S have been calculated the first processing module knows all the macro blocks which include the input span S in the example of the macro blocks M M and M .

The first processing module is arranged to organize the scene buffer according to a display list type data structure associated to each of the above mentioned macro blocks. Particularly the pieces of information relative to the memory address in which the sub context is stored and relative to the sub spans are stored in the display lists which start from the macro block including the span S starting point and which end at the macro block including the span S endpoint. Furthermore for each sub span in which the input span S is divided the display list data structure will have to be filled with list elements representative of the size value and the offset value of the corresponding relevant sub span.

Therefore it shall be observed that for each macro block to which the input span S is overlapped the first processing module is so configured as to create and store a sub span in the display list data structure associated to a macro block intersected by the input span S.

To the purpose of the computation thereof the first processing module is arranged to implement the following relationships offset start 1.2 in the case where the macro block identifier ID is the same as the identifier IDI of the macro block including the input span starting point in the opposite case the value 0 is assigned to the offset value offsetEnd end 1.3 in the case where the macro block identifier ID is the same as the macro block identifier IDF including the input span endpoint in the opposite case the value N 1 is assigned to the offsetEnd value. The offsetEnd value indicates the sub span last fragment calculated in fragment numbers starting from the origin of the individual macro block size offsetEnd offset 1 1.4 

In the relationships 1.2 and 1.3 N and M are the dimensions of the individual macro block Xstart is the coordinate X of the input span starting point Xend is the coordinate X of the input span endpoint the symbol indicates the remainder of the internal division.

In the example of what has been indicated herein below is achieved by applying the relationships 1.2 1.3 and 1.4 

In the case where the input span S is a so called border span the respective of coverage is added at the bottom of the display list following the pieces of information relative to the operative code the offset value and the size value of the sub span. Therefore a border span requires at least 64 bits of information to be stored. Instead in the case of an internal span it only requires 32 bits of information as already stated before since as it is an internal span the coverage value thereof is implicitly defined as equal to 1.

The first processing module by implementing the relationships 1.2 1.3 and 1.4 is so configured as to compute the data and to store in a compact manner all the input spans received in a sub span representation clipped span .

To the purposes of the present description the general compaction operation performed by the first processing module involves the input span clipping operation into sub spans and for each of them the computation of the offset value and the size value.

In a further embodiment of the disclosure the first processing module is so configured as to pre process some steps of a culling algorithm of sub span type primitives which is mainly implemented as it will be described in detail herein below by the second processing module . This pre processing is possible since the context set by the graphics application is already known at the level of the first processing module therefore it is possible to determine if an input span is of the occluded or occluding type. By definition a border span coverage value

In the case of an internal span coverage value 1 if particular setting conditions of the context are not contextually verified the internal span is to be considered as a non occluding span. Instead in the case that said conditions are verified the internal span is to be considered as of the occluding type.

The above mentioned conditions relative to the sub context of the fragment processor and relative to the span are preferably as follows 

coverage value of the span equal to 1 this condition confirms that no border span will be able to be considered as occluding .

If the above mentioned conditions are verified the span is marked as occluding for example by using one of the 16 operative codes available in the display list data.

In practice a span can be marked as occluding only in the case where the color of a span fragment completely overwrites any other colors previously stored in the internal frame buffer.

The marking as occluding or non occluding of a span advantageously allows to the graphics pipeline once the command SHOW has been received from the graphics application processing what has been captured and stored in the scene buffer by the first processing module displaying only the occluding spans and not the occluded ones since they are hidden.

With reference now to the block diagram of a pre processing example of a culling algorithm by the first processing module is now schematically summarized.

The first processing module is configured to receive an input span step IN S and to control whether the received input span is occluding step OCC S . Particularly it is pointed out that at the moment of the storing of the sub context of the fragment processor in the scene buffer in the case where the two context conditions indicated before are verified blending equation set to VG BLEND SRC and Vgmasking a flag is also stored which is equal to the value TRUE to indicate that the span which is being processed could be an occluding span in the case the internal span condition is verified coverage value equal to 1 . The third condition is computed upon storing the span in the scene buffer.

In the case of an affirmative answer step OCC S the input span is marked as occluding step CS O and the first processing module is ready to receive the successive input span. On the contrary in the case of a negative answer the first processing module prepares itself for receiving a new input span.

With reference to the flow of operations implemented by the first processing module except for the operations relative to the pre processing of the culling algorithm is now schematically summarized.

The first processing module is so configured as to receive an input datum step N D and to control whether the input datum is a scene context sub context of the fragment processor or an input span step CON S .

In the case where the input datum is a context the first processing module is intended to store the context in the first local write buffer step SC L and then in the scene buffer step SC B . Then the first processing module is so configured as to store the address of the memory area in which the context is stored step SC R in a special register. As a final operation it is also controlled whether the context provides for the enabling of the culling algorithm step EN OC before returning to process the successive input datum step N D .

Instead in the case where the input datum is a span type primitive the first processing module is so configured as to clip the input span into sub span type primitives in accordance with the macro blocks of the display screen which are overlapped by the input span block CP S . Then a control is performed to determine whether or not a sub span is to be stored in the scene buffer block CHK I . In the case where the sub span is not to be stored then the first processing module prepares itself for receiving a successive input datum block IN D . In the case where the sub span is to be stored then the first processing module proceeds to calculate the sub span offset value and size value by implementing the relationships 1.2 1.4 block CL OD . The offset and size values are inserted in the display list of the macro block in which the sub span is included contextually to the memory address in which the previously processed sub context block CON DL is stored. Then if the sub span flag is equal to the value TRUE and the sub span has a coverage value equal to 1 then the sub span is marked as an occluding sub span block MS O . Next the sub span is inserted in the respective display list block IS DL and the first processing module prepares itself for receiving the successive input datum block CHK I block IN D .

Again with reference to the second processing module results to be operatively associated to the scene buffer to share upon reading what has been written by the first processing module . It shall be noted that the first and the second processing modules also share per se known synchronism signals SC.

Particularly the first processing module is so configured as to capture the data relative to the context or sub context of the scene to be rendered and the data relative to the span type primitives as received from the rasterizer module and to store them in a compact representation sub span associated to respective macro blocks of the screen .

The second processing module is so configured as to perform the opposite or dual role relative to that of the first processing module . Particularly reading the data stored in the scene buffer and proceeding according to a given order for the macro blocks to re set the sub context of the fragment processor and to identify the spans stored therein.

Furthermore the second processing module is advantageously configured to implement an occluded primitive culling algorithm in order to reduce as it will be also reaffirmed herein below the working load of the fragment processor.

It shall be noted that the data processing by the second processing module begins when the graphics application through the driver module provides the command to show the rendered scene command SHOW on the screen to the graphics pipeline . Contextually to the command SHOW further commands can be provided as provided for by the OpenVG standard which indicate to proceed with the empty of the graphics pipeline processing of the data stored within the scene buffer .

It shall be noted that as it is known a sort middle graphics pipeline is configured for a real processing of the data of the previously captured scene only upon reception of one of the above mentioned commands from the graphics application.

It shall be further considered that since each macro block into which the display screen can be clipped is independent from the other macro blocks the modules of the graphics pipeline downstream the first processing module for example the second processing module the fragment processor the macro block memory module are advantageously configured to operate in parallel.

Referring back to the second processing module it comprises a second local write buffer to store the i th display list corresponding to the i th macro block read and withdrawn from the scene memory buffer by the second processing module .

It shall be noted that advantageously in an alternative embodiment it is possible to store a display list portion associated to the macro block in the second local write buffer thereby enhancing the performance of the graphics pipeline .

The second processing module is further configured to load a current context of a macro block region being processed by further external memory buffers relative to the second processing module for example an alpha mask buffer and a frame buffer in the macro block memory module .

It shall be noted that in the above mentioned further external buffers data useful for the representation of the macro blocks could be stored such as for example background images previously processed by the filtering pipeline . In fact typically the graphics module is advantageously prearranged to load the data processed by the filtering pipeline before the graphics pipeline proceeds to render the scene.

It shall be further considered that for example in the case where a per se known super resolution based anti aliasing algorithm is used by the graphics application the macro block memory module inside the graphics pipeline is considered under super sampled resolution.

It is recalled that an anti aliasing algorithm allows improving the displaying of the strokes of a scene so that the same strokes are as shaded as possible and are not hatched. This is typically achieved by increasing the screen resolution during the processing of the data to be rendered. For example this resolution increase can be equal to four times the screen resolution. In this case the frame buffer has not the same resolution of the screen but it is arranged to operate under super resolution. Therefore the scene is rendered with reference to a larger screen frame buffer under super resolution and to the command show scene SHOW by the graphics application each screen pixel original resolution 1 will have a color given by the average of the color of four pixels spatially organized in a 2 2 grid of the frame buffer super resolution 4 . Therefore the strokes of a scene will result to be shaded and not hatched de facto increasing the quality of the scene displayed on the screen.

In the case that the anti aliasing algorithm is enabled a per se known up sample filter which is achieved by replicating the pixel color is adopted when loading the data from the frame buffer. The application of the up sample filter is necessary since the data loaded from an external buffer always refer to the original resolution 1 as large as the screen while internally the internal macro block memory module of the OnChip type refers to a super resolution for example quadruple or 4 . Therefore the up sample filter is arranged to replicate the color of one pixel loaded from an external buffer in four adjacent pixels of the internal memory module of the OnChip type.

Instead in the case that the alpha masking function is disabled or the alpha mask buffer is not used the loading of macro blocks with alpha mask could be omitted.

Again in the case for example that a first instruction contained in the display list of a macro block is full color clear the loading of pieces of information from the external buffer can be omitted since they will be in any event covered by this color.

The second processing module is further configured to implement a culling algorithm of the primitives of the occluded span type stored within the display list being processed and relative to the loaded macro block.

The second processing module is simply intended as a filter adapted to determine whether the span is of the occluded type or not. To this aim the second processing module advantageously comprises a local bitmask buffer having preferably size of N M i.e. equal to that of each macro block. The local bitmask buffer is a one bit buffer that i.e. at the beginning of the current macro block processing is initially supposed to be equal to zero.

The second processing module is so configured as to process the display list in an inverse order since due to the manner in which the display list has been written by the first processing module the rule according to which the last span written in the display list is such as to overwrite all the preceding spans is to be considered as valid. Therefore the second processing module is arranged to process the display list relative to an individual macro block starting from the last display list element stored in the scene buffer and ending with the first element stored therein.

With reference to the block diagram of it is reaffirmed that the local bitmask buffer is set to zero block BIM .

The second processing module is so configured as to receive in input an input span read by the macro block display list being processed block IN SD and to control whether the input span results to be completely occluded or not block S FO . Particularly the second processing module is adapted to verify whether all the bits of the local bitmask buffer which overlap the span under processing in accordance with the respective offset and size values thereof read by the display list are all set for example to the value of 1.

It shall be noted that the condition of bits of the local bitmask buffer set to 1 implies that an occluding type span has been read and pre processed by the display list. Considering that as specified before the data processing is performed in an inverse order the pre processed span that will be rendered in reality on the scene in front of the span which is being processed would have already been rendered as an occluding span therefore the span under processing is to be considered as occluded. It is reaffirmed that the second processing module manages to achieve this conclusion by implementing the culling algorithm since advantageously the local bitmask buffer is set to 1.

In the case where at least one bit of the local bitmask buffer which overlaps the span under processing is equal to 0 then the second processing module is such as to consider the span under processing as partially visible.

Instead in the case where all the bits of the local bitmask buffer which overlap the span under processing are equal to 0 then the second processing module is such as to consider the span under processing as completely visible.

In more detail in the case where the span is considered as completely occluded the second processing module is so configured as to mark the span under processing as SPAN NOT TO BE PROCESSED by modifying the operative code associated thereto block MS K to a given value and to continue the data rendering process by receiving the successive input span block IN DS .

In the case where the span under processing is considered as completely visible the second processing module is intended to control whether it is an occluding type span operative code representative of OCCLUDING SPAN block SP OC . In the affirmative case the second processing module is so configured as to revise to the value of 1 the bits of the local bitmask buffer which overlap the span under processing block UP BM .

In the final case in which the span under processing is considered as partially visible the second processing module is so configured as to control whether it is an occluding span block SP OC and in the affirmative case to consequently revise the local bitmask buffer block UP BM . In addition the second processing module is intended to perform a span shrinking operation in the case where only the span ends result to be occluded block SH SP . Such shrinking operation consists in the removal from the right most or left most bits representative of the ends when they are occluded i.e. they overlap a bit of the local bitmask buffer having a value equal to 1. In the case where such ends are of the occluded type and the span is partially occluding the second processing module is so configured as to revise the local bitmask buffer .

It is recalled that what has been hereto described with reference to the block diagram of relates to a first pre processing of the data withdrawn from a display list in a so called inverse order so as to advantageously allow marking all the completely occluded spans. Therefore the second processing module is configured to efficiently process the display list relative to each macro block of the screen by discarding all the spans having the SPAN NOT TO BE PROCESSED operative code contextually to the context associated thereto. This allows considerably reducing the computation times and the band.

In more detail after the pre processing of the culling algorithm of the occluded spans the second processing module is so configured as to perform the very processing of the loaded display list which can be therefore correctly read by following a natural order i.e. from the beginning to the end thereof.

Particularly when a display list element is read which has an operative code representative of a context such context is read by the scene buffer starting from the memory address stored in the 28 bit field of the display list element currently read pointer to the context .

It shall be noted that the reading of the context simply consists in setting the local context of the fragment processor by using as current values those read by the scene buffer .

Once the context has been set the second processing module is so configured as to read one or more display list elements representative of a sub span in the case of a sub internal span a 32 bit element is read in the case of sub border spans two elements are read 32 bits for the offset and size values and 32 bits for the coverage value .

Starting from said offset and size values and once the size of an individual macro block N M is known the second processing module is so configured as to compute the starting point Xstart Ystart and the endpoint Xend Yend coordinates of the span by implementing the following mathematic relationships start end blockOffset offset 1.5 start blockOffset offset 1.6 end start size 1.7 in which blockOffset 1.8 blockOffset 1.9 where i and j indicate the coordinates which individuate the general macro block under processing. The macro block 0 0 is considered as the macro block in the lower left hand corner of the frame buffer for example the display screen . The macro blocks i 0 internally come back into the lower line composed of M horizontal lines of the frame buffer while the macro blocks 0 j indicate the left most column composed of the first N vertical lines of the frame buffer .

In addition once the processing of a current macro block has been completed the second processing module is so configured as to provide the data relative to the macro block processing via the fragment processor and the macro block memory module to one or more frame buffers external to the graphics pipeline for example display alpha mask buffer and so on .

Particularly the positioning of the rasterizer module upstream the first processing module and the second processing module allows the graphics pipeline to process span type primitives by clipping them into sub span type primitives that can be associated to fixed portions macro blocks of the display screen. Due to the fact that each sub span by definition does not ever result to be larger than an individual macro block it is advantageously possible to implement an overdraw reduction factor since the implementation of the culling algorithm results to be simpler on such small entities.

Again the above mentioned order of the graphics pipeline modules further involves the advantages that the scene context to be stored in the scene buffer is in reality a sub context intended only to the fragment processor and therefore it is more compact than the total scene context intended to the whole graphics pipeline. In this manner it is possible to achieve a reduction of the reading writing band of the scene buffer.

Furthermore the processing of one macro block at a time advantageously allows maintaining the bandwidth confined within the graphics pipeline and in an internal memory module representing the macro block.

In addition the fact that the primitives spans exiting the rasterizer module are associated to the macro blocks advantageously implies that no particular operations of reconfiguration or modification hardware or software of the same rasterizer module are involved.

Again the technical characteristic relative to the compact representation of the data context and span type primitives according to a display list organization each associated to a macro block of the screen advantageously allows saving the internal write traffic from first processing module binner to scene buffer and reading traffic from scene buffer to second processing module parser band.

Furthermore the implementation of a culling algorithm on span type primitives advantageously allows increasing the efficiency of the culling test reducing the actual number of spans to be rendered and decreasing as much as possible from a computational point of view the processing times of the graphics pipeline and the write read band from both internal for example the memory dedicated to the macro block and external for example the frame buffer buffers to the graphics pipeline.

The various embodiments described above can be combined to provide further embodiments. Each of the characteristics described as belonging to a possible embodiment can be implemented independently from the other embodiments described. These and other changes can be made to the embodiments in light of the above detailed description. In general in the following claims the terms used should not be construed to limit the claims to the specific embodiments disclosed in the specification and the claims but should be construed to include all possible embodiments along with the full scope of equivalents to which such claims are entitled. Accordingly the claims are not limited by the disclosure.

