# AudioVisualizer

Basic audio visualizer developed with Unreal Engine 4 and the built in Sound Visualizer plugin using a grid of cubes.

There is an eqController actor which is used to edit the sound being played, the number of cubes to spawn, the distance between the cubes and whether or not to shuffle the cube array used to visualize.

The grid is created and populated using a public variable that can be edited and given a specific number of cubes to create the grid with. There is also an additional variable that can be used to determine the amount of distance between each cube when creating the grid; thus the grid can have overlapping cubes or have them very spread apart. The cubes of the grid are stored in an array for easy access when transforming them for the visualizer.

For every in game second, an array of frequency spectrums are refreshed by the plugin and that is used to update the scale of each cube through a for each loop. The absolute value of the frequency spectrum is then multiplied by a value between 0.1 and 1 as the spectrum could turn out to be negative and when not, it is of extreme values; 0.2 seemed like a good value to normalize with for good looking visualizers. That new value is then used to scale each cube on its Z axis.

When using the grid's cube array as is, the visualizer will look more similar to that of a standard visualizer and a waveform, but if the cube array is shuffled, it will yield more unfamiliar results in that of which may be more interesting.

An emissive material is being used with the cubes in the visualizer.
It basically has two colors and will linearly interporlate between the two given colors depending on a cube's given Z scalar.

A material instance exists where the user can freely change and play around with the two colors they'd like as well as the emissive brightness of the material.

Example Video (Non-Shuffled Cube Array): https://drive.google.com/file/d/1X-ZsfVnBRIVngxKNvNGLA8tDrCIDss1k/view?usp=sharing

Example Video 2 (Shuffled Cube Array):   https://drive.google.com/file/d/18B_Ft2OQfaTIXeoxwxPvtJTTG60C9hcR/view?usp=sharing

There is no packaged build of this project due to it using Unreal's built in plugin which cannot be packaged.
