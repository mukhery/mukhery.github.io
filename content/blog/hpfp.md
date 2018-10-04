+++
author = "Ryan Mukherjee"
title = "High Pressure Fuel Pump Upgrade"
description = "Backwards compatibility for the win!"
date = "2018-10-03"
categories = ["Hardware"]
featured = "apr_hpfp.jpg"
featuredalt = "EA888 Gen2 HPFP vs EA888 Gen3 HPFP"
featuredpath = "/img/2018/10"
linktitle = ""
type = "post"

+++

## Motivation

I'll keep this section short, because most of you probably already know why one might want to upgrade their high pressure fuel pump (HPFP). For those of you who don't, the rationale is simple: to make more power we need to be able to inject more fuel. Along those lines, we might upgrade the fuel injectors to ones that are capable of flowing more volume, or we might change the engine tuning so that the injectors flow fuel for longer. However, if we increase the volume of fuel that the injectors are capable of injecting then we also need to ensure adequate fuel supply to the injectors. That's where fuel pump upgrades come into play. An upgraded HPFP is capable of flowing a larger volume of fuel than the stock pump. 

On the EA888 engine there's a high-pressure fuel regulator that allows the ECU to control fuel pressure. As such, upgrading the HPFP won't have any affect unless the engine wasn't able to keep up with fuel demands before the upgrade, or if the pressure regulator can't cope with the increased volume of fuel (which is probably unlikely). So the good news is that you can upgrade the pump in your garage and then get a tune for it later, or it'll just solve any fueling issues you're already having.

## Aftermarket options

The big problem with the EA888 Gen2 (USA) engine is that, for some reason, the HPFP upgrade options were nonexistent until recently and even now very limited. Supposedly the rest-of-world (ROW) version of the engine had a fuel pump that could be upgraded, but I'm not sure what the difference is. Regardless, now that the manufacturer and a lot of the aftermarket has moved on to the Gen3 engine, I don't expect the Gen2 options to get any better.

APR is one of the big players in this area. The nice thing about APR is that you can simply send your fuel pump over and they'll rebuild it, test it, and send it back. Unfortunately, they don't offer any Gen2 pump upgrade options.

## Retrofitting the EA888 Gen3 HPFP

So the big find that I made is that the EA888 Gen3 pump *can* be used on the EA888 Gen2 engine. The catch is that you have to retrofit a Gen3 vacuum pump as well.

It turns out that the Gen3 engine has an identical vacuum pump mounting location and camshaft lobes for driving the vacuum pump and fuel pump. The fuel pumps themselves are different, so you can't simply put a Gen3 fuel pump in a Gen2 vacuum housing. However, because of the similarities, you can simply retrofit the entire Gen3 vacuum pump and fuel pump onto the Gen2 head.

{{< img-post path="/img/2018/10" file="camshaft_inside_gen3_housing.jpg" alt="Camshaft visible inside Gen3 HPFP housing" type="center" >}}

There are several additional modifications that I had to make to get everything to fit, although none of them were particularly difficult:

* The Gen3 pump housing has the HPFP sitting in a higher position, which meant that I had to bend the fuel lines connecting the HPFP output to the fuel rail to accomodate.
* I had to move my Gen2 HPFP pressure regulator over to the Gen3 pump so that I could use my existing wiring.
* I had to bend the coolant hard line around the Gen3 housing.
* I had to move the Gen2 HPFP vacuum line connector onto the Gen3 pump so that my stock vacuum lines fit.
* I tapped and plugged the extra nipple attached to the Gen3 HPFP.
* Finally, I had to cut the edge of the PCV adapter plate so that it wouldn't impact the HPFP.

After making all these modifications, I found that everything fit perfectly. I sent my Gen3 HPFP to APR to get upgraded and have since installed the upgraded pump on my car. It works beautifully!

{{< img-fit "6u" "pcv_adapter_trimmed.jpg" "Trimmed PCV adapter plate" 
"6u$" "hpfp_mounted.jpg" "Finished view of the EA888 Gen3 HPFP on an EA888 Gen2 engine"
"/img/2018/10" >}}


