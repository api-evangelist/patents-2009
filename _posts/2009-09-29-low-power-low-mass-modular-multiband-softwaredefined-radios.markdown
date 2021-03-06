---

title: Low power, low mass, modular, multi-band software-defined radios
abstract: Methods and systems to implement and operate software-defined radios (SDRs). An SDR may be configured to perform a combination of fractional and integer frequency synthesis and direct digital synthesis under control of a digital signal processor, which may provide a set of relatively agile, flexible, low-noise, and low spurious, timing and frequency conversion signals, and which may be used to maintain a transmit path coherent with a receive path. Frequency synthesis may include dithering to provide additional precision. The SDR may include task-specific software-configurable systems to perform tasks in accordance with software-defined parameters or personalities. The SDR may include a hardware interface system to control hardware components, and a host interface system to provide an interface to the SDR with respect to a host system. The SDR may be configured for one or more of communications, navigation, radio science, and sensors.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08417859&OS=08417859&RS=08417859
owner: The Johns Hopkins University
number: 08417859
owner_city: Baltimore
owner_country: US
publication_date: 20090929
---
This application claims the benefit of U.S. Provisional Patent Application No. 61 101 189 titled Low Power Low Mass Modular Multi Band Software defined Radio for Communications Navigation Radio Science and Sensors to Christopher B. Haskins et. al filed Sep. 30 2008 which is incorporated herein by reference in its entirety.

This invention was made with U.S. Government support under the National Aeronautics and Space Administration NASA contract number NNXD06AH71G. The United States Government has certain rights in the invention.

Disclosed herein are methods and systems to implement and operate modular software defined radios SDRs including SDRs for terrestrial and extraterrestrial use.

Software defined radios SDRs arose in the late 1970s in the defense sector. The term software defined radio has been in use since at least 1991. An early U.S. military SDR initiative named SpeakEasy sought to use programmable processing to emulate multiple existing military radios operating in frequency bands between 2 and 2000 MHz and to enable incorporation of new coding and modulation techniques in the future.

SDR development is driven predominantly by terrestrial needs including military and emergency response needs such as to provide interoperability amongst different equipment. For example the U.S. military has developed a Joint Tactical Radio System to provide flexible and interoperable communications amongst hand held vehicular airborne dismounted fixed base station and maritime radios.

Extraterrestrial environments present challenges that may not be encountered to the same degree in terrestrial environments such as physical inaccessibility higher signal propagation frequencies radiation relatively vast distances between transmitters and receivers different mission requirements and more onerous limitations on size mass and power consumption.

Designs developed for terrestrial applications are not necessarily suitable for extraterrestrial environments and do not necessarily satisfy extraterrestrial challenges. Limited resources allotted for extraterrestrial programs may necessitate unconventional configurations of commercially available components rather than design and manufacture of new components.

An SDR may be configured to perform a combination of numerically controlled fractional and integer frequency synthesis and direct digital synthesis to provide a set of relatively agile flexible low noise and low spurious timing and frequency conversion signals. Frequency synthesis may include dithering to provide additional precision. Direct digital synthesis mixing sampling sub sampling clock synthesis and frequency synthesis including dithering or portions thereof may be performed in hardware firmware software configurable firmware a processor in response to software and combinations thereof.

An SDR may include software configurable firmware modules to perform processing tasks in accordance with one or more software defined personalities wherein a personality may include a set of software defined parameters.

Software configurable firmware modules may include one or more of a carrier tracking module to correct Doppler induced errors in a receive path a channel select module to define or select down conversion channel frequencies and bandwidths and to demodulate data a coherency calculation module to perform mathematics and signal processing to maintain an exciter path carrier signal coherent with a received signal in accordance with a turn around ratio an encoder module including one or more encoder sub modules each configured to provide a corresponding encoding framework a hardware interface firmware module to control receiver and exciter slices and a host interface module to provide an interface to the SDR with respect to a host system.

Additional features and exemplary embodiments are provided in the description below and the accompanying drawings.

In the drawings the leftmost digit s of a reference number identifies the drawing in which the reference number first appears.

Exemplary signal processing tasks are disclosed herein with reference to one or more of a receiver slice and exciter slice DSP processor firmware and hardware . The exemplary signal processing tasks are not however limited to exemplary referenced elements. Distribution of signal processing tasks amongst a receive slice an exciter slice and DSP and amongst processor firmware and hardware may be adjusted to optimize power efficiency. For example as component technology and corresponding power efficiencies improve signal processing tasks may be shifted from slices and or to DSP and or from hardware towards firmware and or processor which may enable more advanced user defined features.

