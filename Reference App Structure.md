
4 Main Activities:
- PermisssionsActivity.kt
- BeaconRangingSmoother.kt
- BeaconReferenceApplication.kt
- MainActivity.kt

https://altbeacon.github.io/android-beacon-library/javadoc/org/altbeacon/beacon/BeaconManager.html

## PermissionsActivity.kt

Requests Permissions:- location, background location, bluetooth, notifications


## BeaconRangingSmoother.kt

* This class is used to smooth out the beacon ranging data to prevent periodic dropouts.  
* default, it will retain beacons in the list if detected in the past 10 secconds,
* Not currently used - should be used


## BeaconReferenceApplication.kt

creates beacon manager and scanning - scans for a particular region of ids and only scans for ibeacons.

setups op beacon scanning in the foreground constantly.
I can use this or reduce if it affects battery life to canning in background for 15mins

wsetup foreground service

uses oberver patterns to log to logcat.

 I should look at the logcat shit
also sends notificaitons
## MainActivity.kt

sets up views, checks permissions granted
starts bluetooth scanning w ranging observer

monitoring observer alerts and creates notifications when a beacon in the id range is detected.  I will likely not require this feature.

ranging Observer fills the list of deteced beacons. I have modified this to write to the logging file.

rangingbutton tapped - starts or stops the ranging observer via beacon manager

monitoring button tapped sets up or stops notifications of detections of specified id ranges, or any beacon currently.









