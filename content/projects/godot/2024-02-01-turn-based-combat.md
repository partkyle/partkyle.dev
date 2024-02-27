+++
title = 'Turn Based Combat Experiments'
date = 2024-02-01T23:23:29-08:00
categories = ['dev']
tags = ['dev', 'gamedev', 'godot']
+++


I have been experimenting with turn based combat in the Godot game engine.

At this stage I have a Turn Queue displayed at the top that shows the order of which character is going to be moved. It removes players as they are killed.

There are different attack ranges per weapon type, and there are only 2 weapon types at the moment.

It also supports collisions - the characters cannot walk through water or through each other.

![Image Demo of the Turn Controller](/gif/2024-02-01-turn-queue.gif)