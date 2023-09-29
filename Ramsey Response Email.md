BLE tracker background info

Ramsey Faragher

Sun 9/24/2023 10:49 AM

Hi Sophie Here are some materials that could be useful in your prep: we will need sources of bluetooth "advertising messages" that have a fixed ID - Airtags intentionally cycle these undeterministically (for us) so we will need other sources. Bluetooth Low

Sophie Walker

Thu 9/28/2023 10:16 AM

Hi Ramsey, Thank you, this is very useful, and has been very interesting. I've put down most of my thoughts here for tomorrows meeting, as well as a few questions I am unsure about. It would be great if you could take a look if you can. My first question is

Ramsey Faragher <ramsey@cantab.net>

via gmail.com

Sophie Walker

Ramsey Faragher;

Markus G. Kuhn

Hi Sophie

On Thu, 28 Sept 2023 at 10:17, Sophie Walker <[smw98@cam.ac.uk](mailto:smw98@cam.ac.uk)> wrote:  

> Hi Ramsey,
> 
>   
> 
> Thank you, this is very useful, and has been very interesting. I've put down most of my thoughts here for tomorrows meeting, as well as a few questions I am unsure about. It would be great if you could take a look if you can.  
> 
>   
> 
> My first question is about whether we want to advertise that a tag is an inhibitor, which we can modify the tags' advertisements for, like with Open Beacon. Or if it would be easier to have an app register tags, and then we can have the web server storing which ids are related to which tags. This would be easier and I am leaning towards this, although it may be less useful for real systems to store which tags are registered as inhibitors or not, instead of just broadcasting that data.

  

We definitely want all tags to be identical in their behvaiour and set up. i.e the tags just broadcast an ID, over and over. The server then has the list of which IDs are trackers, and which IDs are inhibitors - and this can be changed (even back in the past in historical data). Part of the investigation/an extension could be investigating the utility of these sort of aspects. I think I gave an example on our call of "Ah, I've lost my inhibitor tag - that's ok I can just log in and change it on my account to a tracker and see where it pops up on the FindMy network" etc

>   
> 
> For the discussion on Friday, I was thinking my core deliverables would be focused on 
> 
>   
> 
> The Server: Receiving location data and tag ids, calculating distance and time from any inhibitor tags, as well as pausing for a window of time to see if an inhibitor signal is detected. We can then mark these as inhibited. I will also want this data to be exportable.
> 
> This can be implemented with Flask and MySQL (although I'm not particularly set on the SQL database type).

  

We certainly want to log time, phone ID, BLE ID, RSSI, position I think as the minimum. It will be interesting to investgate 2 cases: 1. All inhibitor-tracker interacts only being associated with a single phones's reports. 2. Cross referencing across different phones (and so needing to add in the accuracy/coarseness etc of the phone's position estimates) - i.e. phone A hears tracker K at this location and phone B hears inhibitor J at a similar location at the same time

