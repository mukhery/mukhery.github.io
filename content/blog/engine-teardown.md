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

My next step was to remove the valve/cam cover. After doing this, I realized that I should've removed the timing chain first. The timing chain applies a downward pull to the end of the intake and exhaust cams, so once I removed the valve cover the cams lifted out of their saddles. Later I noticed a small corner dent in one of the saddles that I think was caused by removing the cover before the timing chain. The dent isn't a big deal, but it does show that removing the cover is a reasonably complex job when the engine is in the car because the timing chain is involved.

{{< img-fit "6u" "cams_top.jpg" "Camshafts" 
"6u$" "top_valve_cover.jpg" "Valve cover"
"/img/engine" >}}

Removing the timing chain and cams was fairly straightforward. I had to use a crankshaft pulley counterhold tool ([T10355](http://a.co/1MjnkLO)) to remove the crankshaft pulley bolt, but then it was relatively easy to remove the chain cover, tensioner, guides, and chain. After that, the cams just lift right out.

{{< img-fit "6u" "balance_shaft_chain.jpg" "Timing chain removed" 
"6u$" "cams_removed_side.jpg" "Cams removed"
"/img/engine" >}}

After removing the cams, I removed the head bolts using [this tool](http://a.co/8iSRv3J) and then lifted the head off the block. In hindsight, it probably would have been cleaner to leave the valve cover on the head. The cover has holes in it that lead directory to the head bolts allowing you to unbolt the head without removing the valve cover.

{{< img-fit "4u" "valves.jpg" "Cams removed" 
"4u" "head_standalone.jpg" "Head standalone"
"4u$" "head_removed_3.jpg" "Head removed"
"/img/engine" >}}

Next I unbolted the rods and removed the pistons. The cylinder walls are in decent condition aside from some surface rust and a decent amount of carbon buildup. Taking a closer look at the pistons, I didn't see any cracked ring lands or other major structural damage. Thinking back to the engine that's currently in my car, it's possible that it has a similar amount of carbon buildup to this engine. The carbon on the oil control rings here looks like it could be enough to reduce the effectiveness of the oil control rings.

{{< img-fit "6u" "pistons_and_rods.jpg" "Pistons and rods" 
"6u$" "piston_carbon.jpg" "Cylinder 1 piston"
"/img/engine" >}}

Removing the cross-bolted main caps in this engine required removing both the two main bolts as well as the perpendicularly-positioned bolts through the outside of the block. The caps use dots on a raised right trapezoid indicating the location and rotation that the cap is supposed to be installed.

{{< img-fit "3u" "main_bearings_1_2_3.jpg" "Main bearings 1, 2, and 3" 
"3u" "main_bearings_2_3_horiz.jpg" "Main bearings 2 and 3"
"3u" "main_bearings_3_4_horiz.jpg" "Main bearings 3 and 4"
"3u$" "main_bearings_4_5_horiz.jpg" "Main bearings 4 and 5"
"/img/engine" >}}

After removing the main caps, I was able to inspect the main bearings. The bearings look very good, I don't see any major marks on the bearings, nor was I able to feel any with my fingernail. Next step is to get the engine into the machine shop so that they can clean everything up and get it ready for me to reassemble.