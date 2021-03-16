# Player Controller

This document explains the inner workings of my player controller package as well as a short description of the example scene. 

## Behaviours
- [`GenericPlayerController`]

## GenericPlayerControlller

This script should be applied to the main player of your scene, it will allow your player to move forward, backward, left and right in respect to the Unity world and not the position of your camera, make sure you have positioned your camera south of your player for the best results.
The script also have the following configurable parameters:

- Speed
- Jump Height
- is Grounded

### Speed

This allows you to see the move speed of your player, you and change it in the inspector tab based on the overall scale and theme of your game. The player game object will require a RigidBody for this as the movement relies on physics and velocity.

### Jump Height

This function lets your player jump a certain amount into the air using force propelled in the Y axis, you can adjust this setting in the inspector tab and change how much forced is added. This requires the aforementioned RigidBody to work as the jump relies on unity physics. This is tied to the Spacebar by default.

### is Grounded

Is Grounded is a function that stops the player from jumping if they are not on the ground once the jump button is pressed this works only if you name all the platforms and area’s the player will walk on “Ground”.
