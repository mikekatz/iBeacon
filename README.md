iBeacon References
=======

## Demo Applications
* [__AirLocate__](https://developer.apple.com/library/ios/samplecode/AirLocate/Introduction/Intro.html) - Apple's demo app - shows everything: enter/exit events, ranging, calibration, and acting as a beacon. 
* [iBeacon Demo](https://github.com/mikekatz/iBeacon-Demo) - Demo app I created for showing off iBeacons at Cocoaheads.
* [BeaconOSX](https://github.com/mttrb/BeaconOSX) - turn a Mavericks mac into an iBeacon


## Development/Debug Tools
* Radius tools for OSX - [http://developer.radiusnetworks.com/ibeacon](http://developer.radiusnetworks.com/ibeacon)
* [BeaconOSX](https://github.com/mttrb/BeaconOSX) - turn a Mavericks mac into an iBeacon

## Which devices support iBeacon?
Rule of thumb: all lightning devices + iPhone 4s & retina iPad
* [Official Apple list](http://support.apple.com/kb/HT6048)
* What's the cheapest device to support iBeacon?
     * [Refurbished iPod Touch 16gb (5th generation)](http://store.apple.com/us/browse/home/specialdeals/ipod/ipod_touch) $189
     * [Refurbished iPad Mini Wi-Fi 16gb](http://store.apple.com/us/browse/home/specialdeals/ipad/ipad_mini/wi_fi) $249

## Blogs
* [Beekn](http://beekn.net/)

## Development Reminders/notes
* `notifyEntryStateOnDisplay` if YES, will scan "immediately" for region changes when the phone wakes, otherwise it will wait for the normal bluetooth scan cycle.