DSP may include one or more of a field programmable gate array FPGA and an application specific integrated circuit ASIC .

Hardware may include circuits and devices such as analog to digital converters ADCs digital to analog converters DACs digital frequency synthesizers frequency synthesizers and memory.

Processor may be configured to provide software defined receive and transmit channel assignments to firmware and to provide an interface to a host system such as to permit a host processor to operate SDR . Host processor may be responsible for command and data handling of host .

Processor may include a reduced instruction set computing RISC architecture processor such as a MIPS processor developed by MIPS Technologies Inc. formerly MIPS Computer Systems Inc.

Processor may be implemented within firmware or outside of firmware such as a separate hardware module or slice and may be configured to operate under control of an operating system and to execute applications programs within a corresponding operating environment. The applications may include applications to control functions of SDR . This may be useful for example with respect to communication intensive missions such as a multi user mission.

SDR may be configurable to operate without processor and may be configured to operate under direct control of host processor . This may reduce overall mass and power requirements.

Firmware and associated software may provide one or more of RF hardware interface abstraction user host interface abstraction firmware modularity software re configurability radio auto tuning in flight waveform manipulation within receiver slices and exciter slices and radiation mitigation.

Firmware may include software configurable firmware to selectively configure SDR with respect to for example and without limitation one or more of receive frequencies and bandwidths transmit frequencies and bandwidths a turn around ratio demodulation and modulation schemes clock rates and analog to digital ADC sampling sub sampling rates.

DSP may be configured to selectively operate a receiver slice and an exciter slice independently of one another or to synthesize a two way coherent carrier to operate the receiver slice and the exciter slice coherently with respect to one another in accordance with a turn around ratio. Coherent operation may be useful with respect to for example Doppler navigation sensor and or radio science applications.

DSP may be configured to provide a relatively flexible coherent turnaround ratio which may used in conjunction with one or more multiple spacecraft per aperture MSPA techniques such as shared uplink command and two way radiometric tracking services. An uplink may service multiple spacecraft as each radio can be in flight tuned to a current uplink frequency using a spacecraft ID as a discriminator for specific commands. The flexible turnaround ratio may permit multiple spacecraft to lock to a single uplink signal and coherently generate a downlink at a corresponding assigned frequency channel which may permit increased data throughput and or increased tracking data. This may help to minimize mass and costs of a spacecraft and or to more efficiently use ground based resources.

SDR may include relatively general purpose modulators and demodulators such as vector modulators and vector demodulators which may provide flexibility. Baseband in phase and quadrature I Q data waveforms may be generated using a pair of relatively high speed digital to analog converters DACs and firmware .

SDR may include a digitally controlled frequency control system to generate and synthesize frequency conversion signals from a reference signal fref . The digitally controlled frequency control system may provide numerically controlled tracking and synthesis. The frequency control system may be configured to perform one or more of direct digital synthesis numerically controlled frequency synthesis dithering and combinations thereof to provide relatively agile flexible low noise and low spurious timing and frequency conversion signals.

DSP may include a plurality of software selectable sets of configuration parameters or personalities which may be selectively applied to the software configurable firmware. The parameters may be associated with one or more of direct digital synthesis numerically controlled frequency synthesis clock rates and dithering and each set of parameters may be associated with one or more of a receive frequency and bandwidth a transmit frequency and bandwidth and a turn around ratio.

SDR may include a reference oscillator to generate reference signal fref . Reference oscillator may include a relatively low power low phase noise oscillator such as an oven controlled crystal oscillator OCXO or a temperature compensated crystal oscillator TCXO . Reference oscillator may be implemented as a separate module or may be incorporated within another component of SDR . Reference oscillator may be implemented in a modular fashion such as to permit substitution of an oscillator with another oscillator. Alternatively SDR may be configured to receive reference signal fref from an ultra stable oscillator USO such as from a host which may correspond to an aircraft and or a space craft.

