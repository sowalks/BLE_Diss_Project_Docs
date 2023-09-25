  

Here are some materials that could be useful in your prep:

  

we will need sources of bluetooth "advertising messages" that have a fixed ID - Airtags intentionally cycle these undeterministically (for us) so we will need other sources.

  

Bluetooth Low Energy (BLE) is the tech used in tracking tags, but older bluetooth devices also advertise their existence for pairing, albeit it a much lower rate (i.e. my reference to fixed infrastructure like TVs and other devices in the lab that we might see on bluetooth scans)

  

You will find through Googling some typical BLE tags providers like Tile and Chipolo, there are also open source projects like this: [https://www.openbeacon.org/about.html](https://eur03.safelinks.protection.outlook.com/?url=https%3A%2F%2Fwww.openbeacon.org%2Fabout.html&data=05%7C01%7Csmw98%40cam.ac.uk%7C332558933e164068f76c08dbbce3853e%7C49a50445bdfa4b79ade3547b4f3986e9%7C1%7C0%7C638311457592128726%7CUnknown%7CTWFpbGZsb3d8eyJWIjoiMC4wLjAwMDAiLCJQIjoiV2luMzIiLCJBTiI6Ik1haWwiLCJXVCI6Mn0%3D%7C3000%7C%7C%7C&sdata=NX4ktvI43x%2BcNrCFocBxhKMhthQ8e4CYpi2demZpP3Q%3D&reserved=0 "Original URL: https://www.openbeacon.org/about.html. Click or tap if you trust this link.")

|   |
|---|
|[About the OpenBeacon project – Bluetooth LE Tracking – Active 2.4 GHz RFID tracking](https://eur03.safelinks.protection.outlook.com/?url=https%3A%2F%2Fwww.openbeacon.org%2Fabout.html&data=05%7C01%7Csmw98%40cam.ac.uk%7C332558933e164068f76c08dbbce3853e%7C49a50445bdfa4b79ade3547b4f3986e9%7C1%7C0%7C638311457592128726%7CUnknown%7CTWFpbGZsb3d8eyJWIjoiMC4wLjAwMDAiLCJQIjoiV2luMzIiLCJBTiI6Ik1haWwiLCJXVCI6Mn0%3D%7C3000%7C%7C%7C&sdata=NX4ktvI43x%2BcNrCFocBxhKMhthQ8e4CYpi2demZpP3Q%3D&reserved=0 "Original URL: https://www.openbeacon.org/about.html. Click or tap if you trust this link.")<br><br>Active 2.4 GHz RFID tracking<br><br>[www.openbeacon.org](http://www.openbeacon.org)|

  

We will want to find some tags that definitely don't cycle their ID //open beacon// , and you might want to design your experiments such that we source tags with selectable ID broadcast rates // ones where we have to chose//. Markus mentioned a previous piece of work in the lab recently that used BLE - perhaps there are some lab tags we can make use of in addition to any extras that FocalPoint buys for the project

  

There are many apps that can be used to log BLE encounters, as I mentioned you might want to look into an open source one you can adapt, or simply build your own, building a very simple BLE scanning app that just dumps interesting stuff from Android listeners on BLE, GPS and maybe some other sensors too into a csv file will not take very long. I will check this week on getting a few Android phones provided for the testing. Android phones can also beacon as a pretend BLE tag as well as listen out for BLE tags so that will likely come in handy on the project

  

The papers I mentioned of mine that highlight just how scruffy a BLE measurement is are here:

[[Notes on Ramsey Papers]]

[https://drive.google.com/file/d/1zQI3U3dHXRUznasTGAJCUlAYLqaACqHh/view](https://eur03.safelinks.protection.outlook.com/?url=https%3A%2F%2Fdrive.google.com%2Ffile%2Fd%2F1zQI3U3dHXRUznasTGAJCUlAYLqaACqHh%2Fview&data=05%7C01%7Csmw98%40cam.ac.uk%7C332558933e164068f76c08dbbce3853e%7C49a50445bdfa4b79ade3547b4f3986e9%7C1%7C0%7C638311457592128726%7CUnknown%7CTWFpbGZsb3d8eyJWIjoiMC4wLjAwMDAiLCJQIjoiV2luMzIiLCJBTiI6Ik1haWwiLCJXVCI6Mn0%3D%7C3000%7C%7C%7C&sdata=urdmNg5aNixCB0lhgvaofwikVrQxoZZWeNieb4ah4wo%3D&reserved=0 "Original URL: https://drive.google.com/file/d/1zQI3U3dHXRUznasTGAJCUlAYLqaACqHh/view. Click or tap if you trust this link.")  


  

[https://drive.google.com/file/d/1xTohO1klU6aTrz9Ij9dZ-mMSOeti1iSR/view](https://eur03.safelinks.protection.outlook.com/?url=https%3A%2F%2Fdrive.google.com%2Ffile%2Fd%2F1xTohO1klU6aTrz9Ij9dZ-mMSOeti1iSR%2Fview&data=05%7C01%7Csmw98%40cam.ac.uk%7C332558933e164068f76c08dbbce3853e%7C49a50445bdfa4b79ade3547b4f3986e9%7C1%7C0%7C638311457592128726%7CUnknown%7CTWFpbGZsb3d8eyJWIjoiMC4wLjAwMDAiLCJQIjoiV2luMzIiLCJBTiI6Ik1haWwiLCJXVCI6Mn0%3D%7C3000%7C%7C%7C&sdata=Fts10PcL2g0hNIRws5T7xK7F4yTxwJ1hL6lxKs9Y%2Fns%3D&reserved=0 "Original URL: https://drive.google.com/file/d/1xTohO1klU6aTrz9Ij9dZ-mMSOeti1iSR/view. Click or tap if you trust this link.")  

  

And a talk I gave on what all this meant for COVID contact tracing apps - which covers the same sort of issues that will be in play here for the inhibitor tags on scan rates and probabilities of missed scans etc - an inhibitor tag and tracker tag being correctly or incorrectly "co-located" is the same problem family as two phones being within 2m of each other for 2minutes in the covid era of contact tracing. The great thing for our project is that simply " any detection at all" of a tag is needed (binary decisions), whereas for contact tracing there was the need to determine the range between phones too (within 2m or not)

  

[https://www.youtube.com/watch?v=xL3jGLYRRCE](https://eur03.safelinks.protection.outlook.com/?url=https%3A%2F%2Fwww.youtube.com%2Fwatch%3Fv%3DxL3jGLYRRCE&data=05%7C01%7Csmw98%40cam.ac.uk%7C332558933e164068f76c08dbbce3853e%7C49a50445bdfa4b79ade3547b4f3986e9%7C1%7C0%7C638311457592128726%7CUnknown%7CTWFpbGZsb3d8eyJWIjoiMC4wLjAwMDAiLCJQIjoiV2luMzIiLCJBTiI6Ik1haWwiLCJXVCI6Mn0%3D%7C3000%7C%7C%7C&sdata=EXqR7Nb%2BS34VHsm48gz43Vsw0vhVSby0G7eZZ4Nn4Kk%3D&reserved=0 "Original URL: https://www.youtube.com/watch?v=xL3jGLYRRCE. Click or tap if you trust this link.")  

|   |   |
|---|---|
|[![](https://i.ytimg.com/vi/xL3jGLYRRCE/maxresdefault.jpg)](https://eur03.safelinks.protection.outlook.com/?url=https%3A%2F%2Fwww.youtube.com%2Fwatch%3Fv%3DxL3jGLYRRCE&data=05%7C01%7Csmw98%40cam.ac.uk%7C332558933e164068f76c08dbbce3853e%7C49a50445bdfa4b79ade3547b4f3986e9%7C1%7C0%7C638311457592128726%7CUnknown%7CTWFpbGZsb3d8eyJWIjoiMC4wLjAwMDAiLCJQIjoiV2luMzIiLCJBTiI6Ik1haWwiLCJXVCI6Mn0%3D%7C3000%7C%7C%7C&sdata=EXqR7Nb%2BS34VHsm48gz43Vsw0vhVSby0G7eZZ4Nn4Kk%3D&reserved=0 "Original URL: https://www.youtube.com/watch?v=xL3jGLYRRCE. Click or tap if you trust this link.")|[Demystifying Contact Tracing Apps with Dr Ramsey Faragher](https://eur03.safelinks.protection.outlook.com/?url=https%3A%2F%2Fwww.youtube.com%2Fwatch%3Fv%3DxL3jGLYRRCE&data=05%7C01%7Csmw98%40cam.ac.uk%7C332558933e164068f76c08dbbce3853e%7C49a50445bdfa4b79ade3547b4f3986e9%7C1%7C0%7C638311457592128726%7CUnknown%7CTWFpbGZsb3d8eyJWIjoiMC4wLjAwMDAiLCJQIjoiV2luMzIiLCJBTiI6Ik1haWwiLCJXVCI6Mn0%3D%7C3000%7C%7C%7C&sdata=EXqR7Nb%2BS34VHsm48gz43Vsw0vhVSby0G7eZZ4Nn4Kk%3D&reserved=0 "Original URL: https://www.youtube.com/watch?v=xL3jGLYRRCE. Click or tap if you trust this link.")<br><br>Why is Bluetooth proximity detection harder than people thought? What are the fixes, the alternative approaches, the best architectures?Dr Ramsey Faragher ge...<br><br>[www.youtube.com](http://www.youtube.com)|

  

  

Hopefully that's all useful - I think a good input for our catch up discussion next week will be some of your first thoughts on what you would like the project to cover [[Proposal Draft (100 words)]]and it's main implementation activity with the mark scheme in mind (core components plus some extensions)[[Core Deliverables]] and a rough description of how the experiments you will need might be conducted. [[Ethics committee]]

  

Dont forget, feel free to ask any questions along the way before we catch up again next week

  

Thanks

Ramsey