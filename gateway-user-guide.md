# User Guide

## WebThings Gateway for Raspberry Pi User Guide
[WebThings Gateway](https://iot.mozilla.org/gateway) by Mozilla is a software distribution for smart home gateways which allows users to directly monitor and control their smart home over the web, without a middleman.

This guide assumes you have already followed the [Getting Started Guide](https://mozilla-iot.github.io/docs/gateway-getting-started-guide.html) to bring your gateway online.

## I. Introduction

Congratulations on choosing to set up your own private Smart Home Gateway. This guide provides an overview of
what is currently referred to as the “WebThings Gateway” by Mozilla. This guide covers release version 0.8. Hereafter we will
usually just refer to it as the "gateway". 

The gateway lets you directly monitor and control your home over the web. Unlike many smart home hubs and connected 
IoT devices on the market, your data is not stored or processed in the cloud. It stays in your home on the gateway. 
The gateway can often bypass the need for you to purchase an IoT hub for each brand. And instead of downloading a 
different app for each brand, you can manage everything from one place, using any web browser.

This guide will explain how to customize your gateway, including connecting smart home devices, creating rules to automate 
your home, experimenting with voice and text-based commands, and a few additional tips.

The following image shows a typical collection of smart home devices, the top row shows the Raspberry Pi, power supply 
and a Zigbee USB dongle. The bottom row shows a door sensor, smart plugs, smart bulb, and motion sensor.

<img src="./images/image53.png" alt="smart home devices" width="400">

## II. Smartphone Application Convenience

Currently there is no specific smartphone application for the gateway, but you can load your unique gateway url into a smartphone browser application and save it to your home screen, which makes it work just like any other application. 

If you use Mozilla's tunneling service, your gateway url will be of the form `[your_subdomain].mozilla-iot.org`. 

We recommend that you **bookmark** the web address on all devices that you have access to from home. 
It is also handy to save your Things Gateway as a **web application on the home screen** of your phones and tablets.

On Android phones/tablets: 
* In Firefox: Select the “add to home” icon in the address bar (circled in red) to add an app icon to your home screen. 
* In Chrome: Select “Add Things to Home screen”. 

<img src="./images/image3.png" alt="firefox add to home" width="300"><img src="./images/image23.png" alt="firefox as web app" width="300">

On iPhones and iPads: 
* In Safari: Select the Share icon, and then “Add to Home Screen”. 
* (Note that iOS does not currently support an "add to home screen" function for Firefox or Chrome browsers.)

<img src="./images/image35.png" alt="safari share" width="300"><img src="./images/image37.png" alt="safari add to home" width="300">

## III. Adding and Managing Smart Home Devices

### Scan For and Add Smart Devices

Pick a device to add and prepare it for pairing. Typical preparation steps for Zigbee and Z-Wave devices are as follows:
* Smart bulb: screw into a light fixture that it is turned on (bulb should be lit when ready for pairing)
* Smart plug: plug into an outlet
* Other powered devices: plug in and turn on
* Battery-operated devices such as door/window sensors, motion detectors, pushbuttons, dimmer switches, leak detectors, 
temperature sensors, and more: remove tab from battery, or plug in battery, to power on

<img src="./images/image6.jpg" alt="sensor battery tab" width="250">

**TIP**: Some devices come pre-paired with controllers or IoT hubs. First follow the manufacturers instructions to do 
a **factory reset** on those devices before attempting to pair them with your Mozilla gateway. Refer to the appendix 
and to the wiki for more information.

When you are ready to add devices to your Things Gateway, we recommend that you provision devices one at a time. 

From the main “Things” page, select the <img src="./images/image10.png" alt="plus" width="20">
button at the bottom right corner. 
The gateway will begin scanning to discover unprovisioned and unconfigured devices that are nearby.

<img src="./images/image33.png" alt="scan things" width="800">

When a new device is found, it will appear on the Things scan page. Rename the device, then select 
‘Save’ to add it, and ‘Done’ when you are finished.

<img src="./images/image2.png" alt="save things" width="800">

**TIP**: When naming your smart devices, we recommend using a name that helps you remember where they are 
located in your home. For example, “Bedroom Light”. Choose simple names that will be easy to remember and use if 
you want to command and control your home using voice commands.

Repeat these discovery steps for each device. Powering them up and scanning for them one at a time helps you 
identify each device. 

### Control Your Things

First learn how to monitor and control each device by checking out its capabilities. Then in the next section 
you can learn to create rules to automate interactions between devices.

Devices are displayed on the Things screen and the Floorplan screen. You can toggle light bulb and smart plugs 
on and off by directly clicking on the device icon. You can also see the current state of devices such as 
door sensors and motion detectors, from these screens. 

<img src="./images/image17.png" alt="things screen" width="800">

To view and control additional details, click the <img src="./images/image18.png" alt="bubble" width="20"> icon 
toward the top-right of a device icon. A detailed thing page should open. 

<img src="./images/image32.png" alt="detailed things screen" width="800">

To edit a device’s name or remove it altogether, select 
the <img src="./images/image34.png" alt="edit" width="20"> icon in the bottom right-hand corner.

<img src="./images/image26.png" alt="edit menu" width="200">

## IV. Rules: Automate Your Home

Now that your Mozilla Things Gateway is set up and your smart things are connected, you can start automating 
your home for your convenience by creating ‘Rules’. Practice creating a rule by following the next few steps. 

### Create a Rule

Navigate to the “Rules” page from the main menu. Click the <img src="./images/image10.png" alt="plus" width="20"> icon 
in the lower right corner to create a new rule. In Rule creation, the basic logic is: if (A), then (B). Optionally, 
you can change “if” to “while” and combine multiple inputs for (A), and take action against multiple outputs for (B). 

<img src="./images/image29.png" alt="new rule" width="800">

Let’s start by grabbing our input: time. Drag the ‘clock’ from the bottom of the screen to the left side of the Rule space. 
Since we want something to occur at 10pm, set the time to ‘10pm’.

<img src="./images/image21.png" alt="clock as input" width="800">

Next we select our output: a smart bulb named "Bedroom Light". Drag the light you want to turn off at 10pm to the right 
side of the Rule space.

<img src="./images/image27.png" alt="light action" width="800">

To complete the rule, select the desired property of the smart light that you want to set at 10pm. 
In this example, we want the bedroom light to turn “Off” at 10pm. Go to the light's drop down menu and select ‘Off’. 
The clock and light bulb rectangles should now be connected by a black line, and the “If” statement under 
your Rule name should be updated to reflect the logic of this rule.

<img src="./images/image20.png" alt="completed rule" width="800">

In the top left hand corner, click the tiny pencil near "Rule Name" to edit the name of your rule. For example, 
you can name this rule “At 10pm, turn off bedroom light”. 
For clock-based rules, the “If” statement below the name is appropriate logic. For other situations, such as 
turning on a light only when a door is open, you can change it to "While" instead. When you have more than 
one input parameter, you can select "And" or "Or" as the logical condition to tie together the input parameters.

Click on the back-arrow button in the upper left-hand corner of the Rule space (next to the name), 
to save the rule and return to the main Rule overview page.

### View/Edit, Disable/Enable, or Remove a Rule

From the main Rules view, each rule is represented by a rectangle. 
* View/Edit. You can view or change a rule by hovering over the middle of the rectangle and selecting the "Edit" button. 

<img src="./images/image40.png" alt="rule mouse over" width="600">

* Disable/Enable. You can disable a rule by toggling the "switch" element to the left, which will turn the circle color 
to grey. You can re-enable the rule by toggling the switch element back to the right, turning the circle back to white.

<img src="./images/image13.png" alt="enable or disable rule" width="300">

* Remove. To remove (permanently delete) a rule, hover over the rule rectangle and click on the "(x)" in the upper 
right-hand corner.

<img src="./images/image41.png" alt="remove rule" width="800">

## V. Floorplan: Map the Location of Your Devices

The Floorplan allows you to view your devices as they are positioned within your home. It shows all your devices, 
consistent with what you would see on the Things page, but it lets you see their states mapped over the layput of 
your home. You can still click an icon to change its state, the same as you would on the Things page. However, 
one interaction difference is that you need to click-and-hold on an icon to open the thing's detailed view. 

### Create a Floorplan

First sketch a floorplan of your home, and save it as a digital image. You can draw one by hand and take a picture of it, 
or use an illustrator tool. (If you take a picture of the floorplan using your smartphone, you can upload the image 
directly to your gateway from the phone's browser.)

<img src="./images/image36.jpg" alt="sketched floorplan" width="600">

**TIP**: Save your digital drawing as an SVG file with white lines and a transparent background, using a tool like Inkscape or Sketch, for a minimalist look.

<img src="./images/image14.png" alt="svg floorplan" width="800">

### Upload Floorplan

Click on the pencil icon <img src="./images/image11.png" alt="pencil" width="20"> in the lower right corner of the floorplan 
page to enter edit mode. An "upload file" button will appear -- click on it to select the floorplan image to be uploaded. 

<img src="./images/image7.png" alt="upload floorplan" width="800">

After the floorplan image is uploaded, make sure you are still in edit mode, and then drag the thing icons from the top 
of the page onto the floorplan. Click the check mark <img src="./images/image28.png" alt="checkmark" width="20"> 
in the lower right corner when done.

<img src="./images/image30.png" alt="position things on floorplan" width="800">

## VI. Add-Ons: Extend your Gateway’s Capabilities

The gateway has an add-ons system so that you can extend its capabilities. A few add-ons are installed by default 
(Web Thing, Zigbee, and Z-Wave) so that your gateway will work with a large number of commercial devices right 
out of the box. However, you can boost support for additional devices if they are supported by an Add-on. You'll 
find the Add-on page under Settings.

### Locate and Install More Add-Ons As Needed

From the Settings menu, select Add-Ons. 

<img src="./images/image12.png" alt="addons" width="800">

To enable more Add-Ons, click the "(+)" button in the lower right to browse the add-on list, 
then select ` + Add` to enable any additional add-ons. For example, if you have TP-Link or HomeKit compatible 
devices at home, you can install their add-ons, then discover and pair the devices so that they can be managed 
by your Mozilla gateway. 

<img src="./images/image24.png" alt="select addon" width="600">

New add-ons will continue to be developed to enable control of newly supported devices, so check back periodically 
to scan new Add-ons in the list. You can submit requests for additional device support in the issues tab of the 
[gateway software development site](https://github.com/mozilla-iot/gateway/issues).

## VII. Experiments

You can try out experimental new features, like the Smart Assistant, and Logging, by enabling them in Experiments.

### Enable Smart Assistant and Logging

From the Settings menu, select Experiments, and then check the boxes to enable the Smart Assistant and Logging. 

<img src="./images/experiments.png" alt="enable experiments" width="800">

### Using the Smart Assistant

Once enabled, the smart assistant page can be selected from the main navigation menu. It lets you use voice and 
messaging commands to control the things in your home. The same commands are possible whether using voice or 
typing text input. 

<img src="./images/image4.png" alt="smart assistant" width="800">

The web interface shows both typed and spoken commands that were made recently, as well as the result of the command. 
If a portion of a command that you spoke was misinterpreted, or just missing, try again. Remember to speak loud and 
clear near your PC's microphone.

You can give it commands like “Turn the kitchen light on” and it will respond to you to confirm the action. So far it 
can understand a basic set of commands to turn devices on and off, set levels, set color and set color temperatures.

The first time you click on the microphone icon, your browser will ask for permission to use your computer’s microphone. 
From the popup dialog, click the “Remember this decision” checkbox, then select “Allow”.

Note that in the 0.8 gateway release, browser-based voice commands are processed using Google's voice assistant API, 
so the audio strings are processed in the cloud. The speech-to-text result is passed back to your gateway. If you instead 
type a command into the text field of the smart assistant screen, those commands are processed locally and do not 
require a connection to the Internet.

### Using Logging

Once enabled, the logging page is visible in the main navigation menu. Any devices that can be logged will be visible from
the configuration screen, accessed by clicking the plus icon in the lower right corner. Select the device you want to log, 
the property you want to log, and duration of log data you want to store on your gateway.

<img src="./images/log-temp.png" alt="log temp" width="800">

## VIII. Additional Settings

Browse the other pages listed under the Settings menu to find additional configuration and capabilities. 

<img src="./images/settings.png" alt="settings menu" width="800">

### Domain

The default localhost name is gateway.local, but you can change it to match your subdomain or choose a different name.

<img src="./images/image42.png" alt="localhost name" width="800">

### Network

A Raspberry Pi gateway can connect to your local network using Wi-Fi or Ethernet. On the network configuration page you can 
see which settings are active, and click either option to change the configuration. Be careful with these settings, because 
if your gateway loses access to the local network, your ability to access the UI in a web browser will stop working.

<img src="./images/network.png" alt="network settings" width="800">

### Users

You can add as many user accounts as you like, so that everyone has their own unique login. Although all users currently have the same access and control privileges, a future feature will be to allow lesser privileges to some users, 
such as children or guests.

<img src="./images/image45.png" alt="user accounts" width="800">

Click the "(+)" icon to provision more user accounts.

<img src="./images/image46.png" alt="add user" width="800">

### Add-ons

The gateway supports a unique and flexible Add-on framework that helps users tie legacy devices, non-IP devices, and other 
non-standard devices into the web thing API framework. Only three add-ons are installed by default, and the rest must be 
added manually by the user. Because the add-on upgrades are independent from the core gateway application, they can be 
updated at any time.

<img src="./images/addons.png" alt="add-ons" width="800">

Click the "(+)" icon to install optional add-ons.

<img src="./images/addon-discovery.png" alt="add-on discovery" width="800">

Some add-ons require configuration in order to function (e.g., Pulse, Weather, ONVIF). Others work as soon as they are added 
(e.g., Virtual Things). 

<img src="./images/addon-config-pulse.png" alt="add-on config" width="800">

### Adapters

The Adapters page shows which of the Add-ons are currently installed and active. Go to the Add-ons page to add or remove 
adapters that are shown on this page.

<img src="./images/image44.png" alt="adapters" width="800">

### Updates

Assuming your gateway is connected to the Internet, system updates will be applied automatically when a new 
stable release is ready. New versions are being released approximately quarterly.

<img src="./images/image47.png" alt="updates" width="800">

### Authorizations

Authorizations are enabled in "Settings" by selecting "Developer => Create local authorization". This page shows 
whether or not an authorization has been enabled.

<img src="./images/image48.png" alt="authorizations" width="800">

### Developer

On the "Developer" page you can enable ssh, for connecting directly to the Raspberry Pi console. The default 
username is "pi", and the default password is "raspberry". If you decide to enable ssh, we recommend that you 
immediately ssh into the RPi to change the default password. Type the password command `$ passwd` and follow the prompts 
to change the pi user's password.

<img src="./images/image49.png" alt="developer menu" width="800">

Click "View Logs" to see raw logs displayed in your browser.

<img src="./images/image50.png" alt="view logs" width="200">

Click "Create local authorization" to establish a secure web token that can be exchanged with 3rd party 
applications and services that you may want to enable, or simply for accessing the data using your own 
development tools.

<img src="./images/image51.png" alt="create auth" width="800">

## IX. Support

For support, please sign up to our IoT Discourse forum (https://discourse.mozilla.org/c/iot) or email iot@mozilla.com 
or join us on Mozilla IRC #iot channel 
or post issues on [github](https://github.com/mozilla-iot/gateway/issues). 

## Appendix: Tips on Pairing and Unpairing Smart Devices

Although you typcially can follow manufacturer instructions to pair and unpair devices, there are additional tricks to 
discovering devices. Some devices have a "chain link" or other button that you should click when you are ready to scan 
for the new device. Other products have reset buttons that you have to hold for some period of time to reset the device. 
Still others require multiple power cycles, double-button presses and various schemes. Unfortunately there is no common 
approach across a broad spectrum of device makers! Our supported devices wiki will likely be your best bet to see methods 
that have work for us.
