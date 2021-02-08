# Week1

- Hello!
- What will we be learning?
- Syllabus and our plans for the semester
- Workshop: Turtle Computing with LOGO
- Writing Log
- HW: Algorithmic Walks and LOGO


# Hello!

- Who is your instructor?
  - [Lee](https://leetusman.com/)
- Who are we?
 - Name you prefer to go by
 - pronouns
 - previous art, music, dance-making experience (etc) and previous coding experience
 - where are you physically in the world?

# What will be learning?

- Introduce subjects and tools

# Syllabus

We have one!

- Get feedback on student interests

# Workshop: Turtle Computing with LOGO


Bits and Bytes episode: LOGO - [Youtube video](https://www.youtube.com/watch?v=pGPu2HSSAco)

Bits and Bytes was the name of two Canadian educational television series that taught the basics of how to use a personal computer. It was aired in 1983.

## LOGO

![LOGO commands with visual output](https://www.annehelmond.nl/wordpress/wp-content/uploads/2007/11/logo_mit.png)  
*example LOGO commands with visual result*  

> Logo is an educational programming language, designed in 1967 by Wally Feurzeig, Seymour Papert, and Cynthia Solomon. A general-purpose language, Logo is widely known for its use of turtle graphics, in which commands for movement and drawing produced line or vector graphics, either on screen or with a small robot termed a turtle. The language was conceived to teach concepts of programming related to Lisp and only later to enable what Papert called "body-syntonic reasoning", where students could understand, predict, and reason about the turtle's motion by imagining what they would do if they were the turtle. There are substantial differences among the many dialects of Logo, and the situation is confused by the regular appearance of turtle graphics programs that are named Logo.

> The first working Logo turtle robot was created in 1969. A display turtle preceded the physical floor turtle. Modern Logo has not changed very much from the basic concepts predating the first turtle. The first turtle was a tethered floor roamer, not radio-controlled or wireless. At BBN Paul Wexelblat developed a turtle named Irving that had touch sensors and could move forwards, backwards, rotate, and ding its bell.

![Turtle robot](http://trelford.com/blog/image.axd?picture=1968_LogoTurtle.jpg)

![Turtle robot with eyes](http://harveycohen.net/oznaki/MIT-Turtle-1974.jpg)

> Logo's most-known feature is the turtle (derived originally from a robot of the same name),[5] an on-screen "cursor" that showed output from commands for movement and small retractable pen, together producing line graphics. It has traditionally been displayed either as a triangle or a turtle icon (though it can be represented by any icon). Turtle graphics were added to the Logo language by Seymour Papert in the late 1960s to support Papert's version of the turtle robot, a simple robot controlled from the user's workstation that is designed to carry out the drawing functions assigned to it using a small retractable pen set into or attached to the robot's body.

> As a practical matter, the use of turtle geometry instead of a more traditional model mimics the actual movement logic of the turtle robot. The turtle moves with commands that are relative to its own position, LEFT 90 means spin left by 90 degrees. Some Logo implementations, particularly those that allow the use of concurrency and multiple turtles, support collision detection and allow the user to redefine the appearance of the turtle cursor, essentially allowing the Logo turtles to function as sprites.


![Logo example on screen](https://upload.wikimedia.org/wikipedia/commons/7/76/IBM_LCSI_Logo_Circles.png)  
*A more complex LOGO program with loops (repeat)*  

-- source: [Wikipedia](https://en.wikipedia.org/wiki/Logo_(programming_language)#Implementations)


- Apple LOGO II on [Internet Archive](https://archive.org/details/Apple_Logo_II)
- note: This will start up an emulator of a classic computer inside your web browser. It will be slow! Hit the power button to start, then wait a minute for it to fully boot up inside the browser. You can fullscreen for the full effect of having it feel like you're running this classic computer.

#### Example commands

```
FORWARD 100

FORWARD RANDOM 100

LEFT 90

REPEAT 10 [LEFT 30 FD 30]
```

### Apple LOGO commands

A short list of commands. There are more you can look up in the bookmarked notes below.

```
CLEARSCREEN - Clear the screen. (Shorthand: CS)
HIDETURTLE - Don't show the turtle cursor. (HT)
SHOWTURTLE - Show the turtle cursor. (ST)
HOME - Move back to the home position.
FORWARD steps - Move forward steps. (FD)
BACK steps - Move back steps. (BK)
LEFT degrees - Turn left this many degrees. Negative degrees work too, they'll turn it right. (LT)
RIGHT degrees - Turn right this many degrees. (RT)
SETHEADING degrees - Turn to an absolute heading of degrees. (SETH)
SETPOS [x y] - Set the position to x, y coordinates. These are Cartesian, so 0,0 is the middle of the screen.
SETX x - Set the horizontal position to x.
SETY y - Set the vertical position to y.
RANDOM n  //returns an integer between 0 and n
PRINT x   //prints out contents of x on console
```

### LOGO for Apple II resources

- Apple LOGO II reference manual - [online book](https://archive.org/details/Apple_Logo_II_Reference_Manual/) on the Internet Archive
- Program in Logo on an Apple II - [PDF](https://cdn-learn.adafruit.com/downloads/pdf/program-logo-on-an-apple-ii.pdf) by Matthew Goodrich

Draw an image. Screenshot it and submit.

## Making a Quilt Patch

In order to create a communal quilt, we need to agree upon dimensions. Let’s use the following procedure, frame, as the base for all of our patches. It creates a black 100 X 100 square.

```
to frame
pd
repeat 4 [fd 100 rt 90]
end
```

Rules: The only rule is that your turtle must return to its original position and heading at the end of the design.

idea source: Gary Stager [Old Fashioned Logo Quilt-Making](https://www.stager.org/quilt/index.html)

## Resources
- General intro to LOGO programming - [link](https://el.media.mit.edu/logo-foundation/what_is_logo/logo_programming.html)
- [Learning With Apple LOGO](https://archive.org/details/Learning_With_Apple_Logo_by_Daniel_Watt_1984) - published 1984

# Homework



### Reading

Please read **pages 11 (starting at Decentralization in Technologies) to page 31 (the end of the section on LEGO/Logo and Artificial Life** of **Turtles, Termites, and Traffic Jams: Explorations in Massively Parallel Microworlds**.  It is available [to read online](http://ezproxy.purchase.edu/login?url=https://search.ebscohost.com/login.aspx?direct=true&db=nlebk&AN=1998&site=ehost-live&scope=site) via our library. Note: scroll to page 11 and then you can click *Google Drive* and it will let you export pages to Google Drive.

### Writing

- Review syllabus
- Get a notebook for class
- Read Zach Lieberman's [Lessons For Students](https://medium.com/@zachlieberman/lessons-for-students-cf1acf200ee), 8 minutes
- Write your first log. What did you work on today? Include screenshots. What are your thoughts on LOGO? What did you try to do? What did you make? Anything you thought of for next steps you want to try?

Assignment 1: A situationist algorithmic walk

Questions:

- What is situationism, its history and influences?
- What can it bring to our current understanding of or experience of computation?
- What is algorithmic thinking?
- How can computational thinking be applied to non-computational environments?
- Can we write software to slow down, focus and enhance our lives outside of productivity, social media, and attention?

Method:

- Write a prompt for an algorithmic situationist walk

1.
Write a program for yourself in a simplified LOGO-like pseudocode for taking a walk. The walk should have at least 20 lines of instruction, and you should plan to walk at least 20 minutes. Rather than millimeters or feet, you may want to use a 'block' (aka one street) unit of measurement of distance, even though this may vary.

Your software must include your own homemade randomness generator. In other words, there must be at least one function to pick a random direction at an intersection. What is your method? (Based on sounds heard? Rolling a dice? Flipping a coin? A passing cloud?)

When you get to the end of your software, record yourself talking about your walk in a voice memo on your phone.

Some things to talk about: What did you see on your route? Did you go somewhere new that you didn't know before? Did it feel different from a normal walk through your neighborhood? How did it feel to use your random function? What kinds of interpretations did you have to perform when things were unclear or would have 'broken'? Anywhere that your algorithm could be improved? You are welcome to add other thoughts as well.

On iOS you can use the Voice Memos app in the Extras folder. For Android, there are many options, such as Easy Voice Recorder on the Play store. Put intention to your recording. Speak clearly and mindfully, and in an environment where you can be heard clearly and without distracting chatter. Listen back to your recording. Write a transcript of what you wrote. (the voice recording is just so the ideas will be fresh!)

2. Give your instructions to another student. And another student will give you their situationist walk algorithm. Try to do their walk! Is it clear what to do? Write about trying their instructions. Did your program (your walk) "break"? Did you "debug"?
