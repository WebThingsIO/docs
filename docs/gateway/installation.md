# Installation

As of the 2.0 release the recommended way to install WebThings Gateway is to use the [Docker image](#docker). There is also an experimental [snap package](#snap), or you can choose to [build from source](#build-from-source).


## Docker

<img src="../images/webthings_gateway_docker.svg" alt="WebThings Gateway Docker" style="width: 100%; max-width: 250px; display: block; margin: 20px auto;">

Once you have [installed Docker Engine](https://docs.docker.com/engine/install/) on your host operating system of choice, downloading and running the [WebThings Gateway Docker image](https://hub.docker.com/r/webthingsio/gateway) can be achieved with a single command.

On Linux:

```
docker run \
    -d \
    -e TZ=America/Los_Angeles \
    -v /path/to/shared/data:/home/node/.webthings \
    --network="host" \
    --log-opt max-size=1m \
    --log-opt max-file=10 \
    --name webthings-gateway \
    webthingsio/gateway:latest
```

On Windows or macOS:
```
docker run \
    -d \
    -p 8080:8080 \
    -p 4443:4443 \
    -e TZ=America/Los_Angeles \
    -v /path/to/shared/data:/home/node/.webthings \
    --log-opt max-size=1m \
    --log-opt max-file=10 \
    --name webthings-gateway \
    webthingsio/gateway:latest
```

You should change `/path/to/shared/data` to the location where you would like the gateway to store its local data, e.g. a folder in your home directory.

Once the image has been downloaded and started you should be able to configure the gateway by loading its web interface at [https://localhost:8080](https://localhost:8080).

For more options such as customising the timezone, customising the ports the gateway runs on, or giving the Docker image access to certain hardware, please see the [Docker README](https://github.com/WebThingsIO/gateway/blob/master/README.docker.md).

## Snap

<img src="../images/webthings_gateway_snap.svg" alt="WebThings Gateway Snap" style="width: 100%; max-width: 250px; display: block; margin: 20px auto;">

As of the 2.0 release there is also an experimental [snap package](https://snapcraft.io/webthings-gateway) which you can install on your Linux distribution of choice.


On Ubuntu Server/Ubuntu Desktop:

```
$ sudo snap install --edge webthings-gateway
$ sudo snap connect webthings-gateway:system-observe
$ sudo snap connect webthings-gateway:hardware-observe
$ sudo snap connect webthings-gateway:network-manager
$ sudo snap set system experimental.hotplug=true
$ sudo snap restart webthings-gateway
```

On Ubuntu Core:

```
$ snap install --edge webthings-gateway
$ snap install network-manager
$ snap connect webthings-gateway:system-observe
$ snap connect webthings-gateway:hardware-observe
$ snap connect webthings-gateway:network-manager network-manager:service
$ sudo snap set system experimental.hotplug=true
$ snap restart webthings-gateway
```

Once the snap package has been installed you should be able to configure the gateway by loading its web interface at [https://localhost:8080](https://localhost:8080).

The snap is currently untested on other Linux distributions.

For more options such as giving the snap access to USB devices, please see the [snap README](https://github.com/WebThingsIO/gateway/blob/master/README.snap.md).

## Build from Source

<img src="../images/webthings_gateway_source.svg" alt="WebThings Gateway Source" style="width: 100%; max-width: 250px; display: block; margin: 20px auto;">

To build the gateway from source code, please see the [README](https://github.com/WebThingsIO/gateway/blob/master/README.md#prerequisites-for-building).

Essentially, once you have installed all the build dependencies it's a case of running:

```
$ git clone https://github.com/WebThingsIO/gateway.git
$ cd gateway
$ npm ci
$ npm start
```

The gateway's web interface should then be available at [http://localhost:8080](http://localhost:8080) by default.

## OS images for Raspberry Pi

<img src="../images/webthings_gateway_pi.svg" alt="WebThings Gateway for Raspberry Pi" style="width: 100%; max-width: 250px; display: block; margin: 20px auto;">

⚠️ **Note:** Older versions of the gateway were shipped as a full OS image which could be flashed onto a Raspberry Pi. These images are not currently available for WebThings Gateway 2.0.

![Illustration of a Raspberry Pi single board computer, a microSD card and a USB dongle](images/components.png)

To install WebThings Gateway 1.x on a Raspberry Pi you will need:

1. A **[Raspberry Pi®](https://www.raspberrypi.com/products/)** single board computer (Raspberry Pi 3 or 4 recommended, Pi 5 not yet supported) and power supply
2. A **microSD card** (At least 8GB, class 10 recommended)
3. **USB dongles** (Optional, see the list of [supported hardware](../supported-hardware))

**🗒️ Note:** The Raspberry Pi 3 and 4 come with Wi-Fi and Bluetooth radios. The USB dongles are needed if you want to support other smart home protocols like Zigbee and Z-Wave.

### 1. Download Image

First download the latest 1.x gateway image from the [WebThings website](https://webthings.io/gateway/).

### 2. Flash Image

Next you will need to flash the downloaded image onto your microSD card. There are [various methods](https://www.raspberrypi.com/documentation/computers/getting-started.html) of doing this but we recommend using [Etcher](https://etcher.balena.io/).

![Screenshot of the Etcher user interface showing an .img file as the source and a card reader as the target](images/etcher_screenshot.png)

1. Open Etcher
2. Insert your SD card into an SD card reader attached to your computer
3. Select the downloaded image as the source file
4. Select your SD card as the target
5. Click "Flash!"

Once flashing is complete, remove the microSD card.

### 3. Boot Raspberry Pi

![An illustration showing first inserting the microSD card, then inserting a USB dongle then plugging in the power supply](images/assembly.png)


1. Insert the flashed microSD card into your Raspberry Pi
2. Plug in any USB dongles
3. Connect the power supply to boot the Pi
4. Check that the LEDs light up: red indicates power, green indicates activity
5. Wait a few minutes for the software to boot

**🗒️ Note:** On first boot the Raspberry Pi may take an additional 2-3 minutes longer to boot in order to take care of some first time setup.

