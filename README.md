iBeacon References
=======

## Demo Applications
* [__AirLocate__](https://developer.apple.com/library/ios/samplecode/AirLocate/Introduction/Intro.html) - Apple's demo app - shows everything: enter/exit events, ranging, calibration, and acting as a beacon. 
* [iBeacon Demo](https://github.com/mikekatz/iBeacon-Demo) - Demo app I created for showing off iBeacons at Cocoaheads.
* [BeaconOSX](https://github.com/mttrb/BeaconOSX) - turn a Mavericks mac into an iBeacon


## Development/Debug Tools
* Beacon Management utility - [KCSIBeacon](https://github.com/KinveyLabs/KCSIBeacon/) , also on Cocoapods
* Radius tools for OSX - [http://developer.radiusnetworks.com/ibeacon](http://developer.radiusnetworks.com/ibeacon)
* [BeaconOSX](https://github.com/mttrb/BeaconOSX) - turn a Mavericks mac into an iBeacon


### Android
* [Radius Library](http://developer.radiusnetworks.com/ibeacon/android/)


### Phonegap
* [Plugins](http://plugreg.com/search?q=ibeacon)

## FAQ
### Which devices support iBeacon?
Rule of thumb: all lightning devices + iPhone 4s & retina iPad
* [Official Apple list](http://support.apple.com/kb/HT6048)
* What's the cheapest device to support iBeacon?
     * [Refurbished iPod Touch 16gb (5th generation)](http://store.apple.com/us/browse/home/specialdeals/ipod/ipod_touch) $189
     * [Refurbished iPad Mini Wi-Fi 16gb](http://store.apple.com/us/browse/home/specialdeals/ipad/ipad_mini/wi_fi) $249

### What is the difference between beacons and iBeacons?
* Beacon is a generic term for a device that just periodically broadcasts an identifier. This is commonly used in the mobile space to apply to range of Bluetooth LE devices. iBeacon is a subset of becaons conforming to a particular specification.
* [iBeacon spec](https://mfi.apple.com/) (requires MFI (Made for iOS) enrollment)
* This specification requires the broadcasting of a uuid, major and minor identifier, as well as the radio power. Any compatible device can send the appropriate packets and be seen as an iBeacon, even if the device does not conform to Apple's trademark and MFI program.
* Android devices with Android 4.3+ and Blueooth LE capabilities, such as the latest Samsung Galaxy and Nexus devices can detect iBeacon devices, even if this not supported by Apple. 

## Blogs
* [Beekn](http://beekn.net/)
* [Radius Networks](http://developer.radiusnetworks.com/blog/)

## Development Reminders/notes
* `notifyEntryStateOnDisplay` if YES, will scan "immediately" for region changes when the phone wakes, otherwise it will wait for the normal bluetooth scan cycle.
* Notification events may not be immediate, [https://developer.apple.com/library/ios/documentation/userexperience/conceptual/LocationAwarenessPG/RegionMonitoring/RegionMonitoring.html#//apple_ref/doc/uid/TP40009497-CH9-SW11](https://developer.apple.com/library/ios/documentation/userexperience/conceptual/LocationAwarenessPG/RegionMonitoring/RegionMonitoring.html#//apple_ref/doc/uid/TP40009497-CH9-SW11)
* Monitored regions are persisted across app launches, so no notificaiton is posted if starting inside a region. Either preserve UI state, or use a trick like  [KCSIBeacon](https://github.com/KinveyLabs/KCSIBeacon/) to restart the region monitoring. 
* The accuracy value is kinda a guess of distance, and can vary wildly by relative signal strength, room layout, and people and radio interference. Best attempt to get a compartivie distance is to first use the proximity enum and then compare accuracy within that. __NOTE:__ that if a beacon dissapears or has trouble ranging, it might have it's last proximity value set, so accuracy has to be checked that it is not -1. And `CLProximityUnknown` does not mean it isn't nearby.
* Helpful info: [http://beekn.net/developing-ibeacon-app/](http://beekn.net/developing-ibeacon-app/)

## iBeacon Manufacturers
* [Appflare](http://www.appflare.com/buy-beacons-now/), small battery-powered
* [Bleu Station](http://twocanoes.com/bleu), smal USB
* [Bluesense](http://bluesensenetworks.com/shop/), medium-sized, not sure if they support iBeacon, retail-focused
* [Estimote](http://estimote.com/), medium battery-powered
* [Gelo](http://www.gelosite.com), medium battery-powered, suitable for outdoor use, iBeacon coming soon
* [Gimbal](https://gimbal.com/) by Qualcomm, small battery-powered (NOT iBeacon) and medium battery-powered (iBeacon)
* [Jaalee](http://www.jaalee.com/beacon_en.html) Small, lightweight. I haven't tried these out, but they might be iBeacon compatible and customizable based on their website. Available in many colors. 
* [Radius](http://www.radiusnetworks.com) several form factors, including USB, also have good tutorials, blog and open source utilities
* [Sensorberg](http://www.sensorberg.com/), expensive
* [Sonic Notify](https://sonicnotify.com/), retail-focused
