+++
title = 'Fight or Flea'
date = 2024-10-06T14:11:29-08:00
tags = [ 'godot', 'ludum-dare' , 'gamejam', 'demo']
+++

Ludum Dare 56 Entry.

Fight or Flea is a simple game gameplay is based off of the Monster Hunter mounting system.

This is very much a programmer art project. My focus was on input management and feedback as well as game lifecycle.

![cover](/png/2024-10-06-fight-or-flea-cover.png)


## Links

- [GitHub Repo](https://github.com/partkyle/fight-or-flea)
- [itch.io](https://partkyle.itch.io/fight-or-flea)

## Input Systems

I also experimented with multiple systems to handle input. Typically, I would try to keep all of the input logic in a single place, in a Player class for example. This was an attempt in lowering the complexity of these classes, and in that sense it was successful. This forced me to be careful with how I trigger spawning in the different phases of the game, as multiple instances of the mounting class would result in very strage game behavior.

I will be continuing to search for the best way to handle this sort of state mamangement in Godot.

## Multiple Input Types

I added in controller as well as keyboard and mouse support. Since I based this gameplay off of Monster Hunter, I wanted to capture the feel of the game that I was familiar with.

You'll note that the input feedback will change based on whether the last input came from a controller or a keyboard and mouse. This was a nice touch I added to make sure the 

## Input Feedback

In the top right corner, you'll notice that there's and input feedback that describes the input.

![input example](/png/2024-10-06-fight-or-flea-input.png)

This is coming from my experience working with games like [bellhivers](/portfolio/bellhivers), where I had to include a text description of how to play the game. I wanted the game to be more discoverable and not require a reading a tutorial to play. I think I succeeded in improving at that task, but I still have some way to go.

## Afterthoughts

I think just a few hours thrown into making the visuals better would go a long way. The game is also lacking some impact, so some shaders and sound effects would make it feel more complete.

There is a lot of work involved in even a simple game. 48 hours is not much time to add the polish that makes a game feel good to play.

## Tools

- Godot 4.2
- GDScript
- Aseprite
