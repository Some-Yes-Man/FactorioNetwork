## Introduction

Welcome, mortal :yum: After spending over 1k hours with this fantastic game (and currently setting out to make it 2k), I've accompanied a few people on their journey. Most of them struggled to get a solid grasp of the Factorio circuit network, let alone the intricacies.

Looking at the existing material ([Circuit Network Cookbook](https://wiki.factorio.com/Tutorial:Circuit_network_cookbook) & [Combinator Tutorial](https://wiki.factorio.com/Tutorial:Combinator_tutorial)) it's not hard to figure out why, I'm sorry to say. Although those sources are not wrong about the topic and provide recipes, I always found them lacking in a proper approach to teach people how to do stuff on their own.

So, I'm setting out to give it another try and go step-by-step in basically writing a "Factorio Circuit Network for Dummies" tutorial. I'll also strive to include as many pictures and explanation as possible.

## Table of Contents

- [Introduction](#introduction)
- [Table of Contents](#table-of-contents)
- [List of Signal Sources](#list-of-signal-sources)
- [List of Signal Sinks](#list-of-signal-sinks)

## List of Signal Sources

Item | Icon | Output
:--- | :---: | ---:
Chests | ![Wooden Chest](https://wiki.factorio.com/images/Wooden_chest.png) ![Iron Chest](https://wiki.factorio.com/images/Iron_chest.png) ![Steel Chest](https://wiki.factorio.com/images/Steel_chest.png)<br>![Active Provider Chest](https://wiki.factorio.com/images/Active_provider_chest.png) ![Passive Provider Chest](https://wiki.factorio.com/images/Passive_provider_chest.png) ![Storage Chest](https://wiki.factorio.com/images/Storage_chest.png) ![Buffer Chest](https://wiki.factorio.com/images/Buffer_chest.png) ![Requester Chest](https://wiki.factorio.com/images/Requester_chest.png) | all contents
Storage Tank | ![Storage Tank](https://wiki.factorio.com/images/Storage_tank.png) | fluid content
Belts | ![Transport Belts](https://wiki.factorio.com/images/Transport_belt.png) ![Fast transport belt](https://wiki.factorio.com/images/Fast_transport_belt.png) ![Express transport belt](https://wiki.factorio.com/images/Express_transport_belt.png) | current tile content<br>**or** one pulse signal per new item
Inserter | ![Burner Inserter](https://wiki.factorio.com/images/Burner_inserter.png) ![Inserter](https://wiki.factorio.com/images/Inserter.png) ![Long handed Inserter](https://wiki.factorio.com/images/Long_handed_inserter.png) ![Fast Inserter](https://wiki.factorio.com/images/Fast_inserter.png) ![Filter Inserter](https://wiki.factorio.com/images/Filter_inserter.png) ![Stack Inserter](https://wiki.factorio.com/images/Stack_inserter.png) ![Stack Filter Inserter](https://wiki.factorio.com/images/Stack_filter_inserter.png) | current hand content
Train Stop | ![Train Stop](https://wiki.factorio.com/images/Train_stop.png) | content of currently stopped train<br>**and** the unique, numeric ID of said train
Rail Signals | ![Rail Signal](https://wiki.factorio.com/images/Rail_signal.png) ![Rail Chain Signal](https://wiki.factorio.com/images/Rail_chain_signal.png) | current state<br>either: red, yellow, green, (blue)
Roboport | ![Roboport](https://wiki.factorio.com/images/Roboport.png) | logistic network content<br>**or** number of busy/existing robots
Calculating Combinators | ![Arithmetic Combinator](https://wiki.factorio.com/images/Arithmetic_combinator.png) ![Decider Combinator](https://wiki.factorio.com/images/Decider_combinator.png) | result of calculation
Constant Combinators | ![Constant Combinator](https://wiki.factorio.com/images/Constant_combinator.png) | configured, static values
Mining Drills | ![Burner Mining Drill](https://wiki.factorio.com/images/Burner_mining_drill.png) ![Electric Mining Drill](https://wiki.factorio.com/images/Electric_mining_drill.png) | resources left under the drill<br>**or** resources left in resource patch
Pumpjack | ![Pump Jack](https://wiki.factorio.com/images/Pumpjack.png) | resources expected from oil well
Accumulator | ![Accumulator](https://wiki.factorio.com/images/Accumulator.png) | level of charge
Gate / Wall | ![Gate](https://wiki.factorio.com/images/Gate.png) ![Wall](https://wiki.factorio.com/images/Wall.png) | indicator whether player is coming<br>(only a wall next to a gate can be connected)

ToDo: Steam Turbine, Nuclear Reactor, Heat Exchanger

## List of Signal Sinks

Item | Icon | Input
:--- | :---: | ---:
Belts | ![Transport Belts](https://wiki.factorio.com/images/Transport_belt.png) ![Fast transport belt](https://wiki.factorio.com/images/Fast_transport_belt.png) ![Express transport belt](https://wiki.factorio.com/images/Express_transport_belt.png) | enable/disable
Inserter | ![Burner Inserter](https://wiki.factorio.com/images/Burner_inserter.png) ![Inserter](https://wiki.factorio.com/images/Inserter.png) ![Long handed Inserter](https://wiki.factorio.com/images/Long_handed_inserter.png) ![Fast Inserter](https://wiki.factorio.com/images/Fast_inserter.png) ![Stack Inserter](https://wiki.factorio.com/images/Stack_inserter.png) | set stack size<br>**and** enable/disable
Filter Inserter | ![Filter Inserter](https://wiki.factorio.com/images/Filter_inserter.png) ![Stack Filter Inserter](https://wiki.factorio.com/images/Stack_filter_inserter.png) | like other inserters<br>**and** set filters
Pumps | ![Pump](https://wiki.factorio.com/images/Pump.png) ![Offshore Pump](https://wiki.factorio.com/images/Offshore_pump.png) | enable/disable
Train Stop | ![Train Stop](https://wiki.factorio.com/images/Train_stop.png) | enable/disable<br>**and** send signal to train
Rail Signal | ![Rail Signal](https://wiki.factorio.com/images/Rail_signal.png) | open/close
Lamp | ![Lamp](https://wiki.factorio.com/images/Lamp.png) | enable/disable<br>**and** color
Calculating Combinators | ![Arithmetic Combinator](https://wiki.factorio.com/images/Arithmetic_combinator.png) ![Decider Combinator](https://wiki.factorio.com/images/Decider_combinator.png) | input for calculations
Power Switch | ![Power Switch](https://wiki.factorio.com/images/Power_switch.png) | enable/disable
Speaker | ![Programmable speaker](https://wiki.factorio.com/images/Programmable_speaker.png) | enable/disable<br>**and** pitch of sound
Mining Drills | ![Burner Mining Drill](https://wiki.factorio.com/images/Burner_mining_drill.png) ![Electric Mining Drill](https://wiki.factorio.com/images/Electric_mining_drill.png) | enable/disable
Pumpjack | ![Pump Jack](https://wiki.factorio.com/images/Pumpjack.png) | enable/disable
Gate / Wall | ![Gate](https://wiki.factorio.com/images/Gate.png) ![Wall](https://wiki.factorio.com/images/Wall.png) | open/close

ToDo: Logistic Chests, Steam Turbine, Nuclear Reactor, Heat Exchanger