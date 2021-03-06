---

title: Peak windowing for crest factor reduction
abstract: In order to reduce the crest factor of a signal for power amplification, a windowing function is applied. The windowing function that is applied is a triangular windowing function. The use of this function produces good results when those results are measured in terms of their effect on a transmitted signal in a WCDMA communications system. The filter for performing the triangular windowing function receives the signal, and applies it to a first delay element. The output from the first delay element is applied to a second delay element. An adder forms a weighted sum of the received signal and the signals at the outputs of the first delay element and the second delay element. A first accumulator is connected to receive an input from the adder and provides a first accumulator output, while a second accumulator is connected to receive an input from the first accumulator output and provides a second accumulator output.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08005177&OS=08005177&RS=08005177
owner: Altera Corporation
number: 08005177
owner_city: San Jose
owner_country: US
publication_date: 20090811
---
The present application is a divisional of U.S. patent application Ser. No. 11 109 536 filed Apr. 18 2005 now U.S. Pat. No. 7 586 995 and entitled PEAK WINDOWING FOR CREST FACTOR REDUCTION and is herein fully incorporated by reference for all purposes.

This invention relates to signal processing and in particular to a method and a device for signal processing before the signal is applied to a power amplifier.

In many communications systems electronic signals are applied to a power amplifier before transmission. For example in a base station of a cellular wireless communications system electronic signals are applied to a power amplifier before being passed to an antenna for transmission over the air interface to the various subscribers.

Power amplifiers are designed such that they operate at maximum efficiency when their input signal levels are within a particular range.

In the case of a Wideband Code Division Multiple Access WCDMA or other Code Division Multiple Access CDMA system data streams are multiplied with codes and added together. The composite signal is characterized by large variations in magnitude over time which results in a large peak to average ratio PAR . This reduces the efficiency of the power amplifiers to which these composite signals are applied before transmission because the input signal levels are often outside the particular range within which the power amplifiers can operate with maximum efficiency. It is therefore highly desirable to reduce the PAR without significantly degrading the transmitted signal.

The document Effect of Clipping in Wideband CDMA System and Simple Algorithm for Peak Windowing O. V n nen J. Vankka and K. Halonen World Wireless Congress San Francisco USA May 28 31 2002 pp. 614 619 describes a technique for reducing the PAR of a WCDMA signal. A windowing algorithm is applied to the signal after upconversion to an intermediate frequency. More specifically the document proposes the use of a windowing algorithm based on a Hamming function which is a known mathematical function. The windowing algorithm is therefore known as a Hamming window.

However the use of a Hamming window function requires the use of relatively large amounts of hardware to implement. This is a particular problem if a long window is used although the use of a long window is advantageous from the point of view of improving the performance of the algorithm.

The possibility of an efficient implementation of the windowing function is particularly relevant when the device is to be implemented in a Field Programmable Gate Array FPGA when hardware resources are typically more limited than in a specifically designed integrated circuit such as an ASIC.

In an embodiment of the invention the windowing function that is applied is a triangular windowing function. It has surprisingly been found by the inventors that the use of this function produces good results when applied to a signal that is to be supplied to a power amplifier for amplification. In particular the use of this function produces good results when those results are measured in terms of their effect on a transmitted signal in a WCDMA communications system.

In another embodiment of the invention a filter performs a triangular windowing function on a received signal using only registers and adders subtractors. The filter receives the signal and applies it to a first delay element. The output from the first delay element is applied to a second delay element. An adder forms a weighted sum of the received signal and the signals at the outputs of the first delay element and the second delay element. A first accumulator is connected to receive an input from the adder and provides a first accumulator output while a second accumulator is connected to receive an input from the first accumulator output and provides a second accumulator output.

This filter comprising registers adders and subtractors can be implemented particularly efficiently especially in a FPGA. This means that the filter can be implemented conveniently and at low cost.

