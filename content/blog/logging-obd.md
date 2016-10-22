+++
author = "Ryan Mukherjee"
categories = ["Software"]
date = "2016-09-22"
description = "Developing an Android app"
featured = ""
featuredalt = ""
featuredpath = ""
linktitle = ""
title = "logging obd"
type = "post"

+++

## OBD Adapter

Back in 2009 I purchased an OBDLink USB adapter so that I could scan trouble codes from my car using a laptop. The hardware was very nice, but as I messed around with the tool I realized it had a major shortcoming. While I appreciated that ScanTool offered open source software, I was very disappointed that the software was incapable of handling my vehicle's proprietary protocols. This isn't really the fault of ScanTool but rather the industry itself. Standardized automotive communication protocols have come a long way over the years, but they still have a ways to go in terms of making things more standardized, open, and accessible.

At any rate, I was able to upgrade to an OBDLink MX Bluetooth adapter in 2012. This little adapter is small, fast, and has nice power saving features. The STN11xx IC also supports a variety of different communication protocols to enable some potentially awesome applications.

{{< figure src="http://www.obdlink.com/wp-content/uploads/2014/05/mxbt_main1.png" link="https://www.scantool.net/obdlink-mxbt/" alt="OBDLink MX Bluetooth" >}}

However, I've seen a surprising lack of software options for the STN11xx chip. Most of the apps that I've seen only support the ELM327 command set. This is certainly the best way to cover the widest variety of hardware, as the STN11xx chips also support the ELM327 v1.4 command set. But these apps miss out on some of the advanced features of the ST11xx chips. 

## Building an Android Application

After rebuilding my engine I'm going to need tools to properly tune the engine. I surveyed commercial tuning products, however all of the viable options for an engine this new were too expensive. As such, I have begun to write my own software to interface with my OBDLink MX adapter with the goal of working towards a custom open-source solution to reading and flashing my ECU.

You can follow my progress on the Android app [here](https://github.com/mukhery/AudiECU). My first step is to create a terminal program to interface with the OBDLink MX bluetooth adapter and allow for manual command entry. After testing out OBD command scripts and ensuring that they work on my vehicle, I plan to incorporate these scripts into the app as part of a diagnostics page. There will also be a logs page for importing and exporting terminal logs, and eventually (if possible) the app will also have functionality to dump and flash ECU memory.

My current design for the app has all of the OBD command input and output being fed into a ContentProvider. This allows for fragments to more easily and seamlessly update with the latest terminal history. It also allows me to easily export and import command history by writing out the contents of the SQLite database to a file or vice versa. One of my goals is to ensure that no matter what diagnostic or ECU read/flash command a user runs, he or she can potentially export the terminal log that includes that raw OBD commands that allowed the software to perform these commands.

To handle the Bluetooth connection, my current design is to use an IntentService. The class's onHandleIntent method is used to open a Bluetooth socket and instantiate an infinite loop receiving data through the socket. All received data is written into the ContentProvider and any fragments that are monitoring this data will be automatically notified to pull the latest data. Once the IntentService starts, it registers a BroadcastReceiver that listens for commands to send to the OBD adapter. As soon as it receives a BroadcastIntent, it writes the contents to the Bluetooth socket.

By using an IntentService, I can quickly create a background service that maintains, reads, and writes from/to a Bluetooth connection. Services are required because some OBD commands simply put the adapter into a passive listen-only mode, and we would like to remain in this mode and collect data even when the app isn't in the foreground.