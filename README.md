## Table of Contents

- [Table of Contents](#table-of-contents)
- [1. Introduction](#1-introduction)
- [2. The Basics](#2-the-basics)
  - [2.1 Time for an example!](#21-time-for-an-example)
  - [2.2 So many Signal Types](#22-so-many-signal-types)

## 1. Introduction

Welcome, mortal :yum: After spending over 1k hours with this fantastic game (and currently setting out to make it 2k), I've accompanied a few people on their journey. Most of them struggled to get a solid grasp of the Factorio circuit network, let alone its intricacies.

Looking at the existing material ([Circuit Network Cookbook](https://wiki.factorio.com/Tutorial:Circuit_network_cookbook) & [Combinator Tutorial](https://wiki.factorio.com/Tutorial:Combinator_tutorial)) it's not hard to figure out why, I'm sorry to say. Although those sources are not wrong about the topic and provide recipes, I always found them lacking in a proper approach to teach people how to do stuff on their own.

So, I'm setting out to give it another try and go step-by-step in basically writing a "Factorio Circuit Network for Dummies" tutorial. I'll also strive to include as many pictures and explanation as possible.

## 2. The Basics

So what exactly is the [Circuit Network](https://wiki.factorio.com/Circuit_network), besides a good read?!

A circuit network is a collection of buildings connected by [red wire](https://wiki.factorio.com/Red_wire) and/or [green wire](https://wiki.factorio.com/Green_wire). Those wires are items which can be crafted by the player or, this being Factorio, an assembly machine. Said wires transport what is called "*signals*". You can either directly connect two buildings using a red/green wire connection or attach the wires to your existing power poles.

### 2.1 Time for an example!

![Two chests broadcasting their content into a circuit network.](images/Basics_Signals01.png)
Here we have a tiny network, consisting of a power pole with two chests attached to it using green wire. Both broadcast their respective contents, adding up to the signals shown on the right side.
As is happens, the "strength/height/amplitude" of the iron signal is 100, the one for copper is 200. Pretty obvious, it's the number of plates in the chests and is from now on called *value of the signal*.

![Two chests with similar content sending to a network.](images/Basics_Signals02.png)
Adding 100 iron plates to the right-hand chest, brings both signals up to the same value. Chests send out all the content and for the network it doesn't matter where the **signals** are coming from, they just **add up**.

![A chest and a constant combinator sending the same kind of signal.](images/Basics_Signals03.png)
Exchanging one of the chests with a [constant combinator](https://wiki.factorio.com/Constant_combinator) and configuring it to send a signal of -200 (yes, negative 200 iron plates), the new sum of all signals is a single -100 iron signal. Again, **the network** (ie the wire) just **adds up every signal type**.

### 2.2 So many Signal Types

So, anything that can be put into a chest, can be broadcast as a signal (panel #1 to #4). Just wire up all your chests and you'll have an overview what items (and which amount) exists in your factory. The same goes for all kinds of fluids (see panel #5), as you can also wire up your [storage tanks](https://wiki.factorio.com/Storage_tank) (each holds up to 25k of fluid).

![Logistic & Production Signals](images/LogisticAndProductionSignals.png) ![Intermediate & Combat Signals](images/IntermediateAndCombatSignals.png) ![Fluid & Virtual Signals](images/FluidAndVirtualSignals.png)

And then there are the [virtual signals](https://wiki.factorio.com/Circuit_network#Virtual_signals).

Assume someone actually connects all his or her chests, there would be no kind of signal left to communicate anything else over the network. Train stations for example can read the ID of a train. In order to send the ID over the network, the person might want to choose the *locomotive signal*. But, it's already taken because the chests communicate the number of locomotives in storage.

![Locomotive at a train stop which reads train ID and content.](images/Basics_VirtualSignals.png)

Luckily there is a number (I'm told it's 48) of non-item-related signals to pick from (see panel #6 above). So the train ID could be send as signal "A" for example, while it's content still refers to the items of course. There are also color signals in there (<span style="color:red">red</span>, <span style="color:green">green</span>, <span style="color:blue">blue</span> and so on). Those can even be used by lamps for automatic coloring.

Maybe you already know or have heard that there are also three very special *virtual signals* that are also called *logic signals*. Those would be `Everything`, `Anything` and `Each` (the red, green and yellow star symbol on panel #6). They are extremely helpful and I'll cover them later, due to their complexity.