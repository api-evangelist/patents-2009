---

title: Adaptive keyboard layout mapping
abstract: A method for processing keystrokes is described herein. A first keystroke representing a symbol for a first operating system may be received on a first computer. The first keystroke may be translated to a second keystroke representing the symbol for a second operating system on a second computer. The second operating system is different from the first operating system. The second keystroke may be sent to the second computer.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08122170&OS=08122170&RS=08122170
owner: Microsoft Corporation
number: 08122170
owner_city: Redmond
owner_country: US
publication_date: 20090611
---
The computer laptop is an innovation that enables computer users on the go to perform computer related tasks when they do not have access to their desktop computers. Because memory is more limited on the laptop than the desktop the computer user may keep a limited set of computer applications and files on the laptop. Further the computer user may copy files from the desktop onto the laptop to prepare for a particular task.

However unless the computer user foresees exactly what work or tasks are to be performed the laptop in and of itself may not substitute for access to the desktop computer. Instead the computer user may use remote desktop software to remotely access the desktop computer from another computer. In this way the computer user may do work or other computer related tasks without having to plan ahead by copying files or applications from the desktop to the laptop.

The remote desktop software may send each keystroke entered on the local computer to the remote computer. The remote computer may then process the keystrokes as if entered on a keyboard attached to the remote computer and maps the keystrokes to symbols to be displayed. Those symbols are then displayed on a screen attached to the local computer.

Described herein are implementations of various technologies for adaptive keyboard layout mapping. Using remote desktop software on a local computer having a first operating system OS a user may remotely operate a remote computer having a second operating system OS where the second OS is different from the first OS. During the remote desktop session the user may change a keyboard layout setting that enables the user to produce foreign symbols on the local display that may not be available on the physical keyboard. The keyboard layout may map potential keystrokes entered on the local computer to the symbols of the foreign language.

As each keystroke is entered on the local computer a lookup operation may be performed. The lookup operation may determine a corresponding keystroke entered on the remote computer that produces the same symbol produced by the keystroke entered on the local computer. The corresponding keystroke may be sent to the remote computer. The remote computer may process the corresponding keystroke to produce the symbol and send the symbol to the local computer for display.

The claimed subject matter is not limited to implementations that solve any or all of the noted disadvantages. Further the summary section is provided to introduce a selection of concepts in a simplified form that are further described below in the detailed description section. The summary section is not intended to identify key features or essential features of the claimed subject matter nor is it intended to be used to limit the scope of the claimed subject matter.

In general one or more implementations of various technologies described herein are directed towards adaptive keyboard layout mapping. The various implementations will be described in more detail in the following paragraphs.

Implementations of various technologies described herein may be operational with numerous general purpose or special purpose computing system environments or configurations. Examples of well known computing systems environments and or configurations that may be suitable for use with the various technologies described herein include but are not limited to personal computers server computers hand held or laptop devices multiprocessor systems microprocessor based systems set top boxes programmable consumer electronics network PCs minicomputers mainframe computers distributed computing environments that include any of the above systems or devices and the like.

The various technologies described herein may be implemented in the general context of computer executable instructions such as program modules being executed by a computer. Generally program modules include routines programs objects components data structures etc. that perform particular tasks or implement particular abstract data types. The various technologies described herein may also be implemented in distributed computing environments where tasks are performed by remote processing devices that are linked through a communications network e.g. by hardwired links wireless links or combinations thereof. In a distributed computing environment program modules may be located in both local and remote computer storage media including memory storage devices.

The local computer may include an operating system A a remote client a keyboard layout and a mapping table . The operating system A may be any suitable operating system that may control the operation of a networked personal or server computer such as Windows Vista operating system Mac OS X operating system Unix operating system variants e.g. Linux operating system and BSD operating system and the like.

The remote computer may also include an operating system operating system B . The operating system B on the remote computer may be distinct from the operating system A on the local computer . In one implementation the operating system A may be a Mac operating system and the operating system B may be a Windows operating system.

The remote client may be software that enables a user to operate the remote computer over the network through the use of the local computer .

For example the local computer may be located in the user s home and the remote computer may be the user s computer at work. Through the use of the remote client the user may operate the computer at work from home.

The remote client may connect to the remote computer during a remote desktop session. During this session the user may operate the remote computer using the local computer .

The keyboard layout may map each possible keystroke on the local computer to a particular set of symbols. For example the keystroke consisting of the SHIFT key and the number 1 key may be mapped to the symbol. Multiple keyboard layouts may be available for the user s selection. Keyboard layouts may vary by language and OS. For example a keyboard layout for United Kingdom English and the Windows operating system may map a keystroke of the key to the symbol for the sterling pound . 

The remote computer may also include a keyboard layout . While the set of symbols produced by each of the keyboard layouts may be the same the keystrokes that produce the symbols may differ.

To that end the mapping table may map the keystrokes in the keyboard layout to corresponding keystrokes in the keyboard layout that produce the same symbols. Similar to the keyboard layouts the mapping table may be language specific. In one implementation there may be multiple mapping tables including one mapping table for each language. The mapping table is described in greater detail with reference to .

