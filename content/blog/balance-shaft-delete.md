+++
author = "Ryan Mukherjee"
categories = ["Hardware"]
date = "2017-01-26"
description = "Because eccentric weights spinning at twice engine rpm is a disaster waiting to happen"
featured = ""
featuredalt = ""
featuredpath = ""
linktitle = ""
title = "balance shaft delete"
type = "post"

+++

## Basics

If you don't know what a balance shaft is, it's worth checking out this video first:
<div class="aspect-ratio">
<iframe width="560" height="315" src="https://www.youtube.com/embed/hwigSbyQ7AI" frameborder="0" allowfullscreen></iframe>
</div>

The EA888 Gen 2 has two balance shafts that are located on the front and back of the engine. In the picture below, you can see a single chain that remains connected to the crankshaft sprocket. This chain connects to the two balance shafts.

{{< img-post path="/img/engine" file="balance_shaft_chain.jpg" alt="Balance shaft chain" type="center" >}}

You'll notice that the crankshaft sprocket is roughly twice the diameter for the plane that the balance shaft is connected to as compared to the other two planes (which connect to the timing chain and oil pump). It is this diameter increase that causes the balance shafts to rotate at roughly twice the engine RPM.

You can also see that the front (or rightmost in this image) balance shaft is connected to the chain via a separate gear. To clarify, the balance shaft chain doesn't connect directly to the front balance shaft. Instead, the chain drives a gear, which is connected to another gear that lies in the same plane as the front balance shaft gear. This configuration allows the front balance shaft to rotate in an opposite direction to the rear balance shaft, thereby cancelling unwanted horizontal forces. The secondary vibration that we want to counteract is a vertical force, and if the balance shafts didn't rotate in opposite directions then we would be adding a horizontal imbalance.

## Reasons to remove your balance shaft

One of the major problems with balance shafts is related to reliability. Because the balance shafts rotate at twice the engine RPM, their bearings can take quite a beating. It's also relatively easy to exceed what the balance shaft bearings are capable of handling once your start increasing your rev limit.

Balance shafts also represent an additional load on the engine. It takes energy to spin the weighted balance shafts and it takes oil pressure to stiffen the balance shaft chain tensioner and feed the balance shaft bearings. To make matters worse, the balance shafts aren't actually installed for any performance-related purpose. The purpose of the balance shafts is to prevent engine vibration from reaching the driver/passengers of the vehicle.

One might think that the balance shafts would help the rotating assembly be more balanced. However, the balance shafts are independent of the rotating assembly. Any secondary vibration in the rotating assembly first gets absorbed by the main bearings, transferred to and then cancelled in the block by the balance shafts. So in terms of minimizing bearing load, the balance shafts don't have any benefit. As such, it seems almost necessary to remove the balance shafts for a performance build.

Surprisingly, the EA888 Gen 2 does seem to support balance shaft removal without much effort. Because the balance shafts are driven with an independent chain, we don't need to worry about customizing the oil pump setup (previous engine generations had their balance shafts integrated into the oil pump). The only major hurdle with the EA888 is that the water pump is driven by the front balance shaft. In future posts, I'll go into more detail about the steps necessary to delete the balance shafts and discuss replacing the mechanical water pump with an electric one.
