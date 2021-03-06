---

title: Broadcastings service system using mobile communication terminal
abstract: A system capable of receiving a television signal and telephone signal on a mobile communication terminal. In particular, the system is capable of displaying each television broadcast on a monitor of the mobile communication terminal by receiving the video and audio signal, decoding it, and outputting it to the monitor of the mobile communication terminal. In addition, the system can transmit an EPG (Electronic Program Guide) data corresponding to a subscriber request and a selected broadcasting program in real time.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=07945931&OS=07945931&RS=07945931
owner: LG Electronics Inc.
number: 07945931
owner_city: Seoul
owner_country: KR
publication_date: 20091208
---
The present application is a 37 C.F.R. 1.53 b continuation of U.S. patent application Ser. No. 09 617 036 filed Jul. 14 2000 now U.S. Pat. No. 7 634 794 which claims priority on Korean Patent Application No. 28811 1999 filed Jul. 16 1999 the entire contents of which are hereby incorporated by reference.

The present invention relates to a system which is capable of receiving a broadcasting signal and telephone signal and watching and listening it on a mobile communication terminal and in particular to a system which is capable of receiving a video signal and audio signal decoding it and displaying the decoded signal on the monitor of the mobile communication terminal.

Organic combination or link between the conventional personal mobile communication system and digital television system for maximizing advantages of the both systems are not accomplished. In addition in the digital television system various additional information with high quality images are only provided to digital television sets. In other words the conventional personal mobile communication system such as a cellular phone can not transmit and receive video audio and character information.

It is an object of the present invention to provide a broadcasting service system using a mobile communication terminal which is capable of watching television broadcasting on a mobile communication subscriber terminal when a mobile communication network subscriber wants to watch broadcasting the system is capable of recognizing and answering the subscriber request providing broadcasting information and controlling digital and analog broadcasting signals to transmit on the subscriber terminal through the mobile communication network.

The other object of the present invention is to provide a subscriber terminal when analog and digital moving picture broadcasting signals are converted according to signal standard of the mobile communication network which is capable of receiving and restoring the converted analog and digital moving picture information and outputting images and sounds.

The another object of the present invention is to provide a broadcasting signal selecting mean which is capable of selecting broadcasting information receiving and restoring the selected broadcasting signal in order to watch digital and analog television broadcasting.

The another object of the present invention is to provide a broadcasting service method using a mobile communication terminal which is capable of converting digital and analog broadcasting signals in real time according to a transmission standard of the mobile communication network transmitting the converted broadcasting signals through the mobile communication network watching the transmitted television signals on the subscriber terminal.

To achieve the objects the broadcasting service system using the mobile communication terminal includes a converting mean which receives a video and audio signal provided from the moving picture information and converts the video and audio signal and a transmitting mean which transmits the converted video and audio signal to a subscriber through a certain transmission line of the mobile communication network.

To achieve the objects of the present invention in order to receive broadcasting signals the mobile communication terminal includes a receiving mean which receives the digital video and audio data a decoding mean which decodes the received digital video and audio data and outputting mean which outputs the decoded video and audio signal.

To achieve the objects of the present invention the mobile communication subscriber terminal includes a broadcasting reception mean which receives the broadcasting signal as a moving picture information a communication process mean which receives restores a call signal provided to a subscriber and outputs it through the mobile communication network and coding outputs a transmitting call signal through the mobile communication network a decoding mean which restores the received broadcasting signal by the broadcasting reception mean an output mean which outputs the broadcasting signal restored by the decoding mean to a terminal to be watched a selecting mean which selects the broadcasting signal reception mode and mobile communication call mode.

To achieve the objects of the present invention the broadcasting service method using the mobile communication terminal includes a converting process which converts the broadcasting signal having the digital video and audio data into a data agreed with the signal and transmission standard of the mobile communication network and a transmission process which transmits the converted digital video and audio data to the subscriber through a certain transmission channel of the mobile communication network.

Herein the television broadcasting system is moving picture and audio information it may be an analog television broadcasting system digital television broadcasting system or other moving picture information.

The conventional analog broadcasting system includes a NTSC National Television System Committee a PAL Phase Alternation Line and a SECAM Sequenctial Couleur Avec Memoire broadcasting method which are commonly used.