>   
> 
> The App: There are many out there, I think this [https://github.com/neXenio/BLE-Indoor-Positioning](https://eur03.safelinks.protection.outlook.com/?url=https%3A%2F%2Fgithub.com%2FneXenio%2FBLE-Indoor-Positioning&data=05%7C01%7Csmw98%40universityofcambridgecloud.onmicrosoft.com%7C2956992bcb9c4dfd29bc08dbc02afcd3%7C49a50445bdfa4b79ade3547b4f3986e9%7C1%7C0%7C638315063090318283%7CUnknown%7CTWFpbGZsb3d8eyJWIjoiMC4wLjAwMDAiLCJQIjoiV2luMzIiLCJBTiI6Ik1haWwiLCJXVCI6Mn0%3D%7C3000%7C%7C%7C&sdata=l8wBsukBIDPtu3Lj7zbb%2BnS2zL%2FHMTDQmn38%2B1DbWME%3D&reserved=0 "Original URL: https://github.com/neXenio/BLE-Indoor-Positioning. Click or tap if you trust this link.") app is the most promising as it can visualize data, scan for the common beacon types and is open source in Java. It provides both libraries for calculating distance as well as this app which I can modify to send the detected tags to the server, as well as any additional changes.
> 
>   
> 
> The Tags: Depending on my first question, I might have to modify these, or not at all. Openbeacon seems most appropriate if I do have to edit them, however [https://www.beaconzone.co.uk/allbeacons/K11Beacon?sort=p.price&order=ASC](https://eur03.safelinks.protection.outlook.com/?url=https%3A%2F%2Fwww.beaconzone.co.uk%2Fallbeacons%2FK11Beacon%3Fsort%3Dp.price%26order%3DASC&data=05%7C01%7Csmw98%40universityofcambridgecloud.onmicrosoft.com%7C2956992bcb9c4dfd29bc08dbc02afcd3%7C49a50445bdfa4b79ade3547b4f3986e9%7C1%7C0%7C638315063090318283%7CUnknown%7CTWFpbGZsb3d8eyJWIjoiMC4wLjAwMDAiLCJQIjoiV2luMzIiLCJBTiI6Ik1haWwiLCJXVCI6Mn0%3D%7C3000%7C%7C%7C&sdata=votcSDabH%2FpGbOlZWKErecx65IZwUxxAOIDXve9Uwvs%3D&reserved=0 "Original URL: https://www.beaconzone.co.uk/allbeacons/K11Beacon?sort=p.price&order=ASC. Click or tap if you trust this link.") tags like this I can configure all the settings, but I won't need to change the advertising packet's contents so I can use these as is.

  

These all look good options

>   
> 
>   
> 
> Extensions I could add are implementing the server properly as an actual system, and reporting back to tag owners the location of the tags, rather than just storing them. (Could be useful for a usability experiment)
> 
>   
> 
> I'd like to know how you did the simulations as they seemed very interesting and useful, but other than simulations I think real tests of both how accurate my distance/time bounds are will be informative in the lab. As an extension doing an in-person test, investigating the most useful bounds, beyond simulation over different environments and what would the most useful bounds of range and time be to avoid stalking but to keep surrounding people finding devices. 

>   
> 
> Listening to your COVID talk, I could try to improve the accuracy of my system's time and distance range for inhibiting, based on your suggestions for location accuracy, by doing more than just using the median and doing further filtering for things you suggested. 

  

Yes we will likely find that using a single "ping" from tags will be less reliable than processing multiple into one "decision epoch" - sounds like a sensible extension task

>   
> 
> Another extension can be making the web server detect when a device is being stalked, even with the inhibitor tags or not, detecting if an inhibitor tag is staying within a regular tag's range even whilst moving.

>   
> 
> I also have some questions about what the evaluation means, is it to evaluate that the system I have built works, or would investigating the best parameters for the inhibitors be put here as well? I can evaluate the error of the range and time for the inhibitor tags stopping other tags within the correct area, in similar setups to your lab ones. With the parameter investigation, is this part of the core deliverables I need to have or is it part of the evaluation?

  

Markus can confirm, but I believe it is indeed a bit of both - being able to demonstrate that you have built tests to check that what you have implemented is working properly, and also evaluating the performance of the system (what is our false positive and false negative rate for the various time-and-distance-bounds settings you might test across your datasets). It will likely be useful to do two types of tests - the "innocent daily usage" stuff of trackers and phones moving around an environment, and some simulated stalking tests - intentionally carrying two trackers together and assess how easily the system works. e.g. if one tag is buried in a backpack and the other has been slipped into a coat pocket, how often do passing phones see just one tag but not the other, etc

>   
> 
> I have tried to fit this to match the mark scheme, although I am not sure as it is quite vague. Is this appropriate for the work I should be doing, and do you have any other suggestions?

  

These all look good - I think we just want to collate all these thoughts into your proposal statement now with the main aims and a few possible extensions - but again I defer to Markus to catch anything we are missing here and to comment

  

Thanks

Ramsey