SDR may include an interface to interface amongst components of SDR and or host . Interface may include one or more connector planes and one or more components of SDR may be configured to plug into the connector plane s . Alternatively or additionally one or more components of SDR may be hard wired to interface and or directly connected to one or more other components of SDR and or to host . Interface may include one or more shared bus interfaces which may include a serialized data bus. This may be useful for example where a relatively large number of receiver slices and exciter slices are implemented.

Interface may include for example one or more of a Spacewire a LVDS a RS 422 a RS 232 an Ethernet and or a custom or proprietary interface. Spacewire refers to a spacecraft communication network based in part on an Institute of Electrical and Electronics Engineer IEEE standard 1355 titled Heterogeneous Interconnect. LVDS refers to a low voltage differential signaling system that can run at relatively high speeds over twisted pair cables.

SDR may include a power converter to provide one or more voltage levels to components of SDR . Power converter may receive power from host and may receive one or more control signals from DSP and or from host .

Additional exemplary features of SDR are disclosed below with reference to one or more of which include exemplary frequencies and bandwidths. For example receiver slice is described below with respect to an exemplary S band configuration and exciter slices and are described below with respect to exemplary S band and Ka band configurations respectively. SDR is not however limited to the exemplary frequencies and bandwidths. SDR may be configured receive and or transmit one or more of electromagnetic EM signals including radio frequency RF signals and optical signals.

In DSP may include one or more relatively low phase noise software configurable clock multipliers and or dividers to generate one or more corresponding system clock signals from reference signal fref . In the example of DSP includes a clock multiplier illustrated here as a 5 multiplier which may generate a 150 MHz clock from a 30 MHz reference signal fref . DSP may include one or more software configurable clock frequency translators which may include one or more numerically controlled clock frequency translators to generate one or more additional system clock signals.

In S band receiver slice includes a two stage super heterodyne down converter including a band down converter and an IF down converter .

S band receiver slice further includes a numerically controlled oscillator illustrated here as a directed digital synthesis DDS module to generate a reference tracking signal ftrack from a carrier tracking signal and a frequency synthesizer to generate first and second down converter reference signals and from reference tracking signal ftrack .

Firmware may include software configurable carrier tracking firmware to generate carrier tracking signal and to perform automatic gain control AGC alone or in combination with hardware . Carrier tracking firmware may be implemented within a filter firmware module such as described below with respect to . The filter firmware may be configured for example to execute transfer function mathematics associated with one or more of filtering gain and logic control of processing loops which may include one or more of automatic gain control AGC subcarrier symbol tracking coherency and phase locking.

Band down converter is configured to down covert a received signal to a first IF signal in response to first down converter reference signal .

IF down converter is configured to down convert first IF signal to a second IF signal in response to second down converter reference signal .

Frequency synthesizer may be controllable by DSP to define frequency down conversion channels. DDS module may be controllable by DSP to provide relatively finely tunable frequency agility to frequency synthesizer which may be useful for example with Doppler navigation sensor and or radio science applications.

Frequency synthesizer may include a fractional and integer frequency synthesizer to generate first down conversion reference signal to have a frequency that is N1 M1 times a frequency of tracking reference signal track and to generate second down conversion reference signal to have a frequency that is N2 M2 times a frequency of tracking reference signal ftrack . N1 M1 N2 and N2 may include software defined or selectable integers and or fractions of integers.

Frequency synthesizer may provide relatively fine frequency resolution with relatively low values of N which may provide loop architectures with relatively low phase noise and relatively fast settling times and which may provide relatively wide closed and open loop bandwidths.

In frequency synthesizer includes a dual phase locked loop PLL and first and second voltage controlled oscillators VCOs and to generate first and second down converter reference signals and respectively from tracking reference signal ftrack . PLL may be controllable by DSP through a control .

In DSP includes one or more analog to digital converters ADCs each to support one or more corresponding receiver slices and or or other functions such as sensors. The one or more ADCs may be controllable by firmware .

In the example of DSP includes an ADC to sample or under sample IF signal . ADC may sample or under sample signal at a software controllable rate.

Resultant samples are processed and demodulated to baseband I and Q waveforms within DSP . Demodulation may be performed within demodulation firmware which may provide flexibility. Demodulation firmware may be software configurable which may provide additional flexibility.

Demodulation firmware may be implemented within channel select firmware such as described below with respect to . The channel select firmware may further include firmware to reconfigure receive and transmit channel assignments and bandwidths. Reconfiguration of channel assignments may be controlled within associated band allocations.

