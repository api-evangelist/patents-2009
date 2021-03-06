---

title: System and method for allocating business to one of a plurality of sellers in a buyer driven electronic commerce system
abstract: A system and method for allocating conditional purchase offers (CPO) among a plurality of agency-based and broadcast-based sellers in a buyer-driven commerce system. In one embodiment, the system determines which agency-based or broadcast-based sellers can fulfill or satisfy the CPO and orders those sellers in a priority order. In another embodiment, the priority is determined by relative market share and number of recent opportunities to satisfy the CPO. In another embodiment, the priority is also determined by metrics and buyer information. In another embodiment, the priority is determined randomly. The system ensures that when a buyer can satisfy the CPO at multiple prices levels, the highest price level fulfills the CPO. This ensures maximum seller revenue for each CPO.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08548871&OS=08548871&RS=08548871
owner: Priceline.com Incorporated
number: 08548871
owner_city: Stamford
owner_country: US
publication_date: 20090220
---
This is a Continuation of prior U.S. patent application Ser. No. 09 252 574 filed Feb. 18 1999 now U.S. Pat. No. 7 516 089 entitled SYSTEM AND METHOD FOR ALLOCATING BUSINESS TO ONE OF A PLURALITY OF SELLERS IN A BUYER DRIVEN ELECTRONIC COMMERCE SYSTEM which in turn is a Continuation In Part of prior U.S. patent application Ser. No. 08 889 319 entitled Conditional Purchase Offer Management System filed Jul. 8 1997 now U.S. Pat. No. 6 085 169 which in turn is a Continuation In Part of prior U.S. patent application Ser. No. 08 707 660 filed Sep. 4 1996 U.S. Pat. No. 5 794 207 issued Aug. 11 1998 . The entire contents of the aforementioned applications are herein expressly incorporated by reference.

The present invention relates generally to a system for processing the sale of goods and services and more particularly to a system and method for the allocation of business among multiple sellers within a buyer driven commerce system.

Most systems for processing the sale of products are seller driven whereby the seller prices packages configures and offers the product for sale and the buyer decides whether or not to accept the seller s offer. In a buyer driven system however the buyer dictates the terms of the offer and one or more sellers decide whether or not to accept the offer. A help wanted advertisement for example is a buyer driven inquiry since the employer is looking to locate and buy the services of a qualified employee. The inquiry is advertised to a large number of potential employees who may respond by submitting their resumes to the prospective employer.

Priceline.com Incorporated of Stamford Conn. is a merchant that has successfully implemented a buyer driven system for the sale of products such as airline tickets and automobiles. Priceline.com utilizes a Conditional Purchase Offer CPO Management System described in U.S. Pat. No. 5 794 207 and International Application Number PCT US97 15492 that processes Conditional Purchase Offers and or Binding Conditional Purchase Offers Binding CPO s received from individual consumers. These CPO s contain one or more buyer defined conditions for the purchase of goods or services at a buyer defined price. The Binding CPO s are typically guaranteed by a general purpose account such as a debit or credit account and thereby provide sellers with a mechanism for enforcing any agreement that may be reached with the consumer. The CPO s are provided by the CPO management system to sellers either directly or using seller supplied rules for individual sellers to either accept or reject. If a seller accepts a Binding CPO the CPO management system binds the buyer on behalf of the accepting seller to form a legally binding contract.

Thus the CPO management system empowers individual consumers to obtain goods and services at a price set by the consumer. The CPO management system provides numerous commercial advantages to sellers as well. For example the CPO management system permits individual sellers to effectively sell excess capacity when actual demand fails to meet forecasted demand. In particular the CPO management system provides an effective mechanism for sellers to be confident that if they accept a consumer s offer the consumer will purchase the requested goods or services at the agreed upon price and not just use the information to ascertain the seller s underlying level of price flexibility which if known to a seller s competitors or customers could impact the seller s overall revenue structure.

For some sellers and the airline industry in particular response to an individual CPO is difficult without significant re engineering of the existing transaction processing system. As a result these sellers empower an agent to manage buyer driven commerce transactions. These sellers become agency based sellers with a CPO management system acting as their agent. However with multiple agency based sellers there is no method for the CPO management system to allocate CPO s among the agency based sellers.

