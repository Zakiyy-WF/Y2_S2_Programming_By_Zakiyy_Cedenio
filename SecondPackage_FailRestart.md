# Fail Restart Guide

This document explains what the behaviours in this package does and the requirements needed to work effectively, this will explain how to use this package to create a reset function used in a lot of platformer type games.

## Behaviours

-	[`EventsSystem`]
-	[`LoadScene`]


## EventsSystem
As the name implies, this behaviour is using Unity’s events system but allowing it to be used on other game objects as if you were using a canvas. It allows you to create your own events and store them within this behaviour to invoke those created events. Through the inspector tab, you can change what tag will trigger the functions as well as what function will trigger, this all works around an `OnTriggerEnter` function so your corresponding events will have to synergise with that.

## LoadScene

This behaviour uses Unity’s `Build settings` and its `Scene Management Engine` to switch to a different scene. This requires you to have built your scene into Unity’s build settings as to set your current scene as the `Active` scene, it will load the scene you are currently on once conditions are met. 

Placing each script on the game object you want this to activate and then setting the trigger tag to the tag you want the `LoadScene` function to work on. It will require you to have a collider set to trigger to activate this behaviour. 

### Example Scene

The scene has a sphere tagged “Player” with a RigidBody falling into an invisible collider with the two functions named above, the scene will continually reset once the sphere touches the collider. 