Demodulation firmware may be software configurable to demodulate data that was modulated in accordance with one or more of a plurality of modulation scheme. Agility provided by direct digital synthesis numerically controlled frequency synthesis and or digitally controlled dithering may permit demodulation firmware to demodulate data that was modulated in accordance with one or more relatively complex modulation and pulse shaping schemes which may include for example and without limitation quadrature phase shift keying QPSK M ary phase shift keying M PSK quadrature amplitude modulation QAM M ary QAM M QAM and Gaussian minimum shift keying GMSK .

Firmware may include software configurable decoding firmware to decode demodulated data. The decoding firmware may include for example and without limitation one or more of a command executor and a Viterbi decoder. DSP may include a plurality of software selectable radio configurations or personalities and or may be configured to receive new personality up loads and the decoding firmware may be configured to apply a corresponding software selected decoding personality.

In firmware may include baseband modulation firmware to generate unfiltered in phase and quadrature phase I Q symbols .

Baseband modulation firmware may be software configurable to generate I Q symbols in accordance with one or more of a plurality of modulation and or pulse shaping schemes. Agility provided by direct digital synthesis and numerically controlled frequency synthesis may permit baseband modulation firmware to modulate with respect to one or more relatively complex modulation and pulse shaping schemes at relatively high data or sample clock rates. Exemplary modulation schemes include without limitation QPSK M PSK QAM M QAM and GMSK and oversampled and digitally pulse shaped I Q waveforms. Such agility may also permit baseband modulation firmware and or other elements to implement relatively complex pre distortion schemes such as to compensate for non ideal system effects such as power amplifier distortion.

Hardware may include a pair of I and Q digital to analog converters DACs for each exciter slice supported by SDR . In the example of hardware includes DACs and corresponding to S band exciter and DACs and corresponding to Ka band exciter .

In the example of S band exciter slice includes a numerically controlled oscillator illustrated here as a DDS module to generate a relatively low frequency carrier signal from a tracking reference signal and a frequency synthesizer to generate first and second up conversion reference signals and from reference signal fref . S band exciter slice further includes a two stage super heterodyne IF up converter to frequency up convert carrier signal to an S band signal carrier .

Frequency synthesizer may be controllable by DSP to define approximate frequency up conversion channels. DDS module may be controllable by DSP to provide relatively finely tunable frequency agility which may be useful for example with Doppler navigation sensor and or radio science applications.

Frequency synthesizer may include a fractional and integer frequency synthesizer to generate first up conversion reference signal to have a frequency that is N3 M3 times a frequency of reference signal fref and to generate second up conversion reference signal to have a frequency that is N4 M4 times a frequency reference signal fref . N3 M3 N4 and N4 may include software defined or selectable integers and or fractions of integers.

S band exciter slice further includes an I Q modulator to modulate S band carrier signal with I and Q signals and to sum the results and to output an S band modulated carrier signal .

In at least a portion of Ka band exciter slice may be configured similarly to S band exciter slice . For example Ka band exciter slice may include a numerically controlled oscillator illustrated here as a DDS module to generate a relatively low frequency carrier signal from a tracking reference signal and a frequency synthesizer to generate first and second up conversion reference signals and from reference signal fref . Ka band exciter slice further includes a two stage super heterodyne IF up converter to frequency up convert carrier signal to a carrier signal which may correspond to an S band carrier signal.

One or more up converter stages of IF up converter may be tuned to a different frequency than corresponding up converter stages of IF up converter in S band exciter slice .

Frequency synthesizer may be controllable by DSP to define approximate frequency up conversion channels. DDS module may be controllable by DSP to provide relatively finely tunable frequency agility.

Frequency synthesizer may include a fractional and integer frequency synthesizer to generate first up conversion reference signal to have a frequency that is N5 M5 times a frequency of reference signal fref and to generate second up conversion reference signal to have a frequency that is N6 M6 times a frequency reference signal fref . N5 M5 N6 and N6 may include software defined or selectable integers and or fractions of integers.

Ka band exciter slice may include a band up converter to up convert carrier signal to a Ka band carrier signal . Band up converter may include multiple up conversion stages such as a 4 up converter stage which may be useful for example to generate an X band carrier signal. Band up converter may include a subsequent 3 up converter stage which may be useful to up convert from X band to Ka band which may include a frequency of approximately 26 GHz. Alternatively or additionally band up converter may include a second 4 up converter stage to up convert from X band to a frequency in a range that includes one or more of 32 GHz and 38 GHz. A frequency multiplier may be useful for example where a suitable mixer is not commercially available for a desired up conversion step or a desired up converted frequency.