It is also possible that an agency based seller can satisfy a CPO with more than one seller defined CPO rule. There currently exists no method for the CPO management system to select the seller defined CPO rule generating the maximum revenue for the agency based seller.

For broadcast based sellers some form of allocation is also desirable. This is particularly helpful where allocation based on the order of seller response is not possible or appropriate. For example if two broadcast based sellers respond at the same time there must be some method for allocating the CPO among them. Similarly for broad cast based sellers it may be appropriate to allocate or limit the CPO to particular sellers based on region of business market area service history or other factors.

The invention provides a system and method for allocating conditional purchase offers CPOs in a buyer driven system. First look and second look sellers are identified based on their market share in a relevant market. In identifying first and second look sellers the system and method also considers the numbers of first look opportunities given as compared to numbers of first look opportunities due. The first look seller is given the first opportunity to satisfy the CPO. If the first look seller is unable to satisfy the CPO the second look seller is given an opportunity to satisfy the CPO. If neither the first nor second look sellers are able to satisfy the CPO the system performs a price oriented search across the remaining sellers.

When a seller is able to satisfy the CPO with more than one rule or price the system and method preferably identify the highest value rule or highest price that will satisfy the CPO. In this manner the seller maximizes its revenue from a CPO.

The Figures are understood to provide representative illustration of the invention and are not limiting in their content.

Agency Based Seller A seller who has delegated authority to the CPO Management System to accept or reject a given CPO using seller defined CPO Rules

Broadcast Based Seller A seller who has received a CPO from the CPO Management System directly or by for example access to an electronic posting for evaluation.

Conditional Purchase Offer CPO An offer containing one or more conditions submitted by a buyer for the purchase of goods and or services at a buyer defined price.

Binding Conditional Purchase Offer Binding CPO A binding offer containing one or more conditions submitted by a buyer for the purchase of goods and or services at a buyer defined price. As compared to a CPO a Binding CPO includes a payment guarantee for example with a General Purpose Account and authorization to debit the Account upon acceptance of the Binding CPO.

Conditional Purchase Offer CPO Rule A restriction defined by a Broadcast Based or Agency Based Seller under which the operator of the CPO Management System may act as an agent to determine whether to fill a CPO for that Seller.

CPO Management System A controller that receives and processes CPO s for one or more goods or services from one or more buyers to determine if one or more sellers Agency Based or Broadcast Based Sellers are willing to accept a CPO.

General Purpose Account Any account from which payment can be made including a credit or debit account.

First Look Opportunity The initial opportunity given to a seller to satisfy a CPO when the CPO management system allocates a CPO among multiple sellers.

Second Look Opportunity The follow up opportunity given to a seller to satisfy a CPO when the CPO management system allocates a CPO among multiple sellers. If the CPO is unsatisfied in the first look opportunity the seller given the follow up opportunity to satisfy the CPO receives the second look opportunity.

Rule A restriction or restrictions defined by a seller which must be satisfied before the seller will honor a particular price or sale. In the airline industry rules include among other requirements black out dates day of week for origination minimum and maximum stay length advanced purchase requirements and cancellation change terms.

Metric A ranking parameter used to prioritize sellers. A metric can include seller factors such as market share buyer factors such as preference and random factors.

As shown in the CPO management system preferably includes a central controller discussed further below in conjunction with . The CPO management system may provide a given CPO to selected sellers based on predefined screening criteria so that sellers only obtain CPO s that they may be interested in or are authorized to screen or have the potential to fulfill. Alternatively the CPO management system may provide all CPO s to all sellers for screening.

As discussed further below each buyer contacts the CPO management system for example by means of telephone facsimile online access i.e. the Internet electronic mail in person contact or through an agent and provides the CPO management system with the terms of the buyer s CPO. It is noted that each buyer and seller may employ a general purpose computer for communicating with the CPO management system . Though not illustrated the general purpose computer is preferably comprised of a processing unit a communication device e.g. a modem memory means and any software required to communicate with the CPO management system .

