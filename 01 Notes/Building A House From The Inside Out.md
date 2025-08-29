---
title: "Building A House From The Inside Out"
source: "https://www.ayweb.dev/blog/building-a-house-from-the-inside-out"
author:
published:
created: 2025-06-20
description: "Alex Younger Personal Portfolio Homepage"
tags:
  - "clippings"
---
## written by Alex Younger on March 1st, 2022

![Building A House From The Inside Out](https://www.ayweb.dev/images/blogs/building-a-house-from-the-inside-out.jpg)

## Building A House From The Inside Out

## Separating view from data using Connect Four

### Context

For two years, I've been a community member of and contributor to [The Odin Project](https://www.theodinproject.com/), and in my time there I have grown from a help-seeker to primarily a help-provider. TOP's curriculum features many opportunities to build games, from simple ones like Rock Paper Scissors and Tic Tac Toe, to more complex ones such as Chess and Battleship.

As a Javascript developer, much of my learning happened in the browser environment where access to markup and styling is conveniently close at hand. As wonderful as this is for the process of game creation, I have often witnessed the tendency for inexperienced learners to fall into the anti-pattern of interacting with the DOM too freely within their game logic.

Before we begin, I want to emphasize two things:

1. Modern applications are built in various ways depending on scale, scope, requirements, technological restrictions, etc... This article is not intended to teach about application design, nor to provide a one-size-fits-all methodology to building any web app. Its intent is to teach good practices for separating state logic from the UI controls within the context of vanilla JS.
2. This is not a code-along. I will be creating a game as an example of *how* to implement this separation of concerns, but it is not expected for you to build it along with me. However, for further learning, I will include a few practice assignments to help apply the concepts learned here that you can do by forking the Replit.

### Imagine the outside

Pretend for a moment that building a game application is something like building a house. Imagine your dream house, and what it looks like in its final form. You're probably imagining all the elements of a house that are supposed to be seen from the outside and enjoyed aesthetically: the outside of the house, painted to your liking, decorations, the front yard, a charming front door. As you move inside, each room looks like it came straight from HGTV. Brand new appliances, furniture, etc...

But what about the structural elements of the house? Of course we appreciate those things too, but we don't often think about them because their implementation is hidden from our view in the final product. However, behind each wall in our house we can trust there is a sturdy frame. Above the ceiling, and below the floors, we trust there are joists and beams designed to keep the house standing. Underneath the house, we put all our faith in the foundation, which is responsible for holding everything else in place. Behind each exterior element, there is an interior support structure. In the same way, **our application's user interface should be a visual representation of underlying application logic**. In other words, behind everything that makes our game *look* and *feel* nice, there should be solid, foundational code.

### Build from the inside

It's easy to focus on the visual and interactable elements of a project, just like it's easy to imagine how a house will look from the outside when we dream of building one. But just like a builder would first consider the structural design and blueprints of a house before beginning to imagine walls, doors, and windows, let's attempt to think through how our application is going to function at its core before implementing details in the user interface.

A builder would never construct a wall that had no frame to support it. It is not the responsibility of drywall or plaster to support the weight of a house, nor, by itself, provide a sturdy barrier between rooms. Similarly, our DOM elements and queries should not be responsible for storing or handling the implementation details of how our application works. That is not their responsibility, nor what they were designed to do. They shouldn't be concerned with storing details on the state of our game, nor handling the logic our game requires to function correctly. Instead, the DOM should be responsible for ***reading* and *displaying* the application state to the user** and **providing an easy-to-use gateway to interact with the methods it needs to**.

For example, if I am making a game, my UI should have access to a method it needs to use in order to play a round. This method should be simple to call and as restrictive as possible (meaning, it should **not** need to provide a multitude of arguments to do something). Conversely, the DOM probably doesn't need access to a way of changing which player's turn it is. Instead, it should be able to *read* whose turn it is as it changes after every round. This is an important distinction, and one I hope to further illustrate later.

### How about an example?

Okay, sure! I am going to build a simple [Connect Four](https://en.wikipedia.org/wiki/Connect_Four) game. As you read, take some time to understand what the code is doing and try to draw your own conclusions for how to implement what you've learned into your future projects.

My hope is that this article can be useful for learners in many stages of their journey, so I will do my best to provide comments in the code to explain each chunk.

### Foundation and Framing

One great strategy to help keep game logic separate from your UI is to challenge yourself to build the game so that it can be played, in full, in the console. By not needing to rely on a UI, you can be sure that your code has integrity and is not concerning itself with what the browser window is showing. Here is my console-version of Connect Four. Once again, take some time to digest the code and learn what each piece is doing:

[Connect Four - Console Edition](https://replit.com/@40percentzinc/ConnectFourConsole#script.js)

You may notice that I did not implement win conditions. This logic, while important to the core game, was not important in getting the point of this article across. However, it will be part of the optional practice assignments later for you to implement if you choose.

### Now that our house is framed...

It's worth noting at this point that the beauty of decoupled code is that changing the implementation of any of the sub-modules will not require us to rewrite our whole program. Say, for instance, we wanted to create a version where the rows filled from the top-down. All we'd need to change is the `Gameboard.dropToken()` method's details, and the rest of the game would still run as intended.

### Let's put the walls on!

It's now time to add the "view" aspect of our game. Take a moment to understand that the only way the UI should need to interact with the core game code in order to play a round is through the `GameController.playRound()` method. Remember how I said the method to play should be simple to call and as restrictive as possible? This is what I meant. We've constructed our game to have a very limited interface, and in doing so, made it *very* easy to interact with from the "outside."

For the visual representation of the game, I'm going to create one more module called `ScreenController`. This module will leverage an `updateScreen` pattern. The purpose of this pattern is to take some data about our game, such as the state of the game board and which player's turn it is, and update the screen each time a player takes their turn.

For the purpose of simplicity, I am going to make my styles very basic and just have the board show each cell's value (instead of a token color). Also note that I will be removing all previous comments from the console version shown earlier so as to keep the script file shorter.

[Here is the Replit of the game with an HTML/CSS skeleton](https://replit.com/@40percentzinc/ConnectFourWithDOMSkeleton).

Let's take some time to digest our new controller in `script.js`:

#### ScreenController()

The first thing we do here is pull our game module into the screen controller. We no longer need global access to the game object, since our players will be interacting with the game through the DOM, not the console. Next, we create some DOM references to our game board and player turn display. These will be used by our `updateScreen` and `clickHandlerBoard` methods.

#### updateScreen()

This here is the meat and potatoes of our screen controller. Here is what this method does, in order:

1. Clear the DOM of the current board display by simply setting the `.board` div's text content to an empty string.
2. Get the most up-to-date `board` from the game controller.
3. Get the most up-to-date active player from the game controller.
4. Render the player's turn in the `.turn` div.
5. Render each grid square on the DOM
	- I make sure to give each cell a data-attribute of `column` and set that value to the index of the cell in its row, so that when we click them in the future, we already have access to what column that cell is in.
	- The cells are *buttons*, not *divs*. Why? In most cases, *anything clickable should be a button or link*. This enables those with accessability issues to still be able to use our site easily be tabbing and selecting with the keyboard.

The purpose of this method is to refresh our screen whenever a change happens in our game. It will be called whenever the user interacts with the game, like to play a round.

#### clickHandlerBoard()

The click handler, once it verifies that a valid cell was clicked, will get the column data-attribute value, pass that into our game controller's `playRound` method, then run `updateScreen` to refresh the DOM.

And just like that, we have a functional, decoupled, and modularized Connect Four game!

### Conclusion

It should be easy to recognize that once the console version of our game was created, implementing the user interface was incredibly simple. We limited the scope of the DOM's interaction with our game to just 3 methods, and as a result did not need to worry about querying nodes for their text content or anything messy like that. As a result, our code is significantly easier to read, easier to debug, and more performant than the spaghettified, DOM-coupled, alternative.

### Further Learning

If you felt like you learned something from this article, I'd highly encourage you to fork both replits and finish the game:

1. Create win conditions in the console version, and create a way to check if a win condition was met after each round.
	- Don't forget to account for potential ties!
2. Apply those changes to the DOM version
3. Create an intro screen where players can input their names.
4. Create a winner screen and a "play again" function.
5. Style each cell better - instead of a number, try to render an white, red, or blue circle.depending on the state of the cell.
6. Put some paint on that house! Style the rest of the project to your liking.