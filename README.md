* TOC {:toc}

# Introducing PiWebcam

With PiWebcam you can turn a **Raspberry Pi** into a **fully-featured, dummy-proof Webcam** with just one click.

Even if there are already around a number of projects for using a Raspberry Pi as a webcam, they often require advanced knowledge and skills and look like more ad-hoc solutions rather than finite, reusable products.

PiWebcam is intended to provide a **powerful imaging platform for everyone**, regardless of his/her previous knowledge.

PiWebcam ships as an **ready-to-be-flashed SD card image**. Alternatively, an installation script takes care of fully configuring a vanilla Raspbian with the required software and reasonable default settings. 

Thanks to its powerful **motion detection** feature, augmented by an **object recognition** capabilities, PiWebcam can notify the user by sending the motion picture to an **e-mail** recipient or a **Slack** channel.


## Features

* Can be installed and configured by running a single command
* Simple, mobile-friendly web interface
* Snapshot and video recording upon motion detection
* AI-based object recognition capabilities to prevent false positives
* E-mail and Slack notifications
* Can act as an Access Point or connect to an existing WiFi network
* Can be accessed from the Internet without any additional configuration
* Survive to any power outages
* Can switch automatically to night mode and control IR Leds and IR Cut filter
* Old files are automatically purged when the SD card is almost full
* Ability to import/export the entire configuration of the device
* Queue notifications when offline

# Requirements

* Raspberry Pi Model 3 or Raspberry Pi Zero W
* Raspberry Pi Camera (any model) or a Generic USB Camera
* SD Card (16GB recommended)

# Installation

## Option 1: flash a pre-configured PiWebcam image (recommended)

