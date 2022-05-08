# Non Physically Based Rendering in the Unreal Engine 4

![Image_1](https://github.com/kieranbow/GEA_Unreal_Project/blob/master/Images/HighresScreenshot00014.png)
![Image_2](https://github.com/kieranbow/GEA_Unreal_Project/blob/master/Images/HighresScreenshot00012.png)
![Image_3](https://github.com/kieranbow/GEA_Unreal_Project/blob/master/Images/HighresScreenshot00015.png)

## Introduction
This project was developed for the Game Engine Architecture module in my second year of university at the University of West England (UWE).
The task for the module was to create a system in mulitple game engines. The task that I chose to develop was called "Sketch" where the task was to create many different 
Non Physically Based effects using shaders and to combine them together to create similar effects like in Spiderman Into the Spider-verse. 

The systems were developed mainly in Unreal Engine 4 and Unity and some experimenting was done in Panda3D. This repository only reflects the Unreal Engine version of the project since this is the most feature complete.

## Examples
Here are some examples of the shaders developed for the module.

### Surface Shaders
#### Toon Shader
![Toon Shader](https://github.com/kieranbow/GEA_Unreal_Project/blob/master/Images/ToonShader.gif)  
This is a simple toon shader that modifies the Lambert-Cosine Law to create a shadow stepping effect on the object's surface.  
`float nDotL = saturate(floor(dot(lightDir, normal) * step_count) / step_count)`

#### Gradient Toon Shader
![Gradient Shader](https://github.com/kieranbow/GEA_Unreal_Project/blob/master/Images/gradient.gif)  
This shader uses the same modified Lambert-Cosine Law but this time uses it to map a colour gradient onto it.

#### Halftone Shader Version 1
![Halftone Shader V1](https://github.com/kieranbow/GEA_Unreal_Project/blob/master/Images/halftoneV1.gif)  
This was a first attempt at trying to re-create a halftone effect. The shader is a heavly modified verison of the toon shader and allows for custom halftone patterns.

#### Halftone Shader Version 2
![Halftone Shader V2](https://github.com/kieranbow/GEA_Unreal_Project/blob/master/Images/halftoneV2.gif)  
This is the second version of the halftone effect. This time the effect is created by using fwidth.

### Post-Processing
#### GreenScreen
![Greenscreen](https://github.com/kieranbow/GEA_Unreal_Project/blob/master/Images/PP_greenscreen.png) 
A simple post-processing shader that uses Unreal's stencil buffers to mask out the background and replace it with a green screen

#### Pixelization
![Pixel](https://github.com/kieranbow/GEA_Unreal_Project/blob/master/Images/PP_pixel.png)  
This shader modifies the screen's uv in a way that it creates small uv squares which a pixel is mapped onto creating the pixalated look. The beveled effect is done by mapping a texture onto the modified uv.

#### Brush strokes
![Brush](https://github.com/kieranbow/GEA_Unreal_Project/blob/master/Images/PP_brushStroke.png)  
This shader uses a normal map of a brush stroke texture and projects the texture onto the world space axis (x,y,z). The x and y axis of the normal map is then used to modify the screens uv to distort it and create the brush stroke effect.

#### Outline
![Outline](https://github.com/kieranbow/GEA_Unreal_Project/blob/master/Images/PP_outline.png)  
Uses a 3x3 kernal to find edges in an image and creates an outline effect.

#### Posterization
![Poster](https://github.com/kieranbow/GEA_Unreal_Project/blob/master/Images/PP_poster.png)  
Similar to the gradient surface shader. This converts what the camera renders into a grayscale image and then maps a gradient ontop of it.
