+++
author = "Ryan Mukherjee"
categories = ["Software"]
date = "2016-10-01"
description = "Progress on creating an Android OBD terminal and testing with OBDSim"
featured = "terminal_screenshot.png"
featuredalt = "Terminal screen"
featuredpath = "date"
linktitle = ""
title = "android obd terminal"
type = "post"

+++

## Terminal

The first step to interfacing with the ECU is communicating with the OBD adapter that's plugged into my car. As I mentioned in a previous blog post, I'm using an OBDLink MX Bluetooth adapter to communicate with the car. As this will be my first foray into raw OBD commands, I figured the best place to start would be a terminal interface that would allow me to enter commands manually so that I can test things out. I'd also like to do some general logging of OBD/CAN traffic on my car's network so that I can start to understand how things are connected and what normal communications look like.

Towards that goal, I've just about finished up the terminal interface. I ran into a few snags using an IntentService to handle the Bluetooth connection, but so far I've been able to tackle them. I was successfully able to use a BroadcastReceiver to handle user input and send it to the Bluetooth device, while using the main onHandleIntent function to wait for input from the Bluetooth connection. I initially tried to use service binding to support notifying the main Activity when the Bluetooth connection was successfully connected or not. However, I couldn't find a way to support delaying the onServiceConnected callback until the Bluetooth connection was fully connected. As such, I switched to using a ResultReceiver, which is Parcelable and can be passed in to the IntentService as an extra.

## OBDSim

While I was looking for a way to test the current version of my app, I stumbled upon [OBDSim](https://icculus.org/obdgpslogger/obdsim.html). Written by a guy named Gary, or so it seems, this tool is pretty awesome. Most of the other software ECU simulators I could find are paid and seemed to have pretty clunky interfaces.

I downloaded the latest [OBD GPS Logger](https://icculus.org/obdgpslogger/) source code, which was apparently from 6 years ago, and let out a sigh of relief when I saw that Gary used CMake. So I quickly created a build directory and got to compiling. Unfortunately, it looks like there might be some errors in the main OBD GPS Logger application. However, OBDSim is a separate target, so with a quick "make obdsim" command I was able to compile just the simulator. There were a few linking dependencies that weren't called out in the CMakeLists.txt file, but it was trivial to install them via apt-get.

Next thing I knew, I had a living breathing OBD simulator. A quick Google search led me to a [Stack Overflow](http://unix.stackexchange.com/questions/92255/how-do-i-connect-and-send-data-to-a-bluetooth-serial-port-on-linux) article that allowed me to get my phone connected to OBDSim. I've replicated the necessary commands below:

~~~bash
# Check if serial service is currently supported
sdptool browse local
# If not, create a serial service on channel 22
sdptool add --channel=22 SP
# Watch channel 22 with rfcomm, create /dev/rfcomm0 when a device connects
sudo rfcomm watch /dev/rfcomm0 22
# Start obdsim on /dev/rfcomm0 once a device connects
obdsim -t /dev/rfcomm0
~~~

Once connected, I was able to send commands as you can see from the screenshot in this post. My initial thought is that I need to hide the extra return carriage and terminal prompt that are being returning by the OBD adapter. However, it looks like OBDSim isn't 100% consistent about sending these characters, so I'll need to test on my real device to verify. My next steps will probably be to put logic like this in the Settings dialog, and then I'll want to implement the Log tab so that I can create log files to start understanding my car's network.