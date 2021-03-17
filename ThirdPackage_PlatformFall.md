# Platform Fall Guide 

This document explains what the behaviours in this package does and the requirements needed to work effectively. This will explain how to use the package to set up a falling platform mechanic that will return to its original position after a set amount of time, works for platformer type games. 

## Behaviours 

- [`PlatformFall`]

## Platform Fall

This behaviour, when attached to a game obect with a RigidBody will drop the platform once another game object tagged player colliders the game objects collider, once the player stops colliding with the game object, a reset timer will begin counting, once it reaches its designated time will return to its original position. It has one configurable parameter:
