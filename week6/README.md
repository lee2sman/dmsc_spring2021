# Week 6

* Forces!
* Livecoding workshop with artist Naoto Hieda

### A-life

> New media art self-consciously reworks technology into culture, and rereads technology as culture. What's more, it does so in a concrete, applied way; it manipulates the technology itself, with a nonindustrial latitude that admits misapplication and adaptation, rewiring and hacking, pseudofunctionality and accident. *p.5, Metacreation*

> A-life begins with a notion of life that is wholly materialistic, involving no soul, vital force, or essence. In the words of the convenor of the first artificial life workshop, Christopher Langton, 'Living organisms are nothing more that complex biochemical machines.' Langton contends that rather than being any special substance or force, life is 'a property of the organization of matter.' Further, this organization is not simply a complex structure  but a dynamic structure, a system active in real time: for a-life, life is most importantly manifest in behavior. *p.7, Metacreation*

Tenets of this approach:
  * no central organizer/intelligence
  * bottom-up structure
  * emergence produces lifelike systems
  * as opposed to the study of AI, A-life does not focus on intelligence but on behaviors and is not top-down, procedural

Systems:
  * genetic algorithms
    - separate beings (genotypes) with behaviors (phenotypes)
  * agent-based systems
    - models individuals in an artifical world
  * cellular automata
    - an array of individual cells computed with a set of simple rules governing a cell's future state, as affected by the current state of its neighbor cells

> We are no longer creating a work, we are creating creation...We are able to bring forth...results...which go beyond the intentions of their originators, and this in infinite number. -- Nicholas Schöffer *p.16, Metacreation*

Cybernetic art

Can we make a living cyborg art form?