Ka band exciter slice and or S band exciter slice may include one or more additional frequency synthesizers which may provide additional band conversion flexibility.

Ka band exciter slice further includes an I Q modulator to modulate carrier signal with I and Q signals and to sum the results and to output a modulated carrier signal .

In the example of I Q modulation in exciter slices and is performed subsequent to frequency up conversion of corresponding carrier signals. Alternatively I Q modulation may be performed prior to or during frequency up conversion of a corresponding carrier signal. Performance of I Q modulation subsequent to carrier up conversion may permit a carrier signal to modulate with greater data bandwidth.

In band up converter includes an S to X band up converter to up convert S band carrier signal to an X band carrier signal illustrated here as including two 2 frequency multipliers. Band up converter further includes an X to Ka band up converter to up convert X band carrier signal to Ka band carrier signal .

Where an exciter slice includes a frequency multiplier a corresponding output may be filtered to compensate for non linear effects of the multiplier and I Q modulation may be performed subsequent to the filtering such as illustrated in to avoid imparting non linearity to the I Q data.

Agility and precision of DDS modules within a receiver slice and an exciter slice may permit synthesis of an output the exciter slice that is phase coherent with a received uplink carrier of the receiver slice .

For example in DSP includes coherency calculator firmware to generate tracking reference signals and corresponding to DSS modules and respectively from carrier tracking signal . Coherency calculator may be configured to control one or more of tracking reference signals and to provide coherency between receiver slice and S band exciter slice and or Ka band exciter slice .

With respect to Ka band exciter slice where band up converter includes a first and second 4 multiplication stages one or more other stages of Ka band exciter slice may be re tuned or reconfigured such as to provide suitable coherence with a receiver slice .

In receive path frequency synthesizer includes with first and second frequency synthesizers and respectively to generate first and second down conversion reference signals and from reference tracking signal ftrack in accordance with corresponding sets of numerical values N1 M1 and N2 M2.

Exciter path frequency synthesizer is illustrated with first and second frequency synthesizers and respectively to generate first and second up conversion reference signals and from reference signal fref in accordance with corresponding sets of numerical values N3 M3 and N4 M4.

In DSP includes clock circuits which may include one or more numerically controlled frequency translators. In the example of clock circuits include a clock divider to generate a reference signal from reference signal fref in accordance with a value RxDDcr and a clock multiplier to generate a reference signal from reference signal fref in accordance with a value TxDDcr. Clock divider and clock multiplier may be software configurable.

Clock divider DDS and frequency translator may synthesize system reference signals fref with carrier tracking signal to generate ftrack .

Coherency calculator may be configured to apply compensation values and to tracking reference signal to maintain a turn around ratio between received signal and carrier signal in exciter slice and or carrier signal in exciter slice in accordance with a turn around ratio TurnR. Values and may be determined to effectively remove effects of or contributions from reference signal fref from the turn around ratio.

Clock multiplier and DDS may synthesize tracking reference signal also referred to herein as a compensated carrier tracking signal with system reference signal fref .

Compensation values and may depend at least in part on a hardware configuration of SDR and the turn around ratio. Compensation values and may be determined or calculated with reference to a combination of a frequency of received signal a frequency of carrier signal and or a frequency of reference signal fref values N1 M1 N2 M2 N3 M3 RxDDcr TxDDcr a turn around ratio TurnR and one or more nominal values. Frequency synthesis may include dithering to provide additional precision with respect to and . Exemplary equations to determine compensation values and are provided below with respect to . Determination of compensation values and is not however limited to the exemplary equations herein.

DSP may include a plurality of software selectable sets of compensation values and each set corresponding to a turn around ratio TurnR and a set of software selectable configuration parameters. One or more sets of compensation values and may be pre computed and stored within DSP prior to a mission and or may be uploaded during a mission.

