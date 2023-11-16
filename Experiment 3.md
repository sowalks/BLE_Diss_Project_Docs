We designed an experiment to test the
functionality of commercial detection devices and apps. Our
goal was to evaluate the detectors in a best-case environment.
We selected a room in our building with as little existing
technology as possible to reduce the chance of false positives.
Before the experiment, we marked where we would place the
{beacons} as well as positions that were 1, 5, and 10 feet
away from the {receiver}. At each distance, we picked three
points that are at a 0, −30 , and 30 degree angle from the {receiver}(nine positions in total). To reduce inconsistency in
our measurements, we ensured that the detector was placed at
the same vertical height in the room for each measurement

3. How accurate is RSSI to distance for the specific tags that I am testing? This will affect how any experiment or system I have built works, as if this will determine if I either need to change settings for calculating distance of tags or what base margin of error the system needs to cope with, before interference takes place.

3.1 We need to know the RSSI of the tags at fixed distances,as well as the calculated distance from a receiver vs actual distance.

3.1.1 We can replicate the method used here to test detection, by placing tags at 1,5 and 15 feet away and finding the detected distance and RSSI of the tags. Repeating at these distances can get approximate distances we want to detect, for example 15ft is the size of the average vehicle, so for any anti stalking it is unlikely we would need to measure tags further than this, unless there is a high rate of  tags appearing nearer than they are, further than this should not affect our system, although we can investigate greater distances.

 (https://pages.cs.wisc.edu/~chatterjee/papers/usenix23-spydevices.pdf)

![[Pasted image 20231108174442.png]]

repeat these with different phones


1.  Record at distances for 1 min each distance
2.  Switch which tag is on
3.   Repeat with other phone


