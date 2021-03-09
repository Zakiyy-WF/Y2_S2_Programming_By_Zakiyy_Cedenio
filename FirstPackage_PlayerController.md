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

This allows you to see the move speed of your player, you and change it in the inspector tab based on the overall scale and theme of your game. 

### Jump Height