## Resources / works of Genetics
adapted from [Tega Brain](https://github.com/tegacodes/Drawing-Seeing-Moving-with-Code/blob/gh-pages/docs/lectures/L-06-GeneticExamples.md)

### Cellular Automata
[Steven Hawkings on John Conway's Game of Life:]( https://www.youtube.com/watch?v=CgOcEZinQ2I&feature=share&list=FLwikA_t8e6TSJW-L-lAHkKw)

Conway's Game of Life - [Javascript implementation]( http://pmav.eu/stuff/javascript-game-of-life-v3.1.1/)

 ### Genetic Algorithms
[Karl Sims - Evolved Virtual Creatures](https://www.youtube.com/watch?v=JBgG_VSP7f8)

[Jer Thorp - Smart Rockets](http://www.blprnt.com/smartrockets/)

[Box Car 2D](http://boxcar2d.com/)

# Forces

Goal: Have a number of objects move independently and respond to environmental forces.

A force is a vector that causes an object with mass to accelerate.

### Newton's 3 Laws of Motion

1. An object at rest remains at rest or an object in motion stays in motion at a constant velocity (speed and direction), unless acted upon by a force.
2. Force equals mass times acceleration.
3. For every action there is an equal and opposite reaction. Forces occur in pairs, in equal strength, in opposite directions.

**Mass** - measure of matter in an object, (in kilograms)  
**Weight** - the force of gravity on an object (in newtons)  
**density** - mass per unit (such as grams per centimeter)  

In our sketches, **the acceleration of an object is its force**.

Pseudocode - concept

```
//NOTE: this is PSEUDOCODE to understand a concept!

class Mover {
  constructor(){
    vector location;
    vector velocity;
    vector acceleration;
  }
}
```

```
//PSEUDOCODE
// example applying methods

mover.applyForce(wind);
mover.applyForce(gravity);

....

//example method code inside a mover class

applyForce(vector force) {
  acceleration = force;
}
```

Note: the force really needs to reflect the total of all of the forces acting together: wind, gravity, and anything else. This could change from moment to moment, such as changing wind, so we need to recalculate every draw loop. We can do this by multiplying the acceleration by 0 at the end of a loop.

```
function update() {
    velocity.add(acceleration);
    location.add(velocity);
    acceleration.mult(0);
 }
 ```

Now, let's work in actual Javascript/p5.js.
Let's create a mover, and apply a force to it.

```
//modified from Daniel Shiffman's The Nature of Code

let m;

function setup() {
  createCanvas(640, 360);
  m = new Mover();
}

function draw() {
  background(50);

  //change its x value to move to the right
  let wind = createVector(0.01, 0); 
  m.applyForce(wind);

  m.update(); //change position
  m.display(); //draw to screen
  m.checkEdges(); //did we run off screen?
}
```


Now that we have the basic code mocked out, we need to build the actual Mover class.

```
class Mover {
  constructor() {
    this.mass = 1;
    this.position = createVector(30, 30);
    this.velocity = createVector(0, 0); //starts at 0 until applied
    this.acceleration = createVector(0, 0); //starts at 0 until applied
  }

  applyForce(force) {
    var f = p5.Vector.div(force, this.mass); [derived](//derived) from Newton's Second Law
    this.acceleration.add(f); //add all the forces together (wind, gravity, etc)
  }

  update() {
    this.velocity.add(this.acceleration);  //acceleration is added to velocity
    this.position.add(this.velocity);  //velocity is added to position to get the next position
    this.acceleration.mult(0); //we reset the force to 0 at end
  }

  display() {
    stroke(0);
    strokeWeight(2);
    fill(255, 127);
    ellipse(this.position.x, this.position.y, 48, 48);
  }

  checkEdges() {
    if (this.position.x > width) {
      this.position.x = width;
      this.velocity.x *= -1;
    } else if (this.position.x < 0) {
      this.velocity.x *= -1;
      this.position.x = 0;
    }
    if (this.position.y > height) {
      this.velocity.y *= -1;
      this.position.y = height;
    }
  }

}
```


Our full [code example](https://editor.p5js.org/2sman/sketches/SJ3EZE-9Q).

At this point, we have a single mover.
We can create an array of movers, each with their own starting position, and forces acting on them.

```
//modified from Dan Shiffman Nature of Code
let movers = [];

function setup() {
  createCanvas(640, 360);
  for (let i = 0; i < 20; i++) { //initializing an array of 20 movers
    movers[i] = new Mover(random(0.1, 5), 0, 0);
  }
}

function draw() {
  background(255);

  for (let i = 0; i < movers.length; i++) { //this runs in a loop, so that it affects all movers individually
    let wind = createVector(0.01, 0);
    let gravity = createVector(0, 0.1);
    movers[i].applyForce(wind);
    movers[i].applyForce(gravity);
    movers[i].update();
    movers[i].display();
    movers[i].checkEdges();
  }
}
```


Notice the smaller movers are faster. Acceleration is force divided by mass, so larger masses have smaller accelerations.



An example with mousePressed to create a wind force on 2 movers.

```
// The Nature of Code
let moverA;
let moverB;

function setup() {
  createCanvas(640, 360);
  // A large Mover on the left side of the window
  moverA = new Mover(200, 30, 10);
  // A smaller Mover on the right side of the window
  moverB = new Mover(440, 30, 2);
  createP('Click mouse to apply wind force.');
}

function draw() {
  background(51);

  let gravity = createVector(0, 0.1);

  let gravityA = p5.Vector.mult(gravity, moverA.mass);
  moverA.applyForce(gravityA);

  let gravityB = p5.Vector.mult(gravity, moverB.mass);
  moverB.applyForce(gravityB);

  if (mouseIsPressed) {
    let wind = createVector(0.1, 0);
    moverA.applyForce(wind);
    moverB.applyForce(wind);
  }

  moverA.update();
  moverA.display();
  moverA.checkEdges();

  moverB.update();
  moverB.display();
  moverB.checkEdges();
}
```

[code example](https://editor.p5js.org/2sman/sketches/hEKrAw8rQ)


[array of movers with forces](https://editor.p5js.org/2sman/sketches/g9ewFlXYR) - code example

# Livecoding introduction

# Workshop with Naoto Hieda

[Naoto Hieda](https://naotohieda.com/)

> *Naoto Hieda is an artist from Japan based in Germany, challenging the current paradigm of productive coding to speculate its new form, namely post-coding, through their neurodiverse perspective and live-coding experiences. Currently, Hieda is a fellow of Yoshino Gypsum Art Foundation. Together with Olivia Jack, the duo founded and are organizing Hydra live coding community meetups.*


### Recap

Naoto demonstrated TidalCycles over the web. We used the livecoding hosting environment Estuary for collaborative livecoding in the browser.

[Estuary](https://estuary.mcmaster.ca)

In Estuary, we first selected [Solo Mode](https://estuary.mcmaster.ca/) to practice.

You can alternatively click on "Tutorial" to learn/practice.

**We press Shift-Enter to process/run our code.** If we make a mistake, we see *syntax error* and the previous version of our code is still heard.

We comment out (turn off) our code with ```--``` two hyphens.

We learned with **MiniTidal**.

## Resources

[TidalCycles Functions](https://tidalcycles.org/index.php/Functions)

[TidalCycles Mini notation syntax](https://tidalcycles.org/Mini_notation_syntax)

Recorded Workshop: Babycastles Academy workshop [Intro to Livecoding with TidalCycles](https://www.youtube.com/watch?v=YuEBVxi_6CU) on YouTube, taught by Dan Gorelick, who will be performing [next Friday the 19th online](https://livecode.nyc/event/20210319-COMMONS.html) along with many more performers. In this recording, Dan shows how to install and run the full TidalCycles on your computer instead of the MiniTidal we used in class.


# Homework

## Ecosystem project

* Read section 2.8 on Air/Fluid Resistance
* Can you add mud? water? goo? that will slow down and affect your creature?
* Read section 2.9 on Attraction. This will let us make organisms that move around and follow things, run away from them (or eat them!). Can you add cheese that attracts your mouse? or pheromones that attract a critter? or honey that attracts a bear?
* See examples 2.5 and 2.6 [here](https://github.com/nature-of-code/noc-examples-p5.js/tree/master/chp02_forces) for starter p5.js code adapted from The Nature of Code
* optional: Watch Dan Shiffman's [tutorials](https://www.youtube.com/watch?v=II1A3bBo6gM&list=PLRqwX-V7Uu6ZRrqLcQ5BkBKmBLiGD8n4O) on forces if you'd like a review or alternate instruction model
* Your project should consist of at least one Class. Your environment should have forces. This could be gravity, wind. Add an attraction force. You are welcome to replace your primitive ellipse shape with an image at this point, or wait til the next step. Ideally, you have a metaphor in mind for what you are creating, not just "these circles want to eat these other circles" but a specific system you are trying to build.

## Livecoding Practice

- Pick at least one other student and meet up together to jam together with TidalCycles. Take a screenshot and post. Save any useful code snippets! Add a devlog with some notes (any combination of screenshots, code snippets, and notes on what it's like to livecode music this way).
- *Feeling stuck? Not sure how to get started? Message me to meet up to review*
