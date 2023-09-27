
When you have decomposed your entire project into sub-tasks you can try to identify which
of these sub-tasks are going to be hard and which easy, and hence estimate the relative
amounts of effort involved in each
[[Timetable]]

## Ideas

Core deliverable could include using a simple median to  detect distance and noise for sampling rate + get rid of spurious highs - based on 3 channels
need tag to signal over 3 channels
- however an extension could be to use strong detection methods for distance to improve accuracy  i.e. rayleigh or other methods that have been used by the NHS etc in [[COVID Talk#Covid Talk]]


## Core Deliverables
### App
https://stackoverflow.com/questions/60317899/altbeacon-detection-of-beacon-rssi-values-continuously-at-10hz
- adapt app that can scan from android listerners to csv
- open source one to adapt/ is there a library i can build my own from.
- 
### Inhibitor Tag 

- Take regular tag. i.e. using altbeacon.
- Add a function that it will send an inhibiting signal - i.e. add an extra type/field in advertisement.
- Does it even need to be different???
- Can we use a regular open source tag??
- If we use a regular open source tag - we will have to list and store E V E R Y inhibitor tag registered.
- Instead, if we have a function on the app to tell the

### Web Server

- Get a working server first
- Simple server that tracks ble signals sent to it from devices
- Prints to CSV
- Sends devices back their own tag information.
- Needs filters to send back information only if uninhibited.
- Collate the information about tag - wait if inhibited, if not wait to see if it gets inhibited.
- for x amount of time
- Then we can experiment w timings etc
-Inhibition will work when we receive an inhibited signal/device
###### Inhibition
 -  Receive a signal. 
 - Parse for recent signals  - has this been inhibited
 - No? - wait for T time. Check again.
 - Send signal back to finding  device if not.
 
 - Has this been inhibited?
 - Check the location of an inhibitor tag.
 - Calculate distance between this and recently detected tag
 -  If distance is less than D, INHIBIT AND DO NOT PASS ON
 - If more than, all good. 
 - If the device is in the range of an inhibitor but the tag isn't this works fine.
 - Do we calculate distance between all?
 - Calculate distance only between those still waiting.
 - We can back up history into CSVs, but not actually save on webserve
 - or move to seperate bits?

### Experiments, simulation?


## Extensions

- Use more accurate distance approximations with i.e. learn about rayleigh and rician - i.e in [[COVID Talk]]

- Store which tags are in constant location with X for time - detect stalkers? ( like sending on police thing mentioned)

- Create a simulation for how these function
 