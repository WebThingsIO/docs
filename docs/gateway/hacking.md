# Development

WebThings Gateway is an open source project maintained by a [community](https://webthings.io/community/) of volunteers.

To get started hacking on the gateway, see the [README](https://github.com/WebThingsIO/gateway/blob/master/README.md) and [wiki](https://github.com/WebThingsIO/wiki/wiki/).

As of version 2.0, the API exposed by the gateway is compliant with the [W3C Web of Things](../../wot/introduction/) 1.x family of standards. 

<img src="../images/w3c_wot_logo.png" alt="W3C WoT logo" style="width: 100%; max-width: 250px; display: block; margin: 40px auto;">

This includes [WoT Thing Description 1.1](https://www.w3.org/TR/wot-thing-description11/) for describing connected devices in a standardised way, [WoT Discovery 1.0](https://www.w3.org/TR/wot-discovery/) for exposing a directory of devices, and [WoT Profiles 1.0](https://www.w3.org/TR/wot-profile/) (including the [HTTP Basic Profile](https://www.w3.org/TR/wot-profile/#http-basic-profile) and [HTTP SSE Profile](https://www.w3.org/TR/wot-profile/#http-sse-profile)) for providing interoperability guarantees.


**🗒️ Note:** Versions 1.0 and 1.1 of the gateway used our legacy [Web Thing API](https://webthings.io/api/). You can see an overview of differences between the two [here](https://github.com/webthingsio/wiki/wiki/Mozilla-W3C-Differences).

## Add-on Development

WebThings Gateway has a directory of community-contributed [add-ons](../settings#add-ons) which enhance its capabilities.

To learn how to develop your own add-on or contribute to an existing one, you may want to start with the resources below:

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
* [Updating add ons for WebThings Gateway 2.0](https://github.com/WebThingsIO/wiki/wiki/Updating-add-ons-for-WebThings-Gateway-2.0)