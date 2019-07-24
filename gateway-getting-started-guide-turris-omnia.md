# Getting Started

## WebThings Gateway for Turris Omnia

**Warning:** WebThings Gateway for Turris Omnia builds are currently highly experimental. So far the WebThings Gateway web interface only provides very basic router settings and it is not suitable for replacing your existing router software. We do not recommend using these builds for your primary home router.

<img src="/images/turris_omnia.png" width="400">

[WebThings Gateway](https://iot.mozilla.org/gateway/) is a software distribution for smart home gateways which allows users to directy monitor and control their smart home over the web without a middleman.

### What you will need

1. **A [Turris Omnia](https://www.turris.cz/en/omnia/)** router
2. **A USB stick** (at least 256MB)
3. **USB dongles** (see the list of [compatible adapters](https://github.com/mozilla-iot/wiki/wiki/Supported-Hardware#adapters))

**Note:** The Turris Omnia comes with Wi-Fi built in. The USB dongles are needed if you want to support other smart home protocols like Bluetooth, Zigbee and Z-Wave.

### 1. Download Image

First download the latest Turris Omnia gateway image from the [Mozilla IoT website](https://iot.mozilla.org/gateway/).

### 2. Copy Image

Next you will need to copy the downloaded .tar.gz file onto your USB stick. It should be the only file on the drive.

### 3. Install Image

With the router powered on:
1. Insert the USB stick into one of the USB ports on the router
2. Optionally plug any additional USB dongles into the other USB port
3. Plug one end of a network cable into the WAN port on the back of the router, and the other into a LAN port on your modem or existing broadband router
4. Press and hold the blue reset button on the back of the router until 4 LEDs (power, 0, 1 and 2) are lit 
5. Release the reset button

The router will show various sequences of lights as the image is copied and it reboots. It can take around 5 minutes for this to complete.

### 4. Connect Wi-Fi
When the router finishes starting up it will create a Wi-Fi hotspot called "**WebThings Gateway XXXX**" (where XXXX are four digits from your router's MAC address). Connect to that Wi-Fi hotspot using your desktop/laptop computer, smartphone or tablet.

<img src="./images/wifi_ssid.png" width="300">

Once connected you should be prompted to "Create a new Wi-Fi network" by configuring the network name (SSID) and password.

<img src="/images/router_wifi_setup.png" width="800">

Enter an SSID (or keep the default) and a password, then click "create".

**Note:** If you are connected to the "WebThings Gateway XXXX" Wi-Fi network but you don't see the welcome screen, you can try typing http://192.168.2.1 into your web browser’s address bar to manually navigate to the page.

Re-connect to the new Wi-Fi network by entering the password you just set, and navigate to http://gateway.local or http://192.168.2.1 in your web browser to continue setup.

### 5. Choose Subdomain

You will then be given the option to register a free subdomain to safely access your gateway over the Internet using a [secure tunnelling service](https://github.com/mozilla-iot/wiki/wiki/Gateway-Remote-Access) provided by Mozilla.

![Choose subdomain](/images/choose_subdomain.png)

Enter your choice of subdomain and an email address in case you need to retrieve it later, then click "Create".


**Notes:**
 * You can choose to skip this step (either to only use the gateway locally on your home network or manually configure DNS yourself), but note that currently if you do skip this step you'll have to re-flash the gateway in order to register a subdomain.
 * If neither http://gateway.local or http://192.168.2.1 will load in your browser, double check your computer is definitely connected to the Wi-Fi network you just created.
 * If you have previously registered a subdomain you want to re-use, enter the subdomain and the email address you used to register it and follow the on-screen instructions to re-claim it.
 
### 6. Create User Account
Once you have registered your subdomain you should be automatically redirected to the next step of the setup process, which is to create your first user account on the gateway. Enter your name, email address and a password then click "Next".
 
![Create user account](/images/create_user_account.png)
 
***Note:*** You can create additional user accounts later.
 
### Success!
You should then be redirected to an empty "Things" screen of the gateway where you can start to add devices.
 
![Things screen](/images/things_screen.png)
 
See the [WebThings Gateway User Guide](./gateway-user-guide.md) to learn how to use your gateway.
