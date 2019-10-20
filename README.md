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
As is happens, the "strength" of the iron signal is 100, the one for copper is 200. Pretty obvious, it's the number of plates in the chests.

![Two chests with similar content sending to a network.](images/Basics_Signals02.png)
Adding 100 iron plates to the right-hand chest, brings both signals up to the same "strength", so to speak. Chests send out all the content and for the network it doesn't matter where the **signals** are coming from, they just **add up**.

![A chest and a constant combinator sending the same kind of signal.](images/Basics_Signals03.png)
Exchanging one of the chests with a [constant combinator](https://wiki.factorio.com/Constant_combinator) and configuring it to send a signal of -200 (yes, negative 200 iron plates), the new sum of all signals is a single -100 iron signal. Again, **the network** (ie the wire) just **adds up every signal type**.

### 2.2 So many Signal Types

