---
title: Location Based Security With Conditional Access
date: 2022-01-31
draft: false
---

Some regulated industries require control over the location of data access. In the Microsoft cloud world, this requirement might be implemented with Conditional Access and a location policy. 

If I access, the request is checked against the configured locations, and if the location is allowed to access, the request is granted. In my case, my request comes from:

{{< figure library="true" src="/img/whereami.png" title="My current location according to Google" lightbox="true" >}}

Wait, what? Ah, the location data is gathered through your IP address. And as I am connecting through a VPN running on Azure, this is confusing to IP based localisation. 

If your requirement stems from regulation, you might need to go to GPS based location. It is quite easy. Conditional Access lets you define countries based on their GPS boundaries. Any request made to the policy, will notify users to confirm their location on their smartphone. Beware of the configuration details and on user communication. The user experience is impacted quite profoundly[^1].

Short blog post. Thank you. 

But wait.

From my old Mobile days I remembered something. Android allows you to easily change your phones GPS location. Hmm..

To achieve that, Androids Developer Options need to be activated. The process might differ from device to device, Android after all, but it was the old click-seven-times-on-the-build-number-in-the-settings on my Pixel 3. After managing the shivers of nostalgia, I downloaded FakeGPS from the Play store and picked it as my *Mock Location Provider*:

{{< figure library="true" src="/img/mock_location.png" title="" lightbox="true" >}}

So lets summarise: We have a Conditional Access policy, assigned to our testuser (1). We have a location condition (2), including all locations (3), and excluding Switzerland (4) where I currently sit in my basement. The policy blocks access, if those conditions apply (5). 

{{< figure library="true" src="/img/CA_location.png" title="" lightbox="true" >}}

The first test is with *FakeGPS* set in Switzerland:

{{< figure library="true" src="/img/fakeGPS1.png" title="" lightbox="true" >}}

I try to login to the Office 365 portal on my laptop, and get prompted by Conditional Access:

{{< figure library="true" src="/img/CAprompt.png" title="" lightbox="true" >}}

I confirm on my phone:

{{< figure library="true" src="/img/CAprompt2.png" title="" lightbox="true" >}}

And, voilà:

{{< figure library="true" src="/img/O365portal.png" title="" lightbox="true" >}}

For the next test, lets go somewhere warmer:

{{< figure library="true" src="/img/fakegps2.png" title="" lightbox="true" >}}

I confirm Conditional Access, and as expected, my policy prohibits me from entering any cloud apps:

{{< figure library="true" src="/img/fakegps3.png" title="" lightbox="true" >}}

Which leaves the regulated employee in a somewhat precarious situation. How can we make sure, that access is only happening from our desired locations? 

I am open to suggestions. 


[^1]: Conditional Access will trigger hourly requests to confirm the location. If the smartphones location grant is configured correctly, this request will be handled in the background, but still with a visible UI to the user. 