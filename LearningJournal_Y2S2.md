# Learning Journal

16/02/2021

Started development on an optimal player controller that used Physics to be interactable with other objects and be usable for other games, I realised that a `Rigidbody` was necessary for what I wanted and attached that too my player. Encountered a strange bug that made the controls flip if the players Y axis was changed in any way, was told to use `Velocity` with `Vector3` rather then my original method to avoid this issue. I think I had `AddForce` originally which caused the issues. 

Then I went to work on making a script for the camera to follow the player, I researched that having the camera being a child of the player would bring so problems so instead I just set the offset as the camera’s transform position - the players transform position, then made sure to keep the cameras transform position = to the players + that offset.

Since I wanted to make an almost all-purpose Player Controller I decided to add a jump mechanic to it, I was able to get it done by referencing the RigidBody and then adding force to the up axis, I used a float called jump height to designate how high I wanted to jump to be which worked out.
This led to my next issue of allow the player to jump only once and not able to jump again until on the ground again. 
This was more simple then I expected by just naming all my platforms “Ground” and having a public bool called “isGrounded”, this was set to false and was only true when the player’s RigidBody touched a game object named “Ground”.
