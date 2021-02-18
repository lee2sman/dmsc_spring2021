week 3

# Automatons and Self-Drawing Machines

### Today

- warmup: loops
- Harold Cohen and AARON
- Automatons
- p5.js - arrays and classes

### Harold Cohen and AARON

Harold Cohen - The Age of Intelligent Machines - 1987 (Clip) - [video](https://www.youtube.com/watch?v=IPczQgCuOOc)  - 2 minutes

Harold Cohen - Collaborations with my Other Self - 2011 (Interview) - [video](https://www.youtube.com/watch?v=MwHQx9BrHQc) - 5 minutes

### Automatons

The Draughtsman-Writer, circa 1800 - [video](https://www.youtube.com/watch?v=7ZiH7oF3OMM)

Maillardet's Autommaton [page](https://www.fi.edu/history-resources/automaton) on The Franklin Institute

### Objects and Arrays of Objects

## What is a class?

In a programming language, a *class* is a defined code template that is used to create objects. Objects can have default *instance variables* and methods (functions). We say that classes *encapsulate* objects.

- They store functions and variables together
- A class is a template - a *cookie-cutter*
- They are used to *stamp out* individual Objects
- When we stamp out or create an object using the Class/cookie cutter we are said to be *instantiating* an object. Each object is an *instance* of the class.

Here is an entire example that shows how to declare and instantiate an object in your program.

**Note: This does not include the Bubble class code.**

```
var bubbles = [];

function setup() {
    createCanvas(480, 270);
    stroke(0);
    fill(0,0,255);  
    for(var i = 0; i<3; i++){ //fill our array with new Bubble objects
      bubbles[i]= new Bubble(random(width),random(height));
    }
}

function draw() {
    background(255,0,0);
    for(var i = 0; i<bubbles.length; i++){
      bubbles[i].display(); //call the function display from the bubble OBJECT
      bubbles[i].move(); // call the function move from the bubble object.
    }
}
```


## Writing a class

- At the top of the class is a constructor function
- The constructor is kind of like an object's *setup* in that it provides the initial values for any passed variables and it creates new variables that may be used in class
- ```this``` is a special keyword in javascript.
- Each time you use the class to create a new object instance, it will have its own variables and functions assigned to it
- If I have a class *People* and a variable *name* it's important that my *Billy* object has the name *Billy* and if I also make a *Sally* object it has its name variable be *Sally* and not Billy. (Sorry for this metaphor)
- We use ```this``` in front of the variables because each stamped out object will need to reference its own version of that variable
- Note that functions inside of classes are called methods. You don't need to include the word ```function``` in front of them since they are understood as functions without it.
- ```new``` is the instruction to create an object
- it creates an object *instance*

## An Example Class

[Example Code here](https://editor.p5js.org/2sman/sketches/SJ5DGeIOQ)

```
let wolfgang, clara;

class Person {
	constructor(name,x,y) {
		this.name = name; //takes the passed name and sets the local name variable
		this.x = x //takes the passed x value
		this.y = y //takes the passed y
		this.message = "Hi "+this.name;
	}

  drawName(){
	   text(this.message,this.x,this.y);
   }
}

function setup(){
  createCanvas(500,500);
	wolfgang = new Person("Wolfgang",100,200);
	clara = new Person("Clara",200,350);
}

function draw(){
	wolfgang.drawName;
	clara.drawName;
}
```

## Default arguments

* Default arguments are optional
* You can include default values for the variables connected to each object
* You can specify in the constructor like this: ```constructor(x = 100, y = 300)```

## Resources

* Examples of classes in objects can be found in The Coding Train [videos 5.4, 6.3, 6.4, 6.5.](https://www.youtube.com/playlist?list=PLRqwX-V7Uu6Zy51Q-x9tMWIv9cueOFTFA)
* Mozilla's Classes [reference](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Classes) page
* Classes [example](https://googlechrome.github.io/samples/classes-es6/) by Google Chrome team.
  * [More](https://github.com/GoogleChrome/samples) Google Chrome ES6 examples

# Homework

* Write an object using a constructor function that draws a creature of your imagining.
* Read through I.1-I.3 in the introduction of [Nature of Code](http://natureofcode.com/), but remembering that we will be writing our code in javascript and not Processing. This means that when you read the term 'class', think of way of writing objects with the constructor function. Contain the code that draws your creature within a function called display(). Work through exercise I.1, creating a random walker class in p5js by adding in a step function to your object code. Also do exercise I.2 and I.3. Note that the functions such as random, noise are the same in both processing and p5js. Create your own version of the random walker.
  * [The Nature of Code, Introduction](https://natureofcode.com/book/introduction/), online
  * You may want to watch The Nature of Code Introduction [videos](https://www.youtube.com/watch?v=6vX8wT1G798&index=1&list=PLRqwX-V7Uu6aFlwukCmDf0-1-uSR7mklK), the videos are on Processing, but are still helpful
* The book's example code has been [ported to p5js](https://github.com/shiffman/The-Nature-of-Code-Examples-p5.js) and can be [downloaded](https://github.com/shiffman/The-Nature-of-Code-Examples-p5.js/archive/master.zip). You will have to run the code locally.


