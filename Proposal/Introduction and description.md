

This text will expand on the title quoted for your project by giving further explanation both of the background to the work you propose to do and of the objectives you expect to achieve. Quite often a project title will do little more than identify a broad area within which you will work: the accompanying description must elaborate on this, giving details of specific goals to be achieved and precise characterisations of the methods that will be used in the process. You should identify the main sub-tasks that make up your complete project and outline the algorithms or techniques to be adopted in completing them. A project description should give criteria that can be used at the end of the year to test whether you have achieved your goals, and should back this up by explaining what form of evidence to this effect you expect to be able to include in your dissertation.

### Introduction and description

Bluetooth Low Energy tags such as AirTags or Tile Trackers are useful tools for locating personal items. However, these can be used maliciously, particularly for the purposes of stalking to tracker other people. There are a number of antistalking tools that attempt to alert users when they have been stalked, however, this alerts users after they have already been stalked, and there is no preventative tool to give people peace of mind they are not being stalked, or to stop stalking alerts taking place when simply seeing another person and their tags on a regular basis, for example a tag on a partners keys. Creating an inhibitor mode for these tags can prevent other tags being located by a stalker when detected in the same range. This is more useful
to keep privacy and location private from stalkers, even before stalking has been detected as it stops all tags in an area being found. With people moving about this is advantageous as others trying to find non stalking tags in the area will be able to when the inhibitor moves, and a small range should not disrupt the function of tags for a long period of time.
This also preserves the privacy of users who are simply near an inhibitor tag, and does not offer false detection alerts or that another tag is nearby, to a nontechnical user.

My project will involve building a tracking system for BLE trackers, which will involve modifying a Bluetooth  app to connect to a webserver that will receive RSSI (Received Signal Strength Indicator) to calculate distance from any tracking tags to any inhibitor tags. This can then determine which tags to stop the owner locating. The server will hold a list of which tags are registered as inhibitors and which as trackers.  I will explore modifying the app to implement the inhibitor bubble, as well as the webserver.
I can then evaluate which is best to implement considering how similar systems are implemented, privacy implications, and usage. I will also evaluate my system through accuracy of true detections and inhibitions based on the correct ranges that inhibitor tags should work with. 