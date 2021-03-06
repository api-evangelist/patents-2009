---

title: Communication quality monitoring device, communication system, communication quality monitoring method and program thereof
abstract: A packet transmission and quality monitoring device - which detects deterioration in communication quality based on a buffer length of a session control protocol includes a threshold value calculating unit - which calculates a threshold value for the determination of deterioration in communication quality according to a parameter related to congestion detection of the session control protocol, and a deterioration determining unit - which determines deterioration in communication quality by comparing the threshold value and the buffer length.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08929212&OS=08929212&RS=08929212
owner: NEC Corporation
number: 08929212
owner_city: Tokyo
owner_country: JP
publication_date: 20091218
---
This application is the National Phase of PCT JP2009 071109 filed Dec. 18 2009 which is based upon and claims the benefit of priority from Japanese patent application No. 2008 329558 filed on Dec. 25 2008 the disclosure of which is incorporated herein in its entirety by reference.

The present invention relates to a communication quality monitoring device a communication quality monitoring method and a program thereof and more particularly a communication quality monitoring device a communication quality monitoring method and a program thereof which enable detection of deterioration in communication by a session control protocol.

Related art is disclosed in for example Patent Literature 1 through 3 for detecting deterioration in a communication quality at a TCP Transmission Control Protocol level as a session control protocol in an IP Internet Protocol network.

Patent Literature 1 discloses a method of measuring traffic of TCP by a measuring device provided between a transmission terminal and a reception terminal calculating a logical throughput of the TCP from a network delay a packet loss rate or the like measured by the measuring device comparing the calculated logical throughput and an actual throughput and when the actual throughput is lower than the logical throughput determining that performance is deteriorated.

Patent Literature 2 discloses a method of determining that communication is deteriorated when the number of TCP retransmission time outs exceeds a threshold value according to a time and a procedure of a TCP packet.

Patent Literature 3 discloses a method of measuring a reciprocation delay time of a transmission terminal and a reception terminal and determining whether a response delay derives from a server terminal or a network based on three sensing results a drastic increase in a reciprocation delay time a slow increase of the same and a decrease in an advertisement window the amount of use of a reception buffer on reception side below a value set in advance.

Among related art for determining deterioration by a network repeater are for example the techniques disclosed in Patent Literature 4 and 5.

Patent Literature 4 discloses a traffic congestion symptom monitoring system which when traffic information the amount of use of a communication buffer in a network exceeds a predetermined threshold value notifies to that effect.

Patent Literature 5 discloses a device which monitors a dedicated line transmission queue and when the transmission queue overs a predetermined length determines that a flow of a transmission packet exceeds a dedicated line speed to distribute a part of packets to an ISDN line.

The methods disclosed by Patent Literature 1 and 2 have a problem that deterioration in communication quality cannot be determined in a section where no packet loss occurs. The problem could occur not only in communication using a packet but also in communication using data such as a cell or a frame.

The reason is that they are the determination methods premised on that communication quality deterioration is caused by generation of a packet loss. Even when no packet loss occurs communication quality might be deteriorated due to a narrow link bandwidth with respect to a data input rate or due to a decrease in a speed up rate in a session congestion control system under a large delay circumstance.

An object of the present invention is to provide a communication quality monitoring device a communication quality monitoring method and a program thereof which enable deterioration in communication quality in a session layer to be determined irrespectively of occurrence of a data loss.

According to a first exemplary aspect of the invention a communication quality monitoring device which detects deterioration in communication quality based on a buffer length of a session control protocol includes a threshold value calculating unit which calculates a threshold value for the determination of deterioration in communication quality according to a parameter related to congestion detection of the session control protocol and a deterioration determining unit which determines deterioration in communication quality by comparing the threshold value and the buffer length.

According to a second exemplary aspect of the invention a communication system including a communication device which executes communication by a session control protocol and a communication quality monitoring device which is connected to the communication device through a communication network to detect deterioration in communication quality based on a buffer length of the session control protocol wherein the communication quality monitoring device includes a threshold value calculating unit which calculates a threshold value for the determination of deterioration in communication quality according to a parameter related to congestion detection of the session control protocol and a deterioration determining unit which determines deterioration in communication quality by comparing the threshold value and the buffer length.

According to a third exemplary aspect of the invention a communication quality monitoring method of detecting deterioration in communication quality based on a buffer length of a session control protocol includes a threshold value calculating step of calculating a threshold value for the determination of deterioration in communication quality according to a parameter related to congestion detection of the session control protocol and a deterioration determining step of determining deterioration in communication quality by comparing the threshold value and the buffer length.

According to a fourth exemplary aspect of the invention a communication quality monitoring program to be executed on a computer device which detects deterioration in communication quality based on a buffer length of a session control protocol which causes the computer device to execute a threshold value calculating processing of calculating a threshold value for the determination of deterioration in communication quality according to a parameter related to congestion detection of the session control protocol and a deterioration determining processing of determining deterioration in communication quality by comparing the threshold value and the buffer length.

The present invention enables communication quality deterioration to be determined irrespectively of generation of a data loss by calculating a threshold value of a buffer length for the determination of deterioration according to a congestion state.

Next modes of implementation of the present invention will be described in detail with reference to the drawings.

With reference to a packet transmission and quality deterioration monitoring device as a communication device is connected to a packet reception device through a communication network . The packet transmission and quality deterioration monitoring device is a device which generates a packet by session control to monitor communication quality deterioration in session control. The packet reception device is a device which receives a packet subjected to session control by the packet transmission and quality deterioration monitoring device .

With reference to description will be made of an example of a structure of the packet transmission and quality deterioration monitoring device .

With reference to the packet transmission and quality deterioration monitoring device includes a buffer input unit a buffer unit a session control unit a packet transmission unit a buffer state monitoring unit a session state monitoring unit a state storage unit a threshold value calculating unit and a deterioration determining unit .

The buffer input unit is a part having a function of inputting data from an application or data received from another session to the buffer unit .

The session control unit is a part having a function of generating a packet with respect to data stored in the buffer unit based on session control. The session control includes congestion control.

The packet transmission unit is a part having a function of transmitting a generated packet to the packet reception device .

The buffer state monitoring unit is a part having a function of monitoring a buffer length of the buffer unit .

The session state monitoring unit is a part having a function of monitoring a session control parameter. Here the session control parameter includes a parameter related to congestion detection and a parameter related to speed control. Parameter related to congestion detection represents the number of retransmissions or the number of packet loss detections or a packet loss rate. Parameter related to speed control represents a communication rate or a window and a reciprocation delay time. Window indicates the volume of transfer per one reciprocation delay time. Communication rate can be obtained by dividing a window by a reciprocation delay time.

The state storage unit is a part having a function of storing a buffer length monitored by the buffer state monitoring unit and a session control parameter monitored by the session state monitoring unit .

The threshold value calculating unit is a part having a function of determining existence non existence of a congestion state based on a session control parameter older than an arbitrary time point t stored in the state storage unit and obtaining a threshold value of a buffer length for use in determining deterioration of communication quality by the deterioration determining unit based on existence non existence of the congestion state. Arbitrary time point t here is desirably a latest time point stored in the state storage unit .

The deterioration determining unit is a part having a function of comparing a buffer length at an arbitrary time point t stored in the state storage unit with a threshold value obtained by the threshold value calculating unit to determine deterioration of communication quality. The deterioration determining unit determines that quality is deteriorated when a buffer length is not less than a threshold value or overs the threshold value. As a buffer length to be compared an average value of buffer lengths in proximity to the time point t may be used among buffer lengths stored in the state storage unit .

With reference to the threshold value calculating unit includes a congestion state determination processing unit a congestion time threshold value calculation processing unit and a non congestion time threshold value calculation processing unit .

The congestion state determination processing unit executes processing of determining whether it is in a congestion state or not based on a parameter whose number is increased along congestion detection which is stored in the state storage unit . Determination of a congestion state is made based on whether the number of session control parameters is increased in an arbitrary time period from t d to t stored in the state storage unit .

Session control protocol whose control is dependent on a packet reciprocation delay time uses an arbitrary value larger enough than a packet reciprocation delay time as the time d in order to detect congestion at an interval larger than a control interval. When a measurement interval is larger enough than a packet reciprocation delay time of a session in question a value proportional to the measurement interval may be used as the time d. Among session control parameters which will be increased in number as congestion is detected are the number of packet losses recognized in a congestion control protocol and the number of retransmissions when the congestion control protocol has a retransmission mechanism.

The congestion time threshold value calculation processing unit executes processing of calculating a threshold value of a buffer length for the determination of deterioration hereinafter referred to as a deterioration determination threshold value by the deterioration determining unit when the congestion state determination processing unit determines the congestion state.

In the congestion state a throughput largely varies because control is executed to avoid congestion in session control. Even when the volume of input data is constant a variation range of a buffer length of the buffer unit will be large. Accordingly the congestion time threshold value calculation processing unit obtains a deterioration determination threshold value according to a variation of the buffer length of the buffer unit .

Among methods of calculating a deterioration determination value for the time of congestion are a method based on a statistical value and a method based on a congestion control model expression in session control.

The method based on a statistical value is a method of obtaining a deterioration determination value from statistical values of past variation of the buffer length stored in the state storage unit . Specific manner of obtaining a value will be described with reference to . In this manner a plurality of maximal values of buffer length variation are calculated to obtain a deterioration determination threshold value from an average of these maximal values. A deterioration determination threshold value is preferably an average of maximal values constant x deflection. Deflection may be a standard deflection or an average deflection. Constant is preferably a value not less than 1 .

The method based on a congestion control model expression in session control is a method of deriving an increase model expression of a communication rate parameter in advance obtaining a maximum value of a buffer length when a communication rate is decreased due to N times of congestion prevention between time t d and t based on the increase model expression and using the obtained maximum value to calculate a deterioration determination value.

The maximum value of a buffer length can be obtained by the following procedure. First assume that an input data rate and a communication rate are coincident to have no variation in the buffer length and obtain by a model expression f a period from r1 to r2 which is from a time point where a decrease in the communication rate occurs due to N times of congestion prevention in succession until when the communication rate as of before the rate decrease occurs is restored. Next add a buffer length as of before congestion prevention to a value obtained by integrating the model expression f by the period from r1 to r2. In this method since a maximum value of the buffer length can be obtained only when r2 r1

Deterioration determination threshold value is preferably a maximum value of the obtained buffer length a constant not less than 1.0 or a maximum value of the obtained buffer length a constant not less than 0 .

The present calculation method has a lower possibility of error detection than a method based on a statistical value because a threshold value is obtained based on behavior in session control at the time of congestion.

As to the method based on a statistical value and the method based on a congestion control model expression in session control either one of them or both of them may be used. When both are used it is preferable to use a maximum value among deterioration determination threshold values obtained by both the methods.

The non congestion time threshold value calculation processing unit executes the processing of calculating when the congestion state determination processing unit determines that it is not in the congestion state a threshold value of the buffer length for the determination of deterioration hereinafter referred to as a deterioration determination threshold value by the deterioration determining unit .

Not in the congestion state the buffer length of the buffer unit will be increased when a link rate is lower than an input data rate or when a communication rate calculated by congestion control at the time of non congestion is lower than the input data rate. The latter case will happen when time out occurs after a burst loss such as a path change to result in making the communication rate be higher than an initial value or when a method by which an increase of the communication rate becomes smaller as a reciprocation delay time becomes longer is used as a congestion control system under a condition where a reciprocation delay time is long or other cases.

In any case if the volume of input data is monotonously increased or fixed a buffer length shows a tendency of monotonous increase when the buffer length change is observed in as wide a time span as allows fluctuation of the buffer length due to burst in packet transmission processing or packet reception processing to be ignored. Deterioration determination threshold value at the time of non congestion is calculated by using the monotonous increase tendency.

As a first method of calculating a deterioration determination threshold value at the time of non congestion provided is a method of considering a value calculated from a buffer length at an arbitrary time point t stored in the state storage unit as a deterioration determination threshold value. It is desirable to consider a buffer length a constant not less than 0 at the time point t as a deterioration determination threshold value. Here the time point t is a time point stored by the state storage unit prior to the latest time stored in the state storage unit by more than a time interval in which buffer length fluctuation is ignorable. The time point t is desirably a time point at which the congestion state determination processing unit determines that it is not in congestion. Furthermore as the time point t the last deterioration determination time point may be used.

As a second method of calculating a deterioration determination threshold value at the time of non congestion provided is a method of obtaining a deterioration determination threshold value from a buffer length at a plurality of time points stored in the state storage unit . More specifically the method includes extrapolating buffer lengths at a plurality of time points estimating a buffer length as of a time point where the buffer length to be compared by the deterioration determining unit is measured and making a deterioration determination threshold value be a value based on the estimated buffer length. It is preferable to make the deterioration determination threshold value be a deterioration estimated value a constant not less than 0 . It is preferable to select a plurality of time points determined to have non congestion in succession by the congestion state determination processing unit . As an extrapolation method it is preferable to use linear approximation because of its simplicity. Since as compared with the first calculation method the present calculation method has a narrower range in which determination of deterioration is made an error detection possibility will be lower.

As to the first and second calculation methods either one of them or both of them may be used. When both are used it is desirable to use a maximum value among deterioration determination threshold values calculated by both the methods. It is also possible to add to a result of the deterioration determining unit a higher layer deterioration determining unit which determines deterioration in a higher layer such as an application based on a history of deterioration determination. The higher layer deterioration determining unit determines deterioration in the higher layer deterioration determining unit when the deterioration determining unit makes determination of deterioration n times n is an arbitrary value not less 1 in succession. Threshold value n may be a constant or a value inversely proportional to an increase in the buffer length.

Next detailed description will be made of operation of the buffer input unit the buffer unit and the session control unit of the packet transmission and quality deterioration monitoring device according to the present mode of implementation with reference to the structural diagram in and the flow charts in through .

The buffer input unit stores data in the buffer unit Step A in FIG. . The session control unit takes out the data from the buffer unit according to session control Step A to generate a packet Step A . The packet transmission unit transmits the packet generated by the session control unit to the packet reception device Step A .

The buffer state monitoring unit of the packet transmission and quality deterioration monitoring device obtains a buffer state of the buffer unit Step A in . Store the obtained buffer state in the state storage unit Step A . Thereafter temporarily stop and obtain another buffer state Step A .

The session state monitoring unit obtains a session state of the session control unit Step A in . Store the obtained session state in the state storage unit Step A . Thereafter temporarily stop and obtain another session state Step A .

Next detailed description will be made of operation of the threshold value calculating unit and the deterioration determining unit of the present mode of implementation with reference to the structural diagrams in and and the flow chart in .

The congestion state determination processing unit of the threshold value calculating unit obtains a session state from the state storage unit to determine whether congestion occurs Step A in .

When congestion occurs the congestion time threshold value calculation processing unit calculates a deterioration determination threshold value for the time of congestion Step A . When no congestion occurs the non congestion time threshold value calculation processing unit calculates a deterioration determination threshold value for the time of non congestion Step A .

The deterioration determining unit determines whether a buffer length stored in the state storage unit is not less than a deterioration determination threshold value or larger than that Step A . When the condition is satisfied determine that the communication quality is deteriorated Step A and it is not satisfied determine that the quality is not deteriorated Step S .

Thus structured and operating first mode of implementation enables detection of deterioration in communication quality in a session control protocol at a node which terminates and relays the session control protocol and a node which receives data from an application to communicate by the session control protocol irrespectively of generation non generation of a packet loss.

More specifically according to the first mode of implementation the threshold value calculating unit comprises the congestion state determination processing unit which determines whether it is in the congestion state from a parameter related to congestion detection the congestion time threshold value calculation processing unit which calculates a threshold value of a buffer length when determining that it is in the congestion state and the non congestion time threshold value calculation processing unit which calculates a threshold value of a buffer length when determining that it is not in the congestion state so that calculation of a threshold value of a buffer length for the determination of deterioration according to a congestion state enables determination of communication quality deterioration irrespectively of generation non generation of a packet loss. The reason is that the congestion state determination processing determines whether it is in the congestion state or not to calculate a threshold value for the determination of deterioration according the congestion state.

In addition the methods disclosed in Patent Literature 3 through 5 have a problem that because of difficulty in setting an appropriate threshold value when a threshold value is small a buffer increase will be detected due to fluctuation in packet arrival or temporary congestion to invite error detection of quality deterioration and when the threshold value is large quality deterioration detection might be delayed depending on a buffer increase rate. The reason is that the threshold value is determined in advance without taking variation in an actual buffer length into consideration.

According to the present mode of implementation since the congestion time threshold value calculation processing unit and the non congestion time threshold value calculation processing unit calculate a deterioration determination threshold value according to a variation range of a buffer length erroneous detection of quality deterioration or delay of quality deterioration detection can be prevented.

The methods disclosed in Patent Literature 1 and 2 have a problem that even if deterioration of a TCP session is detected it is impossible to determine whether the deterioration of the TCP session level is related to deterioration of an application level. The reason is that because no relationship is seized between the volume of data input from an application and the volume of transferable data of TCP it is impossible to determine whether a decrease in the volume of transferable data caused by the deterioration of the TCP session level affects transfer of input data.

Since according to the present mode of implementation a buffer length of a buffer which temporarily preserves data to be transmitted by session control and a session control parameter are monitored and a buffer length deterioration determination threshold value is obtained for the determination of deterioration in communication quality according to existence non existence of a congestion state to determine whether the communication quality is deteriorated or not it is possible to determine whether TCP session level deterioration is related to application level deterioration.

While the present mode of implementation has been described with respect to a case of one packet transmission and quality monitoring device and one packet reception device it can be realized also in a case where the packet transmission and quality monitoring device and the packet reception device are provided one to N or N to one or N to N in number without receiving constraints on number. The packet transmission and quality monitoring device and the packet reception device can be the same device.

Next a second mode of implementation of the present invention will be described in detail with reference to the drawings.

With reference to a packet transmission device is connected to a packet reception device through a communication network . The packet transmission device is also connected to a quality deterioration monitoring device through a communication network . The communication network and the communication network may be the same network or different networks or one may be included in the other.

The packet transmission device is a device which generates a packet by session control sends the packet to the packet reception device and sends a buffer length and a control state of the session control to the quality deterioration monitoring device . The packet reception device is a device which receives a packet subjected to the session control by the packet transmission device . The quality deterioration monitoring device is a device which monitors communication quality deterioration of the packet transmission device .

Description will be made of an example of a structure of the packet transmission device with reference to .

With reference to the packet transmission device includes a buffer input unit a buffer unit a session processing unit a packet transmission unit a buffer state monitoring unit a session state monitoring unit and a state information transmission unit .

Since the buffer input unit the buffer unit the session processing unit the packet transmission unit the buffer state monitoring unit and the session state monitoring unit are the same as the buffer input unit the buffer unit the session processing unit the packet transmission unit the buffer state monitoring unit and the session state monitoring unit according to the above described first mode of implementation no detailed description will be made thereof.

The state information transmission unit is a part having a function of notifying the quality deterioration monitoring device of a buffer state monitored by the buffer state monitoring unit and a session state monitored by the session state monitoring unit .

Description will be made of an example of a structure of the quality deterioration monitoring device with reference to .

With reference to the quality deterioration monitoring device includes a state information reception unit a state storage unit a threshold value calculating unit and a deterioration determining unit .

The state information reception unit is a part having a function of receiving a buffer state and a session state from the packet transmission device . Since the state storage unit the threshold value calculating unit and the deterioration determining unit are the same as the state storage unit the threshold value calculating unit and the deterioration determining unit according to the above described first mode of implementation no detailed description will be made thereof.

Next detailed description will be made of operation of the second mode of implementation with reference to the flow charts of through .

Since operation of the buffer input unit the buffer unit the session processing unit and the packet transmission unit of the packet transmission device of is the same as the operation shown at Step A through A in of the buffer input unit the buffer unit and the session control unit shown in according to the first mode of implementation no detailed description will be made thereof.

Next detailed description will be made of operation of the buffer state monitoring unit the session state monitoring unit and the state information transmission unit of the packet transmission device with reference to and the flow charts in and .

The buffer state monitoring unit obtains a buffer state of the buffer unit Step B in . The state information transmission unit notifies the quality deterioration monitoring device of the obtained buffer state Step B . Thereafter temporarily stop to obtain another buffer state Step B .

The session state monitoring unit obtains a session state of the session control unit Step B . The state information transmission unit notifies the quality deterioration monitoring unit of the obtained buffer state Step B . Thereafter temporarily stop to obtain another session state Step B .

Next detailed description will be made of operation of the quality deterioration monitoring device with reference to and .

The state information reception unit receives state information from the packet transmission device Step B in and stores the same in the state storage unit Step B .

Since operation of the threshold value calculating unit and the deterioration determining unit is the same as the operation of Steps A through A of the threshold value calculating unit and the deterioration determining unit shown in according to the first mode of implantation no detailed description will be made thereof.

Similarly to the first mode of implementation thus structured and operating second mode of implementation enables deterioration in a communication quality to be determined by calculating a threshold value of a buffer length for the determination of deterioration according to a congestion state irrespectively of generation non generation of a packet loss.

While the second mode of implementation has been described with respect to a case of one packet transmission device and one packet reception device it can be realized also in a case where the packet transmission device and the packet reception device are provided one to N or N to one or N to N in number without receiving constraints on number.

While the description has been made with respect to a case of one packet transmission device and one quality monitoring device it can be realized also in a case where the packet transmission device and the quality monitoring device are provided one to N or N to one or N to N in number without receiving constraints on number.

The packet transmission device and the packet reception device can be the same device. Alternatively the packet transmission device and the quality monitoring device can be the same device. Alternatively the packet reception device and the quality monitoring device can be the same device.

The threshold value calculating unit according to the first mode of implementation and the threshold value calculating unit according to the second mode of implementation calculate a threshold value for the determination of deterioration according to whether congestion occurs or not. It is also possible not according to whether congestion occurs to determine congestion as a plurality of congestion states according to the amount of increase in parameters which will be increased in number along with congestion detection thereby calculating a threshold value for the determination of deterioration on a congestion state basis.

Further possible is to determine congestion as a plurality of congestion states according to the amount of increase in parameters which will be increased along congestion detection calculate a plurality of threshold values according to a congestion state and determine the degree of deterioration based on the plurality of threshold values.

While the first and second modes of implementation have been described with respect to an example where data is communicated using a packet they can be realized by any method in which communication is executed with data such as a cell or a frame other than a packet sectioned.

The first and second modes of implementation have been described with respect to a case where the threshold value calculating unit and the threshold value calculating unit have a procedure of determining congestion. Without the procedure for determining congestion the threshold value calculating unit and the threshold value calculating unit may obtain a threshold value of a buffer length for the determination of deterioration based on buffer lengths obtained prior to an arbitrary time point t which are stored in the state storage unit . The procedure of obtaining a threshold value in this case is the same as that of the non congestion time threshold value calculation processing unit .

With reference to the packet transmission and quality deterioration monitoring device which can be realized by the same hardware structure as that of a common computer device comprises a CPU Central Processing Unit a main storage unit formed of a RAM Random Access Memory for use as a data working region or a data temporary saving region a communication unit which transmits and receives data to and from other node through a network an input output interface unit connected to an external device to transmit and receive data a subsidiary storage unit which is a hard disk device formed of a non volatile memory such as a ROM Read Only Memory a magnetic disk or a semiconductor memory an input device such as a keyboard or a mouse an output device such as a display device and a system bus which connects the above described respective components with each other.

The packet transmission and quality deterioration monitoring device according to the present mode of implementation has its operation realized not only in hardware by mounting a circuit part as a hardware part such as an LSI Large Scale Integration with a communication quality monitoring program incorporated which executes processing of the session control unit the buffer state monitoring unit the session state monitoring unit the threshold value calculating unit the deterioration determining unit and the like but also in software by storing a program which provides each function of the session control unit the buffer state monitoring unit the session state monitoring unit the threshold value calculating unit and the deterioration determining unit into the subsidiary storage unit loading the program into the main storage unit and executing the same by the CPU .

Although has been described with respect to an example of a hardware structure of the packet transmission and quality deterioration monitoring device the quality deterioration monitoring device according to the second mode of implementation also has the same structure as that shown in .

Next a specific exemplary embodiment of the above described modes of implementation will be described.

The first and second modes of implementation can be embodied on an IP network by using TCP as a session control system. In this case since TCP has a retransmission mechanism the number of packet losses or the number of packet retransmissions is used as a parameter whose number is increased along congestion detection.

As a TCP congestion control system a congestion control system called TCP Reno is widely used. In a congestion avoiding phase as a normal state except an initial state a parameter for adjusting the volume of transmission data per one RTT Round Trip Time called a congestion window hereinafter referred to as a CWND congestion window is increased by 1 1RTT packet per 1ACK ACKnowledgement that is one packet per 1RTT. Accordingly a communication rate parameter increase model expression f will be expressed as f t 1 RTT packet unit time . When a packet loss is detected after completely retransmitting the lost packet CWND is halved to again enter the congestion avoiding phase. As a result even when a plurality of packets are lost per one RTT packet loss detection is counted as one. As a buffer unit monitored by the buffer state monitoring unit it may be a buffer of a TCP stack or a buffer on an application side provided when calling up a transmission function in SOCKT as an API Application Programming Interface of TCP. Both a TCP stack buffer and an application side buffer may be included.

With reference to description will be made of variation of CWND and a TCP transmission buffer in a case where when assuming that the volume of input data and the volume of output data by TCP are balanced immediately before a packet loss no packet loss occurs thereafter for a while. With a CWND value as of immediately before a packet loss time a in as x packet CWND will be 1 2x due to a packet loss and when CWND continues increasing to return to x time b the TCP transmission buffer length will be the largest and when CWND attains 3 2x time c the buffer length will return to a value as of before the packet loss.

In the present exemplary embodiment a deterioration determination threshold value at the congestion time threshold value calculation processing unit for the time of congestion is calculated by a method based on a congestion control model expression in session control. Logically obtain a buffer length at the time point of time b in and obtain a deterioration determination threshold value from the buffer length.

When packet loss detection is once with a time 1RTT as r the time period from a to b will have r x 2. Since the amount of increased of a buffer length in this period will be a discrete integral of a communication rate parameter increase model expression f in the time period from a to b it can be calculated by ceil 2 ceil 2 1 . . . 3 2 2 floor 2 2 ceil 2 ceil 2 1 1 2 floor 2 Expression 1 in which ceil x is a minimum integer value not less than x and floor x is a maximum integer value not more than x .

When packet loss detection occurs N times in succession when halving the CWND due to packet loss detection retransmission and congestion prevention repeats N times in succession after successive packet losses CWND of the congestion window goes 1 2x so that the time period from a to b will have r x 1 1 2 . The amount of increased of a buffer length in this period can be calculated by floor 1 2 floor 1 2 1 . . . 3 2 1 2 floor 1 2 2 floor 1 2 floor 1 2 1 1 1 2 floor 1 2 Expression 2 .

When a delay ACK option is valid since the number of ACK will be 1 2 in general a range of an increase of CWND will be 1 2 per unit time to take the double time for reaching the CWND resulting in doubling the amount of an increase d in a buffer length.

Furthermore taking a retransmission time into consideration add the following expression to the amount of an increase d in a buffer length floor 1 2 floor 1 2 1 floor 1 2 floor 1 2 Expression 3 .

The buffer length at the time point of time b will be a value obtained by adding the amount of increase d in buffer length to a buffer length q as of immediately before packet loss time a .

Next description will be made of a relationship between a deterioration determination threshold value and a packet loss with reference to . Set a deterioration determination threshold value as a buffer length at a time point of the time b obtained with N as 1. While in a case of one packet loss as in a section ac the buffer length fails to exceed the deterioration determination threshold value in a case of two packet losses as in a section a c the buffer length exceeds the deterioration determination threshold value to determine that communication quality is deteriorated.

On the current operating system OS mounted is a TCP having a congestion control system whose rate is higher than TCP Reno particularly under a large delay and wide band environment and which has fairness with TCP Reno at the time of congestion. More specifically on the Windows Server 2008 the Compound TCP is mounted and on Linux the CUBIC TCP is mounted which are used as an OS standard. A deterioration determination threshold value may be obtained based on a communication rate parameter increase model expression of these high speed TCP. Although when a deterioration determination threshold value is used on the premise of TCP Reno the value will be larger than a deterioration determination threshold value on the premise of a high speed TCP to invite a delay in determination it will cause no big problem because no erroneous determination will be made.

In the present exemplary embodiment a deterioration determination threshold value for the time of non congestion in the non congestion time threshold value calculation processing unit is obtained from buffer lengths at a plurality of time points. More specifically linearly extrapolate a buffer length as of t time prior to a latest time recorded and a buffer length as of 2t time prior to the same to estimate a buffer length at the latest time and take the value as a deterioration determination threshold value.

Also executable is in SCTP Stream Control Transmission Protocol having the same congestion control as TCP Reno.

In the first and second modes of implementation DCCP Datagram Congestion Control Protocol can be executed as a session control system on the IP network. Since DCCP has no retransmission mechanism the number of packet losses or a packet loss rate is used as a parameter whose number is increased as congestion detection.

DCCP has its congestion control algorithm changeable by a CCID Congestion Control ID parameter. As the CCID a mode and a mode are defined at the current time point.

In the mode transmission control is executed using a congestion window whose variation is the same as that of TCP Reno. Accordingly the present invention can be implemented by the same manner as that of TCP Reno.

In the mode transmission control is executed using a transmission rate which is set to be a value of a logical throughput of TCP Reno obtained from a delay or a packet loss rate. The rate is set not to vary more than double 1RTT. Since a rate variation is small as compared with that in the mode calculation of a deterioration determination threshold value for the time of congestion at the congestion time threshold value calculation processing unit employs a method based on a statistical value.

Also executable is in a system in which the same congestion control mechanism as that of DCCP is mounted on a UDP User Datagram Protocol . Further executable is in a system in which a congestion control mechanism of either one of the modes and of CCID of DCCP is mounted on UDP.

The present exemplary embodiment has been described with respect to an example of execution on IP network. The present invention can be embodied on other network than the IP network as long as it uses a session control protocol for congestion control.

While the above described first mode of implementation shows an example in which both of the packet transmission function and the quality deterioration monitoring function are mounted on the packet transmission and quality deterioration monitoring device as a single device the packet transmission device may comprise a communication quality monitoring device having the quality deterioration monitoring function. Structuring the packet transmission device to include other components than the threshold value calculating unit and the deterioration determining unit enable the communication quality monitoring device to be realized only by comprising the threshold value calculating unit and the deterioration determining unit as a minimum component.

Also in this case it is possible to determine whether communication quality is deteriorated irrespectively of data loss generation non generation by calculating a deterioration determination threshold value of a buffer length for the determination of deterioration according to a congestion state.

While the second mode of implementation has been described with respect to a structure in which the quality deterioration monitoring device comprises the state information reception unit the state storage unit the calculation value calculating unit and the deterioration determining unit it can be realized only by comprising the threshold value calculating unit and the deterioration determining unit as a minimum component.

In this case communication quality deterioration can be determined irrespectively of data loss generation non generation by obtaining a buffer state and a session state stored in the packet transmission device side and calculating a deterioration determination threshold value of a buffer length for the determination of deterioration according to a congestion state.

Although the present invention has been described with respect to the preferred modes of implementation and exemplary embodiment in the foregoing the present invention is not necessarily limited to the above described modes of implementation and exemplary embodiment and can be implemented in various modifications within the scope of its technical idea.

