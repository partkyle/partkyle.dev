+++
title = 'Ludum Dare 55 - Bellhivers'
date = 2024-04-16T12:11:29-08:00
categories = ['dev']
tags = ['dev', 'gamedev', 'godot', 'ludum-dare']
+++

I have tried to participate in Ludum Dare several times, but I have always either given up or skipped it due to not liking the theme. There was one year where I did technically "complete" a "game", but the assets were terrible and I wasn’t very proud of it.

{{< youtube yhj2D5uuFYE >}}

At first I didn’t really like the theme and wasn’t sure I’d even attempt it, but somehow I ended up coming up with something that I felt satisfied the theme enough and was interesting enough for me to work on.

This was a much more ambitious project than any other attempt. I decided to do mine in 3d, and I have only started doing any sort of 3d modeling earlier this week. I used blockbench, which is a really simple modeling tool. It was pretty approachable for someone who has never used it before. I watched a single tutorial on youtube and then I was able to figure out what I needed to do by just using what I understood about meshes and UVs.

This was also my first attempt at creating a first person camera and a shooter. I was able to figure most of the math out myself using the Godot Basis class.

I’m glad I persevered and actually finished it. I learned a lot about the Godot engine and had a great time. The first time I had the enemy meshes explode I was ecstatic. I was shocked that something so simple looked good enough for me to keep it in the final version.

The code is up on [github](https://github.com/partkyle/bellhivers). It's not the best code I've written. There are few classes that are too large and should be broken out (i.e. Player). The UI code and structure leaves a lot to be desired. And I really wish I had put in a volume slider.

I also wish I would have tested it more with the HTML player version since that's the most likely way to get people to try the game out for the challenge itself. I have some lagging issues due to poor scene loading strategies. I was taking advantage of my PCs hardware, and that proved to be a mistake.

All in all, it was a great experience, and while there is a lot I could have done better I am proud of it. It's a 48-hour challenge after all, so I can't expect it to have everything a finished product would have.

I may go back and do some refactoring and introduce some object pooling to see if that resolves some of the issues.

This was a truly rewarding and worthwhile use of my time.

![bellhivers scene](/png/2024-04-16-bellhivers.png)