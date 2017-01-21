+++
author = "Ryan Mukherjee"
categories = ["Hardware"]
date = "2017-01-20"
description = "Engine teardown"
featured = "crank_removed.jpg"
featuredalt = "Bare block"
featuredpath = "/img/engine"
linktitle = ""
title = "engine teardown"
type = "post"

+++

## Initial Impressions

The first thing I noticed when inspecting the engine I received is that it's noticeable more complete than I had expected. I was expecting the engine assembly that I ordered to be stripped all the way down to the long block. Fortunately, the engine arrived with intake and exhuast manifolds, turbo, fuel system, full wiring harness, and basically any other component that is bolted directly to the block. 

A few components looked like they were either damaged during transport or during engine removal. The after run pump that supplies coolant to the turbo after turning off a hot engine was smashed. There were also a few coolant hoses that were cut. However, a majority of the components were in decent condition, or at least structurally.

{{< img-post path="/img/engine" file="block_front.jpg" alt="Block rust" type="center" >}}

The engine did have decent amount of oxidation on it. I imagine that the engine was poorly maintained by the owner(s), left outside in the crashed vehicle it came from for a decent amount of time, left outside after being pulled out of the vehicle, or more likely some combination of all of these things. A majority of the oxidation should be relatively easy to remove with a wire brush, though. I'll just have to be careful to ensure that I don't marr any critical surfaces.

## Disassembly

I started with the ignition coils and spark plugs. All the ignition coils look good, not that I was expecting anything to be wrong with them, and most of the spark plugs looked normal. The spark plug from cylinder three looks slightly fouled from carbon.

{{< img-post path="/img/engine" file="plugs_and_coilpacks.jpg" alt="Plugs and coilpacks" type="center" >}}

Next I removed the PCV valve on top of the valve/cam cover. This provided a look inside the head at the cams. There's a little bit of oil glazing on the vent tube that comes up from the secondary PCV, as well as on the oil return (both on the right side of the picture). The intake cam lobes (bottom) and exhaust cam lobe that are visible both look good at this point.

{{< img-post path="/img/engine" file="pcv_valve_cover.jpg" alt="PCV removed" type="center" >}}

Next up I removed the intake and exhaust manifolds. On this engine, the exhaust manifold and turbo are integrated into a single piece. From the back of the engine, you can also see the exhaust cam shift actuators on the valve cover (top of the middle picture). The EA888 Gen 2 is one of the first engines to receive Audi's Valvelift variable valve lift system, which adds a decent amount of low-end torque.

{{< img-fit "4u" "intake_valves_1.jpg" "Intake valves cylinder 1" 
"4u" "mounted_exhaust_manifold.jpg" "Exhaust manifold"
"4u$" "block_exhaust_manifold_removed.jpg" "Exhaust manifold removed"
"/img/engine" >}}

Taking a closer look at the intake valves, you can see that there's a significant amount of carbon buildup. Direct injection engines are great from an efficiency standpoint, but the lack of port injection causes rapid carbon buildup. Some newer VW/Audi engines have port injection and most people believe that this is the solution to the problem. However, from what I've read, the US-spec EA888 Gen 3 engines don't actually have port injection, but they do seem to have mitigated the carbon buildup issue.

{{< img-fit "3u" "intake_valves_1_grime.jpg" "Intake valves cylinder 1" 
"3u" "intake_valves_2.jpg" "Intake valves cylinder 2"
"3u" "intake_valves_3.jpg" "Intake valves cylinder 3"
"3u$" "intake_valves_4.jpg" "Intake valves cylinder 4"
"3u" "exhaust_valves_1.jpg" "Exhaust valves cylinder 1"
"3u" "exhaust_valves_2.jpg" "Exhaust valves cylinder 2"
"3u" "exhaust_valves_3.jpg" "Exhaust valves cylinder 3"
"3u$" "exhaust_valves_4.jpg" "Exhaust valves cylinder 4"
"/img/engine" >}}

I've read different reasons for the intake valve buildup. Some people think it's solely related to the PCV valve and, more specifically, blowby being fed back into the intake where it can attach to the valves. As such, it's suggested that using a catch can can mitigate and/or eliminate the intake valve buildup, however I haven't seen any definitive evidence. 

I have seen an example of someone who had their intake valves cleaned, installed a catch can, and then posted images of their valves several thousand miles later. Unfortunately, they still had a decent amount of buildup. I think one of the big flaws with this test was in the catch can that the individual used. Many of the catch can designs that I've seen don't seem very efficient, in that they likely leave enough oil in the crankcase vapor to recoat the valves. In my opinion, the Mishimoto MMBCC-UNI is one of the few efficient designs with cyclonic separation and a metal filter to condense remaining particles.

{{< figure src="https://i.ytimg.com/vi/WJfwc6tMoSc/maxresdefault.jpg" link="https://www.mishimoto.com/mishimoto-baffled-oil-catch-can.html" alt="Mishimoto MMBCC-UNI" class="image center-image" >}}

I don't know much about exhaust valve wear, so there's not much for me to say. The valves for cylinder three do seem to be different than the other cylinders, though. I wonder if this is related to the carbon fouling on the spark plug for cylinder three?

The intake manifold flaps and fuel injectors also seem to have a decent amount of carbon on them. The flaps, also known as [swirl flaps](https://en.wikipedia.org/wiki/Swirl_flap), are designed to help swirl the air entering each cylinder so that it mixes with the injected fuel better at low RPM. There are a few aftermarket options for deleting these flaps as they present an airflow obstruction, which can affect power at high RPM. Seeing this carbon buildup is making me consider one of these options.

{{< img-post path="/img/engine" file="intake_flaps_4.jpg" alt="Intake manifold flaps" type="center" >}}

