---

title: System and method for driving hardware device and processing data
abstract: A system for driving a hardware device and processing data and a method thereof are provided. The system includes a storage unit, a processor, and the hardware device. The storage unit stores a multimedia application interface, a virtual window driving model (WDM) interface, and a multimedia application. The processor is electrically connected with the storage unit and used for executing a multimedia application. The hardware device receives or outputs first format data. When the multimedia application and the hardware device are active, the multimedia application interface and the virtual WDM interface are taken as communication interfaces between the multimedia application and the hardware device, and the virtual WDM interface converts the first format data to second format data and transmits the second format data to the multimedia application via the multimedia application interface, and the second format data is processed by the multimedia application.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08181189&OS=08181189&RS=08181189
owner: Asustek Computer Inc.
number: 08181189
owner_city: Taipei
owner_country: TW
publication_date: 20091222
---
This application claims the benefit of Taiwan application Serial No. 97151851 filed Dec. 31 2008 the subject matter of which is incorporated herein by reference.

The invention relates to a system for driving a hardware device and a method thereof and processing data and more particularly to a system for driving a hardware device in a computer system and processing data and a method thereof.

DirectX is a special multimedia application programming interface API used in Microsoft windows and it allows a programmer to use the functions of various hardware without writing hardware code by himself or herself. The DirectX includes components such as DirectShow DirectDraw DirectSound DirectInput Direct3D DirectAnimation and DirectMusic. Various kinds of multimedia applications such as Yahoo VOIP MSN VOIP Skype and Google Talk are gradually developed on the basis of the architecture of the DirectX.

Additionally Microsoft launches a windows driver model WDM after Window 98 and the WDM and the DirectX are closely related to each other. The WDM is a design specification of a hardware device driver established by Microsoft and compatible with Microsoft operating systems the hardware device performing the design specification is also called a WDM hardware device and the brand the model and the pin of the WDM hardware device in the specification do not need to be considered. Consequently if the WDM hardware device needs to be used by the multimedia application integrated circuit IC manufacturers must first develop a WDM driver performing the design specification of the WDM according to Window driver development kit DDK of Microsoft and then system manufacturers may utilize the WDM driver to drive the WDM hardware device.

For example a web camera includes a complementary metal oxide semiconductor CMOS image sensor and a universal serial bus USB IC. USB IC manufacturers must provide the driver performing the WDM specification and then the system manufacturer may normally drive the web camera.

However if the USB IC manufacturers do not provide a correct WDM driver the system manufacturers cannot amend or use the WDM hardware device.

Additionally since parts of USB ICs do not have enough computing power or corresponding hardware design it cannot support a color adjusting interface and a camera lens control interface regulated by the Directshow.

Moreover since common multimedia applications such as MSN VOIP Skype and Google Talk only support a standard audio input microphone and do not support a Bluetooth microphone the multimedia applications such as MSN VOIP Skype and Google Talk cannot capture multimedia information via the Bluetooth microphone.

The invention relates to a system for driving a hardware device and processing data and a method thereof and it at least includes the following advantages.

First the Bluetooth microphone originally does not supporting the multimedia application the multimedia application can play the audio data captured by the Bluetooth via a virtual WDM interface.

Second system manufacturers may debug program or add additional functions at a virtual control interface or a virtual color adjusting interface by themselves to greatly improve added value which does not need any hardware cost.

Third the color adjusting interface and a camera lens control interface regulated by the Directshow are absolutely supported.

Fifth the image quality in playing is improved via strong computing power of a central processing unit CPU or a graphic processor unit GPU .

The invention provides a system for driving the hardware device and processing the data. The system includes a storage unit a processor and the hardware device. The storage unit stores a multimedia application interface a virtual WDM interface and a multimedia application. The processor is electrically connected with the storage unit and used for executing the multimedia application. The hardware device receives or outputs first format data. When the multimedia application and the hardware device are active the multimedia application interface and the virtual WDM interface are taken as communication interfaces between the multimedia application and the hardware device the virtual WDM interface converts the first format data to second format data and transmits the second format data to the multimedia application via the multimedia application interface and the second format data is processed by the multimedia application.

The invention provides a method for driving a hardware device and processing data. The method includes the following steps. First a multimedia application interface a virtual WDM interface and a multimedia application are stored. Second the multimedia application is executed. Third the first format data is received or outputted via the hardware device. When the multimedia application and the hardware device are active the multimedia application interface and the virtual WDM interface are taken as communication interfaces between the multimedia application and the hardware device the virtual WDM interface converts the first format data to second format data and transmits the second format data to the multimedia application via the multimedia application interface and the second format data is processed by the multimedia application.

These and other features aspects and advantages of the present invention will become better understood with regard to the following description appended claims and accompanying drawings.

