---

title: Method and system for interface detection
abstract: A method and system for detecting the location of an air/sea interface on an Instrumented Tow Cable (ITC) when distributed temperature measurements are provided. The air/sea interface is determined by estimating the variance of observed temperature in the proximity of each measurement cell. The method and system described herein uses a sliding variance across the entire cable length. The variance of the cell or cells in the area of the interface has been found to be large compared to other cells. Accordingly, the location of the air/sea interface is determined based on the location of the peak variance. The location of the air/sea interface is used in determining the catenary of the ITC.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08047709&OS=08047709&RS=08047709
owner: The United States of America as represented by the Secretary of the Navy
number: 08047709
owner_city: Washington
owner_country: US
publication_date: 20090327
---
The invention described herein may be manufactured and used by or for the Government of the United States of America for governmental purposes without the payment of any royalties thereon or therefor.

The present invention relates to the detection of an air sea interface and more specifically to detection of the interface during distributed temperature measurements using an Instrumented Tow Cable.

As is known in the art an Instrumented Tow Cable ITC can be used to measure the ocean temperature profile in relation to depth with an order of magnitude improvement in spatial resolution as compared to other known systems.

The ITC measures the temperature along an optical fiber cable with a spatial resolution of one half meter to one meter and a temporal resolution of approximately two to three minutes. As is known to those ordinarily skilled in the art the measurement is performed using light scattered from within optical fibers integrated into a tow cable.

The ITC uses known Optical Time Domain Reflectometry OTDR techniques to determine the precise location of each measurement cell along the cable length. A depth sensor at the bottom of the cable is used to determine the depth at the end of the cable. To obtain the depth of each temperature measurement it is assumed that the entire cable tows at the same incidence angle with respect to the flow the critical angle. The critical angle is that angle where the weight and drag of the cable balance.

For neutrally buoyant towed array systems the assumption of a zero critical angle tow is in practice very accurate. However when a heavy variable depth body is towed such an assumption of a critical angle is no longer valid. In the case of towing a heavy variable depth body a lookup table needs to be generated to provide the cable catenary as a function of tow speed. Once the catenary is known and the depth is known at the end of the cable the depth for each temperature measurement made using the ITC method can be assigned.

While the critical angle can be estimated from Equation 2 the critical angle can be measured more accurately based on the total length of the cable in the water and the total depth of that length. The total depth can be determined using the depth sensor as described above.

What are needed are a method and system for more accurately measuring the total length of the cable in water i.e. the length of cable from the air sea interface to the end of the cable in the water . If the position on the cable where the cable enters the water referred to herein as the air sea interface can be determined then the total length of the cable in the water can be ascertained.

It is therefore a general purpose and primary object of the present invention to provide a method and system for detecting the location of the air sea interface on an Instrumented Tow Cable during distributed temperature measurements.

The air sea interface is determined by estimating the variance of observed temperature in the proximity of each measurement cell. The method and system described herein use a sliding variance over the entire cable length. As is known in the art the variance of the cell or cells in the area of the interface has been found to be large compared to other cells. Accordingly the location of the air sea interface is determined based on the location of the peak variance.

In one embodiment a method of determining a position of an interface along a temperature sensing cable passing through the interface comprises obtaining multiple temperature readings at each of a plurality of measurement cells along the cable determining locations of the measurement cells along the cable obtaining variance estimations in proximity of each of the locations based on the multiple temperature readings and determining the position of the interface based on the position having the largest of the variance estimations.

In another embodiment the variance estimations are obtained over sliding windows along the cable. The method further comprises obtaining a representative temperature for each of the locations based on the multiple temperature readings. The representative temperature can be one of an average an arithmetic mean a geometric mean a mode or a combination thereof of the multiple temperature readings at each of the plurality of measurement cells. The locations can then be determined through optical time domain reflectometry.

In yet another embodiment the method further comprises obtaining at least one of an average an arithmetic mean a geometric mean and a mode of the multiple temperature readings at each of the plurality of measurement cells.

In yet another embodiment the method further comprises the step of determining a base depth of an end of the cable beneath the interface and determining a catenary describing a shape of the cable based in part on the base depth and the position of the cable.

The method further comprises obtaining depths of the locations beneath the interface based on the catenary obtaining representative temperatures for the locations based on the multiple temperature readings and constructing a temperature in relation to depth profile based on the representative temperatures and the depths of the locations.

The representative temperatures can be obtained from one of an average an arithmetic mean a geometric mean and a mode of the multiple temperature readings at each of the plurality of measurement cells. The base depth can be determined based on a reading from a depth sensor.

The catenary can be further determined based on one or both of a tow speed of the cable and a length of the cable. The variance estimations can be obtained over sliding windows along the cable.

In one embodiment a processor program product disposed on a processor readable medium can have instructions for causing at least one processor to receive multiple temperature readings from each of a plurality of measurement cells along a temperature sensing cable to determine locations of the measurement cells along the cable based on optical time domain reflectometry to obtain variance estimations over sliding windows along the cable in proximity of each of the locations based on the multiple temperature readings and to determine a position along the cable of an interface through which the cable passes based on the position having the largest variance estimation.

In another embodiment the processor program product can have further instructions for causing the at least one processor to receive a base depth reading from a depth sensor at the end of the cable beneath the interface to determine a catenary describing a shape of the cable based at least in part on the base depth and the position to determine depths of the locations beneath the interface based on the catenary to determine representative temperatures for the locations based on the multiple temperature readings and to construct a temperature in relation to a depth profile based on the representative temperatures and the depths of the locations.

