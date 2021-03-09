# Learning Journal

16/02/2021

Started development on an optimal player controller that used Physics to be interactable with other objects and be usable for other games, I realised that a `Rigidbody` was necessary for what I wanted and attached that too my player. Encountered a strange bug that made the controls flip if the players Y axis was changed in any way, was told to use `Velocity` with `Vector3` rather then my original method to avoid this issue. I think I had `AddForce` originally which caused the issues. 

Then I went to work on making a script for the camera to follow the player, I researched that having the camera being a child of the player would bring so problems so instead I just set the offset as the camera’s transform position - the players transform position, then made sure to keep the cameras transform position = to the players + that offset.

Since I wanted to make an almost all-purpose Player Controller I decided to add a jump mechanic to it, I was able to get it done by referencing the RigidBody and then adding force to the up axis, I used a float called jump height to designate how high I wanted to jump to be which worked out.
This led to my next issue of allow the player to jump only once and not able to jump again until on the ground again. 
This was more simple then I expected by just naming all my platforms “Ground” and having a public bool called “isGrounded”, this was set to false and was only true when the player’s RigidBody touched a game object named “Ground”.

23/02/2021

Decided on making a falling platform package for my third package, I underestimated how much was needed to make a close to all purpose script for a falling platform and ran over my baseline estimate by more than two hours.

The first problem came when I figured it be a good idea to have the platform come back once it fell, this brought a problem though as that meant I could not just add negative force to the Y axis of the platform because it would continue adding that force and might cause issues, that and it will not come back up. 

My tutor showed me that I could attached a `RigidBody` to the platform and periodically turn on `Is Kinematic` and `Use Gravity` when the need occurred to rise and lower the platform.

I had set up two floats called `downSpeed` which dictates how fast the platform would drop and `resetTime` which would bring the platform back up after a certain amount of time. 

I was then informed that it would be best to return the platform to its original position rather then add force to its Y axis as it would set itself into position.

I was able to develop a reset position script by referencing the RigidBody and turning on and off its `Is Kinematic` and `Use Gravity` as well as setting a bool called isRising to true, isRising means if the platform position is lower then its original position, then it will drop lower, I then set it to return to its original position once a few seconds had passed. 


01/03/2021
I was developing a sound manager for one of my briefs, I researched what would be the best way to develop this and found a method that allows me to incorporate as many sound effects as I need. 

I set up a sound array and wrote foreach sound effect in the array, it would add a component, that being an audio source, I also made two settings which allowed me to change the volume and pitch in another script called “sounds”
```
[Range(0f, 1f)]
public float volume;
 [Range(.1f, 3f)]
public float pitch;
```

I made it a public class by erasing the `mono behaviour` and then making it viewable through the inspector by writing `[System.Serializable]`

Then to allow me to choose a particular sound effect I wrote:
```
public void Play (string name)
    {
        Sound s = Array.Find(sounds, sound => sound.name == name);
        s.source.Play();
    }
```

02/03/2021
To make for my last Unity Package, I wanted to make a good reset the game script that would reliably reload the active scene if the player went through a certain collider.

To do this, I set up two different scripts as I was going to use Unity’s events system to accomplish this, I made am “Events system” script with a string called “triggerTag” which sets up the code to only trigger when a specific tag meets the codes conditions and a public unity event called “triggerAction”. I could now attach this to any game object and it would allow me to call different functions as if I were using a button on a canvas.

I then set up the method that I wanted to happen to call functions, which was an `OnTriggerEnter` and then made it so the `triggerTag` would invoke the triggerAction. This means that the trigger tag could be changed in the inspector to meet different needs and call the corresponding action.

Then I just made a reload the scene script by writing
```
public void ReloadScene()
    {
        SceneManager.LoadScene(SceneManager.GetActiveScene().buildIndex);
    }
```

09/03/2021
Made a countdown system to go along with my RCR project, was able to develop a countdown function by using a `vanvas text` and making two variables called ` currentTime` and `startingTime`. startingTime would be set to ten for the text and currentTime would be set to 0. I also made a `[SerializeField] Text countdownText;` which would be my countdown text.
I then made `currentTime = startingTime` in the start method and made `currentTime-= 1 * Time.deltaTime;` which meant that the currentTime will be 10 and will countdown one per second. Finally, I made `countdownText.text = cuttentTime` So the canvas text would display the current time counting down.

I ran into a small issue when Unity told me I couldn't "convert to string" but I was able to reactify that by adding `.ToString("0");`. Also adding the zero meant that the game would countdown using whole numbers rather then decimals.
