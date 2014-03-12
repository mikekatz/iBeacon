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

## Development Reminders/notes
* `notifyEntryStateOnDisplay` if YES, will scan "immediately" for region changes when the phone wakes, otherwise it will wait for the normal bluetooth scan cycle.
* Notification events may not be immediate, [https://developer.apple.com/library/ios/documentation/userexperience/conceptual/LocationAwarenessPG/RegionMonitoring/RegionMonitoring.html#//apple_ref/doc/uid/TP40009497-CH9-SW11](https://developer.apple.com/library/ios/documentation/userexperience/conceptual/LocationAwarenessPG/RegionMonitoring/RegionMonitoring.html#//apple_ref/doc/uid/TP40009497-CH9-SW11)
* Monitored regions are persisted across app launches, so no notificaiton is posted if starting inside a region. Either preserve UI state, or use a trick like  [KCSIBeacon](https://github.com/KinveyLabs/KCSIBeacon/) to restart the region monitoring. 