The CPO management system as well as any general purpose computers utilized by buyers or sellers collectively the nodes preferably transmit digitally encoded data and other information between one another. The communication links between the nodes preferably comprise a cable fiber or wireless link on which electronic signals can propagate.

According to one feature of the present invention the CPO management system preferably provides an optional agency feature that permits the CPO management system to accept or reject a given CPO on behalf of certain agency based sellers who have delegated such authority to the CPO management system . Thus the CPO management system preferably i evaluates CPO s on behalf of certain agency based sellers who have delegated authority to the CPO management system to accept or reject a given CPO and ii permits broadcast based sellers such as sellers to evaluate CPO s independently.

Thus the CPO management system can preferably provide one or more CPO s to each broadcast based seller for the seller to independently determine whether or not to accept a given CPO. It is noted that the CPO management system can provide a CPO to each appropriate broadcast based seller for example by means of a broadcast transmission or by means of posting the CPO for example on an electronic bulletin board accessible by each broadcast based seller . Alternatively the CPO management system can evaluate one or more CPO s against a number of CPO rules defined by one or more agency based sellers to decide on behalf of an agency based seller to accept or reject a given CPO. An illustrative set of CPO rules for illustrative agency based sellers is set forth in .

Thus the CPO management system can determine if one or more sellers accepts a given CPO by broadcasting the CPO to each seller and receiving an acceptance or rejection or by applying the CPO to the CPO rules to render a decision to either accept reject or counter a CPO on behalf of an agency based seller .

As discussed further below a CPO rule is a set of restrictions defined by a given agency based seller for which the seller is willing to accept a CPO. For a more detailed discussion of CPO rules the manner in which they are generated and related security issues see U.S. patent application Ser. No. 08 889 319 entitled Conditional Purchase Offer Management System filed Jul. 8 1997 and U.S. Pat. No. 5 794 207.

The ROM and or data storage device are operable to store one or more instructions discussed further below in conjunction with which the CPU is operable to retrieve interpret and execute. For example the ROM and or data storage device preferably store processes to accomplish the transfer of required payments charges and debits between the sellers and buyers . The processing of such accounting transactions are preferably secured in a conventional manner for example using well known cryptographic techniques.

The data storage device includes at least a seller database a buyer database an offer database and a seller rules database . The seller database preferably stores information on each seller which is registered with the CPO management system to sell goods or services to CPO buyers including contact information. The buyer database preferably stores information on each buyer of the CPO management system including identification information and billing information such as a credit card number. The offer database preferably contains a record of each CPO being processed by the CPO management system including the conditions associated with the CPO and the associated status. The seller rules database preferably maintains the CPO rules for one or more agency based sellers .

In addition the data storage device includes a CPO evaluation process and a rules evaluation subroutine discussed further below in conjunction with B and respectively. Generally the CPO evaluation process i receives each CPO from a buyer ii provides each CPO to the appropriate broadcast based sellers and evaluates each CPO against the appropriate rules of each agency based seller and iii determines whether any sellers accept the CPO. The rules evaluation subroutine is a subroutine executed by the CPO evaluation process which receives a CPO and compares the CPO against the rules of one or more agency based sellers to generate a response on behalf of the sellers to the given CPO.

Having described the system of the present invention a first method of the invention will be described. At step of the system receives a CPO from one of the plurality of buyers .

At step if the system determines that the CPO is not valid the system requests the buyer retransmit the offer.

At step if the system determines that the payment identifier is not valid the system requests the buyer retransmit the payment identifier.

At step the system transmits the offer to broadcast based sellers and executes a rules evaluation subroutine for agency based sellers. The rules evaluation subroutine is discussed below in conjunction with .

At step when the system receives more than one acceptance signal the system selects one acceptance signal.

At step if the CPO is not a binding CPO the system determines whether the buyer defaulted or reneged.

At step if the buyer defaults or reneges the system collects a penalty from the buyer and then ends the CPO evaluation process at step .

As discussed above the CPO evaluation process executes a rules evaluation subroutine during step of to determine if one or more agency based sellers are willing to accept a CPO.

