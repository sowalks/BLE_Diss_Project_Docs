[https://drive.google.com/file/d/1zQI3U3dHXRUznasTGAJCUlAYLqaACqHh/view](https://eur03.safelinks.protection.outlook.com/?url=https%3A%2F%2Fdrive.google.com%2Ffile%2Fd%2F1zQI3U3dHXRUznasTGAJCUlAYLqaACqHh%2Fview&data=05%7C01%7Csmw98%40cam.ac.uk%7C332558933e164068f76c08dbbce3853e%7C49a50445bdfa4b79ade3547b4f3986e9%7C1%7C0%7C638311457592128726%7CUnknown%7CTWFpbGZsb3d8eyJWIjoiMC4wLjAwMDAiLCJQIjoiV2luMzIiLCJBTiI6Ik1haWwiLCJXVCI6Mn0%3D%7C3000%7C%7C%7C&sdata=urdmNg5aNixCB0lhgvaofwikVrQxoZZWeNieb4ah4wo%3D&reserved=0 "Original URL: https://drive.google.com/file/d/1zQI3U3dHXRUznasTGAJCUlAYLqaACqHh/view. Click or tap if you trust this link.")  

2014

Received Signal Strength (RSS)

BLE enables short unsolicited messages
Base proximity on received signal strength

long battery low  mainenance

Fingerprinting
Fingerprinting is currently the state-of-the-art indoor
positioning scheme readily available on standard
smartphones. A fingerprint refers to the pattern of radio
signal strength measurements recorded at a given location
in space and consists of a vector of signal identity
information (such as cellular Cell-IDs, or WiFi MAC
addresses) and a corresponding vector of Received Signal
Strength (RSS) values


that a receiver coming back to a
fingerprint location in the future should record the same
RSS measurements, within the limits of measurement
noise.


In reality fingerprints degrade over time as environmental changes occur i.e. people and furniture


we need re-serveuyomg tp evaluate location

were to assume a modest measurement noise such as
3 dBm, this would result in a ranging uncertainty of the
same order of magnitude as the distance to the source;
within a metre of the transmitter a positioning uncertainty
of only a few centimetres would be possible, however, at
10 m the ranging error would be around 5 m

Human body attentuates signals!!

![[Pasted image 20230926150354.png]]

![[Pasted image 20230926150518.png]] 
fast fading effects:

due to interference in space, deep multipath fade occurs within 10cm of movement

different channels exhibit fades at different regions!! 
multipath interference


ray tracing to simulate wifi channel

constructive interference only x2 more

Fingerprints are a batch of data that identify the region of
space where they were recorded, and so the BLE
measurements must be batched together intentionally to
form an RSS fingerprint. 


Positioning
A Bayesian estimator provided the positioning solution on
subsequent walks. The operating region was divided into
a grid with square cells of length 1 m or smaller and the
probability of a given fingerprint corresponding to each
cell was determined for each epoch using the Euclidean
distance:
𝐹 = √∑ (𝑅𝑖−𝑀𝑖)2𝑁
𝑖=1
𝑁 Equation 1
for current fingerprint R containing RSS measures for N
beacons and the value M extracted from the coordinate of
interest from the signal strength map for the
corresponding beacon.
This fingerprint distance was then weighted using a
Gaussian kernel to generate a probability for that cell
which accounted for the uncertainty in both the map
estimate and the current fingerprint measurement. The
variance data within the Gaussian Process survey maps
were thresholded such that map cells with moderate or
high variance were ignored completely (not trusted)
during these calculations. The resulting function across all
cells was the Bayesian Likelihood function
𝐿 = 𝑒− 𝐹
2𝜎2 Equation 2
where 𝜎 is the standard deviation associated with the
fingerprint measurement noise. The Gaussian kernel is
well suited to the error distributions following the use of a
multipath mitigation scheme.
Two priors were tested, a uniform prior at every epoch,
and a prior based on the previous epoch’s posterior, to
enable a tracking mode. The uniform prior carried no
correlations through time, and so represents the
performance of an acquisition position estimate at every
epoch. This is referred to as “one shot” positioning. The
tracking mode reduces the effects of sporadic errors in the
fingerprint measurements pulling the user far from the
true location, as it is assumed that the new posterior
distribution will be close to and overlap with the previous
one. Note that this tracking mode is only appropriate for
high beacon rates and good signal coverage such that it is
a valid assumption that the user moves only a small
fraction of the length scale of the posterior distributio lol same as that other talk

Once a posterior distribution was calculated, we estimated
the position (and hence the error) using the maximum
value (i.e. maximum a posteriori (MAP) probability) and
also the weighted mean of the posterior (i.e. Minimum
Mean Square Error (MMSE)). In general the results were
very similar, except when the posterior was multi-modal,
or described a sickle shape