And the conventional digital broadcasting system includes a ATSC Advanced Television Systems Committee method of America a DVB digital Video Broadcasting method of Europe and a digital broadcasting method of Japan. Herein the ATSC method of America adopts a MPEG2 Moving Picture Experts Group2 Dolby AC3 and 8VSB and DVB method of Europe adopts a MPEG2 Moving Picture Experts Group2 and an OFDM Orthogonal Frequency Division Multiplexing .

As described above in the digital television broadcasting system the video and audio signal are provided as a compressed digital data bit stream . Herein the compressed digital data has a protocol in relation to reception and transmission accordingly the digital broadcasting information agreed with the protocol includes the video and audio data and EPG Electronic Program Guide and additional data and are processed together.

In of the present invention processing of the digital video signal compressed as the MPEG2 Moving Picture Experts Group2 is described.

When the television broadcasting system is the digital television broadcasting system the video information provided to the digital television is a compressed encoded information as the MPEG2 Moving Picture Experts Group2 standard accordingly a format converter for converting the compressed encoded information into a MPEG4 Moving Picture Experts Group4 agreed with an image standard of the mobile communication network is included.

Meanwhile when the television broadcasting system is the analog television broadcasting system the television broadcasting system moving picture provider or the format converter can have a converting mean which converts the provided video information into a digital signal having a certain format agreed with the mobile communication network transmission standard.

The format converter is inputted the MPEG2 Moving Picture Experts Group2 videotex provided from the television broadcasting system and format converts the MPEG2 videotex into the MPEG4 Moving Picture Experts Group4 videotex agreed with the mobile communication network.

The format converter can convert the MPEG2 Moving Picture Experts Group2 videotex into H.26L H.263 or H.26X format. As far as the converted format agrees with the mobile communication network there is no limitation in the format.

The format converter exchanges the information needed in the format conversion with the television broadcasting system through a transmission line .

For example the bit rate of the digital television adapts high speed broadcasting band such as 19.236 Mbps of HD level or 6 Mbps of SD level.

However the data transmission rate of IMT 2000 is maximum 144 Kbps or 2 Mbps in case of a Pico Cell according to a Cell likewise on the mobile communication network which can process maximum 2 Mbps two way signal transmitting the digital television signal directly to a cellular phone or PCS is impossible due to the distinctive character of the mobile communication network.

Therefore the format converting process which converts the MPEG2 digital television signal into the signal agreed with the mobile communication network such as the MPEG4 Moving Picture Experts Group4 is required the format converter performs transcoding of the video and audio data formats and converts the EPG and additional information of the digital television information to make the signals agree with the mobile communication network.

The converted digital video and audio data information are provided to a MTSO System Controller and Switch through a transmission line . The MTSO provides a signal for answering a request from a subscriber to the format converter through a transmission line allots the digital video and audio information to a certain channel of the mobile communication network and transmits the digital information as a RF frequency to a subscriber terminal through a base station.

As described above the video and audio signal of the television broadcasting system are converted into the signal agreed with the mobile communication network and are transmitted to the subscriber terminal . Accordingly it is possible to watch the television broadcasting on the subscriber terminal cellular phone PCS IMT 2000 terminal .

When a moving picture information is the digital television broadcasting system a television reception unit receives the additional information including the digital video audio information and the EPG Electronic Program Guide data agreed with the digital television broadcasting system and transmits the MPEG2 Moving Picture Experts Group2 signal to a transcoder . The television reception unit abstracts the EPG electronic Program Guide data and transmits it to a EPG converting unit and abstracts the additional data and transmits it to a additional data converting unit .

The transcoder converts the inputted MPEG2 Moving Picture Experts Group2 digital video and audio data into the MPEG4 Moving Picture Experts Group4 digital video and audio data and transmits it to a channel multiplexer .

As the digital video data transmission medium are diversified and the characters of each medium are different accordingly there is a need to make bit rate and converting method of the digital image agree with the medium character during the transmission.

In particular the system of the present invention provides the digital television broadcasting signal to the mobile communication terminal such as the cellular phone or PCS through the mobile communication network accordingly transcoding for converting the compressed bit is adapted in order to transmit the digital video data to the medium having different band.

The additional data converting unit decodes the inputted MPEG2 additional data into the MPEG4 additional data.

The channel multiplexer puts the MPEG4 video and audio data provided from the transcoder on a certain allotted channel at the same time puts the EPG data outputted from the EPG converting unit and the additional data outputted from the additional data converting unit on a certain allotted channel.