At step of the system compares the CPO with corresponding restrictions as set forth in any CPO rules that are defined by agency based sellers .

At step if the system determines that a CPO rule is satisfied the system identifies the corresponding seller.

At step the system returns to the rules evaluation subroutine with an indication of whether a rule was or was not satisfied at step .

The steps thus described and illustrated in B and allow the system to accept and validate a CPO transmit the CPO to broadcast based sellers execute a rules evaluation routine for agency based sellers determine whether any seller accepts and bind the CPO when a seller accepts assuming the CPO is a Binding CPO . The method in B and does not provide a method to allocate a CPO among multiple agency based sellers . Such a method to allocate a CPO to multiple agency based sellers in accordance with a predetermined strategy is described in greater detail with reference to .

With multiple agency based sellers the system uses information in the seller database in and the seller rules database in to determine whether any of the agency based sellers can satisfy a CPO. As an example in the seller rules database in includes information on flight schedules for multiple agency based sellers of airtravel. Depending on the restrictions in a CPO more than one of those agency based sellers may be able to satisfying the CPO. Thus if the CPO merely requires departure from New York and a destination in California during the first quarter of 1997 two agency based sellers can satisfy the CPO. One agency based seller has a flight originating in New York on Jan. 1 1997 and terminating in Los Angeles with a stop in Chicago. Another agency based seller has a non stop flight originating in New York on Mar. 3 1997 and terminating in San Francisco. However agency based seller is unable to satisfy the CPO because the departure point is not New York and the date is not in the first quarter of 1997.

As thus described with more than one agency based seller able to satisfy a CPO system must have a method to allocate the CPO among the agency based sellers. Additionally when multiple agency based sellers are able to satisfy a CPO and they are further able to satisfy the CPO at different prices the system must desirable allocate the CPO to one particular agency based seller and must further allocate the CPO to one of the possible prices. These steps are described below in greater detail with reference to .

A method to allocate a CPO among multiple agency based sellers is illustrated in . At step system receives data from a buyer and forms a CPO. This step is functionally the same as described at steps through in .

At step the system determines which of the agency based sellers can possibly satisfy the CPO. As an example if the CPO is for air travel with specified departure and destination points only agency based sellers servicing those departure and destination points can possibly satisfy the CPO. The other agency based sellers are unable to satisfy the CPO and are excluded from further consideration. Similarly if an agency based seller has no qualifying prices that could satisfy the CPO they are unable to satisfy the CPO and are excluded from further consideration. The system thus uses multiple factors to determine whether a seller can possibly satisfy the CPO.

At step the system determines a first look opportunity seller from those agency based sellers that can possibly satisfy the CPO. This determination is based on a metric which in the preferred embodiment considers a relative market share of all the agency based sellers that could satisfy the CPO. The system assigns the first look opportunity to the seller with the largest relative market share in the market offered in the CPO with consideration for the number of first look opportunities provided to that agency based seller versus the number of first look opportunities due to that agency based seller.

The system records numbers of first look opportunities provided to sellers for different CPOs. This historic information forms part of the consideration for allocation of first look opportunities. When the system receives a new CPO the historic information on opportunities provided for each seller is compared to the number of opportunities that are due for each seller. As a result of many factors the number of opportunities due and the number of opportunities provided are seldom in agreement and the system attempts to bring them into closer agreement by weighting or biasing allocation to the seller that is most out of agreement. The disagreement can be a simple numerical difference between opportunities due and provided or a percentage difference between opportunities due and provided.

With multiple factors considered in the metric to determine which agency based seller gets the first look opportunity some weighting or priority of factors is required. If the relative market share is normalized among agency based sellers who can possibly satisfy the CPO that relative market share can have a value between zero percent 0 and one hundred percent 100 . With two agency based sellers A B that can each satisfy the CPO and seller A having three times the relative market share of seller B in the relevant market then seller A with the larger share would have a relative market share of 75 while seller B with the smaller share would have a relative market share of 25 .

With these relative market shares in the relevant market seller A will receive seventy five percent 75 of the first look opportunities e.g. three out of four first look opportunities while seller B will receive twenty five percent 25 of the first look opportunities e.g. one out of four first look opportunities .

