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
variations  (DbM/Signal strength) if the BLE channel number is not reported to
the system  - what are RSS variations?

RECIEVED SIGNAL STRENGHT
[[COVID Talk]]

Lots of sources in these papers

Regular bluetooth scans farless than BLE

Simultaneous Localization and
Mapping (SLAM) - look into??

f Ferris et al. [11], who used Gaussian Pro-
cess regression (a form of non-parametric data fitting) to esti-
mate continuous signal maps from discrete WiFi RSS data. This
approach is superior to traditional surveying methods and we
apply it to pure RSS data in this work. -  is this related to [[COVID Talk]] NHS calculations RECIEVEDSIGNAL STRENGH

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
 RECEIVEDE SIGNAL STRENGTH
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

What are RSS Maps -  RECEIVED SIGNAL STRENGTH MAPS

 "Each fingerprint was linked to a true position
and we used Gaussian Process regression to generate a signal
strength map per source. We constructed a separate database
for each set of fingerprint construction parameters (i.e., window
length and filter algorithm)."


Gaussian Process Regression.

## Position Computation
 Entire area ofinterest was divided into grid cells  1$m^2$
  Probability of a given fingerprint corresponding to each cell was determined.
We need to evaluate distance between the signal strengthvalues in a map cell, and the current fingerprint measured by the tracked device.
### Evaluation of Distance

cell is 1 square meter on the map. This generates a score for each cell -  so the measures within a cell error/ distance what it should be.

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

This gives a score for each cell generating a fingerprint of all beacons. 

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

This is the probability for each cell meaning the function across all cells was the bayesian likelihood function. Cell is the 1m2 area the map is split into, so the probability for being within a cell? (probability of getting this result with certain parameters - i.e. accurate distance etc.)

where σ is the standard deviation associated with the fingerprint
measurement noise.

#### Usage
One shot - single position fixed - For one-shot position-
ing the prior was taken to be uniform across the test area at each
epoch
Tracking 0  user wishes to be tracked around an environment continuously -  position history can constrain the prior.
(We can assume user moved within one square meter, or to adjoining)


WTF is A GAUSSIAN kernel

For the posterior function - we assume the user moves only within the cell or to an adjacent one between measurement updates.

This is appropriate for high beacon rates - i.e. at 10Hz, a user only moves 15 centimeters between beacon measurement epochs

Epoch - a moment in time, or an entire pas through in machine learning. Here i am assuming an epoch is our window of time we have covered to detect ads.


Once a posterior distribution was calculated, we estimated
the position (and hence the error) using the distribution max-
imum (i.e., maximum a-posteriori (MAP) probability, P max).
We also compared this to a weighted mean of all positions



When deploying a BLE positioning system, there are
many parameters to consider, including: 
- fingerprint construction algorithm
- beacon rate
- transmit power
- antenna orientation
- beacon mobility
- beacon geometry
- beacon density


Interdependent! This is about tracking phone not phone tracking beacons.

It acts the same!! We can do experiments where we track a moving "tag" phone - or we can measure a movign phone w stationary tags and vice versa. [[Evaluation]]

W interdependent parameters - exhaustive search for best is unfeasable and results are highly environmental specific


[[IDEAS TO PUT ELSEWHERE]]



Tracking can be a filter of one shot positioning!!!


Instead, our approach was to deploy an over-specified set
of beacons with parameters set to give good results without
consideration of real-world issues such as power consumption.


This allowed us to bound the possible performance and to
look at the effects of the parameters by post-processing the
data many times. 

To explore the parameter space we focus
on one-shot positioning since any improvements should be
reflected in the tracking performance (tracking can be viewed
as a filter on top of one-shot positioning, so improving one-
shot performance typically improves tracking). 

Having explored the parameter space we propose a realistic beacon setup
and deployment and evaluate both its one-shot and tracking
performance.

Since our positioning algorithms are based on mapping RSS
values, it is important to consider the temporal stability of these
values. We use data collected over a few weeks, during which
time we observed little, if any, significant change in the signal
RSS values. We attribute this to the nature of the testbed—
an office space that was rarely crowded or changed. 

RSS signal strength  

