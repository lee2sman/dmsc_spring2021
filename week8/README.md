Week 8

Today:
- class feedback
- warm-up play with simulations
- discussion: simulations by Max Bittker and hardmaru
- particle systems
- coding time: ongoing time to work on ecosystem project plus 1-on-1s

## Warm-up

#### Simulations

[Otoro](https://otoro.net/) 

[Planks](https://otoro.net/planks/) 
- by @hardmaru

### Videos

[![Hexapod](../images/hexapod.jpg)](https://www.youtube.com/watch?v=z2j69eI9ob8)  
*Hexapod (land jellyfish) by Zenta*

[![Soft Jellyfish Robot](../images/jellyfish-robot.jpg)](https://www.youtube.com/watch?v=Aaugq16rCAw)  
*Soft robot jellyfish by Jennifer Frame + team*

# Particle Systems

* p5js [example code](https://github.com/shiffman/The-Nature-of-Code-Examples-p5.js/tree/master/chp04_systems) from The Nature of Code
* Daniel Shiffman particle system [tutorial videos](https://www.youtube.com/watch?v=vdgiqMkFygc&list=PLRqwX-V7Uu6Z9hI4mSgx2FlE5w8zvjmEy)

> “A particle system is a collection of many many minute particles that together represent a fuzzy object. Over a period of time, particles are generated into a system, move and change from within the system, and die from the system.” —William Reeves, "Particle Systems—A Technique for Modeling a Class of Fuzzy Objects," ACM Transactions on Graphics 2:2 (April 1983)

* used to model irregular types of natural phenomena such as fire, smoke, waterfalls, fog, grass, bubbles, etc.

#### Why use particle systems

* for tracking many things
* as opposed to an array, a particle system allows for flexibility in size - it can increase, decrease elements, or shrink to 0
* particles are independent. They can be created or die separate from the rest of the flock.

## A single particle

**A single particle object is just another name for our *mover*. A particle has a positon, velocity and acceleration.**

We can start with the basics of the mover class we made earlier. Now we'll add one more method to the class called lifespan().

Our particle system will also have a *emitter*, which creates the initial settings for the number of particles, location, velocity, etc.

The emitter will create particles, give them a lifespan, and continue to create particles throughout the run of our program.

In our first example we'll start the lifespan at 255 and count down to 0. This value will also count as the alpha channel, so the particle is getting more transparent, and when it reaches 0 it will be dead. We have a method to check whether the individual particle is alive or dead.

We have a run method that runs display and update (move). The particle has an initial velocity and downward acceleration (simulating gravity).

[A single particle](https://editor.p5js.org/2sman/sketches/S1_Ej-7iX)

<iframe src="https://editor.p5js.org/embed/S1_Ej-7iX"></iframe>

Last week we covered ways to expand and splice arrays of objects/particles in Javascript.

In the example code there is a for each statement.
> "For each Particle p in particles, run that Particle p!

[Array of Particles](https://editor.p5js.org/2sman/sketches/B1U0Y-XoQ) code

<iframe src="https://editor.p5js.org/embed/B1U0Y-XoQ"></iframe>

# An array of particle systems

[code](https://editor.p5js.org/2sman/sketches/By7SNe4j7)

**Implications: Building a system of creatures in our ecosystems. Using particle system and lifespan ideas, can you implement birth, lifespan (possibly tying it to a resource like food), death, a emitter that creates creatures if they are  spawned from a particular location, polymorphism and inheritance to create a variety of creatures...**


# Cellular Automota and Conway's Game of Life

* Steve Wolfram - A New Kind of Science

![Textile Cone Snail](../images/textile-snail.jpg)
*Textile Cone Snail*  

> The game is a zero-player game, meaning that its evolution is determined by its initial state, requiring no further input. One interacts with the Game of Life by creating an initial configuration and observing how it evolves, or, for advanced players, by creating patterns with particular properties. The Game of Life, also known simply as Life, is a cellular automaton devised by the British mathematician John Horton Conway in 1970

*[Wikipedia](https://en.wikipedia.org/wiki/Conway%27s_Game_of_Life)*

[Conway's Game of Life - p5js code](https://editor.p5js.org/2sman/sketches/HJjNlb7jm)


# Homework

### Read/study
- Read [Artificial Life and Conway's Game of Life Part 1](http://makeyourownalgorithmicart.blogspot.com/2018/05/artificial-life-and-conways-game-of-life.html) - about 10 minutes
- Read [How Do Simple Programs Behave](http://www.wolframscience.com/nks/p23--how-do-simple-programs-behave/) by Steven Wolfram - about 20 minutes
- Review Chapter 4 in Nature of Code on Particle Systems
- P5js examples are in [here.](https://github.com/shiffman/The-Nature-of-Code-Examples-p5.js/tree/master/chp04_systems)
- Daniel Shiffman [tutorials](https://www.youtube.com/watch?v=vdgiqMkFygc&list=PLRqwX-V7Uu6Z9hI4mSgx2FlE5w8zvjmEy)

### Code
- Complete a working implementation of your ongoing ecosystem project. Like some of the projects by Hardmaru and Max Bittker that we played with, your ecosystem simulation should consist of entities with their own visual identity, not primitives (cirles and rects). We will present and play with these next week.