The remote client may include a keystroke mapper . The keystroke mapper may be software that uses the mapping table to translate a keystroke entered on the local computer to the corresponding keystroke on the remote computer .

The operating system A may receive a keystroke from a keyboard not shown attached to the local computer . The operating system A may send the keystroke to the remote client for processing. In turn the remote client may send the keystroke to the keystroke mapper . Upon receiving the keystroke the keystroke mapper may translate the keystroke to the corresponding keystroke for the remote computer . The translation is described in greater detail with reference to . The keystroke mapper may then send the corresponding keystroke to the remote computer .

Upon receiving the corresponding keystroke the remote computer may determine the symbol that the corresponding keystroke produces. The remote computer may then send the symbol to the remote client . The remote client may then send the symbol to the operating system A . In response the operating system A may display the symbol on a computer screen not shown attached to the local computer .

At step the remote client may receive a keyboard layout selection. The selection may be received from the user as a default keyboard layout. In one implementation the user may change the keyboard layout selection during the remote desktop session.

At step the keystroke mapper may receive a keystroke. The keystroke may be entered by the user on the keyboard attached to the local computer .

At step the keystroke mapper may translate the keystroke to the corresponding keystroke for the remote computer . In one implementation the keystroke mapper may lookup the corresponding keystroke in the mapping table . As stated previously the mapping table may be language specific. As such the keystroke mapper may perform the lookup in the mapping table for the language that corresponds to the language for the selected keyboard layout .

At step the keystroke mapper may send the corresponding keystroke to the remote computer . Upon receiving the corresponding keystroke the remote computer may process the corresponding keystroke as described with reference to .

Each row in the mapping table may represent a potential keystroke entered on the local computer and its translation to a corresponding keystroke for the remote computer .

A keystroke may include one or more modifier keys and a regular key. In computing a modifier key is a special key on a computer keyboard that modifies the normal action of another key when pressed in combination. For example the modifier key SHIFT in combination with the 1 key produces a symbol instead of the 1 symbol. Modifier keys may include one or more of a set of keys such as CTRL ALT SHIFT COMMAND OPTION and the like. Regular keys may be any other key on the keyboard that produces symbols such as letters number and character keys like a 1 and . 

The combination of modifier keys and a regular key produce the symbol associated with the keystroke in the keyboard layouts . It should be noted that certain keystrokes may not include a modifier key as is the case for symbols like lower case letters numbers and certain characters. In one implementation the mapping table may include the symbol. In the implementation where there is one mapping table used the mapping table may include identifiers for the operating systems and the languages.

In one implementation keystrokes may be functional instead of symbolic. A functional keystroke may cause the remote computer to perform a function instead of producing the symbol. For example the F key is functional. In the Windows operating system pressing the F key performs the function of opening a help window.

Functional keystrokes may include modifier key regular key and function key combinations. For example in the Windows operating system the modifier key CTRL in combination with the regular key W performs the function of closing the currently opened window. Those skilled in the art know a multitude of functional keystrokes are possible including user defined functions modifier keys in combination with function keys etc.

In such an implementation the keyboard layouts may map keystrokes to functions similarly the mapping table may include identifiers of the functions. Further in response to the user entering a functional keystroke on the local computer the keystroke mapper may translate the functional keystroke send the translated keystroke to the remote computer and the remote computer may perform the function e.g. open the help window. The help window or other output of a function may be displayed on the local computer similar to displaying symbols for symbolic keystrokes.

The operating system A modifier key s and operating system A regular key may represent the keystroke entered by the user on the local computer . The operating system B modifier key s and operating system B regular key may represent the corresponding keystroke sent to the remote computer by the keystroke mapper .

The combination of operating system A modifier key s and operating system A regular key may be associated with a symbol within the keyboard layout . Similarly the combination of operating system B modifier key s and operating system B regular key may be associated with a symbol within the keyboard layout .

In some cases the keystroke for a symbol on the local computer may be the same as the corresponding keystroke on the remote computer . As shown in the row the keystroke and corresponding keystroke are the same for the symbol a modifier key of SHIFT and a regular key of 1. 

However the keystroke and the corresponding keystroke are not typically the same particularly when the local computer and the remote computer have different operating systems. For example row represents a translation for the keystroke that produces the symbol for the sterling pound. The keystroke on the local computer includes the operating system A modifier key s of NONE no modifier key entered and an operating system A regular key of . The corresponding keystroke for the remote computer includes the operating system B modifier key s of CTRL and ALT and an operating system B regular key of . 

One or more programs that may implement or utilize the various technologies described herein may use an application programming interface API reusable controls and the like. Such programs may be implemented in a high level procedural or object oriented programming language to communicate with a system. However the program s may be implemented in assembly or machine language if desired. In any case the language may be a compiled or interpreted language and combined with hardware implementations.

Although the subject matter has been described in language specific to structural features and or methodological acts it is to be understood that the subject matter defined in the appended claims is not necessarily limited to the specific features or acts described above. Rather the specific features and acts described above are disclosed as example forms of implementing the claims.

