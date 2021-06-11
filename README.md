# Retro-Shooters
Retro Shooters is a fixed shooter game in which the player is in a spaceship and the space ship has a missile shooter. The player can move horizontally across the bottom of the screen and fires at aliens overhead. The aliens begin as four rows of six that moves left and right as a group, shifting downward each time it reaches a screen edge. The goal is to eliminate all of the aliens by shooting them. The aliens attempt to destroy the player's spaceship by firing bombs. The game ends immediately if the invaders reach the bottom of the screen or the spaceship gets hit by one of the aliens bomb.

<b>Design</b><br>
This game has following features:<br>
• Accelerated Mode Graphics<br>
• Simple game loops<br>
• Keyboard Input<br>
• Brute force collision detection<br>
<br>
Our game is divided into seven java classes:<br>
• Game.java<br>
• SpriteStore.java<br>
• Sprite.java<br>
• Entity.java<br>
• ShipEntity.java<br>
• ShotEntity.java<br>
• AlienEntity.java<br>

Algorithm
<pre>
1.) Start function:
    function SpaceInvaders :
    store welcome message in a variable
    add start-mission buttons to the home screen
    add help button to the home screen
    add welcome message to the home screen
    choosing the fonts of the home screen
    arranging the frames of the game app
    end of function
2.) Initialization of the gaming board:
    function actionPerformed:
    (Will be called on pressing the start-mission button)
    set the frame size of the board
    add the board class to the frame
3.) Setting the colors of the game:
    function paint:
    setting the colour of the board to black
    filling the board with black colour
    setting the colour to green
    if( /*condition*/){
    draw the aliens, players, shots and bombs
    }
4.) Spaceship left-right movement using left-right key:
    Function keyPressed:
    gets the key code of the pressed key
    if(key == left){
    decrement the spaceship x-position by 2
    }
    if(key == right){
    increment the spaceship x-position by 2
    }
5.) When left-right key is released:
    function keyReleased:
    gets the key code of the released key after pressing
    if(left || right){
    x-position will remain same
    }
6.) Shooting missile when we press space-bar:
    function keyPressed:
    calls above functions to check which key is pressed
    gets current position of the player in the frame
    if(/*inside the game*/){
    gets the keycode of the key press
    if(/* key pressed is space*/){
    create a new class of shot
    }
    }
7.) Check if aliens and the missile are in contact:
    For(every alien){
    Get the x-coordinate of the alien
    Reverse the alien direction if they have reached the board side ends
    If side ends reached, increase the y-coordinate to make them closer to ground
    For(every alien){
    Get the y coordinate of the alien
    Check if the y coordinate touches the ground, GAME OVER
    }
    }
8.) Aliens throwing bombs:
    Random class will pick a number b/w 0 and 15
    If number picked is equal to chance bomb will be created for the alien, if it hasn’t been destroyed yet
    Set the bomb construct and set its x and y co-ordinates
    Check coordinates of the bomb and spaceship
    if (player still alive and bomb still not destroyed){
    check if bomb and player are in range
    if(player in range){
    destroy bomb and the player
    }
    If(y-coordinates of bomb > ground){
    destroy bomb
    }
    }
9.) Spaceship shooting missiles at alien:
    if (spaceship released the missile){
    get the x and y coordinates of the missile
    for(every alien){
    get the x and y coordinates of the alien
    if (missile and alien both alive){
    change the missile icon to explosion image
    kill the alien
    increase the death count
    destroy the missile
    }
    }
    }
    To show missile going in upward direction decrease its y coordinate after every interval
    if the missile gets out of the frame without getting then destroy the missile
10.) function run:
     get the current time with respect to when game start
     while(game running){
     repainting the board every second to animation
     a.) Function repaint:
     repainting the board every second to animation
     b.) Function animation:
     Changes coordinates which makes the elements look like they are moving
     Calculate how much time it took in animation cycle
     tried to maintain the animation rate at 17ms/frame
     if ingame is false then we come out and execute gameOver function
     }
11.) function gameOver:
     set graphics class for gameover
     filling the frame with the given width
     get the color of graphics
     fill a box with the given color
     set the text color and font to white for that box
     write the appropriate message on the text box
</pre>
<b>Program Screenshots</b><br>
<br />*Welcome Screen<br>
![Screenshot (1522)](https://user-images.githubusercontent.com/64474195/120179647-7b6aa880-c228-11eb-83ea-ed9dcaec29b9.png)

<br />*Spaceship shooting missile and aliens are throwing bombs<br>
![Spaceship shooting and](https://user-images.githubusercontent.com/64474195/121633865-3acd2380-caa1-11eb-87c5-81a0f6eb4e94.jpg)<br>
<br />*An alien died because of the missile<br>
![An alien died because of missile](https://user-images.githubusercontent.com/64474195/121633873-3f91d780-caa1-11eb-83de-4485ab345948.jpg)<br>
<br />*Alien’s bomb about to hit the spaceship<br>
![aliens bomb about to hit ](https://user-images.githubusercontent.com/64474195/121633876-415b9b00-caa1-11eb-896d-5511903e9296.jpg)<br>
<br />*Player’s spaceship gets destroyed due to the bomb and spaceship contact<br>
![players ship gets destroyed](https://user-images.githubusercontent.com/64474195/121633884-43255e80-caa1-11eb-8425-98a478bcb0e3.jpg)<br>
<br />*Game Lost Screen<br>
![img2](https://user-images.githubusercontent.com/64474195/120179633-79084e80-c228-11eb-82f7-ea5d10c3db2e.jpg)<br>
<br />*Game Won Screen<br>
![img3](https://user-images.githubusercontent.com/64474195/120179644-7ad21200-c228-11eb-8915-2582666d7c2a.jpg)

