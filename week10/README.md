week 10

today:
- sprite animation
- coding challenge: squirrel eat squirrel

### Sprite animation

New code technique:

In the latest version of Javascript (Ecmascript 2015), we have an ability to loop through items in an array in a clearer manner, using for...of. This lets us loop through the values of an iterable object.

Instead of:

```
for (let i = 0; i < horses.length; i++){

  //do something to each of the horses
  
  horses[i].display();
}
```

Now we can loop through with *for...of*

```
for (horse of horses){
  
  //do something to each of the horses
  
  horses[horse].display();
}
```

Note that you could still use i instead of the word horse, but the full word may help explain what's happening better in the code.

[More info](https://www.w3schools.com/jsref/jsref_forof.asp) on for..of

- [code](https://editor.p5js.org/2sman/sketches/1b-OxDxrL)

### Open Game Art

- [link](https://opengameart.org/)

### Coding Challenge: Squirrel Eat Squirrel

> Squirrel Eat Squirrel is loosely based on the game *Katamari Damacy*. The player controls a small squirrel that must hop around the screen eating smaller squirrels and avoiding larger squirrels. Each time the player’s squirrel eats a squirrel that is smaller than it, it grows larger. If the player’s squirrel gets hit by a larger squirrel larger than it, it loses a life point. The player wins when the squirrel becomes a monstrously large squirrel called the Omega Squirrel. The player loses if their squirrel gets hit three times.

[video demo](https://www.youtube.com/watch?v=xB1sLRfcWj4)

Basic Requirements:

- [ ] game works in fullscreen mode
- [ ] a player's squirrel. controlled by up, down, left, right arrow
- [ ] Procedurally generated 'squirrels' and grass (grass is for decoration)
- [ ] three classes: Player, EnemySquirrel, Grass (or equivalent)
- [ ] when any enemy squirrel collides with another squirrel, the big one eats the smaller one and grows bigger
- [ ] if the player hits a larger squirrel, lose a life point and grow smaller.
- [ ] if player hits a larger squirrel three times, game over

Advanced:

- [ ] balance the variables so the game gets to a compelling level of difficulty (the 'goldilocks' amount)
- [ ] animation of the squirrels via a spritesheet
- [ ] have camera follow squirrel
- [ ] better 'walking' pattern. hop? perlin noise?
- [ ] eating sounds
- [ ] procedurally generated flowers
- [ ] what else?

DOUBLE BONUS POINTS:
- [ ] self-playing version ('player' moves itself without player)

Next week:

- class visit by alums: Iwan Traeger-Payne and Jonah Senzel
- 3d!

### Homework

Finish Squirrel eat Squirrel! All students should create a devlog explaining their process, choices made, what was difficult, and describing their final version. Include screenshots. Fulfill all of basic requirements and at least 3 in advanced. This is a collaborative effort, but each student should submit their own work and link to final project. **Note: Your devlog post should include a link to your game in full screen mode as well as a link to your code**

Practice hydra. Get to a pattern you are happy with (at least one) and save it. **Post a link to your code URL on our #hydra channel on Discord as well as to the homework on Moodle**

We will do an in-class algorave on Thursday May 6 at 5pm!
