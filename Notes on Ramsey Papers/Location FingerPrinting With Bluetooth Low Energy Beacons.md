[https://drive.google.com/file/d/1xTohO1klU6aTrz9Ij9dZ-mMSOeti1iSR/view](https://eur03.safelinks.protection.outlook.com/?url=https%3A%2F%2Fdrive.google.com%2Ffile%2Fd%2F1xTohO1klU6aTrz9Ij9dZ-mMSOeti1iSR%2Fview&data=05%7C01%7Csmw98%40cam.ac.uk%7C332558933e164068f76c08dbbce3853e%7C49a50445bdfa4b79ade3547b4f3986e9%7C1%7C0%7C638311457592128726%7CUnknown%7CTWFpbGZsb3d8eyJWIjoiMC4wLjAwMDAiLCJQIjoiV2luMzIiLCJBTiI6Ik1haWwiLCJXVCI6Mn0%3D%7C3000%7C%7C%7C&sdata=Fts10PcL2g0hNIRws5T7xK7F4yTxwJ1hL6lxKs9Y%2Fns%3D&reserved=0 "Original URL: https://drive.google.com/file/d/1xTohO1klU6aTrz9Ij9dZ-mMSOeti1iSR/view. Click or tap if you trust this link.")  


- fingerprinting techniques, where positioning is performed via a
previously-constructed radio map, usually of WiFi signals. 

- We demonstrate the high susceptibility of BLE to
fast fading, show how to mitigate this, and quantify the true power
cost of continuous BLE scanning.   - do i want to do this - quantify power w inhibitor

#### Key Parameters of a BLE positioning system

- Beacon density?
- Transmit Power
- Transmit Frequency

GNSS - global Navigation satellite systems

like gps good for outdoor bad intdoor

"BLE is designed for machine-to-machine communication
with the “Internet of Things” in mind. BLE devices are small,
inexpensive and designed to run on batteries for many months
or years and it is expected that many buildings will contain a
high density of BLE devices in the near future"

that happened

FAST FADING INTERFERENCE

Opportunistic fingerprinting? "[exploiting](https://www.google.com/search?client=firefox-b-d&sca_esv=568452477&sxsrf=AM9HkKlOoDGFyCvrGpJJLN-X_oQVInZ6TA:1695721882525&q=exploiting&si=ALGXSlbxwhdHKc0fpoiOcM6OGd45SJ-AZylYNdTec-s265F7lE2IkxUlIxq0nMsB9eHC7Mgqzzckr1FdAXoSBPID360AxY56CA%3D%3D&expnd=1) immediate opportunities, especially regardless of planning or principle" advertising


WiFi fingerprinting had more challenges
much of this so far are about tech that has alreayd gone and BLE is ubiquitous

![[Pasted image 20230926105307.png]] This bitch again

37 38 and 39 channels to avoid wifi

BLE suffers none of these problems: advertise-
ment packets are reported immediately and the specification
demands that all are reported by the platform in standard units
of dBm. 

Has low power, simpler protocols and optimization for advertisement, easily deployed.

we investigate the
rate and transmission power needed for good positioning- 
can do that w inhibitor??

Fusion of other location related sensors may be useful - not sure in my project. [[Core Deliverables#Extensions]]?


1.  the first experimental test of fine-grained BLE positioning
using fingerprinting;
2. a detailed study into the key parameters for accurate
indoor positioning using the BLE radio signals;
3. the discovery that the use of three widely spaced but
narrow band advertising channels leads to severe RSS
variations if the BLE channel number is not reported to
the system (this can be seen as a weakness in the current
BLE specification);
4. the testing of mitigation schemes to protect against this
problem;
5. detailed experimental validation; and
6. a series of recommendations for the developers of BLE-
based positioning systems - woo!!

severe RSS
variations if the BLE channel number is not reported to
the system  - what are RSS variations?
"The residual sum of squares (RSS) **measures the level of variance in the error term, or residuals, of a regression model**. The smaller the residual sum of squares, the better your model fits your data; the greater the residual sum of squares, the poorer your model fits your data."

Lots of sources in these papers

Regular bluetooth scans farless than BLE

Simultaneous Localization and
Mapping (SLAM) - look into??

f Ferris et al. [11], who used Gaussian Pro-
cess regression (a form of non-parametric data fitting) to esti-
mate continuous signal maps from discrete WiFi RSS data. This
approach is superior to traditional surveying methods and we
apply it to pure RSS data in this work. -  is this related to [[COVID Talk]] NHS calculations

3 frequencies widely spaced to minimize wifi interference

scan cycle over channels, pausing to listen for advertisements switch listening channel after a few milliseconds generally listening for
a significant fraction of a second could produce advertisements
on any or all of the three channels.


BLE scan is indefinite and each ad reported when received.
Form fingerprint from observations in a time window.

We want a larger time interval than the beacon for the receiver, so we can get multible sightings.

redundancy is required for robust positioning - need long windowing length

BLE specification did not include channel which is received - should now days?

![[Pasted image 20230926110455.png]]


The mean levels of 3 channels are all different - caused by

- ##### Uneven channel gain 
	- This occurs as 
embedded antennas rarely have a flat response across the entire
2.4 GHz band, so Channel gain (Signal to Noise Ratio) is uneven, meaning this mean changes, and result sin diferent responses even without interference.

- #### Multipath interference
	- furthers differences and changes over time with singal fading and cluttered environments
- #### Different channels exhibit fades at different spatial positions
- due to their different centre
frequencies – use this observation in constructing
our positioning system.

![[Pasted image 20230926112042.png]]

we need to segregate measurements into 3 different channels

BLE signal would otherwise have an artificially-high signla noise that reduces performance 

fading will still occur but we will know as it will be unambigueously clear.

We can exclude faded data as these will be sharp.

We need many matches for this


## BLE Fingerprint construction

BLE ads are reported immediately -  we will ned an RSS fingerprint that can be formed w a time window of measurements

#### Choice of Time Window Factors:
- ###### movement rate:
	- if we're moving a lot, fingerprint will be formed from measurements at different location. -  SMEARING WILL OCCUR if window is too long in moving. 
- ###### Presence of fast fades: 
	- short windows limits the detection of fast fades, while decreasing smearing
- ###### The Beaconing rate
	- Receive rate - BLE ads can be reported rate - is a lower bound on beaconing rate, otherwise ads may be missed, so beaconing rate must be higher.
	-  Lower rate requires a longer fingerprint window so we can get enough samples.

Time window < 1s : humans walk 1.5m/s and we want to detect at this level, so we cannot detect for longer than this without excessive smearing

Time window > 0.1s - fast fade occurs at spatial seperation of hhalfthe signal wavelength (~12cm) -  lower bound ignores beacon transmission rates

Diff RSS values between different channels - we  an then take a window of ads from each channel to form the fingerprint. 

Filter w mean/max/median

We need at least one reading on each channel.

If we cannot detect channel detected on then:
"We must choose
a window that guarantees that the handset has listened
on all three channels and hope that the collected samples
span the channels. 
Longer windows clearly increase the
likelihood of this occurrence"

At least 3 samples per window per beacon -  window length w, need beaconing rate 3/w.

if limit of w=1s is used -  3Hz beaconing is required at minumum. 
(i.e. https://stackoverflow.com/questions/60317899/altbeacon-detection-of-beacon-rssi-values-continuously-at-10hz specify eddystone advertises with a frequency of 10Hz)

Not all apps will depend on high receive rates, so w designing for battery life time , best positioning result is done by forcing user to remain still, and position using longer time windows, as advertising is less frequent.

What are RSS Maps

 "Each fingerprint was linked to a true position
and we used Gaussian Process regression to generate a signal
strength map per source. We constructed a separate database
for each set of fingerprint construction parameters (i.e., window
length and filter algorithm)."


Gaussian Process Regression.


### Evaluation of Distance

Walk for detected position  vs true position:

The most commonly used metric in the literature is the Euclidean
distance:
$$distance(B, m, M) =
\sqrt{∑^{N}
_{i=1}
\frac{(m(b i) − M(b i))^2}{N}
} $$
for current fingerprint m containing RSS measures for beacons
B = {b1, . . . , b N } and the set of beacon survey maps, M. 

This gives a score for each cell/detector generating a fingerprint of all beacons.

##### Gaussian Kernel

Generates a probability for that detector which accounts for uncertainty in the map estimate and current fingerprint measurement.

The variance data within the Gaussian Process survey maps
were thresholded such that map cells with moderate or high
variance were ignored completely (not trusted)

$$p = exp
(- \frac{
 distance^2}{
2σ^ 2}
)
,$$

This is the probability for each cell meaning the function across all cells was the bayesian likelihood function. (probability of getting this result with certain parameters - i.e. accurate distance etc.) ?????????

where σ is the standard deviation associated with the fingerprint
measurement noise.

#### Usage
One shot - single position fixed - For one-shot position-
ing the prior was taken to be uniform across the test area at each
epoch
Tracking 0  user wishes to be tracked around an environment continuously -  position history can constrain the prior.