This gave them an upper bound for performance. Environmental changes affect this [[COVID Talk#Other Challenges]]


acons were installed a height of approximately 1 m from the
floor and oriented such as to provide maximum response in the
horizontal plane (to coincide with users holding smartphones
approximately parallel to the ground during interactions with
them). Each was set to beacon at 50 Hz with an output power
of 0 dB

 The iPhone logged the BLE advertise-
ment events to local storage using an application supplied by
CSR Ltd [[Core Deliverables#App]]

Ground Truth Location: The Active Bat system [1] was
available throughout the testbed and was used to provide ground
truth position. This system is a low error (less than 3 cm
in 3D 95% of the time), high-infrastructure location system
capable of estimating positions at around 15 Hz. The data
from it were post processed and smoothed to remove spurious
positions.

Synchronization: The Active Bat system, the iPhone and the
Nexus 4 each ran on independent clocks. Before each experi-
ment, each clock was manually synchronized using a Network
Time Protocol (NTP) server [20]


## Results of Parameter Exploration

There are 2 BLE algorithms to locate the user relative to beacons -

Proximity and kNN requiring knowledge of beacon position

Proximity: selects the beacon with the strongest received sgnal at a given time .. Locates the user with it.


kNN -  used k=3, so the three strongest signals were used
Produced a weighted mean of corresponding beacon positions.

![[Pasted image 20230926140309.png]]

Weight decided by 1/ri (which is RSS for RECEIVED signal strength in dBm)

Sample BLE Signal map
Fig. 5 gives a sample RSSI signal strength map for a beacon,
generated using the iPhone data in E1 and applying Gaussian
Process regression

##### How to mitigate fading?
 Raw scheme used 0.05ms windowing so v small.
 Multipath mitigation with 0.5s and median filter here:
 Green areas of high signal are centered w the mitigation

![[Pasted image 20230926140633.png]]

![[Pasted image 20230926140706.png]]

 
Positioning based on widnow size above
Positioning based on mitigation method below
Both show probability of positioning error of that distance.

![[Pasted image 20230926140934.png]]

Any mitigation vastly outperforms raw scheme.
Mitigations [[Core Deliverables]]

The choice between mean, median and
maximum is not so clear, however, with all three producing
very similar results. The maximum appears to give the best
results and is the cheapest to compute. 

However, we have exper-
imented with other handsets and observed occasional spurious
high RSS values that skew the performance of the maximum
[9]. The median and mean both filtered these out. Given a
moderate sampling rate, we expect the median score to be the
most robust to large outliers (i.e. both spurious high values and
very deep fast fades which may distort the mean)

USE THE MEDIAN 

### Window Selection

We observe
that window sizes of around 0.5 to 2 s seem to provide the best
performance, corresponding to a pedestrian covering approxi-
mately 0.7–3.0 m while walking. The performance in this range
is very similar, with an error of less than 3 m 95% of the time.


### measurement noise and the typical slow-fading correlation scale intrinsically limit the accuracy to this level
Which is an error of <3m for 95% of the time.

For shorter windows, mul-
tipath mitigation is not as effective; for longer windows the
smearing error dominates.

But smearing is not a limiting factor between 0.5-2s, measurment noise and the scale is.

### Effect of beacon Advertising Period

The beacons used in this work transmitted at a very high
rate of approximately 50 Hz. This is far higher than would be
expected in any opportunistic system, and would significantly
reduce the lifetime of battery-powered nodes in any dedicated
system (as a guideline, our beacons were each powered by
two AA batteries and exhibited a lifetime of approximately six
months at 50 Hz advertising). We therefore studied the effect of
downsampling the BLE signals.

What about we try this again w/ average sampling rates?? - i.e. measure and chsoe features w a typical air tag rate,

![[Pasted image 20230926142947.png]]

1s window. Median used if there was more than one. Has diminishing returns. Error 95% w/ 2.6m. 05Hz was far lower - advertising at double window than fingerprint window.
Long tail in cimilative prob. Lower than expected dimensionality

![[Pasted image 20230926143046.png]]


Number of beacons detected by a receiver !!! NUMBER OF ELEMENTS IN FINGERPRINT!!! [[#BLE Fingerprint construction]]

aRTIFICIALLY REDUCEED NUMBER OF BEACONS detected. vs positioning accuracy.7


taper at 8-190 beacons -  any more accuracy levelled off w diminishing returns.

Reducing to just 7 beacons:
![[Pasted image 20230926143524.png]]

very similar performance-  but increased errors of upt to 5m 95% of the time.


#### Transmit Power

The previous results were collected with the BLE bea-
cons transmitting near the top of the BLE specification range
(0 dBm). This inevitably resulted in fingerprints of greater
dimensionality since a given beacon has a much greater range ??????????????????????????????????

what is dBm


Very low power results in short range, isolated beacons and re-
gions of no positioning coverage, but as the power is increased
and beacon coverage patterns start to overlap, we expect to
see diminishing returns in terms of positioning accuracy as
power increases further still. 

artificially
attenuated the BLE readings for our datasets, discarding any
that fell below the empirically-determined noise floor for the
smartphone of −115 dBm.


![[Pasted image 20230926143734.png]]

25 dB would have had little effect on the positioning.
For attenuations of 30 dB and above, we see the positioning
performance decline. By 40 dB the error has grown approxi-
mately 50% at the 95% confidence level. However, we note that
even with a 40 dB attenuation applied, there was 100% avail-
ability of positioning (i.e., there was always a signal to position
with, regardless of the error it resulted in). 

ur key conclusions are:
1) The three BLE advertisement channels are associated
with different gains and multipath effects due to their
narrow width and wide spacing. Thus a BLE RSS mea-
surement without channel information may be tri-modal
at any given point, making a single measurement of the
RSS—as per WiFi fingerprinting—insufficient.
2) Batch filtering multiple beacon measurements per finger-
print is necessary for BLE fingerprinting. This requires
longer fingerprint listening periods or faster beaconing
rates. Rates of multiple Hertz are required when the
subject is moving to eliminate fingerprint smearing, and
as such slow-rate opportunistic beacons are unlikely to
support accurate tracking of moving users.
3) Diminishing returns were observed for beaconing rates
above 10 Hz using a 1.0 s filtering window.
4) Positioning error decreased as the number of beacons
per fingerprint increased, up to a threshold of around
8–10 beacons. Beyond this there was no further im-
provement in positioning accuracy. Combining this in-
formation with the desired beacon power level will steer
the beacon density required for maximum positioning
performance.
5) Beacon transition powers around −15 dBm provided
good coverage for a reasonably low density of beacons
in our office environment

Our deployment of one beacon per 30 m 2 gave accuracies of
< 2.5 m 95% of the time. Lowering the density to one beacon
per 100 m2 degraded this result to < 5.5 m. However, this is
still a significant improvement compared to positioning via the
established WiFi network in the same area, which achieved only
< 8.5 m error 95% of the tim
