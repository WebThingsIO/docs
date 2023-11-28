# W3C Web of Things

![An illustration of a web of connected devices with the Web of Things logo at the centre](images/web_of_things_illustration.png)

The [Web of Things](https://www.w3.org/WoT/) (WoT) is defined by a collection of specifications standardised by the [World Wide Web Consortium](https://w3.org) (W3C).

According to the W3C, *"the Web of Things (WoT) seeks to counter the fragmentation of the IoT by using and extending existing, standardized Web technologies. By providing standardized metadata and other re-usable technological building blocks, W3C WoT enables easy integration across IoT platforms and application domains."*

The Web of Things is to the Internet of Things what the World Wide Web is to the Internet. 

It gives URLs to physical devices in the real world to make them linkable, provides a data model to describe them and a communication protocol to interact with them.

The Web of Things can be used as a unifying application layer for the Internet of Things, linking together multiple underlying IoT protocols using existing web technologies.

The core normative specifications (standards) which define the Web of Things are:

- [WoT Architecture](https://www.w3.org/TR/wot-architecture/) - Describes the building blocks of the Web of Things and how they fit together
- [WoT Thing Description](https://www.w3.org/TR/wot-thing-description/) - Defines an information model and JSON-based serialisation format for describing the capabilities of connected devices in a protocol agnostic way
- [WoT Discovery](https://www.w3.org/TR/wot-discovery/) - Defines various mechanisms for discovering web things, including a Thing Description Directory
- [WoT Profiles](https://w3c.github.io/wot-profile/) - Defines sets of prescriptive constraints called "profiles" to enable out-of-the-box interoperability between conformant web things and their consumers

There are also some informative notes which provide additional guidance:

- [WoT Binding Templates](https://www.w3.org/TR/wot-binding-templates/)
- [WoT Scripting API](https://www.w3.org/TR/wot-scripting-api/)
- [WoT Security and Privacy Guidelines](https://www.w3.org/TR/wot-security/)

These specifications were designed to fulfill a collection of [Use Cases and Requirements](https://www.w3.org/TR/2022/NOTE-wot-usecases-20220307/) originally defined by the [Web of Things Interest Group](https://www.w3.org/WoT/ig/).

In addition to the specifications written by the WoT Working Group, there is a specification being incubated by the [Web Thing Protocol Communtiy Group](https://www.w3.org/community/web-thing-protocol/) which defines a common protocol for the Web of Things called the Web Thing Protocol:

- [Web Thing Protocol Use Cases & Requirements](https://www.w3.org/community/reports/web-thing-protocol/CG-FINAL-web-thing-protocol-requirements-20231101/)