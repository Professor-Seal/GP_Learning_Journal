# GP_Learning_Journal
Learning Journal for Game Programming Module at LSBU

## 14/10/25
If I create a new reprositry and don't add a README.md file I won't have any information to see on the reporir=try homepage. To rectify this issue I created a README.md file.

## 16/10/25
Deciding on what my 4 components for my protype would be. These are a button that opens and closes a door, a switch that changes the perception for the player, player movement including left, right and the ability to double jump and enemy projectiles that damage/ kill the player. I also decided to do this in Unity 3D.

Had an error message appear relating to the packet manager. To rectify this issue I select the remove option for the JetBrains Rider Editor. This seems to have fixed the problem. I did this for all 4 prototype Unity files.
<img width="1918" height="1008" alt="image" src="https://github.com/user-attachments/assets/f9c3fbb0-f65e-4be5-9d80-526eb5032cfe" />

## 17/10/25
I had a problem where the ground, walls and player where all the same colour and difficult to tell apart. To fix this I created a new material - with the help of a tutorial linked here: https://www.youtube.com/watch?v=vhZtjL4Buik - to change the colour of the player.

## 21/10/25
I came accross an error today from the player jump script. The player could jump but only once and then was unable to jump again. Looking in the inspector the error came from the OnGround check being faulty. To fix this I changed the OnTriggerEnter function to an OnCollisionEnter function.

I also had an error with the double jump, where the player could infinetly jump. To solve this I created a nested if statement to check whether the player is on the ground and if they are they can jump and if the player is not on the ground they can press jump again but only 1 time until they are on the ground again.

## 28/10/25
I had an error with my enemy projectiels where the procetiles weren't spawinging in the right place and were floating upwards when the game was played. The problem was I was using a tutorial for 2D projectiles instead of a tutorial for 3D projectiles. So I had to find a different tutorial for a 3D projectile.

I had another bug where the projectiles weren't spawning. I relisedn that the function I had written to spawn the projectiles wasn't being called so to fix this I put the shootAtPlayer function inside the Update function so it can be called. 

However, the game still didn't spawn the projectiles. I managed to fix this problem by creating an If statement in the Update function. But this created a new issue where the enemy moves along the negative Z axis. This problem was fixed when I added movement to the projectile but this created its own bug.

The bug was when the enemy shot the projectile at the player, the enemy rotated on its x, y and z axis. To fix this I set the spawn point of the projectile to be outside of the enemy.

An bug that occured later was that the projectile would not kill/ do damage to the player when it collides with them. To fix this I changed the OnTriggerEnter function to the OnCollisionEnter function.

## 11/11/25
Today I was working on a button that when pressed would open a door fort eh player to then walk through (following this tutorial - https://www.youtube.com/watch?v=DNKGe3IyPs4), however I had an error occur where nothing happend when the player steeped on the button. To fix this I change the OnTriggerEnter and OnTriggerExit functions to their Collision counterparts.

Another bug that I came across was that when the player interacted with the button, the door did not open. I could manually open the door by changing the _isDoorOpen variable from false to true in the Untiy Inspector when the game was running. After experimenting I discovered that button does work with the door but only if the _isDoorOpen variable is set to true before the game runs.

To fix this issue I had to change one function to include the not (!) command.

## 18/11/25
Today I was working on making a camera perspective switch but couldn't figure out how to do it so I deceide to change to something easier - Player Power-Ups.
I had an issue with changing the player's colour when collecting up a power up. I had help to fix this issue. And the method of fixing was to call the Player colour from the player rendere into the script and then set a change colour command using an if statement depening on which power up the player picks up. I also created a timer that resets the player back to normal after a certain time has passed.

## 25/11/25
I was working on my pplayer projectiloes and had and error where the Input Button space was not setup to be used for the game. To fix this I changed the GetkeyDown from Space to Fire1 and then changed what button Fire1 is related to in the Input Manager to be the space bar.

<img width="385" height="71" alt="image" src="https://github.com/user-attachments/assets/a77a584b-6de7-49af-a374-834c72039386" />

After I got the projectile working I came accross another problem, the projectile did not destroy itself when colliding with the enemy, instead it pushed the enemy backwards until the enemy collided with the wall and then the projectile went through the enemy and the wall, it then continued to travel off screen. To fix this issue I changed the OnCollisionEnter function to an OnTriggerEnter function.

Next, I had to fix the issue that the player could constantly spam the projectiles even without picking up the power up. To fix this I created a canFire bool variable then made an ActivateFire function to change the bool between true and false if the player has picked a power up or not.

## 28/12/25
I found a bug when the player collects one power up and then they collect anoother power up they can still fire both types of projectiles. To fix this issue is set the canFireFire and canFireIce bool to false for the corresponding power up/ projectile types.

## 02/12/25
Today I had a bug with the AOE damage from the projectile. The projectile could only damage 1 enemy instead of the enemies in the radius even when the radius was set to 100 and definitely included more than 1 enemy.
