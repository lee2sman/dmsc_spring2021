
schedule:
- finish squirrel eat squirrel
- visiting artists: Jonah Senzel and Iwan Traeger-Payne  
- 3d / WebGL
- procedural generation


### Visiting artists

[Jonah Senzel](https://works.rip/)

[Iwan Traeger-Payne](https://www.iwan.tech/)


### 3d / WebGL


Examples I've made:

- [rooms](https://leetusman.com/everyday/47/)
- [rolling computers](https://leetusman.com/everyday/48/)
- [tired text](https://leetusman.com/everyday/46/)
- [oil roller](https://leetusman.com/everyday/50/)
- [rothkubes](https://leetusman.com/everyday/52/)

*examples taken from [Getting Started with WebGL in p5](https://github.com/processing/p5.js/wiki/Getting-started-with-WebGL-in-p5)*

There are 2 rendering systems in p5.js. We have been using the built-in p2d. 

For 3D space, we need WebGL

```
function setup() {
  createCanvas(200, 200, WEBGL);
}
```

### 3d coordinate system

Confusingly, the 3d coordinate system starts 0,0,0 in the center of the screen (not in the top left).

Basic example:

```
function setup() {
  createCanvas(windowWidth, windowHeight, WEBGL);
}

function draw(){
  background(255);
  box();
}
```

### Switching back to the top-left oriented system

> We feel that centering objects by default makes more sense as a starting point for thinking about 3D space, and is especially fast if you want to draw a couple of geometric primitives, but if you prefer to move the origin back to the top left corner similar to 2D mode, simply apply a negative width and height translation:

```
function draw(){
  background(255);
  //moves our drawing origin to the top left corner
  translate(-width/2,-height/2,0); 
  box();
}
```

### Rotation

> A helpful way to remember which function to use for rotation is, “rotate around the ____ axis” Therefore, If we want to do a barrel roll around the X axis, we’d write:

```
rotateX(radians(45));
```

**By default, all rotations take radians**.

This converts 45 degrees to radians (Pi over 4 here), then rotates around the X axis.

### Camera options

> The default camera view in WEBGL mode is perspective with a 60 degree field of view. This is created when you initialize WEBGL mode in createCanvas(). To override the default camera options, simply call perspective() or ortho(). In a perspective view, objects closer to the viewer in the z-plane appear larger than those farther away. In orthographic view (ortho()), objects of the same dimensions appear to be the same size even if they are farther away on the z-plane. For example:

### Primitives in 3d

```
box()
plane()
sphere()
ellipsoid()
cone()
cylinder()
torus() 
```

Each takes 3 optional parameters 

The first two are usually width and height. The third may be depth or optionally the amount of detail (the number of curves).

```
cone(40,100);//draws a cone with radius: 40, height: 100, and a default detail: 24
```

### 2d shapes in 3d

These 2d shapes work in 3d:

```
point()
line()
triangle()
quad()
```

*Note that they need x,y,z coordinates, not just x and y.*

You can also use beginShape() and endShape() to define a custom 2d shape in 3d space.

### Textures

You can wrap 2d images and even video around 3d shapes.

```
let img;
function preload(){
  img = loadImage(“path/to/img.jpg”);
}
function setup(){
  createCanvas(500,500,WEBGL);
}
function draw(){
  background(255);
  texture(img);
  box(45);
}
```

### Text in 3d

Rendering text in 3d WebGL is different than the 2d renderer.


### Lighting

3 modes of lighting:

```
ambientLight(); // nice even (and colored) light
directionalLight(); //like the sun
pointLight(); //like a light bulb
```

#### WebGL in p5.js resources

[Getting Started](https://github.com/processing/p5.js/wiki/Getting-started-with-WebGL-in-p5)


## Homework

Watch Kate Compton [Creating Generative Art with Javascript](https://www.youtube.com/watch?v=tJ49bTJ6fbs). 

Read Algorithms and Approaches by Brian Bucklew, and read Characters and Personalities by Emily Short, both in Procedural Generation in Game Design - these are short! just a few minutes read

Read Chapter 1 of The Lifebox, the Seashell and The Soul - Computation Everywhere - [link](http://www.rudyrucker.com/lifebox/html/#calibre_link-178) by Rudy Rucker - a longer read
- take notes! We are going to discuss this!


## Propose

Your final project is a project that makes use of procedural generation. It can be a procedurally-generated game, story, art toy or other digital media.

It is permitted to include 'hand-crafted' content as well as procedurally-generated content.

The final project should be a compelling work that is complete on its own and produces different meaningful results each time it is run.

Write a proposal for your final project. Includes screenshots of other media that has influenced your thinking, and any thoughts, techniques for building, or questions that you have at this time.