In this illustrated embodiment the transmitter forms part of a base station in a CDMA wireless communications system. As such the downlink signal sent from the transmitter is made up of a relatively large number of individual signals combined together. In the individual data signals are represented by the input lines . . . . These individual data signals are applied to respective modulators . . . where as will be well known to the person skilled in the art they are multiplied by respective spreading codes. It will be appreciated that the operation of the modulators . . . is complex but for the purposes of understanding the present invention it is sufficient to know that the outputs of the modulator are baseband signals whose amplitudes vary with time.

The modulator outputs are then applied to a frequency upconversion block which converts the baseband signal to a signal at the desired radio frequency. This radio frequency signal is then applied to a power amplifier for amplification to a desired power level and is then applied to an antenna for transmission.

Unless special measures are taken the radio frequency signal applied to the power amplifier has a relatively high peak to average ratio PAR or crest factor. That is the peaks in the signal level are considerably higher than the average level of the signal. A disadvantage of the relatively high peak to average ratio PAR of the signal is that the power amplifier is designed to operate efficiently with input signal levels in a particular range. When the input signal level falls outside that range the power amplifier can no longer operate efficiently.

In order to mitigate this disadvantage it is known to take action to reduce the peak levels in the modulator output signal. In this illustrated embodiment of the invention the action that is taken is to apply a windowing function at an intermediate frequency.

Thus within the frequency upconversion block the baseband modulator output signals are applied to respective first upconverters . . . which also receive signals at respective first intermediate frequencies IF . . . IF and convert the baseband modulator output signals to the first intermediate frequency.

The signals at the first intermediate frequency are then combined with the composite signal at the first intermediate frequency being applied to a windowing block which applies a windowing function as will be described in more detail below.

The output of the windowing block is applied to a second upconverter which also receives a signal at a second intermediate frequency IF and converts the signal to the desired radio frequency for transmission.

Specifically the signal represents the sort of signal that would typically be obtained in a CDMA system before any windowing function is applied. As can be seen in the signal reaches a peak value. However to avoid inefficient operation of the power amplifier it is preferred that the level of the signal should not exceed a level L.

One way to achieve this is to apply a clipping function to the signal to produce a clipped signal . That is the clipped signal is exactly equal to the original signal except that when the original signal exceeds the level L the clipped signal is restricted to the level . This has the disadvantage that the clipping adds sharp corners to the clipped signal at the points where the clipping begins and ends. These sharp corners will result in frequency leakage into adjacent frequency bands.

In accordance with the preferred embodiment of the present invention therefore a windowing function is applied to the original signal . shows the form of the windowed signal and it can be seen that this avoids introducing the sharp corners into the signal.

Clipping can be described mathematically by the following equation in which x n is the original signal y n is the clipped output signal and c n is a clipping function and where the clipping function is given by 

For most values that is except where the input signal level x n is close to the clipping threshold A b n should be as close as possible to c n to minimize unnecessary clipping. At the same time b n must not exceed c n so that the range of the output signal y n is guaranteed not to exceed the clipping threshold.

This can be achieved by setting values of the weighting coefficient ak using the value of the clipping function c n and more specifically the term 1 c n such that when c n reaches a steady state value of 1 b n also has a steady state value of 1 and the windowing function has no effect on the input signal level.

This would work well if the distance between samples to be clipped exceeded the window length. Since this can not be guaranteed and the number of taps must be fixed in order to allow the system to be implemented using FIR filters the document Effect of Clipping in Wideband CDMA System and Simple Algorithm for Peak Windowing O. V n nen J. Vankka and K. Halonen World Wireless Congress San Francisco USA May 28 31 2002 pp. 614 619 cited above proposes a structure containing a FIR filter with feedback.

A first FIR filter has an impulse response that defines the window function and it receives an intermediate signal m n as its input. An output from the first FIR filter is subtracted from 1 in a first adder to form the output b n . The intermediate signal m n is also applied to a second FIR filter and the output of the second FIR filter is fed back to a second adder where it is subtracted from 1 c n to form a second intermediate signal y. A logic block then causes the first intermediate signal m n to take the value of y if and only if y is greater than 0. Otherwise m n takes the value 0 and in the steady state there is no windowing and b n 1.

