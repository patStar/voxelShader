# voxelShader
Repository for magica voxel shaders.

## Installation

Install the shader by copying the file from the `shader` directory into the `shader` directory of your MagicaVoxel installation. 

## Usage

After installing the shader (see Installation above) you should see the overgrowth shader in the shader menu.

There are 5 parameters right now:

| Parameter | Description |
| ------ | ------ |
| Max Volume | The growth width or thickness of the plants. 3 to 5 looks quite natural. 1 is interesting and higher values might cause MagicaVoxel to crash due to high computational effort. |
| Random Seed | Using the shader on the same scene will always yield the exact same result as long as you don't change this value. Play with this to yield different patterns on the same scene.  |
| Growth Density | Between 0 and 1. 1 will look like a very thick carpet of plants while lower values will look more natural. |
| Color A | You may color the different layers of your plant in different colors. Color A will be the index of the color of the lowest layer. Just above the dirt.|
| Color B | You may color the different layers of your plant in different colors. Color B will be the index of the color of the highest tip of the plants.|

After setting your values as you like, you need to place some voxels of any colors in range of the `Color A` and `Color B` parameter you have choosen. These are the seeds of your plants. Then hit the play button on the shader a few times to watch them grow step by step.

You can also use this command in the console to execute the shader multiple times:

xs -n 20 overgrowth 4 123.0 0.3 232 226

20 is the number of iterations (e.g. the number of times you would press the play button).
The parameter after overgrowth are the parameter defined above in the same order.

## Issues

I tested the shader with objects of max size 256 x 256 x 256. It can get really slow on this size. Also the `Max Volume` parameter should be kept under 8. I encountered some crashes when using 8 or higher. 