The processor program product can have further instructions for causing the at least one processor to determine the representative temperatures based on one or more of an average an arithmetic mean a geometric mean or a mode of the multiple temperature readings at each of the plurality of measurement cells. Further instructions can cause the processor to determine the catenary based on one or more of a tow speed of the cable or a length of the cable.

Referring now to there is shown a view of vessel towing ITC . Near end of the ITC is attached to the vessel and distal end of the ITC is at depth D below air sea interface . Depth sensor is connected to the distal end and communicates the depth D of the distal end to the vessel .

The ITC measures the temperature along a length of the ITC using light scattered from optical fibers integrated into the ITC. Using optical time domain reflectometry OTDR techniques as are known to those ordinarily skilled in the art the location of each measurement along the length of the ITC can be determined. Typical ITCs have a spatial resolution of one half to one meter along the cable. Temporal resolution of ITCs is in the range of two to three minutes with a series of measurements being averaged over that time period.

To obtain temperature measurements at various depths below the interface a heavy and variable depth body is connected to the distal end . The body maintains the distal end below the interface . Thus a temperature measurement at a known location along the length of the ITC corresponds to a certain depth d beneath the interface and a temperature profile can be obtained.

Generally those of skill in the art assume that the ITC forms a catenary the shape of which depends on the speed at which the ITC is towed. Thus the relationship between and d can be computed using known catenary formulas based on the known total length of the ITC the depth D of the body determined using the depth sensor and the tow speed indicated by direction arrow . However such computed catenaries are subject to errors due to underwater currents tow speed errors and the like. The accuracy of the computed catenaries can be improved by determining the point along the ITC that passes through the air sea interface .

Referring now to a detailed view of section of the ITC at the air sea interface is illustrated. Due to wave motion at the air sea interface illustrated by waves and pitching of the vessel not shown in which moves the ITC up and down the section is exposed to both air and water. A typical period for ocean waves and ship pitching is about five seconds. Thus the alternation between air and water can happen multiple times over a three minute measurement period.

As previously described the ITC obtains a series of temperature measurements over a two to three minute measurement period. Typically the series of measurements can be averaged to obtain the temperature measurement for the period. Due to the movement of the section above and below the interface the variance of the series of measurements for the section is found to be greater than that of other sections of the ITC .

Using a sliding variance across the entire length of the ITC the peak variance can be determined. The location of the peak variance corresponds to the location of the section along the ITC . This information can be included in the catenary computations resulting in more accurate temperature profiles.

Referring now to there is shown a block diagram of method for determining a location of an air sea interface. As is known in the art temperature readings are obtained Step at a number of measurement cells along an ITC such as the ITC of . Known OTDR techniques are used to determine the location of each measurement as at Step . Additional readings are obtained at each location for a predetermined time period as indicated at Step .

Using the multiple readings a representative temperature and an estimation of variance of the temperature readings in proximity of each location are obtained as indicated at Step . The representative temperature may be determined based on an average of the multiple readings at a location. The variance estimations are obtained over sliding windows along the length of the ITC using variance estimation techniques well known in the art. The parameters used in the sliding windows variance estimations will depend on the spatial resolution of the ITC.

In general the window size that is selected for variance calculation is at least twelve times larger than the spatial resolution of the measurement. This provides an ensemble of at least twelve independent measurements to go into the variance calculation. An ensemble size of at least twelve samples is necessary for meaningful statistical tests. The overlap that used for successive windows can vary but 50 overlap is a typical value used such that the peak variance can be resolved.

The location along the ITC corresponding to the air sea interface is determined Step based on having the largest variation. The depth of the heavy and variable depth body being towed by the ITC is determined Step using a depth sensor located on or near the body. The catenary for the ITC is determined Step based on the total length of the ITC the depth the tow speed and the location of the air sea interface.

Based on the locations determined at the Step and the catenary obtained at the Step the depths of each location can be obtained Step . A profile of the representative temperature with depth then can be constructed for the predetermined time period as indicated at Step and for each succeeding time period as indicated by return Step .

What have thus been described are a method and system for detecting the location of the air sea interface on an ITC during distributed temperature measurements. OTDR techniques can determine the precise location of each temperature measurement along the cable length. The air sea interface is determined by estimating the variance of the temperature measurements in the proximity of each measurement location using a sliding variance across the entire cable length. The location of the air sea interface is determined based on the location of the peak variance.

The location of the air sea interface is used in determining the catenary of the ITC. In turn the catenary provides the relationship between a location on the ITC and the depth of that location below the interface. Accordingly a temperature in relation to depth profile can be constructed.

The method and system described herein also provide for an enhanced ability to determine the catenary of an ITC and hence a more accurate temperature in relation to depth profile. Additionally the method can be easily automated. Known algorithms for computing sliding variance as well as catenary computations can be incorporated into processors currently employed in obtaining and converting raw ITC temperature data. Thus the method described herein can be automated and a temperature in relation to depth profile can be displayed directly to a system operator.

Obviously many modifications and variations of the present invention may become apparent in light of the above teachings. For example over the predetermined time period the representative temperature can be taken as the mean of the temperature readings. Alternatively the representative temperature can be determined by other known mathematical techniques such as geometric mean or mode.

The method described can be generalized to perform boundary detection across OTDR based temperature measurements other than that of an air sea interface. As an example the air liquid interface of a mixing vat may be obtained using the methods described herein. In environments having little or no wave action the ITC can be moved in an up and down motion such that air and liquid temperatures at the interface can be sampled over one section of the ITC.

It will be understood that many additional changes in details materials steps and arrangements of parts which have been described herein and illustrated in order to explain the nature of the invention may be made by those skilled in the art within the principle and scope of the invention as expressed in the appended claims.

