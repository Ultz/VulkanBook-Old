# A world of triangles
If you've used a game engine before, you've probably just been able to drag your model files from whatever modelling program you were using and seamlessly drop them into your engine editor, and it just work. In the world of Vulkan, everything is different. Everything you see running on those game engines are actually rendered as lots of tiny triangles, and unfortunately we have the job of forming those triangles in a way the GPU understands.

## Vulkan's coordinate system
As you hopefully remember from last chapter, Vulkan works a little differently in that it uses a "right hand" 3D space (by default). This means that:
- The X axis ranges from -1 to 1, -1 being the left edge of the screen and 1 being the right edge of the screen
- The Y axis ranges from -1 to 1, -1 being the bottom edge of the screen and 1 being the top edge of the screen.
- The Z axis ranges from 0 to 1 (by default), 0 being closest to the screen/camera and 1 being furthest away.

These 3D coordinates are orthographically projected onto your 2D screen as part of the rending process.

## Primitive Topologies
As described earlier, all objects you see on screen are built of many triangles. This is because three-point polygons (i.e. triangles) are always planar (meaning flat), making the rasterization process a lot less complex. However, because everything is made up of triangles, how do you define how the many triangles that go into a 3D model are laid out and drawn? There are three main ways:

### Triangle Strips
A triangle strip consists of lots of connected triangle primitives <TODO continue>