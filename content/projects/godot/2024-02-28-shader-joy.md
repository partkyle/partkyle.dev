+++
title = 'Shader Joy - Vertical Disolving Effect via Godot Shaders'
date = 2024-02-01T23:23:29-08:00
categories = ['dev']
tags = ['dev', 'gamedev', 'godot', 'shaders', 'graphics']
+++

I decided to experiment with some shaders in godot.

I was able to get something working nice enough that I figured I should write it up.

Here's what it looks like.

![Single Object](/gif/2024-02-28-shader-boy.gif)

It's a simple shader that fades out from the top of the object down. Here is the gdshader code for reference

```glsl
shader_type spatial;

uniform sampler2D noise_texture;

uniform vec3 base_color : source_color = vec3(0.0, 1.0, 0.0);

// The height of the dissolve effect. This can be thought of as a percentage
// of how much is dissolved.
uniform float dissolve_height : hint_range(0.0, 1.0, 0.01) = 1.0;

// How much of the noise should effect the value
uniform float noise_scale: hint_range(0.0, 1.0, 0.1) = 0.1;

// Color the object should Glow.
// This requires that the camera have an environment that supports glowing.
// This color also needs to have a value > 1.0 for whatever color we want to
// glow.
uniform vec3 glow_color : source_color;
uniform float glow_thickness: hint_range(0.0, 1.0) = 0.05;

void fragment() {
	// get a noise value and only use one the r channel
	float noise_at = texture(noise_texture, UV).r * noise_scale;

	// use the UV.y vector inverted so that we dissolve downwards
	// this could be something that was parameterized.
	float y = 1.0 - UV.y;

	// we want to normalize the noise_val so that we get something
	// between 0.0 and 1.0. This can cause some floating point issues
	float noise_val = 0.0;
	if (dissolve_height < 1.0) {
		// Originally I was dividing this by 2.0, but that's before I added in the
		// noise_scale variable.
		noise_val = (y + noise_at) / (1.0 + noise_scale);
	}

	// always set the base_color
	ALBEDO = base_color;

	// fade out the parts of the shape that should be gone
	ALPHA = 1.0 - step(dissolve_height, noise_val);

	// add the glow line based on the glow_thickness using the glow_color
	EMISSION = step(dissolve_height - glow_thickness, noise_val) * glow_color;
}
```

Giving it a bit of a stress tests with 10000 objects all tweening at the same time.

![Single Object](/gif/2024-02-28-see-ya-later-boy.gif)

The performance is not bad as bad as it seems in the gif. I'm averaging about 80 FPS in DEBUG, but I'm stressing out my screen gif recorder. It's probably time to find an alternative that will be more reliable.