* Download the latest PiWebcam image (.img.zip) from <https://github.com/piwebcam/PiWebcam/releases>
* Unzip the file
* Write the image to a SD card (<https://www.raspberrypi.org/documentation/installation/installing-images/>)
* Plug the SD card on your Raspberry Pi and power it on

## Option 2: build a PiWebcam image

Installing PiWecam would require a fresh installation of Raspbian and a SD card. Please do not re-use an existing installation but start from scratch as listed below:

* Download Raspbian Stretch Lite operating system (<http://downloads.raspberrypi.org/raspbian_lite/images/raspbian_lite-2019-04-09/2019-04-08-raspbian-stretch-lite.zip>)
* Unzip the image
* Write the image to a SD card (<https://www.raspberrypi.org/documentation/installation/installing-images/>)
* Download the latest release of PiWebcam (.zip) from <https://github.com/piwebcam/PiWebcam/releases>
* Extract and copy the `PiWebcam` directory into the boot partition (on Windows, the only one accessible)
* For a headless setup, review https://www.raspberrypi.org/documentation/configuration/wireless/headless.md
* Plug the SD card on your Raspberry Pi, power it on and connect to it through SSH (Hostname: raspberrypi.local, Username: pi, Password: raspberry)
* Ensure the Raspberry is connected to Internet
* Run `sudo /boot/PiWebcam/PiWebcam.sh install`

At the end of the installation you will be requested to reboot the device to make the changes fully effective.
All the credentials will be summarized on the screen. 

Once rebooted, the device will start acting as an Access Point. 

## Default Credentials

* **WiFI Access Point**:
    * **SSID**: PiWebcam-*XXXXX*"
    * **Passphrase**: PiWebcam-*XXXXX*
* **Web**:
    * **Username**: admin
    * **Password**: PiWebcam-*XXXXX*
* **SSH**:
    * **Username**: admin
    * **Password**: PiWebcam-*XXXXX*
    
Where *XXXXXX* are random characters set during the installation process (e.g. *PiWebcam-d68c2f*)

## First Usage

Connect to the WiFi network created by the device and point your browser to http://PiWebcam.local to finalize the configuration.

To connect the webcam to an existing WiFi network, go to Device / Network, select "*WiFi Client*" and fill in your
"*WiFi Network*" and "*Passphrase*".

The entire device configuration (camera, network, notification and system settings) can be performed through the web interface. 
The configuration file can be easily exported and imported under Device / System. 

Furthermore, the configuration file (`PiWebcam.conf`) is stored in the boot partition under the PiWebcam folder and can be altered or copied out from there as well.

# Configuration

PiWebcam already comes with reasonable default settings. Once installed, no additional configuration is required; PiWebcam will start taking snapshots and record videos, whether is connected or not to the network.

To access the webcam and/or customize the settings, connect to the web admin panel.

For a detailed description of the menus available through the web interface and CLI commands, please see the [User Guide](https://github.com/piwebcam/PiWebcam/tree/master/PiWebcam)

# Build a real webcam based on PiWebcam

For step by step instructions for building a webcam based on PiWebcam please visit <https://www.instructables.com/id/Fully-featured-Outdoor-Security-Camera-Based-on-Ra/>

A sample bill of materials to build indoor and outdoor webcams based is provided below.

## Indoor Webcam BOM

Item  | Cost | Link
------  | ------| ------ 
Raspberry Pi Zero W  | $20 | https://www.aliexpress.com/item/-/32836672820.html
Acrylic Case | $1 | https://www.aliexpress.com/item/VONETS-Acrylic-Case-Cover-Box-Shell-Aluminum-Heatsinks-40-Pin-Connector-Header-Screwdriver-Screw-Set-for/32811914803.html
16GB SD Card | $5 | https://www.aliexpress.com/item/Original-SanDisk-80mb-s-class-10-128gb-64gb-32gb-16gb-Ultra-memory-TF-micro-SD-Card/32689968307.html
2.5A  Power Supply | $3 | https://www.aliexpress.com/item/5V2A-Power-Supply-Adapter-Micro-Port-Power-Charger-US-EU-UK-AU-With-ON-OFF/32520570725.html
Camera cable for Pi Zero | $1 | https://www.aliexpress.com/item/For-Raspberry-Pi-Zero-Camera-Cable-FFC-Cable-For-Raspberry-Pi-zero-W-H-zero-1/32890256486.html
Acrylic Camera Holder | $1 | https://www.aliexpress.com/item/Acrylic-Holder-Camera-Mount-Bracket-For-Raspberry-Pi-3-B-3-Mounting-Bracket/32902702298.html
Raspberry Camera Night Vision with IR-CUT and Wide Angle  | $17 | https://www.aliexpress.com/item/Raspberry-Pi-3-B-IR-CUT-Camera-Night-Vision-Focal-Adjustable-5MP-Fish-Eye-Automatically-Switch/32881466491.html
| **$48** |

## Outdoor Webcam BOM

Item  | Cost | Link
------  | ------| ------ 
Raspberry Pi Zero W  | $20 | https://www.aliexpress.com/item/-/32836672820.html
Waterproof Camera Housing  | $7 | https://www.aliexpress.com/item/CCTV-Camera-Housing-Outdoor-Bullet-Camera-s-Case-Shell-Whit-for-Security-CCTV-IR-IP-Camera/32844215710.html
16GB SD Card | $5 | https://www.aliexpress.com/item/Original-SanDisk-80mb-s-class-10-128gb-64gb-32gb-16gb-Ultra-memory-TF-micro-SD-Card/32689968307.html
IR Cut Double Filter | $1 | https://www.aliexpress.com/item/HD-MP-IR-CUT-filter-M12-0-5-lens-mount-double-filter-switcher-for-cctv-camera/32793880567.html
12v - 5v buck regulator | $1 | https://www.aliexpress.com/item/Ultra-small-LM2596-power-supply-module-DC-DC-BUCK-3A-adjustable-buck-module-regulator-ultra-LM2596S/32440888820.html
Micro USB Male plug | $1 | https://www.aliexpress.com/item/10sets-lot-Micro-5P-USB-Male-Plug-Solder-Type-Tail-Charging-Plug-90-Degree-Free-Shipping/32846969677.html
12v Female plug | $1 | https://www.aliexpress.com/item/Tanbaby-5pcs-lot-5-5-X-2-1mm-12V-Male-and-Female-DC-Cable-Connector-Adapter/32776328118.html
12v IR Led Array | $2 | https://www.aliexpress.com/item/52mm-diameter-4-array-IR-led-Spot-Light-Infrared-4x-IR-LED-board-DC12V-300-400mA/32904475675.html
12v 3A Power Supply | $4 | https://www.aliexpress.com/item/5V-24V-12V-Lighting-Transformer-AC-110V-220V-to-12V-Power-Supply-1A-2A-3A-5A/32808214233.html
Raspberry Camera Night Vision Wide Angle  | $13 | https://www.aliexpress.com/item/Raspberry-Pi-Zero-W-Camera-Module-Night-Vision-Wide-Angle-Fisheye-5MP-Webcam-with-Infrared-IR/32802572768.html
| **$55** |

# Technical Overview

All PiWebcam files **reside in the boot partition** of the SD card, in a directory called PiWebcam. This includes a single bash file, `PiWebcam.sh` and the PHP pages for the admin panel.

During the installation process,  a very **basic system configuration** is performed, an **initramfs image is created** and the **PiWebcam.sh** script is added to */etc/rc.local* so to be **executed at startup** with the "*configure*" parameter.

At the first reboot, the initramfs image will **shrink the root partition** (previously expanded to fill the entire SD card by the Raspbian installer) and **create a data partition** just after.

Both the boot and root filesystems are mounted read-only and an overlay filesystem is created by the initram image upon the root filesystem so that any change to the system is stored in memory only and get lost at the next reboot. In this way the device will be more **robust to misconfigurations**, can be easily **restored to factory defaults** and can **survive  to any power outage** since no system file is ever written to the SD card during normal operations. 
The **data filesystem** is instead formatted with **F2FS** (*Flash-Friendly File System*) which takes into account the characteristics of flash memory-based storage devices. 

During startup, PiWebcam **reads its configuration file** stored at `/boot/PiWebcam/PiWebcam.conf`,  **configure the system, the camera, the network and the notifications** based on the settings found there (details can be found in the "*API*" section) and **deploy the web interface** from `/boot/PiWebcam/web` into the web root location. Just after the installation or after a factory reset a default empty configuration file is created. Since the root filesystem is volatile and any change lost at the next reboot, all the relevant settings are stored in this configuration file.
The **configuration can be exported and imported** through the web interface or altered / copied out by mounting the SD card to any other system and accessing the FAT32 boot partition. When a device is reset to factory defaults, the configuration is simply deleted and the data partition formatted. 

For the initial configuration, there is **no need to install any mobile app or desktop software**: when no configuration is found, the device **acts as an access point** (by leveraging *hostapd* and *dnsmasq*) so the user can connect to it and customize the network settings.

PiWebcam comes with a **responsive, mobile-friendly web interface** based on the Bootstrap SB Admin 2 template (<https://startbootstrap.com/template-overviews/sb-admin-2/), running on *lighttpd* and exposed on port 80. The web panel, written in PHP and protected with basic authentication, has no real business logic but just wraps CLI commands provided by the PiWebcam.sh script which the web server user has the rights to run as root. When changing the password, the same is applied to both the system and the web interface. 

If **remote Internet access** is enabled, the device initiates a SSH tunnel through <https://serveo.net>, **without the need to configure any NAT or UPnP** in your router. The device name is used as hostname and both the web and ssh services are exposed.  Autossh is used to keep the connection always alive.

Motion detection is based on the excellent **Motion Project software** (<https://github.com/Motion-Project>) which, among the others, is capable of generating a single notification when consecutive motions are detected so you will **not be overloaded with notifications**. **Only relevant settings are exposed** to the user while reasonable defaults are set during the device startup. Both **pictures and movies are stored into the data filesystem** and grouped in folders by year/month/day/hour so to allow an easier access. All the recordings can be reviewed through the web interface with h5ai (<https://larsjung.de/h5ai/>),  a **modern file indexer** which allows files and directories to be displayed in a appealing way and providing picture and video previews without the need to download the content beforehand.

When a motion is detected, PiWebcam.sh is invoked with the "*notify*" parameter through the *on_picture_save*/*on_movie_end* motion's event. 
If object detection is enabled for further analyzing the image, the picture is sent to Clarifai (<https://clarifai.com/>) to **recognize all the objects** within the image. This would work great to lower down false positives e.g. if you are interested to know if there is somebody stealing in your house and not just a sudden light change. **For the security camera use case, Clarifai seems to fit best** since pretty accurate to identify objects and people whereas other services could be integrated in the future (Google Vision works great with landscapes but poorly to identify a person, Amazon Rekognition is accurate but prone to false negatives when identifying persons and its authentication schema is complex to integrate in a bash script). If the AI service cannot be reached, the analysis is queue for when the connection is restored. In case of a false positive (e.g. there are no people in the motion picture), by default both the motion picture and video are deleted and no notification is sent.

After that, PiWebcam check if an Internet connection is available and if so, sends out the notification. In addition to traditional e-mail notifications, sent out with *ssmtp*, with the detected motion picture attached, PiWebcam can also upload the same picture to a **Slack channel**. If you don't know Slack, check it out (<https://slack.com/>); it is a great collaboration tool but can also be used to create a group dedicated to your family, grant access to your family members, chat with them and allow PiWebcam or Home Automation utilities (like e.g. https://www.egeoffrey.com) to post updates over there.
If there is **no Internet connection, the notification does not get lost** but it is **queued and sent out when the connection is restored**.

Periodically, through cron, PiWebcam.sh is called with the "*checkup*" parameter which will **perform routine tasks to ensure the system is running smoothly**. It will reboot the device if the overlayed root filesystem is almost full (even if this shouldn't happen), **remove oldest pictures and movies** from the data directory when the data filesystem fills up, process the notification queue, **restart core services** if no more running and try reconnecting to the network when disconnected.

PiWebcam logs any activity in data filesystem so they survive a device reboot. Logs can be accessed and reviewed through the web interface as well.

An **upgrade functionality** is provided through the web interface as well. A zip file is expected to be uploaded containing a PiWebcam directory and the files of the new version of the software under it (the same package used during the installation). The device can also check for new updates, download and install them automatically. During an upgrade, all the files are extracted into a temporary directory the the PiWebcam.sh script of the new version is run with the "*upgrade*" parameter so to execute the version-specific upgrade routine. A basic upgrade will just replace the files in /boot/PiWebcam with the new one and the same can be done even manually and install additional software if needed.

When building an outdoor webcam, you might want to add to your project an external IR led board and a mechanical IR Cut filter and PiWebcam can handle all of those on your behalf. Night mode manually or automatically and for the latter a pin of the board (21 BCM) is monitored for changes; when turning HIGH, night mode is entered, when turning LOW is left. Entering night mode means turning on the IR leds (if connected) by setting HIGH a pin (26), toggling the IR CUT filter by sending a pulse to a pin (16 for OFF, 20 for ON) and adjusting camera settings for a better representation of the night scene. Keep in mind the GPIO pins cannot drive directly the IR Cut filter or the IR Leds; you would need a H-Bridge or a transistor in between to provide adequate current.

Upon installation, the system and web password as well as the Access Point passphrase are all set to the default device name. Always keep in mind in PiWebcam usability has been preferred over security in most of the cases (no HTTPS, passwords stored in log files, etc.) so consider further protecting the device from a security standpoint.

# About

* Project Page: <https://piwebcam.github.io>
* Bug Report: <https://github.com/piwebcam/PiWebcam/issues>
* Instructables: <https://www.instructables.com/id/Fully-featured-Outdoor-Security-Camera-Based-on-Ra/>
