# Things

On the WebThings platform, connected devices are referred to as "things".

## Add Thing

To add a thing to your gateway, click the "+" button on the Things screen. This will tell the gateway to start scanning for new devices.

**🗒️ Note:** Many smart home devices will require the user to press a pairing button of some kind in order to initiate a pairing mode. You should follow any instructions that came with your device to enable pairing mode before clicking the "+" button.

![A screenshot showing an empty screen with a main menu and an add button](images/empty_things_screen.png)

A preview of any discovered devices will appear on the screen.

![A screenshot showing the add thing screen with some thing previews of devices that have been found](images/add_thing_screen-new_things.png)

When a device has multiple capabilities (e.g. it acts as both an on/off switch and an energy monitor) you can choose the primary function to display in the user interface from a drop-down menu.

You can also change the name of the device to something meaningful to you (e.g. "Kitchen Light") before clicking "Save" to add it to the gateway.

If you click the back button at the top left of the screen to go back to the Things screen, you should now see an icon representing the device you added.

![A screenshot showing an icon for a Living Room Light](images/things_screen-single_thing.png)

**🗒️ Note:** Only the Zigbee, Z-Wave and Web Thing add-on adapters are installed by default. To support other types of devices, you will need to install additional [add-ons](../settings#add-ons).

### Add Thing by URL

In addition to scanning for new devices, you can manually add a new thing by its "web thing URL". That is the URL of a [Web Thing Description](https://webthings.io/api/#web-thing-description).

**🔧 Technical Note:** Currently the gateway only supports [Web Thing Description](https://webthings.io/api/#web-thing-description)s following the legacy Mozilla format. There is a [work-in-progress add-on adapter](https://github.com/WebThingsIO/wot-adapter) for supporting W3C WoT compliant Thing Descriptions.

To add a thing by a web thing URL, click the "Add by URL" link on the Add Thing screen.

![A screenshot showing the Add Thing screen with the Add by URL link](images/add_thing_screen-scanning.png)

A form will then appear with a text box into which you can paste a web thing URL. Click "Submit" to retrieve details about the Thing, then click "Save" to add it to the gateway.

![A screenshot showing the Add Thing screen with the Add by URL link](images/add_thing_by_url.png)

## View Things

To view all of your things, select the "Things" option from the main menu.

Each thing is represented by an icon. The icon shows a live overview of the current state of the thing (e.g. its on/off state or the current value of a key property). Different styles of icon are used for different types of devices.

![A screenshot showing a collection of icons representing things](images/things_screen.png)


### Thing Detail

To view the properties and actions of a thing, click on the small round detail button at the top right of a thing icon. This will navigate to its detail view.

![A screenshot showing the detail view of a thing, including an on/off property and a brightness property](images/thing_detail.png)

The detail view will show you all of the properties and actions associated with a device.

#### Properties

Properties may be read-only (e.g. a temperature reading) or writable (e.g. an on/off state which can be toggled with a switch, or a level which can be set with a slider).

There are many different types of properties for different types of devices, which each have a specialised user interface.

![A screenshot showing the detail view of a thing, including an on/off property, brightness, color, color temperature and color mode](images/thing_detail-dimmable_color_light.png)

#### Actions

Actions are represented by a button and may accept one or more input values (e.g. a percentage to fade a light to over a specified number of seconds).

![Screenshot of showing the detail of a thing with buttons to invoke actions](images/action_and_events_things.png)

To provide inputs to an action, click the action's button on the thing detail view and complete the fields in the form which appears before pressing the submit button.

![A screenshot showing a form to provide inputs for an action](images/action_input.png)

If an action doesn't require any inputs then pressing its button will immediately invoke the action.

#### Events

To view a log of events emitted by a thing, click the overflow menu button at the bottom right of the screen and select the "Event log" option.

![A screenshot showing the overflow menu on the thing detail view with the "Event log" option selected](images/event_log_option.png)

You will then be shown a live log of events being emitted by the device, including event data and timestamps.

![A screenshot showing a collection of events represented by boxes showing an event name, data and relative timestamp](images/event_log.png)


**🔧 Technical note**: The gateway's adapter [add-ons](../settings#add-ons) are responsible for mapping various devices and protocols to an extensible set of "[WoT capability schemas](https://webthings.io/schemas/)". These schemas are represented in a machine-readable format via semantic annotations on a Thing Description. Thing Descriptions are then used by the gateway to generate a rich user interface for each type of device capability, property, action and event.

## Edit Thing

To edit a thing, select the "Edit" option from the thing detail overflow menu at the bottom right of the screen.

![Screenshot of the thing detail overflow menu with the "Edit" option selected](images/edit_thing_option.png)

You can then edit the name of the thing and/or its primary device type before clicking "Save" to save your changes.

![Screenshot of the edit thing dialog with a text input to edit its name and a dropdown menu to choose the primary device type](images/edit_thing.png)

## Remove Thing

To remove a thing, select the "Remove" option from the thing detail overflow menu at the bottom right of the screen.

![Screenshot of the thing detail overflow menu with the "Remove" option selected](images/remove_thing_option.png)

You will then be asked to confirm the removal of the device from the gateway.

![Screenshot of the confirm remove thing dialog with a remove button](images/confirm_remove_thing.png)

**🗒️ Note:** Whilst removing a device from the gateway using the remove thing feature will remove it from the gateway user interface, it might not always fully un-pair it from the gateway at the hardware level (e.g. if using a USB dongle). Sometimes a device will have an un-pairing procedure which needs to be followed in order to full disassociate it from the gateway (e.g. involving pressing a button on the device).