When the multimedia application and the hardware device are active the multimedia application interface and the virtual WDM interface are taken as communication interfaces between the multimedia application and the hardware device the virtual WDM interface converts first format data D to second format data D and transmits the second format data D to the multimedia application via the multimedia application interface and the second format data D is processed by the multimedia application . In this embodiment the multimedia application may be an instant messenger such as Yahoo VOIP MSN VOIP Skype or Google Talk the multimedia application interface may be DirectX and the DirectX may further include the components such as DirectShow DirectDraw DirectSound DirectInput Direct3D DirectAnimation and DirectMusic.

The first format data D received or outputted by the hardware device is the data stored in a hard disk or captured via the hardware device. For example the first format data D received by the virtual WDM interface may be obtained by capturing external sound or images by the hardware device such as a Bluetooth microphone or a web camera. First embodiments to a third embodiment are taken as examples to illustrate the invention hereinafter but the invention is not limited thereto. Persons having ordinary skill in the art may make various modifications and changes without departing from the scope and spirit of the invention.

Since the multimedia application interface does not support the Bluetooth microphone the multimedia application cannot directly play the first format data D captured by the Bluetooth microphone . To solve this problem the virtual WDM interface includes a voice processing interface converting the first format data D to the second format data D.

Since the multimedia application interface can receive the second format data D the multimedia application can receive the second format data D via the multimedia application interface to play accordingly. As a result the Bluetooth microphone originally does not supporting the multimedia application . The multimedia application can play the audio data captured by the Bluetooth via a virtual WDM interface.

Moreover the virtual WDM interface further includes a virtual sound interface of the Bluetooth microphone . The virtual sound interface is used for processing the sound effect of the second format data D to obtain better sound effect. The sound effects processing may be reducing an echo.

Since the multimedia application interface in the second embodiment does not support the web camera the multimedia application cannot directly play the first format data D captured by the web camera . To solve this problem the virtual WDM interface includes a picture processing interface . The picture processing interface converts the first format data D to the second format data D.

Since the multimedia application interface can receive the second format data D the multimedia application receive the second format data D via the multimedia application interface to play accordingly. As a result the web camera originally not supporting the multimedia application can support the multimedia application via the virtual WDM interface .

The virtual WDM interface further includes a virtual picture capturing control interface and a virtual color adjusting interface . The virtual picture capturing control interface and the virtual color adjusting interface may be obtained by intercepting the picture capturing control interface and the color adjusting interface . The virtual picture capturing control interface is used for controlling the functions of a camera lens of the web camera such as zoom of the camera lens or the upward downward leftward and rightward movement of the camera lens. The virtual color adjusting interface is used for adjusting color such as hue saturation brightness or contrast of second format data D.

Since the virtual WDM interface is at an application layer system manufacturers can debug program via the virtual WDM interface by themselves which does not need to depend on technical support of the USB IC manufacturers. Additionally the system manufacturers may add additional functions via the virtual WDM interface by themselves to greatly increase added value which does not need any hardware cost.

The virtual WDM interface can intercept a function requirement such as a camera lens control or a color adjustment transmitted by the original multimedia application and the function requirement is processed by utilizing strong computing power of a CPU or a GPU. As a result even the cheap USB IC does not have the enough computing power or a corresponding hardware design it can absolutely support a color adjusting interface and a camera lens control interface regulated by the Directshow via the virtual WDM interface . Consequently the system manufacturer can quickly replace the original USB IC with the USB IC with low cost and the image quality in playing is greatly improved via the strong computing power of the CPU or the GPU.

Since the multimedia application interface can receive the second format data D the multimedia application receives the second format data D via the multimedia application interface to play accordingly. As a result the second format data D originally not supporting the multimedia application can support the multimedia application via the virtual WDM interface . As a result the multimedia application can play various kinds of the multimedia files such as various kinds of movies and pictures via the virtual WDM interface .

First as shown at step the storage unit stores the multimedia application interface the virtual WDM interface and the multimedia application . Second as shown at step the processor executes the multimedia application . Third as shown at step the first format data D is received or outputted via the hardware device . Fourth as shown at step when the multimedia application and the hardware device are active the multimedia application interface and the virtual WDM interface are taken as the communication interfaces between the multimedia application and the hardware device the virtual WDM interface converts the first format data D to the second format data D and transmits the second format data D to the multimedia application via the multimedia application interface and the second format data D is processed by the multimedia application .

The system for driving the hardware device and processing the data and the method thereof according to the invention at least include the following advantages.

First the Bluetooth microphone originally does not supporting the multimedia application. The multimedia application can play the audio data captured by the Bluetooth via a virtual WDM interface.

Second the system manufacturers can debug program or add additional functions at the virtual control interface or the virtual color adjusting interface by themselves to greatly increase the added value which does not need any hardware cost.

Third the color adjusting interface and a camera lens control interface regulated by the Directshow are absolutely supported.

Although the present invention has been described in considerable detail with reference to certain preferred embodiments thereof the disclosure is not for limiting the scope of the invention. Persons having ordinary skill in the art may make various modifications and changes without departing from the scope and spirit of the invention. Therefore the scope of the appended claims should not be limited to the description of the preferred embodiments described above.