In USO freq represents the frequency of system reference signal . Rx freq represents the frequency of received signal . Tx freq represents the frequency of up converted carrier signal . Rx synR1 represents numerical values N1 and M1. Rx SynR2 represents numerical values N2 and M2. Tx synR1 represents numerical values N3 and M3. Tx SynR2 represents numerical values N4 and M4. RxDDScr represents a value applied to clock divider . TxDDScr represents a value applied to clock multiplier . Rx DDSnom represents a nominal value that carrier tracking firmware may add to carrier tracking signal . Tx DDSnom represents a nominal value that may be added to carrier signal prior within or subsequent to coherency calculator .

A set of values for Rx freq Tx freq USO freq Rx synR1 Rx SynR2 Tx synR1 Tx SynR2 Rx DDScR Tx DDScR Rx DDSnom may be determined for one or more turn around ratios TurnR in accordance with equations below  freq USO freq  freq USO freq and USO freq  freq . Where 1  DDS  syn1 syn2 and 1 DDS 1 1 12  syn1 syn2 .  freq USO freq  syn1 syn2 DDS . Where Turn  DDS  syn1 syn2  DDS 2.

An exemplary set of values are provided below for illustrative purposes. Methods and systems disclosed herein are not however limited to the exemplary values below.  freq 2092133333  DDSnom 43480011  syn1 154 74 76 2  syn2 121 15  DDS1 3 USO freq 3 10 Turn240 221  freq 2271999999.63801  DDSnom 23321089390  syn1 139 11 30 2  syn2 77 15 and  DDS5.

In firmware may include a plurality of processing components or cores one or more of which may be software configurable in response to software defined parameters. A core may be configured to perform one or more particular processing tasks and may be specifically designed and optimized with respect to the particular task s . A core may be configured with software programmable flexibility associated with the corresponding task s . The combination of software and firmware associated with a core may be optimized to balance capability power consumption and logic gate count.

Multiple cores may be configured to interface coordinate and or inter operate with one another such as under control of processor . The multiple cores may utilize one or more common clocks and or a bus network.

A core may be configured in a modular fashion at a top level and at sublevels. Such multi level modularity may reduce costs associated with firmware upgrades such as to modify a personality of SDR or a waveform.

Firmware and associated software may provide RF hardware interface abstraction user host interface abstraction firmware modularity software re configurability in flight waveform manipulation and autonomous action.

Firmware may include an application specific integrated circuit ASIC and may include a field programmable gate array FPGA . A FPGA may include a fuse based program once FPGA and or a re writeable or reprogrammable FPGA which may include one or more of SRAM and flash memory. A program once FPGA may provide a greater degree of radiation hardness. A rewriteable FPGA may provide greater flexibility such as for in flight uploads.

A channel select core may include software configurable firmware to define select or re configure up conversion and down conversion channel frequencies and bandwidths such as described with respect to one or more examples above. Channel select core may include demodulation firmware in .

A filter core may include software configurable firmware to implement performance driving functions such as loop filters such as described in one or more examples above. Filter core may include carrier tracking module to generate carrier tracking signal and coherency calculator firmware to maintain a turn around ratio such as described above. Coherency calculator firmware may include firmware to apply and such as described above.

A clock manager core may include software configurable firmware to generate one or more clock signals from reference signal fref in response to software defined parameters to be used by one or more components of SDR . Alternatively or additionally clock manager core may include software configurable firmware to apply one or more software defined numerical values to one or more hardware based numerically controlled clock circuits.

A modulation core may include software configurable firmware to implement modulation such as described with respect to one or more examples above.

An encoder core may include software configurable firmware to implement one or more encoding techniques in accordance with software defined parameters. Encoder core may include for example turbo encoding firmware. Encoder core may be software configurable to operate with respect to multiple rates and frame sizes without modification of firmware . The multiple rates and frame sizes may correspond to a Consultative Committee for Space Data Systems CCSDS standard such as a CCSDS 131.0 B 1 standard titled TM Synchronization and Channel Coding published in September 2003 by the CCSDS Secretariat Office of Space Communication Code M 3 National Aeronautics and Space Administration Washington D.C. 20546.

Encoder core may be implemented in a modular fashion such that one or more sub cores associated with corresponding encoding frameworks may be added to or removed from encoder core with little or no impact on other cores or sub cores. Encoder core may include for example a low density parity check LDPC encoder core.

