# Hackintosh ASUS ROG STRIX GL702VSK
Hackintosh Files for High Sierra 13.6 @ ASUS GL702VSK

![alt text](https://raw.githubusercontent.com/zubenelakrab/Hackintosh_ASUS_GL702VSK/master/About.jpeg)

**Software:**
* Olarila (last image for High Sierra 13.6)

**Specs:**
* Intel Core i7-7700HQ (Intel Core i7)
* 32GB RAM
* NVIDIA GeForce GTX 1070 (Laptop) - 8192 MB
* 256GB x M.2 (Root partition Type: APS) + 1TB x SATA (Backup partition)

**Working:**
* NVIDIA GTX 1070
* Audio (Internal Speakers + HDMI Audio)
* Sensors 
* Ethernet
* Audio Jack
* USB 3.0/3.1, Thunderbolt, USB Type C, HDMI, Mini Display Port, Card Reader
* Webcam
* WIFI 2.4ghz + 5ghz (USB Dongle EDiMAX EW-7611UCB) **Bluetooth on this device won't work on OSX.*
* CPU/GPU Fans
* Battery
* 4K Display (3840 x 2160) **No GSYNC.*
* Belkin Mini Bluetooth V4.0 USB Adapter (F8T065)
https://www.amazon.es/gp/product/B009IQB3US/ref=ppx_yo_dt_b_asin_title_o01_s00?ie=UTF8&psc=1

**Not working:**
* Touchpad
* Built-in WIFI/Bluetooth card
* Keyboard Backlight
* Some FN keys
* Temperature Sensors

**Testing:**
* Built-in microphone

**Tips**
After install kexts check permissions and update kextcache 

a. to repair permissions use Kext Wizard or 

```
sudo chmod -Rf 755 /S*/L*/E*
sudo chmod -Rf 755 /L*/E*
sudo chown -Rf 0:0 /S*/L*/E*
sudo chown -Rf 0:0 /L*/E*
```

b. to update kextcache

```
sudo kextcache -i /
```

# Abbreviations
* /L/E = /Library/Extensions
* /S/L/E = /System/Library/Extensions

# Creating USB Stick

# Battery + Sensors

1. Apply DSDT Patch 
2. Install FakeSMC (*/EFI/CLOVER/kexts/Other/*)

![alt text](https://raw.githubusercontent.com/zubenelakrab/Hackintosh_ASUS_GL702VSK/master/bat_sensors.jpeg)

# Fixing USB Stick KEXTS

1. Mount your USB Stick EFI Volumen
2. Replace all kexts in your EFI volumen with EFI.zip kexts (*/EFI/CLOVER/kexts/Other/*)
3. Delete any other folder in /EFI/CLOVER/kexts (keep only Other)
4. Restart & Boot with your USB Stick

# Pre-Install 

DISABLE(Lock) Wifi + Bluetooth in your BIOS. 

# Installing


# Post-Install

# Bluetooth

Built-in bluetooth *MUST* be disabled after try anything.

**How?**
1. Open Clover Configurator
2. Mount your EFI
3. Import your /EFI/CLOVER/config.plist
4. Go to Boot Menu (below Acpi)
5. Add an extra argument: uia_exclude=HS09
6. Reboot

**Why HS09?**
1. Download Hackingtool & Install
2. Open it and go to the USB tab
3. Find for USB Device: IOUSBHostDevice
4. Got it, that is your Bluetooth HCI (Internal)
5. DISABLE IT!

**Enable your BT USB**
1. Download Bluetooth kext folder.
2. Copy them to /L/E
3. Run on terminal *sudo kextcache -i /*
4. Reboot
5. Enjoy your BT working

# DDST Patch

**Working on it**

# High Sierra updates
High Sierra can be updated from App Store but after this action kexts path permissions must be fixed using Kext Wizard (or command-line)