At step the system also determines the seller receiving the second look opportunity in the same manner that the first look opportunity is determined.

At step the system determines whether the seller receiving the first look opportunity satisfied the CPO.

At step if the seller receiving the first look opportunity did not satisfy the CPO the system determines whether the seller receiving the second look opportunity satisfied the CPO.

At step if either of the sellers receiving the first look opportunity or the second look opportunity satisfies the CPO the system binds the CPO to create a Binding CPO and informs both the buyer and seller.

At step if neither of the sellers receiving the first look opportunity or second look opportunity satisfied the CPO the system determines whether there are remaining sellers.

At step if there are no remaining sellers the system notifies the buyer that no seller was able to satisfy the CPO.

At step of if there are remaining sellers the system performs a low price lookup from all sellers and selects the lowest price satisfying the CPO.

At step the system determines whether any seller satisfied the CPO. If a seller was able to satisfy the CPO the system binds the CPO and informs the buyer and seller at step of .

If no seller was able to satisfy the CPO during the low price lookup the system so notifies the buyer at step of .

As illustrated in the system gives the highest priority agency based seller an opportunity to satisfy the CPO. It is possible that an agency based seller will be able to satisfy a CPO with more than one rule. For example if a CPO includes a price term of 300.00 and the priority agency based seller can satisfy the CPO with two rules having prices of 250.00 and 270.00 the system must decide which rule to fulfill the CPO with. In the example the CPO binds at 300.00 but the specific question is whether the system fulfils the CPO at 250.00 or 270.00.

In the described embodiment when more than one rule satisfies the CPO the system selects the highest value or highest priced rule that will satisfy the CPO. In this manner the system fulfils the CPO at the highest price or value satisfying the CPO though the system binds the CPO at the price specified by the buyer. This ensures that the agency based seller can also fulfil another CPO which could only be fulfilled at the lower price. It also assures agency based sellers that they will receive the maximum possible revenue for each CPO they fulfil. Without these assurances certain agency based sellers might decline to participate.

It is also possible that factors other than price are used instead of or in addition to price in selecting a particular seller. In the airline industry examples of these other factors include level of service date time of flight seat class or booking options and day of week of travel.

Using the CPO management system illustrated in the preferred embodiment of the method illustrated in allows agency based sellers a first look and second look opportunity to fulfil or satisfy a CPO based on a predetermined metric. The metric described is relative market share in a relevant market. When a seller can satisfy a CPO with more than one rule the system allows the seller to maximize revenue with the highest price or highest value CPO. Various alternative embodiments are also available.

The metric that system uses at step of to determine the first and second look sellers can be something other than an adjusted market share. For example the metric can be based on total market share without adjustment for the relevant market e.g. origin destination pair . Alternatively the metric can be based on a random number. It is also possible that a buyer preference metric is used. A buyer preference metric can be a buyer requirement regarding a particular agency based seller as a condition of the CPO. For example the buyer may indicate a preference for a particular agency based seller or an unwillingness to accept a particular agency based seller.

At step system orders agency based sellers in priority order from highest to lowest for the first look opportunity to satisfy the CPO. As previously described system uses a metric such as market share adjusted market share random number or a buyer specific metric to order the sellers.

At step if the seller was able to satisfy the CPO the system binds the CPO and informs the buyer and seller.

At step if the system determined that the seller was not able to satisfy the CPO the system identifies that highest priority seller as unable to satisfy the CPO.

At step if there are remaining sellers the system shifts the priority of all remaining sellers up by one.

The system then gives the new highest priority seller a second look opportunity to satisfy the CPO at step . The process repeats with other look opportunities third fourth etc. until a seller satisfies the CPO at step or the system determines that no sellers remain at step .

At step if the system determines that no sellers remain the system notifies the buyer that no seller was able to satisfy the CPO.

In another embodiment illustrated in at step system receives data from a buyer and forms a CPO. This step is functionally the same as described at steps through in .

At step system identifies the highest priority seller for a first look opportunity to satisfy the CPO. Determining priority of sellers is accomplished with a metric such as the previously described adjusted market share market share random number and buyer specific metric.

