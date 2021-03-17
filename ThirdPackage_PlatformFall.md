# Platform Fall Guide 

This document explains what the behaviours in this package does and the requirements needed to work effectively. This will explain how to use the package to set up a falling platform mechanic that will return to its original position after a set amount of time, works for platformer type games. 

## Behaviours 

- [`PlatformFall`]

## Platform Fall

This behaviour, when attached to a game obect with a RigidBody will drop the platform once another game object tagged player colliders the game objects collider, once the player stops colliding with the game object, a reset timer will begin counting, once it reaches its designated time will return to its original position. It has one configurable parameter:

-	resetTime

### resetTime

Reset Time allows you to change the duration it takes for the platform to reset to its original position, note that this reset time will only begin once the players collider is no longer colliding with the platform that this function is attached to.

## Example Scene

This scene shows a ball tagged “Player” and with a RigidBody rolling down a ramp onto a platform with the function attached to it, the platform will fall once the sphere collides with it and raise when the adjustable reset timer reaches its set time.