Thus as mentioned above the first FIR filter has an impulse response that defines the window function and it can also be seen that the second FIR filter in this embodiment has a shape which is half of the shape of that window function.

It has now surprisingly been found that good results can be obtained by the use of a regular triangular window function for the first FIR filter . That is the value of the window function increases in equal sized steps from zero to a maximum value and then symmetrically decreases in equal sized steps to zero.

The optimum length of the window will depend on the nature of the received data stream. In general the length of the window will be set on the basis of a compromise between achieving a minimum error vector magnitude EVM which in general requires a small number of taps and achieving a low adjacent channel leakage ratio ACLR which in general requires a high number of taps.

In an embodiment of the invention the window length is set to a predetermined value based on prior knowledge of the expected form of the received data stream. However in principle the window length can be varied.

An input signal m n is applied to a first input of an adder of a first stage . The input signal m n is also applied to a first delay block of the first stage while the output of the adder which receives a 0 on its second input is applied to a second delay block of the first stage .

The output of the first delay block of the first stage is applied to a first input of an adder of a second stage while the output of the second delay block of the first stage is applied to a second input of the adder . The output of the first delay block of the first stage is also applied to a first delay block of the second stage . The output of the adder is applied to a second delay block of the second stage .

The output of the first delay block of the second stage is applied to a first input of an adder of a third stage while the output of the second delay block of the second stage is applied to a second input of the adder . The output of the first delay block of the second stage is also applied to a first delay block of the third stage . The output of the adder is applied to a second delay block of the third stage .

The output of the first delay block of the third stage is applied to a first input of an adder of a fourth stage while the output of the second delay block of the third stage is applied to a second input of the adder . The output of the first delay block of the third stage is also applied to a first delay block of the fourth stage . The output of the adder is applied to a second delay block of the fourth stage .

The output of the first delay block of the fourth stage is applied to a first input of an adder of a fifth stage while the output of the second delay block of the fourth stage is applied to a second input of the adder . The output of the first delay block of the fourth stage is also applied to a first delay block of the fifth stage . The output of the adder is applied to a second delay block of the fifth stage .

It will be noted from that the values applied to the first inputs of the adders that is up to and including the middle one of the five stages are added to the values applied to the respective second inputs. However the values applied to the first inputs of the adders that is after the middle one of the five stages are subtracted from the values applied to the respective second inputs. This results in the required triangular profile.

The outputs of the respective second delay blocks of the five stages are then summed in an adder to form an output signal p n .

The form of the filter shown in is generally conventional and is particularly suitable for implementation in an Application Specific Integrated Circuit ASIC . However in some circumstances for example where a particularly long window is to be used or where the device is to be implemented in a Field Programmable Gate Array FPGA a more efficient implementation of the triangular windowing function may be advantageous. For example in the adder receives two identical inputs and so its output is equal to twice one of those inputs. The adder could therefore be replaced by a 1 bit left shift operation. In practice other similar substitutions can be performed.

The input signal is also applied to a first multiplier which in this case trivially multiplies the input signal by 1. The output signal of the first long delay block is also applied to a second multiplier which in this case multiplies the input signal by 2 it being appreciated that this can be achieved by shifting the binary value one place to the left and changing the sign of the binary value. The output signal of the second long delay block is also applied to a third multiplier which in this case trivially multiplies its input signal by 1.

The output signals from the multipliers are applied to an adder . It will be apparent that where the multipliers replace their respective inputs by 1 they can be removed such that the adder adds the input to the first long delay block and the output from the second long delay block and subtracts twice the output of the first long delay block .

The output of the adder is applied to a first accumulator which is made up of an adder connected to a block that delays its input signal by one clock cycle and feeds the result back to the adder . The result is that the output of the accumulator becomes equal to its previous output value plus its current input value.

The output of the accumulator is applied to a second accumulator which is made up of an adder connected to a block that delays its input signal by one clock cycle and feeds the result back to the adder . The result is that the output of the second accumulator becomes equal to its previous output value plus its current input value.

To illustrate the operation it is assumed that an impulse of magnitude is applied to the input of the circuit as shown in . As described above this input value is applied to the adder which is receiving no other non zero inputs and so shows the value 1 at the input to the accumulator .

The effect of the accumulator as described above is that the value output from the first accumulator remains at 1 as shown in for so long as the first accumulator does not receive any further non zero input.

This constant value is then input to the second accumulator and as described above the output value of this accumulator is equal to its previous output value plus its current input value. Thus as shown in the output value of the second accumulator increments by 1 in each clock cycle continuously for so long as the first accumulator outputs the value 1.

After a delay of n clock cycles the initial input is output by the first long delay block and applied to the second multiplier which multiplies the input signal by 2. The value 2 is therefore applied to the adder which is receiving no other non zero inputs and so shows the value 2 at the input to the accumulator in the nth clock cycle after the initial input.

The effect of the accumulator as described above is then that in the nth clock cycle after the initial input the value output from the first accumulator becomes equal to its previous output value that is 1 plus its current input value that is 2 that is 1 and it remains at 1 as shown in for so long as the first accumulator does not receive any further non zero input.

This constant value is then input to the second accumulator and as described above the output value of this accumulator is equal to its previous output value plus its current input value. Thus as shown in the output value of the second accumulator decrements by 1 in each clock cycle continuously for so long as the first accumulator outputs the value 1.

After a further delay of n clock cycles the initial input is output by the second long delay block and applied to the third multiplier and then to the adder . As this is receiving no other non zero inputs shows the value 1 at the input to the accumulator in the 2 nth clock cycle after the initial input.

The effect of the accumulator as described above is then that in the 2 nth clock cycle after the initial input the value output from the first accumulator becomes equal to its previous output value that is 1 plus its current input value that is 1 that is zero and it remains at zero as shown in for so long as the first accumulator does not receive any further non zero input.

This constant value is then input to the second accumulator and as described above the output value of this accumulator is equal to its previous output value plus its current input value. Thus as shown in the output value of the second accumulator having decremented by 1 for as many clock cycles as it had previously incremented by 1 has become equal to zero and then remains at zero thereafter.

It can therefore be seen that the circuit shown in produces a regular triangular window having equal length periods of incrementing and decrementing. However different form of triangular window can be achieved if desired by adjustment of the relative delays introduced by the first and second long delay blocks and by adjustment of the multiplication factors by which the multipliers multiply their respective inputs.

It will be noted that the window length is determined only by the lengths of the delays introduced by the long delay blocks and that the window length can be altered by varying the delays introduced by these long delay blocks without requiring any additional hardware other than a possible change in width of the adders.

As mentioned above the FIR filter in preferably performs a triangular windowing function. In that case the FIR filter in the feedback loop preferably performs a half triangular windowing function.

Where the FIR filter has a filter length of N the half triangular window of the FIR filter has a filter length FL N 1 2.

Then the output q n of the FIR filter is related to its input m n by the relationship FL. FL 1 .x 1 . . . Similarly 1 FL. 1 FL 1 .m . . . Therefore 1 FL. 1 11 

The input m n is also applied to a first input of a first adder and to a FL 1 period delay block . The output of the delay block is applied to a second adder where it is subtracted from the output of the first adder . The output of the second adder is fed back to a second input of the first adder .

The output of the first adder is also applied to a delay block and the output of the delay block is applied to a third adder . where it is subtracted from the output of the multiplier . The resulting signal is applied to an accumulator comprising a fourth adder and a delay block to form the output q n .

Thus as described above with reference to the input data stream from the first upconverter is applied to the windowing block which applies the windowing function. That is based on the current value x n of the input a value for c n is calculated determined by the relationship between x n and the clipping threshold A. From that and based on the triangular window function described above a value for b n is calculated and hence a value for the output y n is calculated.

There is thus described a system which provides good performance in terms of its crest factor reduction without excessively adversely affecting the other properties of the signal while being easy to implement.

Although the invention has been described with particular reference to a CDMA wireless communications system it could equally be applied to other wireless communications systems such as OFDM systems. Further although the invention has been described in terms of a wireless communication system the crest factor of any signal can be reduced if required in a corresponding way.