At step if the seller did not satisfy the CPO the system identifies that highest priority seller as unable to satisfy the CPO and removes that highest priority seller from the eligible list of sellers for the CPO.

If there are remaining sellers at step the system identifies the highest priority seller for a second look opportunity to satisfy the CPO. In this manner the method continues with other look opportunities third fourth etc. until the system determines that a seller satisfies the CPO at step or the system determines that no sellers remain at step .

In this manner sellers may be reprioritized according to the selected metric with any influence of a higher priority but non filling seller removed.

At step if there are no remaining sellers the system informs the buyer that no seller was able to satisfy the CPO.

In an alternate embodiment an allocation system is used to provide an advantage or disadvantage to one or more participating agency based sellers. In this embodiment the objective of the system is to create imbalance in an attempt to favor a specific seller without providing that favored seller with all of the first look opportunities.

In one example of this embodiment the CPO management system allocates first look opportunities to the plurality of agency based sellers on the basis of market share between two points. When a first look opportunity is allocated to a favored seller it does not count as being allocated unless the favored seller binds or fulfills the offer. This creates a structural advantage in that if the favored seller does not fulfill the offer the favored seller automatically receives a first look at the next unit of demand between those two points.

It is understood that there are many methods by which a CPO management system can provide a structural advantage or disadvantage to one or more agency based sellers.

The airline industry is used as an example however any industry in which the buyer driven commerce model can be applied is appropriate for the system and method of the invention.

The embodiments thus described disclose allocation among Agency Based Sellers. It is also envisioned that the invention provide allocation among Broadcast Based Sellers. Similarly the invention envisions allocation among multiple sellers including a combination Agency Based and Broadcast Based Sellers.

The embodiments have described the invention in the context of a Binding CPO. However the invention is also appropriate for circumstances where the CPO is not binding.

In another embodiment a CPO may contain a seller defined variable or flexible condition typically specified using a range. For example the variable condition may be a date range within which the product may be delivered by the seller. Other variable conditions might include a price range a performance range a quality range etc. . . . . The seller may then choose a product to fill the buyer s flexible condition within the specified range. Such a variable condition may provide substantial assistance to the seller in filling the buyer s CPO. For example with respect to an airline ticket the seller may be able to be meet a buyer s specified price if the CPO permits him to select a flight within a range of times or days.

It is desirable that in one embodiment the present invention include features that prevent buyers from repetitively querying or pinging the system to determine the underlying price flexibility of the sellers. Such pinging might result in potential damage to the seller s price margins and profitability. As mentioned above requiring a buyer to enter into a Binding CPO at least discourages pinging by insuring that if an offer is accepted the product is actually purchased. Another method of discouraging pinging includes preventing buyers from submitting repetitive similar offers. For example repetitive CPOs changing only the offer price in an effort to determine price flexibility may be blocked by the system. In one embodiment subsequent CPOs by the same buyer are accepted by the CPO Management System only if there is some substantial change to the buyer specifications that would result in the purchase of an essentially different product. For example with respect to the sale of airline tickets subsequent CPOs may be accepted for processing only if there is a significant change in the itinerary. Yet another method for discouraging pinging is to require a payment for each submission of a CPO.

In another embodiment of the invention sellers identities are maintained anonymous within the CPO Management System until a CPO is accepted. Such identity anonymity by itself and in combination with the discouragement of price pinging discussed herein enables sellers to participate in the CPO Management System process without fear of undercutting their published price structures and losing their regular customer base. For example most retailers have published product prices and loyal customers who willingly pay those prices. Participating in the CPO Management System enables a seller to discount those products potentially below its published prices to fill offers from buyers who might not otherwise pay published prices. With anonymity these sellers can more freely participate in the CPO Management System process with less fear of losing their regular customers and undercutting their published price structure.

Although illustrative embodiments of the present invention and various modifications thereof have been described in detail herein with reference to the accompanying drawings it is to be understood that the invention is not limited to these precise embodiments and the described modifications and that various changes and further modifications may be effected therein by one skilled in the art without departing from the scope or spirit of the invention as defined in the appended claims.

