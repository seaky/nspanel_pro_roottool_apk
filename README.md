## Sonoff NSPanel Pro

Sonoff NSPanel Pro is a smart home control panel which based on Android 8.1 Oreo (AOSP) system.

After gain ADB access custom applications can be installed onto this unit. See (https://blakadder.com/nspanel-pro-sideload/)

![Drag Racing](doc/assets/nspanel-pro.png)

https://itead.cc/product/sonoff-nspanel-pro-smart-home-control-panel/

## NSPanel Pro Roottool 

After the development mode is enabled on the device via eweLink App the official further firmware updates are prohibited due to EULA.

This tool allows you to install the official firmwares.

> [!WARNING]
> Warning, this software has been created for experimental purposes only. Perform any modifications on the device at your own risk. I assume no responsibility for any consequences of using the software!

# Frequently Asked Questions

- [Where can I download the official update packages?](#where-can-i-download-the-official-update-packages)
- [Can I disable the developer mode, somehow?](#can-i-disable-the-developer-mode-somehow)
- [How do I reset the device?](#how-do-i-reset-the-device)
- [Is there any benefit to update the sideloaded panel?](#is-there-any-benefit-to-update-the-sideloaded-panel)
- [What should I do if my device has entered factory mode?](#what-should-i-do-if-my-device-has-entered-factory-mode)

## Where can I download the official update packages?

https://drive.google.com/drive/folders/1bHLLJy8vYUjkCCnyUmrHgEFWi_2cxywv

## Can I disable the developer mode, somehow?

Short answer is you can't. Reffering to the eWeLink App you were asked asked numerous times if you are sure and fully aware of the consequences. What you accepted. So the device rooted forever.

## How do I reset the device?

Power on the device and wait until the Sonoff logo boot animation starts playing then power it off. Power it on again and repeat the process 5 times. After that the panel will boot into “Update Firmware Protect Mechanism” and factory reset everything to the version stored in the recovery partition.​

[more details](https://blakadder.com/nspanel-pro-secrets)

## Is there any benefit to update the sideloaded panel?

I've analyzed all the system updates till 1.11.
From OS perspective it is intact and still the AOSP 8.1 Oreo so for example the fw 1.3 android binaries are equivallent to 1.7.
The rockchip drivers also looks the same.
Of course the vendor part is different for example the ControlApp and the internal zigbee server.

As a "sideload user" definitely there is no reason to upgrade to higher version or I assume that the performance will be the same looks like the rockchip drivers are the same in every version. If you want to mix Sonoff Ecosystem and HA usage could be a benefit. But some new feature is limited to a "non-rooted" user such as intercom calling between the devices even if you upgrade fw and force ugrade the apk (normally if you are rooted wont get any update).


## What should I do if my device has entered factory mode?

If you encouter the following screen:
![nspanel_pro_recovery](https://raw.githubusercontent.com/seaky/nspanel_pro_roottool_apk/main/doc/assets/ewelinknwpro.dev.jpg)

Try the following
- disassemble the unit
- power it up by usb otg cable
- try to access it via adb
- use 
```
adb input keyevent 3
```
- change default launcher 
