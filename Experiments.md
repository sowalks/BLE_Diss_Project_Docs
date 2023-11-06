  1. q
  2. 1 what data to answer
  3.  experiments

1 Example question - how reliable are phones for detecting tags? How often is a tag simply just missed? Do you ever see a spurious tag detection that isn’t actually near you (e.g. some weird glitch/bug/incorrectly decoded ID?)

1.1 We need either knowledge of “truth” - e.g exactly where all tags are, exactly where we are at all times, and look for evidence of not detecting a tag that was in range. Or we need to have lots of receivers all together scanning the same area at the same time and see how much disagreement there is in the logs

1.1.1 One way to try to establish this is to take lots of phones together on the same journey and cross-check all the bluetooth logs recorded by them. The advantage of this approach is that we do not need to know exactly where all the bluetooth sources are in the environment, we are simply testing for the consistency/reliability/repeatability/integrity of the current smartphone-based BLE listener API calls in Android devices

  

2. Will tags across a person all be detected at similar strengths/distances? 

2.1 While the previous experiments just cover detection, it is still important to know the specific positions. 

2.1.1

3. Can multiple tags be colocated by the same phone - this can be done vice versa in lab - can multiple tags be colocated by a phone. And how accurrate can one tag be located by multiple phones.
i.e locate phone from tag position & find distances apart from tags, from two/three phones
    This can be used for how many false negatives to expect, as well as giving a reasonable idea of the range required to avoid spurious results enabling stalking.



4. How accurate is pure RSSI distance for these specific tags
Specific Tag RSSI to distance accuracy similar , at ranges similar to prson/backpack/car [https://pages.cs.wisc.edu/~chatterjee/papers/usenix23-spydevices.pdf](https://pages.cs.wisc.edu/~chatterjee/papers/usenix23-spydevices.pdf)

Information in a fixed environment, data such as the distance phones are from the person, and the detected separation of tags compared to the expected distance. How much does this vary in crowded/ empty environments?





1. In evaluation  - experiments similar to BLE-Dpoubt and HomeScout to track if always blocked / time not blocked + any other detected and blocked tags for potential disruption



Send email to not fall of radar!! - I'm currently sending work - make a bit of progress before  we meet
