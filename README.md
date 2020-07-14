# voxelShader
Repository for magica voxel shaders.

## Installation

Install the shader by copying the file from the `shader` directory into the `shader` directory of your MagicaVoxel installation. 

## Usage

After installing the shaders (see Installation above) you should see them in the shader menu.

Use them according to the description below and try mixing them up for cool results.

### Overgrowth Shader

This shader lets you create a mossy or leafy plant or foam (you choose the color set) on your voxel art.

![...](readme_img/im6.png?raw=true "Title")

There are 5 parameters right now:

| Parameter | Range | Description |
| ------ | ------ | ------ |
| Max Volume | 0,1,2 |The growth width or thickness of the plants. 3 to 5 looks quite natural. 1 is interesting and higher values might cause MagicaVoxel to crash due to high computational effort. |
| Random Seed | 0 to 1.000.000 |Using the shader on the same scene will always yield the exact same result as long as you don't change this value. Play with this to yield different patterns on the same scene.  |
| Growth Density |0.000 to 1.000| 1 will look like a very thick carpet of plants while lower values will look more natural. |
| Color A | You may color the different layers of your plant in different colors. Color A will be the index of the color of the lowest layer. Just above the dirt.|
| Color B | You may color the different layers of your plant in different colors. Color B will be the index of the color of the highest tip of the plants.|

After setting your values as you like, you need to place some voxels of any colors in range of the `Color A` and `Color B` parameter you have choosen. These are the seeds of your plants. Then hit the play button on the shader a few times to watch them grow step by step.

You can also use this command in the console to execute the shader multiple times:

xs -n 20 overgrowth 4 123.0 0.3 232 226

20 is the number of iterations (e.g. the number of times you would press the play button).
The parameter after overgrowth are the parameter defined above in the same order.

You can also use marquee select with the box select and voxel shader option to apply the shader only to a part of your scene.

#### Issues

I tested the shader with objects of max size 256 x 256 x 256. It can get really slow on this size. Also the `Max Volume` parameter should be kept under 8. I encountered some crashes when using 8 or higher. 

### Corrosion Shader

Caution! This shader will eat your voxels :). Once you place a drop of color (you choose the color set) and run the shader it will dissolve your voxels like acid. 
It's the inverse of the overgrowth shader

![...](readme_img/im7.png?raw=true "Title")

### Patina Shader

This shader will grow a patina on your voxels. It won't create new voxels, just change the color.
It uses the same pattern as the corrosion shader and the overgrowth shader.

![...](readme_img/im8.png?raw=true "Title")

### Plates Shader

This one is very versatile!

There are the current maximum of 8 parametes for you to adjust this shader.

| Parameter | Description |
| ------ | ------ |
| Mode | One of the following. <ul><li>0 - Use shader in 1-layer-a-time mode on vertical surfaces only</li><li>1 - Use the shader in 1-layer-a-time on vertical and horizontal surfaces</li><li>2 - Use the shader to fill the volume of whatever is selected if using BoxMode-Attatch with VoxelShader option</li><li>3 - Attach plates to walls and floors but distort the pattern</li><li>4 - Attach plates to floors only (no walls)</li></ul>   |
| Random Seed | Using the shader on the same scene will always yield the exact same result as long as you don't change this value. Play with this to yield different patterns on the same scene.  |
| Density | Between 0 and 1 | How compact the plates will be. This corresponds to the total number of plates as well. |
| Color A | The index of the first color you want to use for your plates. Colors are distributed randomly between plates.|
| Color B | If different from Color A, it defines the last index of the color range given by all colors between A and B (inclusive). Colors are distributed randomly between plates.|
| xWidth | The thickness of the plates in x direction. |
| yWidth | The thickness of the plates in y direction. |
| zWidth | The thickness of the plates in z direction. |

The last 3 properties, together with the density define the look and outcome of the shader massively. 
Try playing around with them.
Use very high xWidth and yWidth with a zWidth of 1 or change density during iterations to create interesting patterns.

![...](readme_img/im1.png?raw=true "Title")
![...](readme_img/im2.png?raw=true "Title")
![...](readme_img/im3.png?raw=true "Title")
![...](readme_img/im4.png?raw=true "Title")
![...](readme_img/im5.png?raw=true "Title")

### Plaster Shader

A bit like the Plates shader but it draws multiple layers of plates and only on Floors.

![...](readme_img/im9.png?raw=true "Title")

### Coating Shader

Very simple shader. It adds one vertex to the outside of every existing vertex on every wall in the selection.
The color of the coat is always the currently selected color. It simply adds layers to existing vertices.

![...](readme_img/im11.png?raw=true "Title")





### Riffle Shader (Early in development)

This one cuts out vertical (mode 0) or horizontal (mode 1) lines from selected walls.

![...](readme_img/im10.png?raw=true "Title")