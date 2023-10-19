Hi Sophie and Markus

  

I think your response was all fine Sophie, although I would just make "investigated using different size ranges for the inhibitor tag" a little clearer - i.e. "different settings for the time bounds and distance bounds for two devices being co-located" or similar

  

I think in general - and Markus it would be great to get your thoughts too - perhaps we just want to make it clear:  

  

- There are lots of options for extensions of various complexities and disciplines (security, technical implementation, usability, system integration, etc)
- A project that involves tailoring a smartphone app, building a server and databasing setup from scratch, designing experiments, performing experiments, analysing data, sensitivity analyses to establish the efficacy of the proposed system, and using unusual hardware is not in itself a trivial undertaking
- Many projects get into difficulties because the "baseline" task is simply much too ambitious - here we have an achievable baseline project with plenty of options for extensions and further implementation tasks (the impact of adding more security features being the most obvious - e.g. cycling the IDs)

  

In terms of the direct questions being asked:

  

"The proposal isn't very clear to me. 

  

Certainly in the response to this we will be able to benefit from not being limited to 100 words, which is most likely a reason for this issue. It will be worth perhaps putting down in bullet form all the steps involved in the project

  

How is the mode set at the tracking nodes and how can it be enforced? 

  

We can explain here that the tags are all identical and just broadcast IDs. Tag type is determined is in the server alone in the main implementation, an extension may explore tag type being set by the detecting phones. This adds flexibility later (tags can be changed from one type to another, even historically. This can aid the implementation/usability/efficacy part of the study. One experiment is actually many experiments in post processing. Enforcement is by the seving system - e.g. a provider such as Apple provides the find my network and can enforce/change the tag types

  

Is inhibiting as simple as comparing the tag value with a 'do not track' list and, if so, forgetting about the tag?  I worry that this might be too simple for a Part 2 project."  

  

In theory inhibiting is as simple as confirming how near in space and time an inhibitor tag and a tracker tag are, but in practise BLE is a suboptimal system and by implementing this test system we can establish the false positive rates, false negative rates, and any other stats of interest for various settings and scenarios. We will address the question "is introducing inhibitor tags to a BLE tracking system an effective way to reduce the risk/impact/ease of stalking". There are a lot of possible extensions to this project (we should list them) that increase the complexity of the project. Implementing the same security procedures used by Apple to cycle IDs regularly and encrypt data in the server is a clear example.

  "here are a lot of possible extensions to this project including using more complex and accurate methods for locating tags based on an epoch of measurements or identifying stalkers even if they have been blocked as well as other extensions mentioned earlier. These can all increase the complexity of the project. Implementing the same security procedures used by Apple to cycle IDs regularly and encrypt data in the server is a clear example."

Does that help?

Any thoughts Markus?

  

Ramsey

  

p.s. I have an Android phone for you to use Sophie, and the BLE tags are ordered and on their way, so we can coordinate separately how to get those to you