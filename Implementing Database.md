
We want to have 2 last known locations - one most recent,
one before blocked.

Keep measurements in seperate table in an effort to be able to have all past locations, or to swap to inhibitor 


Modes table :- id and mode

Location table for each tag?
Is this feasible?

either way it will need time of detection, blocked or not, location at detection.

This will also require updating location only with 15min blocks for past ones

i.e. keep updating 5 recent < 5 mins, then keep only one of those after this to 
prevent 100s of detections.

