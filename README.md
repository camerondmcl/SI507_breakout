# SI 507 Project 4: Breakout

This program runs a game similar to the vintage arcade game 'Breakout'. It is based around code written by Sam Carton and Paul Resnick given to us in lecture to introduce us to Pyglet. It uses one code file (breakout.py) and several .png sprite files,  as well as a requirements.txt to ensure that Pyglet is installed.

The basic framework of the game is largely unchanged from the lecture example, with the mechanics of the movement of the ball and paddle (aside from their velocities) and collisions between objects being essentially the same. I changed it mainly to remove the second player and add the destructible 'Brick' class. The player's goal is to hit the ball into the bricks to destroy them. Initially, my biggest challenge was figuring out how to make multiple instances of Bricks appear in columns and then to make the bricks break on impact. After that, I modified the break_brick function so that it would increase the speed of the ball every 10 bricks (originally I wanted to increase the speed by quite a bit more to make the game more challenging, but I found that the faster the ball got, the more it tended to glitch out and disappear or crash the game).

Once I had that working, I changed the code creating the Bricks so that each row would be a different color, and then spent a long time fussing around with the score text and various functions involved with bricks breaking and the game ending to a) keep track of 'lives' (I was already tracking number of bricks broken), b) display both of those values on the screen, and most difficult of all, c) display text when the player wins (by destroying all bricks) or loses (by running out of their 3 lives).

Finally, I started work on what proved to be the most finnicky feature of all, a method to start a new game without closing and reopening the program through the command line. It took me a long time simply to figure out how to create a new instance of Game(), and longer still to get the new game to run without being stuck in a permanently paused state.

## Game Features & Controls:

* 'w' and 's' move the paddle up and down, respectively; the goal is to hit the ball into the colored bricks and break as many as possible while keeping it from hitting the left wall. Each time it does, a life will be deducted.
* The game keeps track of how many bricks you have broken and how many lives you have left and displays this in the lower lefthand corner. The speed of the ball will gradually increase with every 10 bricks you break.
* If you lose all three of your lives, it's game over. You can start a new game by pressing 'n' and everything will reset.
* If you manage to break all the bricks, you've won! Again, pressing 'n' will start a new game.
* You can also press 'n' and any point while playing to restart the game with all your lives back and all the bricks back in place.
* If at any point you want to reset the ball without completely restarting the game (for instance, if the ball gets glitched and disappears from the screen, which occasionally happens at high speeds), press 'r' and it will reset the ball and paddle to their starting positions without changing the score, lives, or remaining bricks.
* Pressing 'esc' or 'q' at any time will quit the program.
* You can press 'p' at any time to pause the game, and again to unpause.