A hardware interface core may include firmware to provide a relatively abstract interface to devices and sensors throughout SDR . Hardware interface core may permit processor to manipulate hardware slices and to support multiple receiver slices and multiple exciter slices . Hardware interface core may be configured to permit SDR to operate with less than all permitted slices installed. For example and without limitation hardware interface core may be configured to support up to two receiver slices and up to two exciter slices and may be operable with less than two receiver slices and or two exciter slices . Hardware interface core may be configured to provide variable refresh rates such as to scale power consumption with capability. Hardware interface core may be configured to initiate device scrubbing reloading and or failure detection and correction such as in response to external device radiation faults.

A host interface core may include firmware to provide a relatively abstract interface of SDR to host or other systems alone or in combination with processor . Host interface core may be implemented with a modular firmware configuration which may permit customization of physical and electrical layers associated with radio interfaces and which may permit SDR to be reconfigured for different missions with little or no impact to other modules of the interface firmware. This may reduce non recurring engineering NRE costs. Software associated with processor which may include C code may serve to abstract away relatively complex status collection and mode command routines. The software may be configured to provide various levels of in flight reprogram ability which may vary amongst missions.

Firmware may include firmware to monitor voltages and temperatures within SDR which may be available as software defined status telemetry points through interface in . Interface may include multi master serial computer bus such as an inter integrated circuit I2C bus to permit monitoring of voltages temperature and or other sensors within SDR and or external of SDR .

In DSP may include memory . In memory may include one or more of programmable read only memory PROM which may be used to store default or failsafe radio personalities and software electrically erasable PROM EEPROM which may be used to store uploaded software defined parameters or radio personalities and static random access memory SRAM for scratch and other temporary storage.

In power converter may be configured to generate a core set of one or more voltage levels and S band receiver slice exciter slices and and DSP may be configured to generate corresponding custom voltages from the standard secondary voltages. Power converter may provide independent voltage banks for receiver slices exciter slices reference oscillator and DSP and may provide voltage sequencing within one or more of the banks and may synchronize to reference oscillator .

Where power converter operates on a single primary bus voltage input DSP and or host may be configured to gate voltages associated with receiver slices and exciter slices . Gating may be implemented within power converter and or within receiver slices and exciter slices .

SDR may be configured with a pulse off feature to momentarily turn off power converter or portions thereof. This may reduce risk of damage where for example a primary bus voltage is hard wired on. A pulse off feature may be used to recover from single event effects due to radiation.

A plurality of exciter slices may share a power converter secondary voltage bank and may be configured to be independently gated on and off such as with field effect transistor FET switches within exciter slices controlled by firmware .

Methods and systems disclosed herein may be implemented to provide desired RF performance and frequency band coverage with relatively low mass and low power consumption and may be implemented substantially with commercially available components which may reduce development and manufacturing costs. Alternatively or additionally band tuning capability may be provided with future monolithic microwave integrated circuit MMIC based voltage controlled oscillators VCOs having relatively low phase noise and low power consumption.

A modular SDR as disclosed herein may be readily upgradeable with future technology and or modified for other applications.

The Unites States National Aeronautics and Space Administration NASA has promulgated a Space Telecommunications Radio System STRS specification to define a standard architecture for space qualified radios in support of NASA missions. STRS version 1.0 was released December 2005. SDR or portions thereof may be configured in accordance with a Space Telecommunications Radio System STRS specification promulgated by NASA such as version 1.0 released December 2005 and or subsequent versions.

Additional exemplary parameters and corresponding exemplary configurations of SDR are provided in Table 1 below.

One or more features disclosed herein may be implemented in hardware software firmware and combinations thereof including discrete and integrated circuit logic application specific integrated circuit ASIC logic and microcontrollers and may be implemented as part of a domain specific integrated circuit package or a combination of integrated circuit packages. The term software as used herein refers to a computer program product including a computer readable medium having computer program logic stored therein to cause a computer system to perform one or more features and or combinations of features disclosed herein.

Methods and systems are disclosed herein with the aid of functional building blocks illustrating the functions features and relationships thereof. At least some of the boundaries of these functional building blocks have been arbitrarily defined herein for the convenience of the description. Alternate boundaries may be defined so long as the specified functions and relationships thereof are appropriately performed.

While various embodiments are disclosed herein it should be understood that they have been presented by way of example only and not limitation. It will be apparent to persons skilled in the relevant art that various changes in form and detail may be made therein without departing from the spirit and scope of the methods and systems disclosed herein. Thus the breadth and scope of the claims should not be limited by any of the exemplary embodiments disclosed herein.

