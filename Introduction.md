Clear motivation, justifying potential benefits of success.  
Clear presentation of challenging background material covering a range of computer science topics beyond Part IB

The introduction should explain the principal motivation for the project and show how the work fits into the broad area of surrounding computer science and give a brief survey of previous related work. It should generally be unnecessary to quote at length from technical papers or textbooks. If a simple bibliographic reference is insufficient, consign any lengthy quotation to an appendix.

## Motivation

- explanation and use of tracking tags currently
- Inadequate antistalking practices -  https://www.cl.cam.ac.uk/~kst36/documents/cant-keep-them-away-spw-preproc.pdf
- The majority of stalking occuring with technically illiterate?
- The idea being reasonable - instant, peace of mind, protecting users
- Current methods may not be used, or are difficult to find.
- inhibiting tags - implemented on current hardware, is user controlled
- find out if this option is realistic, if it works, if it is likely to be used
- as new standards are coming out,exploration -  https://security.googleblog.com/2023/05/google-and-apple-lead-initiative-for.html, 

Bluetooth Low Energy (BLE) tags such as AirTags or Tile Trackers are popular and useful tools for locating personal items. However, there are major concerns as stalkers can maliciously use these to track their victims.
Apple was sued in 2022 by women who had stalking incidents involving AirTags \cite{bbc},
and they linked AirTags to murders where the victim had been tracked.  Additionally, these devices have been planted on cars to track their location and steal them. 

Therefore, it is key to prevent stalking through AirTags, and various anti-stalking protocols have been implemented to detect tags that have been following them by the victim's phone. This includes can alert them to how long it has been near them, can play a sound on the device. However, many methods have been found to be ineffective
and are rarely used \\cite{cantkeepaway}. In addition current preventions for stalking, typically detecting stalkers takes at least 4 hours, even when used.

Additionally, until recently, users who did not use Apple Phones were not alerted to stalking, or required an additional app to perform background checks. Although, new features have been introduced and there is a Google-Apple intiative for a new specifcation to address this unwanted tracking \\cite{googleapple}. So this area is active and more effective preventions are being developed and explored such as 
DeTagTive, HomeScout and BLEDoubt \\cite{DeTagTive} \cite{homescout} \\cite{BLEDoubt}.

However, all these, while claiming to be more effective and quicker, are focused on the task of classifying trackers as malicious or not, which is not useful as we cannot fully distinguish stalking from safe tracking here. For example, if users are near others for long periods of time, like an AirTag in a shared car or a partner's keys, this can be detected as stlaking and repeatedly alert the user to non malicious behaviour.

This all motivates my project to create an Anti-Stalking feature that can be implemented to stop stalking from BLE trackers immediately, without needing to distinguih malicious behaviour, being convenient for users and providing certain peace of mind that stalking attempts have been prevented.

My project is to create a prototype of a similar tracking system and investigate the effectiveness of adding an antistalking ‘privacy bubble’ feature. This involves having the system set tags as inhibitors or trackers. Tracking tags will function as regular tags so their owner can locate them and their items. However, if they are in the range of an inhibitor tag, the owner will not receive the tracking tag’s location. A privacy bubble means any tracking tags near in time or distance ranges to an inhibitor will not report their location back to their owner. This can instantly prevent stalking with these devices, while not disrupting benign user's who are not stalking or tracking the victim, but any nearby stalking tracker's will be blocked. The idea is for usersto place the tags in valuable items like car's or on a person, to prevent the stalking issues more effectively and give peace of mind to the user.

My aim is to build this software and evaluate whether this unique anti-stalking idea is feasible and useful for anti-stalking, and if issues with BLE \\cite{ramsey} can be worked around and if they would be used?


convenient safe, peace of mind 







Prior research on domestic abuse victims introduced the “UI-bound adversary”
threat model \\cite{uibound} 


\\bibitem{bbc}   https://www.bbc.co.uk/news/technology-63880969
\\bibitem{nytimes}Mac, R., Hill, K.: Are Apple AirTags being used to track people and steal cars?
The New York Times (2021) https://www.nytimes.com/2021/12/30/technology/apple-airtags-tracking-stalking.html

\\bibitem{uibound} Diana Freed, Jackeline Palmer, Diana Minchala, Karen Levy, Thomas Ristenpart, and Nicola Dell. 2018. “A Stalker's Paradise”: How Intimate Partner Abusers Exploit Technology. In Proceedings of the 2018 CHI Conference on Human Factors in Computing Systems (CHI '18). Association for Computing Machinery, New York, NY, USA, Paper 667, 1–13. https://doi.org/10.1145/3173574.3174241

\bibitem{cantkeepaway}K.I. Turk, A. Hutchings, A. Beresford, “Can’t Keep Them Away: The failures of anti-stalking protocols in personal item tracking devices” to appear in the proceedings of the Security Protocols Workshop, March 2023.

\bibitem{googleapple} https://security.googleblog.com/2023/05/google-and-apple-lead-initiative-for.html

\\bibitem{DeTagTive} https://dl.acm.org/doi/pdf/10.1145/3609396.3610544

\bibitem{BLEdoubt} https://ieeexplore.ieee.org/stamp/stamp.jsp?tp=&arnumber=9833870

\\bibitem{HomeScout} https://ieeexplore.ieee.org/stamp/stamp.jsp?tp=&arnumber=10223406

\\biitem{ramsey} Faragher, R., Harle, R., “An Analysis of the Accuracy of Bluetooth Low Energy for Indoor Positioning Applications,” Proceedings of the 27th International Technical Meeting of the Satellite Division of The Institute of Navigation (ION GNSS+ 2014), Tampa, Florida, September 2014, pp. 201-21

