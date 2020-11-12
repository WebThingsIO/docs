# WebThings

[WebThings](https://webthings.io/) is an open platform for monitoring and controlling devices over the web.

It is an open source implementation of emerging [Web of Things](https://www.w3.org/WoT/) standards at the W3C.

## User Guide
### WebThings Gateway
[WebThings Gateway](https://webthings.io/gateway/) is a software distribution for smart home gateways which allows users to directly monitor and control their smart home over the web, without a middleman.
* [Getting Started Guide - Raspberry Pi](./gateway-getting-started-guide.md)
* [Getting Started Guide - Docker](https://github.com/WebThingsIO/gateway-docker/blob/master/README.md)
* [User Guide](./gateway-user-guide.md)
* [Supported Hardware](https://github.com/WebThingsIO/wiki/wiki/Supported-Hardware)
#### Tips
* [Pairing SmartThings sensors](https://github.com/WebThingsIO/wiki/wiki/Pairing-SmartThings-sensors)
* [Configuring the Arlec Smart Plug](https://github.com/WebThingsIO/wiki/wiki/Arlec-Smart-Plug)
* [Factory reset a Cree Connected bulb](https://github.com/WebThingsIO/wiki/wiki/HOWTO%3A-Factory-reset-a-Cree-Connected-bulb)
* [Factory reset a Hue bulb](https://github.com/WebThingsIO/wiki/wiki/HOWTO%3A-Factory-reset-a-Hue-bulb)
* [Factory reset a Hue Wireless Dimmer](https://github.com/WebThingsIO/wiki/wiki/HOWTO%3A-Factory-reset-a-Hue-Wireless-Dimmer)
* [Factory reset an IKEA bulb](https://github.com/WebThingsIO/wiki/wiki/HOWTO%3A-Factory-reset-an-IKEA-bulb)


## Developer Guide

### Web Thing API
The Web Thing API is the REST & WebSockets API used by the WebThings IoT platform for monitoring and controlling devices over the web. Parts of the Web Thing API specification are currently being standardised via the W3C.
* [Introduction to the Web Thing API](https://github.com/WebThingsIO/wot/blob/gh-pages/README.md)
* [Web Thing API specification](https://webthings.io/api/)
  * [Examples using curl](https://github.com/WebThingsIO/curl-examples/blob/master/README.md)
  * [Differences with W3C specification](https://github.com/webthingsio/wiki/wiki/Mozilla-W3C-Differences)
* [WoT Capability Schemas](https://webthings.io/schemas/)

### WebThings Gateway
[WebThings Gateway](https://webthings.io/gateway/) is an open source implementation of a Web of Things gateway which bridges a range of different IoT protocols to the Web Thing API and provides a web interface for users to monitor and control devices.
* [Gateway Architecture](https://github.com/WebThingsIO/wiki/wiki/Gateway-Architecture)
* [Build Instructions](https://github.com/WebThingsIO/gateway#readme)
* [Creating a new translation](https://github.com/WebThingsIO/wiki/wiki/Fluent%3A-Making-a-new-translation)
* [Testing pre-release OTA updates](https://github.com/WebThingsIO/wiki/wiki/Testing-prerelease-OTA-updates)
* [Releasing a Gateway OTA Update](https://github.com/WebThingsIO/wiki/wiki/How-To-Release-a-Gateway-OTA-Update)
#### Add-Ons
* [Introduction to Add-ons](https://github.com/WebThingsIO/addon-list/blob/master/guidelines.md)
* [Creating an Add-on](https://github.com/WebThingsIO/wiki/wiki/HOWTO%3A-Create-an-add-on)
* [Configuring an Add-on](https://github.com/WebThingsIO/wiki/wiki/Add-on-Configuration)
* [Publishing an Add-on](https://github.com/WebThingsIO/addon-list#readme)
* Examples:
  * [Adapter Add-on](https://github.com/WebThingsIO/example-adapter)
  * [Notifier Add-on](https://github.com/WebThingsIO/example-notifier)
  * [Extension Add-on](https://github.com/WebThingsIO/example-extension)
* Add-on APIs
  * [Node.js Add-on API](https://github.com/WebThingsIO/gateway-addon-node)
  * [Python Add-on API](https://github.com/WebThingsIO/gateway-addon-python)
* [Adapter Inter-process communication](https://github.com/WebThingsIO/wiki/wiki/Adapter-IPC)
* [Debug Controller](https://github.com/WebThingsIO/wiki/wiki/Using-the-debug-controller)

### WebThings Framework
[WebThings Framework](https://webthings.io/framework/) is a collection of re-usable software components to help developers build their own web things which directly expose the Web Thing API.
#### WebThings Libraries
* [Node.js](https://github.com/WebThingsIO/webthing-node)
* [Python](https://github.com/WebThingsIO/webthing-python)
* [Java](https://github.com/WebThingsIO/webthing-java)
* [Rust](https://github.com/WebThingsIO/webthing-rust)
* [Arduino](https://github.com/WebThingsIO/webthing-arduino)
* [MicroPython](https://github.com/WebThingsIO/webthing-upy)
#### Third Party Libraries
* [Moddable](https://github.com/Moddable-OpenSource/moddable/blob/public/documentation/network/webthings.md)
* [Atmosphere IoT](https://developer.atmosphereiot.com/documents/guides/gettingstartedwebthings.html)
* [IoT.js](https://github.com/rzr/webthing-iotjs) by rzr
* [C#](https://github.com/lillo42/webthing-csharp) by lillo42
* [Go](https://github.com/rzr/webthing-go) by rzr
* [Go](https://github.com/dravenk/webthing-go) by dravenk
* [ESP-IDF](https://github.com/akshayvernekar/esp-webthing) by akshayvernekar
* [PHP](https://github.com/maliknaik16/webthing-php) by maliknaik16
* [Python](https://github.com/hidaris/aiowebthing) by hidaris

### WebThings Cloud
WebThings Cloud is a collection of cloud services for remotely managing web things over the internet. WebThings Cloud includes a remote access service which can create an end-to-end encrypted tunnel between a WoT gateway (or device) and a WoT client so that it can be securely accessed over the internet.
* [How Remote Access Works](https://github.com/WebThingsIO/registration_server/blob/master/doc/flow.md)
* [Registration Server API](https://github.com/WebThingsIO/registration_server/blob/master/doc/api.md)

### Tips
* [Glossary of Terms](https://github.com/WebThingsIO/wiki/wiki/Glossary-of-Terms)
* [Installing Node.js](https://github.com/WebThingsIO/wiki/wiki/Installing-Node.js)
* [Accessing the command line on the Raspberry Pi](https://github.com/WebThingsIO/wiki/wiki/Logging-into-the-Raspberry-Pi)
* [Configuring GPIO on the Raspberry Pi](https://github.com/webthingsio/wiki/wiki/Configuring-GPIO-for-use-with-the-gpio-adapter)
* [Running OAuth locally](https://github.com/WebThingsIO/wiki/wiki/Running-OAuth-Locally)
* [Command line tool for exploring new Zigbee and Z-Wave devices](https://github.com/WebThingsIO/wiki/wiki/Command-Line-Tool)
* [Installing OpenZWave](https://github.com/WebThingsIO/wiki/wiki/Installing-OpenZWave)
* [Node for OpenZWave](https://github.com/WebThingsIO/wiki/wiki/Node-for-OpenZWave)
* [Debugging Z-Wave](https://github.com/WebThingsIO/wiki/wiki/Debugging-OpenZWave)
* [Debugging Zigbee](https://github.com/WebThingsIO/wiki/wiki/Debugging-Zigbee)
* [Recording Zigbee frames sent by XCTU](https://github.com/WebThingsIO/wiki/wiki/Recording-Frames-sent-by-XCTU-(Zigbee))
* [Zigbee attributes](https://github.com/WebThingsIO/wiki/wiki/Zigbee-Attributes)
* [Setup of eslint in PyCharm](https://github.com/WebThingsIO/wiki/wiki/PyCharm-Setup)
* [Loop mounting a Raspberry Pi image file under Linux](https://github.com/WebThingsIO/wiki/wiki/Loop-mounting-a-Raspberry-Pi-image-file-under-Linux)

### External Resources
* [Mozilla Hacks Blog - Web of Things](https://hacks.mozilla.org/category/web-of-things/) - Original Mozilla WebThings blog
* [TwoBraids Blog](https://www.twobraids.com/search/label/programming) - Blog posts about WebThings
