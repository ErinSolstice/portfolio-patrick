---
title: "Designing an Iontophoresis Device"
date: 2020-08-01
description: Investigating the current during an iontophoresis session when using a constant voltage source.
menu:
  sidebar:
    name: Designing an Iontophoresis Device
    identifier: iontophoresis-current
    parent: projects
    weight: 20
hero: images/full-setup.jpg
tags: ["electronics","raspberry-pi"]
categories: ["hobbies"]
---

One of the accepted treatments for hyperhidrosis (excessive sweating) is iontophoresis. Iontophoresis involves running a small current through the hands, feet, or armpits of the patient. Some people set the current whereas others set the voltage for a session. I wanted to see if these control methods were equivalent. Safety concerns around the body and electricity are obviously very important and complicated. RA Fischer, a manufacturer of an FDA approved device, has max settings of 30mA and 58V. To be on the safe side, I chose to use only 9V in my tests.

{{< figure-custom class="grid two" figcaption="Start up and sessions screens." >}}
  {{< img src="images/start-screen.jpg" alt="Start up screen." sizes="0.5" >}}
  {{< img src="images/session-screen.jpg" alt="Session screen." sizes="0.5" >}}
{{< /figure-custom >}}

I used a raspberry pi, a bundled voltage/current sensor, and a 9V battery. I added a 16x2 LCD display that shows relevant session information and allows adjustment of starting values by pushbutton. As a learning exercise, I used C to write most of the code. However, to interface with the current/voltage sensor I embedded python code in the C code.

To test the device, I placed my hands in the two plastic containers with aluminum foil electrodes covered by paper towels and just enough tap water to cover my palms. (I also added a ¼ teaspoon each of salt and backing soda as our water has a low mineral content.)

{{< figure-custom class="grid two" figcaption="Close up showing the breadboard wiring." >}}
  {{< img src="images/breadboard-potentiometer.jpg" alt="Breadboard with potentiometers." sizes="0.5" >}}
  {{< img src="images/breadboard.jpg" alt="Breadboard with screen and buttons." sizes="0.5" >}}
{{< /figure-custom >}}

{{< figure-custom class="grid two" figcaption="Setup of the iontophoresis device." >}}
  {{< img src="images/full-setup.jpg" alt="Setup of the testing circuit and iontophoresis device.  Shows two 9V batteries, however, in the end only one was used." sizes="1.0">}}
{{< /figure-custom >}}

Despite having a fairly constant voltage at about 8.5V, the current present in the circuit varied from 2mA-4.5mA through the 10-minute session. Clearly a constant voltage does not equate to a constant current.  What remains unclear is whether controlling the voltage, the current, or some other parameter such as total charge (i.e. current×time) works best.

{{< figure-custom class="grid two" figcaption="Data collected during the session." >}}
  {{< img src="images/voltage.png" alt="Graph of the voltage during the session." sizes="0.5" >}}
  {{< img src="images/current.png" alt="Graph of the current during the session." sizes="0.5" >}}
  {{< img src="images/resistance.png" alt="Graph of the resistance during the session." sizes="0.5" >}}
  {{< img src="images/power.png" alt="Graph of the power during the session." sizes="0.5" >}}
{{< /figure-custom >}}

{{< youtube 5xvp_0NI6Zk >}}
