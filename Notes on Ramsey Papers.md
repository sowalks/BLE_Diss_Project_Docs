z
[https://drive.google.com/file/d/1zQI3U3dHXRUznasTGAJCUlAYLqaACqHh/view](https://eur03.safelinks.protection.outlook.com/?url=https%3A%2F%2Fdrive.google.com%2Ffile%2Fd%2F1zQI3U3dHXRUznasTGAJCUlAYLqaACqHh%2Fview&data=05%7C01%7Csmw98%40cam.ac.uk%7C332558933e164068f76c08dbbce3853e%7C49a50445bdfa4b79ade3547b4f3986e9%7C1%7C0%7C638311457592128726%7CUnknown%7CTWFpbGZsb3d8eyJWIjoiMC4wLjAwMDAiLCJQIjoiV2luMzIiLCJBTiI6Ik1haWwiLCJXVCI6Mn0%3D%7C3000%7C%7C%7C&sdata=urdmNg5aNixCB0lhgvaofwikVrQxoZZWeNieb4ah4wo%3D&reserved=0 "Original URL: https://drive.google.com/file/d/1zQI3U3dHXRUznasTGAJCUlAYLqaACqHh/view. Click or tap if you trust this link.")  


  

[https://drive.google.com/file/d/1xTohO1klU6aTrz9Ij9dZ-mMSOeti1iSR/view](https://eur03.safelinks.protection.outlook.com/?url=https%3A%2F%2Fdrive.google.com%2Ffile%2Fd%2F1xTohO1klU6aTrz9Ij9dZ-mMSOeti1iSR%2Fview&data=05%7C01%7Csmw98%40cam.ac.uk%7C332558933e164068f76c08dbbce3853e%7C49a50445bdfa4b79ade3547b4f3986e9%7C1%7C0%7C638311457592128726%7CUnknown%7CTWFpbGZsb3d8eyJWIjoiMC4wLjAwMDAiLCJQIjoiV2luMzIiLCJBTiI6Ik1haWwiLCJXVCI6Mn0%3D%7C3000%7C%7C%7C&sdata=Fts10PcL2g0hNIRws5T7xK7F4yTxwJ1hL6lxKs9Y%2Fns%3D&reserved=0 "Original URL: https://drive.google.com/file/d/1xTohO1klU6aTrz9Ij9dZ-mMSOeti1iSR/view. Click or tap if you trust this link.")  


## Covid Talk

[https://www.youtube.com/watch?v=xL3jGLYRRCE](https://eur03.safelinks.protection.outlook.com/?url=https%3A%2F%2Fwww.youtube.com%2Fwatch%3Fv%3DxL3jGLYRRCE&data=05%7C01%7Csmw98%40cam.ac.uk%7C332558933e164068f76c08dbbce3853e%7C49a50445bdfa4b79ade3547b4f3986e9%7C1%7C0%7C638311457592128726%7CUnknown%7CTWFpbGZsb3d8eyJWIjoiMC4wLjAwMDAiLCJQIjoiV2luMzIiLCJBTiI6Ik1haWwiLCJXVCI6Mn0%3D%7C3000%7C%7C%7C&sdata=EXqR7Nb%2BS34VHsm48gz43Vsw0vhVSby0G7eZZ4Nn4Kk%3D&reserved=0 "Original URL: https://www.youtube.com/watch?v=xL3jGLYRRCE. Click or tap if you trust this link.")  

- ![[Pasted image 20230925165630.png]]

- All announce unique identifier and signal strength - rough approximation of location

Unique identifier logging means identifying original person?
 -  privacy preserving techniques using decentralised or centralised
 - Key difference is if info is managed or stored through server, i.e. w NHS
 - Or decentralised routing service
- ![[Pasted image 20230925170021.png]]
- Difficult data analysis decentralised and cannot correct errors w contacted and has a lack of data, so problems may not be spotted
- But centralised is v tricky w data breach, 3rd parties and GDPR rulings

First joint venture for apple and google is contact tracing!

Key Problems w Schemes:
Traditional scheme doesnt work on apple w bluetooth. New scheme is not accurate enough for NHS but works  iphones.

iPhone races to dark which is v bad for contact tracing!!

Using signal strength is not accurate for range - bluetooth not designed for this

![[Pasted image 20230925170436.png]]
- What about humans? and walls? Blocks distances:
- ![[Pasted image 20230925170515.png]]
- people are detected too much and walls not enough!!
- Impossible high power far away is useful for tracking and why this is exploited. However.....
- ![[Pasted image 20230925170804.png]]
- what? higher signal strength than broadcasted has been detected even far away. The causes is not just cheap equipment
- Averaging is the wrong thing to do
- Impossibly high noise level - 10 times greater than expected!
-  ![[Pasted image 20230925171502.png]]
- This is very bad asit is possible to be far away with a high signal strength
- So you can have high power and detect covid even if very far away
suprising results!!

most people chose to average lol

First Problem"!!
#### Cross talk between wifi and Bluetooth

turning off wifi removes spuriously high incorrect values.
We want to remove these high values so people far away do not get recorded as covid contacts.

Difference before and after fixing
![[Pasted image 20230925172020.png]]

But we cant do this every time - however OS systems can do this
If developers cannot turn of wifi - we need data to detect these high values and remove them.

![[Pasted image 20230925172114.png]]
BLE can only hop between these 3 hello channels.

If a device can only transmit from a single channel. Then use a standard phone to detected it - then we have standard deviation

Some weird non white noise blateaus

why is this impportant? At least its way lower  - 10x less the noise as before as it has expected noise


![[Pasted image 20230925172843.png]]
Different channels have very different power

If smartphone is detecting from the different channels - characteristics and detection differs. 
A lot of the noise is just measuring the different channel characteristics as one.
More complicated when both devices are moving quicly


RHS shows decreasing profiles - deep fades at various time but not smooth.

Why??

also work out how to remove the interference

### Multipath Interference


![[Pasted image 20230925203247.png]]


The signal has multiple paths i.e. by reflection or scattering

This shows between the boosts and massive decreases seen as the in phase is v close to out of phase as the wavelength is only about 10cms
![[Pasted image 20230925203354.png]]

e.g. massive dip then spike next to each other by inphase and out of phase, in phase can double but thats it, wehreas out of phase can decrease durastically 1000x weaker

- Highly asymmetrical distribution of data
- ![[Pasted image 20230925203540.png]]
- ![[Pasted image 20230925203639.png]]

Use mean - however its much better to use rayleigh and rician errors - multipath modelling correction.


Model and simulate very well!

Simulated different room dimensions and material properties

![[Pasted image 20230925203749.png]]

Very useful for not in person!!

Find actual spread and likelyhood of being a certain distance away

Get high attenuation values at close ranges??
(Attenuation - make it less or weaker)
RSS dBm measure signal strength

![[Pasted image 20230925204010.png]]

simulations is WAY better than in person data collection

reduce false positives and false negatives - my project too many false positives ideally

simulation useful - although its very important

simple analysis for google apple vs nhs

![[Pasted image 20230925204327.png]]randomly draawn figure for making a measurement w G&A
nhs is way less likely to miss an interaction

used all 3 BLE ad channels - inherint mitigation ads

gA try to save battery w one channel - but more subject to multipath fades - more likely to be told to be really far away and not detect it like you would if you switched and left multipath fade

What is a multipath fade?

Multipath fading occurs when signals reach a receiver via many paths & their relative strengths & phases change.

So this is multipath interference when out of phase

nhs app used v impresses gaussion processes range estimate - so had least a negatives

google apple simply used the mean

use statistics of multipath interference

the pronblem is iphones asleep 95% of the time so huge false negatives

so we need these ideas in the google apple protocol

but basically want to not impact battery life too much

### Other Challenges

2.4GHz was chosen as it punches through walls verry well

chosen for wifi and bluetooth


this is an issue for contact tracing - just close distance wise but not aspace wise
![[Pasted image 20230925210358.png]]

need sensors to tell if same airspace. for covid.

i.e. barameters , audio data - 0.1sec - less than for siri or google.

![[Pasted image 20230925210619.png]]

exposure in stationary traffic

materials also focus ble beam

WELL UNDERSRSTOOD VALUES [[Starting Point]]
apparently a lot of research on this

![[Pasted image 20230925210949.png]]
projects a fan beam with much stronger signal

projects strongly for about 5 meters

carried forward and side in increased range if car infront false positives.

need to use other sensors!!

##### NOVID 
uses ultrasound fir same airspace and sub meter accuracy

![[Pasted image 20230925211135.png]]

how close in your network

networking effect!1


### Location Problems
Google Apple exposure does not share location - forces privacy into protocol - but how do we track contacts, not workable - do not use locations


however many use gps etc

![[Pasted image 20230925211404.png]]

![[Pasted image 20230925211431.png]]

internal priorities vs diff entities priorities

end users should be given the choice?
BLE scanning rate vs battery consumption oo


give end users right to change even if difficult or nudge defaults

### Conclusion

The same sort of issues that will be in play here for the inhibitor tags on scan rates and probabilities of missed scans etc - an inhibitor tag and tracker tag being correctly or incorrectly "co-located" is the same problem family as two phones being within 2m of each other for 2minutes in the covid era of contact tracing. - not necessarily 2 meters, just within same space

So look into researching solving for crosstalk, multipath interference and location based on same room! - i.e. sounds etc