The MPEG4 Moving Picture Experts Group4 digital television video audio EPG electronic Program Guide and additional information converted in accordance with the character of the mobile communication network by passing through the above process are transmitted to the subscriber mobile communication terminal through a RF Radio Frequency reception unit .

Herein the RF reception unit is corresponding to the server MTSO or base station of the mobile communication network.

In SD level of the MPEG2 Moving Picture Experts Group2 6 Mbps band is required in HD level about 19 Mbps band is required when the MPEG2 is converted into the MPEG4 Moving Picture Experts Group4 moving picture can be transmitted as about 64 Kbps bit rate. Herein the moving picture can be transmitted by being allotted a part of the IMT 2000 band as a television broadcasting band.

Meanwhile when moving picture information is transmitted as a packet in order to transmit the moving picture information through exclusive broadcasting channel transmission line in consideration of the character of the mobile communication network a voice band is changeable on one base station in accordance with a subscriber telephone call quantity at this time television broadcasting information should not be taken all band accordingly a band controlling method for changeable band allotment is required.

When a BW video means moving picture including sound band for the digital television broadcasting and a BW audio means audio band for voice communication of the mobile communication terminal the size of the audio band changes from 0 to maximum BW audio in accordance with the voice telephone call quantity.

Accordingly the channel multiplexer provides voice telephone call quantity information to a transmission rate control unit in accordance with the voice telephone call quantity the transmission rate control unit controls encoding rate of the MPEG4 Moving Picture Experts Group4 of the transcoder by using the provided information from the channel multiplexer .

In addition as described above the digital television broadcasting can service not only the video and audio information but also additional information the additional information is provided to a subscriber through the additional information converting unit and channel multiplexer .

Herein a format converter for converting the signal inputted from the television broadcasting system into the signal agreeable to a mobile communication network includes an A V stream transcoder which receives an A V stream from the television broadcasting system and converts it into the format agreed with the mobile communication network an EPG converting processor which receives an EPG Electronic Program Guide stream from the television broadcasting system and converts it into the format agreed with the mobile communication network and a data service converting processor which receives a data stream from the television broadcasting system and converts it into the format agreed with the mobile communication network.

First the A V stream transcoder converts the MPEG2 Moving Picture Experts Group2 digital video including audio information into the MPEG4 Moving Picture Experts Group4 or H.26L H.263 H.26X format and provides it to the mobile communication network . Herein the converted digital video data can be provided to the subscriber in accordance with a subscriber request A V RQ of the mobile communication network .

The EPG converting processor converts the MPEG2 EPG stream inputted from the television broadcasting system into the signal agreed with the mobile communication network.

Herein format conversion in WAP wireless Application Protocol PSIP Program Stream Internet Protocol text is converted into HDML Handheld device Mark up Language or TTML Tagged Text Mark up Language . In format conversion in wireless data protocol the PSIP is converted into HDTP Handheld Device Transport Protocol or ITTP Intelligent Terminal Transfer Protocol .

As depicted in it illustrates an EPG analysis unit an EPG answering control unit a schedule data base and a protocol converter .

First the EPG analysis unit analysis the inputted EPG guide stream according to a encoded format abstracts information in relation to channel and schedule of broadcasting programs and stores the abstracted result on the schedule data base .

The schedule data base records and stores the inputted information from the EPG analysis unit on a memory and checks and outputs a certain information of the data base in accordance with a request from the EPG answering control unit .

The EPG answering control unit operates in accordance with the EPG answering request EPG RQ from the subscriber through the server MTSO searches the information corresponding to the subscriber request on the schedule data base and transmits it to the protocol converter .

The protocol converter converts the data inputted from the EPG answering control unit into a format agreed with the MTSO and outputs it to the MTSO for answering the subscriber request and being watched by the subscriber on the mobile communication terminal.

Meanwhile the service converting processor is inputted the additional information data stream from the television broadcasting system converts it into a format agreed with the mobile communication network and provides the information corresponding to the subscriber request Data RQ .

In other words the data service converting processor performs the bit rate and protocol conversion process which converts the digital television broadcasting contents into the contents format agreed with the mobile communication network.

For example the service information of the digital television broadcasting system is decoded by a MHEG 5 engine or XHTML browser and the decoded information is converted into the signal and format agreed with the mobile communication network.

Herein in the WAP conversion Carousel IP Datagram is converted into HDTP High definition transport Protocol and MHEG XHTML Multimedia and Hypermedia Expert Group XHyper Text Markup Language is converted into HDML Handheld Device Mark up Language .

