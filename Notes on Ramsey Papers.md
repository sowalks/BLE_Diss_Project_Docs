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

why is this impportant? At least its way lower  - 10x less the=an noius as it has expected noise


![[Pasted image 20230925172843.png]]
Different channels have very different power

If smartphone is detecting from the different channels - characteristics and detection differs. 
A lot of the noise is just measuring the different channel characteristics as one.
More complicated when both devices are moving quicly


RHS shows decreasing profiles - deep fades at various time but not smooth.

Why??

### Multipath Interference




