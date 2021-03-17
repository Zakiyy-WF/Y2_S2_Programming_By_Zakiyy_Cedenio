# Camera Follow Guide

This document explains what the behaviours in this package does and the requirements needed to work effectively, this will explain how to use this package to create a camera follow function used in a lot of adventure, exploration and endless runner type games.

## Behaviours

-	[`CameraFollowPlayer`]

## CameraFollowPlayer

This function makes your in-game camera follow your players position at a set angle and height, it is made so it will not be changed if your player raises its elevation or turns to face a different direction, so it’s best used for games with a single direction type game. Also the  It has one configurable parameter:

-	Player

### Player

This references the player, allowing you to choose which game object of certain scenes the camera will follow, this can potentially allow you to change to different playable characters if you have more than one by simply choosing a different game object and assigning it to this parameter. (Note this will require extra steps not taking in this package)


### Example Scene

This scene shows off how the camera stays at the same distance of a rolling sphere even if it rolls at an angle and suddenly drops in elevation.