As depicted in the digital broadcasting system using the mobile communication comprises a digital signal processing unit a medium storing unit a data processing converting unit and a transcoder transmission unit . Its operation will be described in detail.

The digital signal processing unit is a information program transmission unit which provides broadcasting program to the mobile communication network by receiving 19.2 Mbps HD level and 6 Mbps SD level multi channel digital television signal.

The digital signal processing unit selects the inputted digital television signal on a tuner demodulates the selected signal on a demodulating unit abstracts information in accordance with each broadcasting channel on a de multiplexer reproduces and outputs the video and audio signal as the original digital television broadcasting signal by a MPEG decoder .

Herein the MPEG TP de multiplexer abstracts the data regardless of the format for providing PSI Program System Information guide information and additional information.

The medium storing unit includes a MPEG recorder A a MPEG file input output unit B and a file filter C it is a file system to make a disk scheduling and disk data block size agree with the MPEG stream for storing digital television broadcasting signal maximum 30 Mbps level MPEG2 stream in real time. The medium storing unit stores a stream such as the MPEG4 itself and services it to the mobile communication network.

Herein a striping method is used to store the MPEG2 transmission stream transmitted from the digital television broadcasting signal reception unit as a consecutive block unit. The transcoder may support GOP unit I Frame Value on the file system in order to operate effectively a Bit Rate Drop Macro Block and Intra Inter compensation.

A data processing converting unit includes an EPG decoder a data decoder a presentation engine unit and a protocol converting unit . As described above the data processing converting unit abstracts and converts the EPG and additional information received from the digital television broadcasting for being used by a mobile communication terminal user.

The EPG decoder abstracts and decodes the EPG data inputted from the digital signal processing unit .

The presentation engine unit contents format converts the decoded EPG data and outputs it to the protocol converting unit .

Herein as described above the format conversion in the WAP Wireless Application Protocol PSIP Program Stream Internet Protocol text is converted into HDML Handheld Device Mark up Language or TTML Tagged Text Mark up Language and in the wireless data protocol PSIP Program Stream Internet Protocol is converted into HDTP Handheld Device Transport Protocol ITTP Intelligent terminal Transfer Protocol .

In addition the presentation engine unit contents format converts the decoded additional service information and outputs it to the protocol converting unit .

Herein in wireless internet WAP converting Carousel IP Datagram agrees with HDTP and MHEG XHTML agrees with HDML.

The protocol converting unit converts the additional information including the format converted EPG data into a protocol agreed with the mobile communication network and outputs it.

The transcoder converts the digital video including audio broadcasting signal inputted from the digital signal processing unit into the signal agreed with the mobile communication network. For example it can convert the MPEG2 into the MPEG4 and provides the converted digital video and audio data to a wireless stream processing unit in accordance with transmission control of a transmission rate control unit .

The medium storing unit data processing converting unit and transcoder transmission unit are same in description of the parts are abridged.

The analog signal processing unit includes an analog broadcasting signal reception unit an analog digital converting unit a MPEG4 encoder and a VBI abstraction unit . Herein the analog signal processing unit is information program transmission unit for receiving the analog television signal and providing the broadcasting program to the mobile communication network.

In addition the analog signal processing unit includes an analog broadcasting reception unit which receives and restores the analog television signal an analog digital converting unit which converts the restored analog broadcasting signal including moving picture and audio information into a digital data a MPEG4 encoder which converts the converted digital data into MPEG4 Moving Picture Experts Group4 format and outputs it to the transcoder transmission unit and the VBI abstraction unit which abstracts the EPG Electronic Program Guide data and additional data on the VBI section and provides it separately to the EPG decoder and the additional data decoder .

Accordingly when the moving picture information is the analog television broadcasting signal broadcasting service using the mobile communication is possible.

As depicted in when H.26L H.263 H.26X are the digital video and audio data formats agreed with the mobile communication network a construction of a circuit and algorithm for converting these formats is possible.

As described above in order to transmit television broadcasting signal by using a wireless communication network in real time the television broadcasting signal has to agree with the character of the wireless communication network. In other words transcoding has to be performed between the different systems. Herein in order to prevent video image deterioration due to the transcoding a certain pertinent transcoding method can be selected between wide spread transcoding methods.

