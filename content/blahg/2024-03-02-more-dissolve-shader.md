+++
title = 'More work with the dissolve shader'
date = 2024-03-01T23:11:29-08:00
categories = ['dev']
tags = ['dev', 'gamedev', 'godot', 'shaders', 'graphics']
+++

I noticed that the shader was not showing shadows properly and also there were alpha issues with any meshes that had occluded faces. This is due to modifying the ALPHA value in the shader.

![example](/png/2024-03-02-toroid-issue.png)


I was able to resolve it by enabling a render setting for godot shaders called depth_prepass_alpha.

```glsl
shader_type spatial;
// This is needed for toroids and other objects with faces behind other faces.
// It also allows for shadows on meshes with this shader.
render_mode depth_prepass_alpha;
```

This fixes both the shadows and the face rendering issues for meshes with occluded portions.


### Updating Dissolve Height to work relative to the model

I noticed another issue with shapes that weren't capsules. Since the height was based on the UV values, depending on the mesh and how the UV was mapped, models would dissolve unexpectedly.

![rendering using uv](/png/2024-03-02-uv.png)

I resolved this using a vertex shader to use the Y value of the vertex and passed that to the fragment shader.


### Time Scale

I also added a time_scale value that will make the noise more active, and I have that defaulted to 0.0 so it will not take effect unless you change it.

![Single Object](/gif/2024-03-02-time-scale.gif)
