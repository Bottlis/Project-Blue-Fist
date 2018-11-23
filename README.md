# Project-Blue-Fist (FistBump BLE Edition) 
[<img src="https://img.shields.io/badge/Device%20Image%20Latest%20Release-v.3.0.0-green.svg">](https://github.com/eliddell1/Project-Blue-Fist/releases)

[<img src="https://img.shields.io/badge/Android%20App%20Latest%20Release-PlayStore-green.svg">](https://play.google.com/store/apps/details?id=liddell.onus.com.fistbump_ble)

[![Donate](https://img.shields.io/badge/Donate-PayPal-green.svg)](https://www.paypal.com/cgi-bin/webscr?cmd=_s-xclick&hosted_button_id=MLBAU3J6JVDS8&source=url)

Project Blue Fist is the next iteration of my P.O.C. project, [FistBump](https://github.com/eliddell1/FistBump), a handheld pentesting tool that can be used to grab WPA handshakes and PMKID hashes on Red Team engagements. It was designed to allow one to get close to a given target allowing the attack to be more effective, without raising suspision.  The original proof of concept was a stand alone device that launched a very effective attack via the push of a button, but was not exactly stealthy with its' use of blinking lights to indicate various stages of the attack as well as the outcome. It was also a bit bulky and difficult to conceal. 

Project Blue-Fist aims to remedy these short comings by removing the array of led lights as well as the trigger button, leaving only a single button to power on or off the device.  This greatly lowers its' physical footprint allowing for the device to gracefuly fit in your pocket.  This iteration also now makes use of bluetooth and an android app so that the device can be completely controlled from your android phone. It still saves the hashes to removable storage, but now allows for on the fly targeting and detailed results which include new naming conventions for targeted vs broad attack results, and catalog file generation on broad attacks that details what essids can be found in the hashfile of the same file name.

<img src="https://github.com/eliddell1/Project-Blue-Fist/blob/master/Images/white_device.jpg" width="300" height="400">      <img src="https://github.com/eliddell1/Project-Blue-Fist/blob/master/Images/white_phone_device.jpg" width="300" height="400"> 

## Power on/off Device

To power on the device, hold down the power button.  A red and blue light will turn on, hold the power button until the red light turns off indicating the boot process has begun.  The boot process takes about 30 seconds.

Once the device is on, open the FistBump app on your bluetooth enabled android device. The app will attempt to conect to the FistBump Device

<img src="https://github.com/eliddell1/Project-Blue-Fist/blob/master/Images/connecting_screenshot.png" width="200" height="367">     <img src="https://github.com/eliddell1/Project-Blue-Fist/blob/master/Images/Screenshot_retry.png" width="200" height="367">

If it fails, simply press retry.  Sometimes it maybe required to quit the app and try again, should it be unable to connect after the second or thrid attempt.

## Launching an Attack

Once you have connected to the FistBump Device, the app will display a list of wifi networks around you, available to attack.

At this point you can conduct a "Broad Attack" which will target anything in range, by pressing the red attack button or a Targeted Attack simply by selecting one of the displayed networks before tapping the attack button.

<img src="https://github.com/eliddell1/Project-Blue-Fist/blob/master/Images/Screenshot_20181109-181027.png" width="200" height="367">            <img src="https://github.com/eliddell1/Project-Blue-Fist/blob/master/Images/Screenshot_20181109-181002.png" width="200" height="367">            <img src="https://github.com/eliddell1/Project-Blue-Fist/blob/master/Images/Screenshot_attacking.png" width="200" height="367">

## Collecting Booty

When attacks are successful, the booty/loot is stored to your removable usb storage.  Booty is currently organized into two folders, PMKID and Handshakes. 

<img src="https://github.com/eliddell1/Project-Blue-Fist/blob/master/Images/booty_main_dir.png" width=30% height=30%>

Note that actual hash files have an extension of .2500 or .16800. These correspond to the hashing mode you would use in hashcat to bruteforce those hashes.  2500 being standard WPA handshakes and 16800 being PMKID hashes. i.e. <code>$ hashcat -m 2500 ... </code>  or <code>$ hashcat -m 16800 ... </code>

When you drill into the appropriate directory, you will find broad attack results named with a date/time stamp while targeted attacks will be named with the convention "targeted-[ESSID NAME]"  

<img src="https://github.com/eliddell1/Project-Blue-Fist/blob/master/Images/handshake_dir.png" width=50% height=50%>

Above is the Handshake Directory.  You will notice that each hash file has a corresponding .catalog file.  Because an individual hash file may contain more than one hash, and in the case of broad attacks, even more than one target, this catalog file is there to list the targets found in it's corresponding hash file.

<img src="https://github.com/eliddell1/Project-Blue-Fist/blob/master/Images/broad_booty.png" width=50% height=50%>

<img src="https://github.com/eliddell1/Project-Blue-Fist/blob/master/Images/catalog.png" width=50% height=50%>


## Donate 

If you enjoyed this project, help me make more by buying me a coffee or something.

### PayPal
[<img src="https://www.paypalobjects.com/en_US/i/btn/btn_donateCC_LG.gif">](https://www.paypal.com/cgi-bin/webscr?cmd=_s-xclick&hosted_button_id=MLBAU3J6JVDS8&source=url)

### Bitcoin
1KuntExCV54WJaVxyBMDbAXMye6zWcZfR

## Purchase Inquiries

If you are one of those who would rather have one built for them, send inquiries to liddell.erik@gmail.com subject:FistBumpBLE


