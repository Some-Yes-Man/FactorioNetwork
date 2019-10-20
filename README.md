## Table of Contents

- [Table of Contents](#table-of-contents)
- [1. Introduction](#1-introduction)
- [2. The Basics](#2-the-basics)
  - [2.1 Time for an example!](#21-time-for-an-example)
  - [2.2 So many Signal Types](#22-so-many-signal-types)
  - [2.3 Controlling something](#23-controlling-something)
  - [2.4 First logic](#24-first-logic)
  - [2.5 Everything, Anything & Each](#25-everything-anything--each)
- [3 Ticks, Delay & Propagation](#3-ticks-delay--propagation)
  - [3.1 Feedback > Clocks](#31-feedback--clocks)
  - [3.2 Latches](#32-latches)
  - [3.3 Even more creepy stuff](#33-even-more-creepy-stuff)

## 1. Introduction

Welcome, mortal :yum: After spending over 1k hours with this fantastic game (and currently setting out to make it 2k), I've accompanied a few people on their journey. Most of them struggled to get a solid grasp of the Factorio circuit network, let alone its intricacies.

Looking at the existing material ([Circuit Network Cookbook](https://wiki.factorio.com/Tutorial:Circuit_network_cookbook) & [Combinator Tutorial](https://wiki.factorio.com/Tutorial:Combinator_tutorial)) it's not hard to figure out why, I'm sorry to say. Although those sources are not wrong about the topic and provide recipes, I always found them lacking in a proper approach to teach people how to do stuff on their own.

So, I'm setting out to give it another try and go step-by-step in basically writing a "Factorio Circuit Network for Dummies" tutorial. I'll also strive to include as many pictures and explanation as possible.

## 2. The Basics

So what exactly is the [Circuit Network](https://wiki.factorio.com/Circuit_network), besides a good read?!

A circuit network is a collection of buildings connected by [red wire](https://wiki.factorio.com/Red_wire) and/or [green wire](https://wiki.factorio.com/Green_wire). Those wires are items which can be crafted by the player or, this being Factorio, an assembly machine. For now I'll act as if there's only one color, green. More about that later. Said wires transport what is called "*signals*". You can either directly connect two buildings using a red/green wire connection or attach the wires to your existing power poles.

### 2.1 Time for an example!

![Two chests broadcasting their content into a circuit network.](images/Basics_Signals1.png)
Here we have a tiny network, consisting of a power pole with two chests attached to it using green wire. Both broadcast their respective contents, adding up to the signals shown on the right side.
As is happens, the "strength/height/amplitude" of the iron signal is 100, the one for copper is 200. Pretty obvious, it's the number of plates in the chests and is from now on called *value of the signal*.

![Two chests with similar content sending to a network.](images/Basics_Signals2.png)
Adding 100 iron plates to the right-hand chest, brings both signals up to the same value. Chests send out all the content and for the network it doesn't matter where the **signals** are coming from, they just **add up**.

![A chest and a constant combinator sending the same kind of signal.](images/Basics_Signals3.png)
Exchanging one of the chests with a [constant combinator](https://wiki.factorio.com/Constant_combinator) and configuring it to send a signal of -200 (yes, negative 200 iron plates), the new sum of all signals is a single -100 iron signal. Again, **the network** (ie the wire) just **adds up every signal type**.

### 2.2 So many Signal Types

So, anything that can be put into a chest, can be broadcast as a signal (panel #1 to #4). Just wire up all your chests and you'll have an overview what items (and which amount) exists in your factory. The same goes for all kinds of fluids (see panel #5), as you can also wire up your [storage tanks](https://wiki.factorio.com/Storage_tank) (each holds up to 25k of fluid).

![Logistic & Production Signals](images/Basics_LogisticAndProductionSignals.png) ![Intermediate & Combat Signals](images/Basics_IntermediateAndCombatSignals.png) ![Fluid & Virtual Signals](images/Basics_FluidAndVirtualSignals.png)

And then there are the [virtual signals](https://wiki.factorio.com/Circuit_network#Virtual_signals).

Assume someone actually connects all his or her chests, there would be no kind of signal left to communicate anything else over the network. Train stations for example can read the ID of a train. In order to send the ID over the network, the person might want to choose the *locomotive signal*. But, it's already taken because the chests communicate the number of locomotives in storage.

![Locomotive at a train stop which reads train ID and content.](images/Basics_VirtualSignals.png)

Luckily there is a number (I'm told it's 48) of non-item-related signals to pick from (see panel #6 above). So the train ID could be send as signal "A" for example, while it's content still refers to the items of course. There are also color signals in there (<span style="color:red">red</span>, <span style="color:green">green</span>, <span style="color:blue">blue</span> and so on). Those can even be used by lamps for automatic coloring.

Maybe you already know or have heard that there are also three very special *virtual signals* that are also called *logic signals*. Those would be `Everything`, `Anything` and `Each` (the red, green and yellow star symbol on panel #6). They are extremely helpful and I'll cover them later, due to their complexity.

### 2.3 Controlling something

Using what we learned so far, we can build a small network that's actually controlling something. The chest on the left is sending its content into the network (2.4k iron plates) and six other buildings use it as input. On the one hand we have the belt which is only enabled if the iron plate signal drops below 2k. On the other hand we've got 5 lamps that light up in steps of 960 iron plates (20% of the maximum amount of iron in the chest).

![Chest content controlling lamps and belts](images/Basics_Control1.png)

Okay, apparently there are a bunch of [buildings producing signals](SignalSources.md) and there are other [buildings which can be controlled](SignalSinks.md) by them. Some of the buildings fall in both categories. Now that you know how to get the signals out of the first kind and into the second kind of buildings, you already can build simple control mechanisms.

![Probably the smallest network possible :D](images/Basics_Control2.png)

A fairly easy and common one is the controlled power switch to attach/detach your backup steam engines after switching to solar power. You only want the steam to kick in if the accumulator charge drops below a certain level. So output the charge and feed it into the power switch. In this case, attach the engines as soon as the charge is below 10%.

Easy! But that can't be it, right?!

### 2.4 First logic

> basic building blocks: AND, OR, XOR, ..
> plus example and pictures

### 2.5 Everything, Anything & Each

> 3x example plus picture

## 3 Ticks, Delay & Propagation

> tick explanation
> bad delay chain example

### 3.1 Feedback > Clocks

> stuff

### 3.2 Latches

> stuff

### 3.3 Even more creepy stuff

> like I said, stuff