In addition not passing through the transcoding transmitting digital television broadcasting information is possible by using the digital compressed algorithm such as MPEG4 Moving Picture Expert Group4 or H.263.

The circuit of includes a decoder unit which is inputted the MPEG2 Moving Picture Experts Group2 bit stream and decodes it and encoder unit which encodes the decoded restoration digital video data into the MPEG4 Moving Picture Experts Group4 bit stream its operation will be described in detail.

First the decoded video data on a variable signal decoder of the decoder unit is converted into reverse quantization and IDCT Inverse Discrete Cosine Transform through a reverse quantization unit and IDCT Inverse Discrete Cosine Transform unit . The converted reverse quantization and IDCT are decoded perfectly by passing through motion compensation process of the output device including an adder a memory and a motion compensation unit .

The encoding unit encodes the restored digital video data according to quantization step which is different with the above decoding quantization step in the present invention the MPEG2 Moving Picture Experts Group2 is converted into the MPEG4 Moving Picture Experts Group4 quantization step of the encoder is lager than quantization step of the decoder the digital compressed video data coated with the MPEG4 is outputted.

In order to compress and process the digital video data the encoder unit discrete cosine converts the difference between inputted video and restored video outputted through an adder a DCT Discrete Cosine Transform unit outputs it a quantization unit makes the signal inputted from the DCT unit quantized a variable signal encoder converts the quantized signal into the MPEG4 bit stream and outputs it the outputted data from the quantization unit is restored through the reverse quantization unit and IDCT Inverse Discrete Cosine Transform unit the balance between the restored video data and the inputted video data of the adder is calculated by passing through the motion compensation process of the adder memory and a motion compensation unit the calculated balance is discrete cosine transformed and quantized.

Accordingly the transcoded data by the above process is inputted to a transmission rate control unit in B is controlled as transmission rate agreeable to the mobile communication network and is inputted to a wireless network stream processing unit .

Meanwhile a wireless network data protocol processing unit designates a data protocol agreeable to the mobile communication network such as a HDTP High Definition Transport Protocol or a ITTP Intelligent Terminal Transfer Protocol on the WAP Wireless Application Protocol to the EPG Electronic Program Guide data and additional data outputted from the protocol converting unit of the data processing converting unit .

When the mobile communication terminal requires a search for a certain broadcasting schedule by sending a key word such as an program title or an actor name the wireless network data protocol processing unit supports the data base of the presentation engine unit to search easily the program schedule or the program concept.

The medium synchronization control unit reconstructs the transcoded video and audio data by the transcoder and the converted data by the data processing converting unit and provides the data which does not require synchronization directly to the wireless stream processing unit .

In other words the medium synchronization control unit resynchronizes the lost synchronization information of the synchronized broadcasting data with the closest video and audio data through the transcoder .

As described above the reconstructed digital video audio and additional information agreed to the mobile communication network are inputted to the wireless stream processing unit .

The wireless stream processing unit transmits the moving picture and data to pertinent channel of the mobile communication network in real time performs channel allot or cancel in relation to the digital television signal transmission for answering request of the subscriber.

First a RF reception and transmission unit receives and transmits the base station communication signal received from an antenna and the signal for voice telephone call communication and receives the television broadcasting signal transmitted to pertinent call channel.

In the voice telephone call communication a voice encoding and decoding unit duplicates the received voice signal of the opponent caller received from the RF reception and transmission unit and outputs it to a voice processing unit .

The voice processing unit outputs the duplicated voice signal to a speaker SP encodes the duplicated voice signal through a microphone MIC of the subscriber and transmits it to the RF reception and transmission unit .

A video encoding and decoding unit performs a MPEG4 decoder function. In the preferred embodiment of the present invention the MPEG decoder is included in order to reproduce the transcoded MPEG4 Moving Picture Experts Group4 video data which is transmitted through the mobile communication network but a H.263 codec may be included in the IMT 2000 in accordance with circumstance of the mobile communication network.

Accordingly in order to process moving picture information as a format agreed with the mobile communication network various encoding standard codec can be included.

In the television broadcasting reception mode the video encoding and decoding unit receives the MPEG4 Moving Picture Experts Group4 digital video signal inputted from the RF reception and transmission unit restores it and outputs the restored television video signal to a monitor through a video processing unit .

In the mobile communication system having two way monitor communication function a camera transmits a signal having the photographed subscriber image by passing through the video processing unit video encoding and decoding unit and RF reception and transmission unit .

A processor having the voice telephone call mode and television reception mode controls the each construction unit in accordance with the mode reads information on a memory unit and stores information on the memory unit .

A key input unit has designated keys for the television reception with a key input function for telephone calls.

However as described above when the RF reception and transmission unit includes a TV tuner although the television signal is not converted into a signal agreed with the signal transmission standard of the mobile communication network the mobile communication terminal of the present invention can receive the analog or digital television broadcasting signal restores it and outputs it.

Herein in the subscriber mobile communication terminal which receives the analog television broadcasting signal the RF reception and transmission unit performs a tuner function which receives the analog television broadcasting signal from the antenna and selects it the voice processing unit processes the voice signal of the selected channel broadcasting signal of the RF reception and transmission unit hereinafter referred to tuner and the video processing unit processes the video signal of the selected channel broadcasting signal and outputs it to the monitor in order to display.

As described above the subscriber mobile communication terminal receiving the analog television broadcasting signal includes the antenna the tuner the video and audio processing unit in the video and audio encoding and decoding unit can be excluded. As for the antenna speaker and monitor of the above construction the antenna speaker and monitor of the conventional cellular phone PCS and IMT 2000 terminal can be used.

Meanwhile in the subscriber mobile communication terminal the RF reception and transmission unit tuner receives the digital television broadcasting signal from the antenna and selects it the voice decoding unit outputs the restored voice signal to the speaker SP the video decoding unit restores the video signal of the selected digital broadcasting signal and the video processing unit processes the restored video signal and outputs it to the monitor for displaying.

As described above the subscriber mobile communication terminal includes decoding mean which decodes the digital video and audio signal the antenna speaker and monitor of the conventional PCS cellular phone and IMT 2000 terminal can be used as it is.

In and operations will be described. The EPG data is transmitted to the subscriber for answering the subscriber request the format converted signal based on the EPG data is transmitted to the subscriber in accordance with the subscriber select program through the allotted channel.

At the same time a bill is demanded to the subscriber it is assumed the subscriber has right to watch the digital television broadcasting. It is also assumed a mobile communication company has a designated telephone number to handle subscriber requests and also performs key word certifying process for confirming the subscriber.

First when the mobile communication terminal subscriber wants to receive the digital television broadcasting through the subscribed mobile communication network the subscriber sets up the TV reception mode by using the key input unit and connects to the designated telephone number of the mobile communication company.

After the connection completion the subscriber is confirmed whether the certified subscriber having the right for receiving the digital television broadcasting by inputting the pass word.

When the subscriber is certified access is granted the pertinent channel for watching moving picture is allotted.

As an answer for the EPG data request the format converter provides the EPG data packet to the server MTSO. The server MTSO transmits the EPG data packet to the subscriber through the pertinent channel.

The EPG data packet received on the antenna is decoded on the video encoding and decoding unit through the video processing unit the decoded result shows on the monitor through the video processing unit . The subscriber answers it by searching the EPG data and selects a channel.

In order to make possible the subscriber search a web browser mean is provided on the terminal processor for searching the EPG and additional information.

The channel select information is inputted to the processor through the key input unit the processor coding controls the pertinent signal and transmits it to the server through the RF reception and transmission unit and antenna .

The server MTSO requires the video and audio data corresponding to the selected channel by the subscriber to the format converter the format converter outputs the video and audio data and transmits it to the subscriber through the mobile communication network.

In order to watch the television broadcasting by using the mobile communication network the transmitted television broadcasting signal is provided to the video encoding and decoding unit through the antenna and RF reception unit . As described above the video encoding and decoding unit performs the MPEG4 decoder function accordingly decodes outputs the video and audio to the monitor and speaker SP through the each processing unit .

Meanwhile after the subscriber certification the server can perform payment demand by using the subscriber certification key word such as an ID.

Herein the television broadcasting signal transmission to the certain channel changeable channel opened and continued between the server and subscriber is described but as described above it is also possible to perform the television system using the mobile communication of the present invention by allotting a certain channel for the television broadcasting.

As described above in detail the present invention is capable of watching moving picture by using the mobile communication network watching the television broadcasting by using the mobile communication terminal transmitting the EPG data for answering the subscriber request and providing the selected broadcasting program from the data to the subscriber in a real time.

In addition the subscriber can choose the television broadcasting and watch by using the mobile communication terminal such as the cellular phone PCS and IMT2000.

