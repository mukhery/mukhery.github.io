+++
author = "Ryan Mukherjee"
title = "Tuning the EA888 - Reading/Writing Tools"
description = "Is it even possible to DIY?"
date = "2018-12-03"
categories = ["Software"]
featured = "tune_hex.png"
featuredalt = "Original ECU hex dump"
featuredpath = "/img/2018/12"
linktitle = ""
type = "post"

+++

## Why bother?

When I tell other car people that I tuned my car a common follow up question is, "Who did you go with?" They'll ask if I bought a tune from APR, Unitronic, or some other large corporation. I think one of the reasons for this is the complexity of modern cars. There are so many little computers, wires, and other electronic devices inside modern cars that people assume it's almost impossible for individuals to understand what's going on, let alone non-destructively make changes themselves.

I think this perceived complexity actually helped convince me to try. For one, it makes success even more satistfying if other people think it's an impossible problem. But, before I started, I also thought tuning modern cars was a nearly impossible problem, and it was very cool to crack the problem open and change that belief. 

One of the things I wrote about in my college application essay was that I wanted to understand, at a fundamental level, how computers worked. How does one turn raw electricity into the wealth of information and enjoyment that you can get from a computer? At the time I wrote my essay, it seemed almost like magic. Slowly and steadily, I began to realize that it isn't magic. In fact, like most (man-made) things in life it seems, computers are pretty much just an aggregation of a bunch of simple concepts and technologies. I think it's completely justifiable to be in awe of complex fully assembled products and systems, but I don't think we should believe that any man-made system is beyond our understanding. Most people are capable of understanding how these systems work if they put time and effort into understanding the components.

All of this is to say that, having spent some time learning about tuning, I think tuning is also fairly straightforward. Back when most cars were carbuerated, I think people wouldn't have been very surprised if you told them you tuned your car yourself. Maybe some would've argued that anyone could grab a screwdriver and tweak their own carbuerator. To be honest, I think at some level tuning modern cars hasn't really changed that much. I think what has changed is that the knobs we need to tune are harder to get to, but on the upside, once we get access to the knobs we'll have more control.

## What do we mean by tuning?

Generally, when we talk about tuning we're talking about changing the operating parameters of our engine. In other words, we're talking about changing how much fuel gets injected, when it gets injected, when the spark plugs fire, when and how variable valve timing actuators are controlled, etc. On modern vehicles, most engine parameters are controlled by computer. There are a bunch of modules around the vehicle and they all communicate via networks such as [CAN](https://en.wikipedia.org/wiki/Canbus). These modules are then connected to and control things like the injectors and spark plugs.

The primary module controlling the engine is called the [ECU](https://en.wikipedia.org/wiki/Engine_control_unit). In many modern cars, the ECU is combined with the [TCU](https://en.wikipedia.org/wiki/Transmission_control_unit) and the combined module is sometimes referred to as the [PCM](https://en.wikipedia.org/wiki/Powertrain_control_module). Even in cars with manual transmissions, the PCM module might still have all of the logic and hardware for controlling an automatic transmission to reduce manufacturing costs.

Ideally, we would like full control over the ECU so that we can quickly and easily tune the car. Unfortunately, unless we switch to something like an aftermarket standalone ECU (such as the [AEM Infinity](https://www.aemelectronics.com/products/programmable-engine-management-systems/infinity-ecu) or [Haltech Elite Series](https://www.haltech.com/product-category/universal-ecu-kits/)), gaining control of the stock ECU is basically a form of reverse engineering. Different manufacturers use different protocols, modern vehicles are often protected by keys and passwords to prevent unauthorized reading/writing, and the software running on the ECU is kept secret so you can't simply modify some source code, recompile, and then upload to your ECU. The easiest way to overcome these hurdles and get straight to tuning is to buy some tuning tools.

## Tuning Tools

To get started tuning, you'll need some tools that will enable you to read and write different software onto the ECU as well as help you understand what bytes to modify. For this post I'll focus on reading and writing. One of the biggest problems I encountered while trying to tune my own car was that tuning tools, especially ones that support modern vehicles, are very expensive. Alientech, Flashtec, and Magic Motorsport are some of the biggest players that offer tools supporting a wide variety of makes and models including many modern vehicles. Unfortunately, most of these tools are priced for professional tuners and tuning companies, which put them out of reach for myself and probably most individuals.

I contacted the big three tuning tool companies and asked if they had any cheaper options for individuals. Alientech was the only company that had a cheaper tool, which they call [Powergate3+](https://www.alientech-tools.com/en/powergate3/). The Powergate3+ unit essentially locks itself to a particular vehicle, which makes it less suitable for professional tuning companies but great for an individual. I purchased the Powergate3+ and tried to use it with my car, but only had partial success. The tool was able to successfully read my ECU after working with customer support and providing them with a readout that I obtained from another tuner, but the Powergate3+ was never able to fully write to the ECU. I tried working with customer support again, but my North American contact basically told me that his Italian colleagues weren't responding to resolve my problem.

If you can't find the tools you need directly from the companies themselves, it is possible to find some stuff on eBay. There are also some forums, such as NefMoto and MHH Auto where people discuss and sometimes even sell used tools. The most popular options seem to be Alientech's KESS and KTAG. KESS provides ECU reading and writing capabilities via OBD, as well as boot mode support for various ECUs. KTAG provides ECU reading and writing capabilities via BDM.

OBD is ideal, because it allows you to modify the software on your ECU without removing and opening the ECU. Tuning the car well, especially for a beginner (like me), requires making lots of little changes and testing them out to see what happens. Having to remove the ECU, open it, and solder wires just to write new software adds a huge amount of overhead to this process. If you're lucky, a tool like KESS will be able to OBD read and write software to your ECU. If not, you still may be able to open the ECU and solder wires to use KESS in what's called boot mode.

From what I've learned, boot mode is like a diagnostic mode that you can put the ECU's primary processor in during bootup. I think of it like accessing the BIOS on your computer. If you change the voltage on certain pins during bootup, or hold down a certain key (to use the BIOS analogy), you can enter a special mode where you can access features that might otherwise be locked by the ECU's software. However, there are limitations to boot mode. Often times you still only have access to a certain region of the ECU's memory.

[BDM](https://en.wikipedia.org/wiki/Background_debug_mode_interface) is another method that KTAG uses, which I think is similar to [JTAG](https://en.wikipedia.org/wiki/JTAG). Using BDM, Alientech's KTAG tool essentially provides full read and write access to the ECU's memory. When modern cars come out with new ECUs and protection mechanisms to prevent unauthorized OBD modification, BDM is usually the method that most tuners use to bypass these protections. Unfortunately, BDM also requires you to physically open the ECU to access special pins connected to the primary processor.

I also recently learned about HP tuners [MPVI2](https://www.hptuners.com/mpvi2/). It doesn't support my car specifically, but they support the same ECU versions in other vehicles. I reached out to the company to see if it would be possible to add support for my vehicle and I'll create another blog post if they get it working.

That's all for reading and writing tools. In future tuning posts, I'll go into more detail on how to edit the tune.
