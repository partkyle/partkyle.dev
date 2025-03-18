+++
title = 'Bellhivers'
date = 2024-04-16T14:11:29-08:00
tags = [ 'godot', 'ludum-dare', 'gamejam', 'demo', 'blockbench' ]
+++

This was a 48 hour gamejam, so it was limited in scope intentionally. It has not been modified since. I do have some notes on ways I would improve this if I was going to continue this idea moving forward.

Ludum Dare was a great experience and it left me with a bunch of feedback from users that played my game. I think it improved my skills considerably, as this was my first real attempt doing my own 3D modeling.

## Demo

{{< youtube yhj2D5uuFYE >}}

## Links

- [GitHub](https://github.com/partkyle/bellhivers)
- [itch.io](https://partkyle.itch.io/bellhivers)

## Afterthoughts

There are some performance issues while playing on a browser that aren't easily noticed when playing on a high powered gaming PC. In future gamejams I plan on focusing more on this, becuase I think more users will be willing to play a game if it runs in a browser.

This uses shaders and particle effects for some really simple visuals (i.e. the beams and the muzzle flash). I think these are computationally inefficient. In addition, they don't seem to work well in the browser deployment.

## Lessons Learned

- Having an options panel for basic settings would go a long way (i.e. volume, disabling particle effects).
- Test the product in the desired deployment method before the last hour of the gamejam.

## Tools

- Godot 4.2
- GDScript
- blockbench - 3d models
- bfxr - sound effects
