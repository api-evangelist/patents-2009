---

title: Method and system for managing cookies in web communications
abstract: A system and method which may allow a Web application to manage cookies and prevent important data in cookies from being arbitrarily deleted. Cookie data may be separated into a number of tiers according to their importance. When a request to write new data to a cookie is received, the tier to which the new data belongs may be determined and compared to the tier(s) of existing data in the cookie, and existing data may be deleted from the cookie to free room for the new data only when the existing data is not more important than the new data.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08380763&OS=08380763&RS=08380763
owner: Yahoo! Inc.
number: 08380763
owner_city: Sunnyvale
owner_country: US
publication_date: 20090922
---
A cookie is a small text file stored by a Web browser on a user s computer. A cookie may contain information that identifies each user such as user names and passwords. When a user revisits a Web site the Web server may establish the user s identity by the cookie.

Cookies have finite limits defined by Web browsers both on the number of cookies being used and the overall cookie size. When these limits are exceeded Web browsers start deleting data stored in cookies. Different Web browsers have different limits on cookies and follow different rules to determine which data to delete. A user s browsing experience may be affected when important data e.g. login information is deleted.

Therefore it may be desirable to provide a system and method which allows Web applications to determine which data should be deleted from cookies to ensure that the most important data always remains safe.

The present invention provides a system and method which may allow a Web application to manage cookies and prevent important data in cookies from being arbitrarily deleted. Cookie data may be separated into a number of tiers according to their importance. When a request to write new data to a cookie is received the tier to which the new data belongs may be determined and compared to the tier s of existing data in the cookie and existing data may be deleted from the cookie to free room for the new data only when the existing data is not more important than the new data. The invention may be carried out by computer executable instructions such as program modules. Advantages of the present invention will become apparent from the following detailed description.

In one embodiment a three tier system may be used. The first tier may include the most important data that would severely disrupt the user experience should it be removed. The first tier may include cookie data for user settings e.g. users login information and users selection of their homepage content. The first tier may also include geographic information or contact information. The second tier may include the second most important data the loss of which might affect the user experience but not so much that it would severely impact the user. The second tier may include cookie data for page level settings related to the state of the overall page e.g. themes. The third tier may be the least important data which may be related to the state of a small section on the page and the user may not notice if it s missing. The third tier may include cookie data for module level settings e.g. which tab was selected in a tabset. It should be understood that the cookie data may be separated into more or fewer tiers. The more the tiers that are accommodated the less likely it may be that existing cookie data will be replaced by less important new data.

The memory device may store data relevant to the service provided by a Web server e.g. information about items to be sold items to be auctioned people in a social network or photos in online photo albums. The memory device may also store user information e.g. users browsing history.

A cookie management module which may be an Application Programming Interface API may be stored in one of the memory devices e.g. the memory device for performing the process shown in or . The cookie management module may receive requests to write new data to a cookie and make sure that the new data will not risk the loss of important data in the cookie. The request may be written with e.g. pre hypertext processor PHP language or other suitable code. If adding the new data may cause the cookie to exceed its size limit the cookie management module may determine which tier the new data belongs to and only delete data in the cookie belonging to a tier which is not more important than the tier of the new data.

User terminals may be personal computers handheld or laptop devices microprocessor based systems set top boxes or programmable consumer electronics. The user terminal may include one or more of a processing unit a display screen an input device memory devices and and a system bus coupling various components in the computer system. Each user terminal may have a browser application configured to receive and display Web pages which may include text graphics multimedia etc. The browser may store cookies from a Web server on the user terminal e.g. in the memory device . The Web pages may be based on e.g. HyperText Markup Language HTML or extensible markup language XML . A cookie management module which may be JavaScript may perform the process shown in or .

Cookies stored in the memory device may include e.g. users login information geographic information preferences etc. It should be understood that the memory device may be internal or external.

Network connectivity may be wired or wireless using one or more communications protocols as will be known to those of ordinary skill in the art.

At the cookie management module may receive a request from the processing unit or the input device to write new data to a cookie.

At the cookie management module may determine whether the addition of the new data will cause the cookie to exceed its size limit.

If not the new data may be added to the cookie at . The updated cookie may then be sent to a Web browser in a user terminal and be stored therein.

If the cookie may exceed its size limit the cookie management module may determine whether the new data belongs to the highest data tier the first tier in this embodiment at . If not the process may proceed to in .

If the new data belongs to the first tier the cookie management module may determine whether the cookie has third tier data at . If yes at the cookie management module may delete some third tier data from the cookie to free room for the new data which belongs to the first tier and is more important. The process may then proceed to to write the new data to the cookie.

If it is determined at that there is no third tier data in the cookie the cookie management module may determine whether the cookie has second tier data at . If yes at the cookie management module may delete some second tier data from the cookie to free room for the new data which is more important. The process may then proceed to to write the new data to the cookie.

If it is determined at that there is no second tier data in the cookie additions of new data to the cookie may be limited since all data in the cookie belongs to the first tier and needs to be protected. In one embodiment at the cookie management module may reject the request for writing new data to the cookie.

If it is determined at that the new data does not belong to the first tier it may be determined at in whether the new data belongs to the second tier. If not the new data must belong to the third tier. Since the third tier data is the least important and users may not notice if it is missing in one embodiment the cookie management module may be configured to allow deleting existing third tier data for new third tier data. Accordingly the process may proceed to to delete some third tier data in the cookie to free room for the new data and then to to write the new data.

If it is determined at that the new data belongs to the second tier it may be determined at whether the cookie has third tier data at . If yes the process may proceed to to delete some third tier data from the cookie to free room for the new data and then to to write the new data.

In one embodiment the cookie management module may be configured to allow addition of new data to a cookie only when the new data is more important than existing data in the cookie. So if there is no third tier data in the cookie both the new data and the least important data in the cookie belong to tier two and the cookie management module may reject the write request at to protect data already existing in the cookie.

Since the loss of the second tier data may not severely impact a user s browsing experience in an embodiment shown in the cookie management module may be configured to allow addition of new data to a cookie when both the new data and the least important data in the cookie belong to tier two. So if the cookie does not have third tier data the cookie management module may determine whether the cookie has second tier data at . If yes at the cookie management module may delete some second tier data from the cookie to free room for the new data and write the new data to the cookie at . If there is no second tier data in the cookie the cookie management module may reject the write request at since all data in the cookie must belong to the first tier which is the most important data and needs to be protected.

The cookie management module may facilitate user terminal side cookie management via communication with the cookie management module which may be e.g. JavaScript . The cookie management module may control data addition to and deletion from a cookie in a way similar to the flowcharts shown in or C. For example a user may want to change the theme of his home page which is the second tier data through his browser and the cookie management module may receive the request. If the cookie has third tier data at the cookie management module may delete some third tier data to free room for the theme change. However if the cookie is fully occupied by the first tier data the cookie management module may limit the addition of new data at e.g. by informing the user that there is not enough room in the cookie for the change.

Since a user may change his settings via a browser in a user terminal the cookie management module may give high priority to the user s input and may be configured to follow the flowchart shown in so that some second tier data may be deleted to free room for the new data.

Several features and aspects of the present invention have been illustrated and described in detail with reference to particular embodiments by way of example only and not by way of limitation. Those of skill in the art will appreciate that alternative implementations and various modifications to the disclosed embodiments are within the scope and contemplation of the present disclosure. Therefore it is intended that the invention be considered as limited only by the scope of the appended claims.

