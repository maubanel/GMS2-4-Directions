<img src="https://via.placeholder.com/1000x4/45D7CA/45D7CA" alt="drawing" height="4px"/>

### Acceleration

<sub>[previous](../gamepad/README.md#user-content-using-a-gamepad) • [home](../README.md#user-content-gms2-move-in-4-directions) • [next](../)</sub>

<img src="https://via.placeholder.com/1000x4/45D7CA/45D7CA" alt="drawing" height="4px"/>

Our player is at maximum speed right away.  There is no sense of them having a force applied and going towards max speed.  Lets implement a more sophisticated physcis model starting by addin a force to accelerate to terminal velocity.

<br>

---


##### `Step 1.`\|`4DIR`|:small_blue_diamond:

Complete the [Four Keys Tracked with Animated Player](../four-4dir/README.md#user-content-four-keys-tracked-with-animated-player) walk through.  We will use this as our starting off point. 

Duplicate **obj_player_track_4_4Dir** and name the object `obj_player_acceleratino_4Dir`.

![alt_text](images/dupePlayer.png)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 2.`\|`4DIR`|:small_blue_diamond: :small_blue_diamond: 

*Right click* on **Rooms** and select **New | Room** and name it `rm_acceleration`. Change the **Room Order** to place this room on the top of the list or use the space bar.

*Drag and drop* **obj_game** and **obj_player_acceleration_4Dir** into the level.

![add rm_acceleration as well as obj_game and obj_player_acceleration_4Dir](images/AddRoom.png)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 3.`\|`4DIR`|:small_blue_diamond: :small_blue_diamond: :small_blue_diamond:

Go to **obj_game | Draw GUI** and add a title for this level.

![add title](images/addTitles.png)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 4.`\|`4DIR`|:small_blue_diamond: :small_blue_diamond: :small_blue_diamond: :small_blue_diamond:
 
 Now open up **obj_player_acceleration_4Dir | Step** event.  Lets accept both keyboard **and** gamepad inputs.  So add an or (||) statement so that both inputs will work.

![check for gamepad and keyboard](images/checkBothInputDevices.png)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 5.`\|`4DIR`| :small_orange_diamond:

Now *press* the <kbd>Play</kbd> button in the top menu bar to launch the game. Now you can play the game with both gamepad and keyboard!

![play the game and control with keyboard and gamepad](images/4DirControlAndKey.gif)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 6.`\|`4DIR`| :small_orange_diamond: :small_blue_diamond:

Now we want to add a force to the player each frame so they accelerate and don't hit their maximum speed right away.  Open up **obj_player_accelerate_4Dir | Create** event add a variable called `p_force` to the script and set it to a very small number like `0.1`.  It will run every frame so 60 times a second.

![add p_force to player create event](images/addForce.png)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 7.`\|`4DIR`| :small_orange_diamond: :small_blue_diamond: :small_blue_diamond:

Now open up **obj_player_accelerate_4Dir | Step**  event and change the variable we use for acceleration and instead of setting it, add or subtract depending on the direction you are moving in.

![add or subtract acceleration](images/addSubtractPForce.png)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 8.`\|`4DIR`| :small_orange_diamond: :small_blue_diamond: :small_blue_diamond: :small_blue_diamond:

Now *press* the <kbd>Play</kbd> button in the top menu bar to launch the game. Now when you move you keep speeding up endlessly until you go too fast to see the player.

![run game and go infinitely fast](images/enlessAccel.gif)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 9.`\|`4DIR`| :small_orange_diamond: :small_blue_diamond: :small_blue_diamond: :small_blue_diamond: :small_blue_diamond:

Go back to your **obj_player_accelerate_4Dir | Create** event and change `p_speed` to `max_speed`.The value will still be `2.5`, but this now represents our maximum speed.

![change p_speed to max_speed](images/maxSpeed.png)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 10.`\|`4DIR`| :large_blue_diamond:

Now we will use the **[clamp(val, min, max)](https://manual.yoyogames.com/GameMaker_Language/GML_Reference/Maths_And_Numbers/Number_Functions/clamp.htm)**.  With this function you can maintain an input value between a specified range. So we will limit the `speed` to be a value between `0` and `max_speed`. Open up **obj_player_accelerate_4Dir | Step** and add this clamp.

![clamp max speed](images/clampSpeed.png)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 11.`\|`4DIR`| :large_blue_diamond: :small_blue_diamond: 

Now *press* the <kbd>Play</kbd> button in the top menu bar to launch the game. Now you cannot exceed a speed of `2.5`.

![speed clamped in game](images/MaxSpeedImplemented.gif)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>


##### `Step 12.`\|`4DIR`| :large_blue_diamond: :small_blue_diamond: :small_blue_diamond: 

Now lets slow down acceleration and take a critical look at it. Open up **obj_player_accelerate_4Dir | Create** event and change the `p_force` to `0.01`.  This will slow down the acceleration.

![change p_force to .01](images/slowAcceleration.png)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 13.`\|`4DIR`| :large_blue_diamond: :small_blue_diamond: :small_blue_diamond:  :small_blue_diamond: 

Now *press* the <kbd>Play</kbd> button in the top menu bar to launch the game. Notice that the acceleration is VERY slow.  But the animation runs at full speed.

![play in game and notice animation is running too fast](images/WrongSpeed.gif)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 14.`\|`4DIR`| :large_blue_diamond: :small_blue_diamond: :small_blue_diamond: :small_blue_diamond:  :small_blue_diamond: 

What we can do is divide the speed that we play `image_speed` by the speed the player is moving by the max_speed.  So when it is full max_speed this will be `1` (the speed in the game previously) and when the speed is lower it will be fractional all the way down to 0 when the player stops. Open up **obj_player_accelerate_4Dir | End Step** and add this change to the `image_speed`.

![scale speed](images/scaleSpeed.png)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 15.`\|`4DIR`| :large_blue_diamond: :small_orange_diamond: 

Now *press* the <kbd>Play</kbd> button in the top menu bar to launch the game. Now when you play the player accelerates at the same time as the animation accelerates!

![player animaion now accelerates](images/CorrectSpeed.gif)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 16.`\|`4DIR`| :large_blue_diamond: :small_orange_diamond:   :small_blue_diamond: 

![alt_text](images/.png)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 17.`\|`4DIR`| :large_blue_diamond: :small_orange_diamond: :small_blue_diamond: :small_blue_diamond:

![alt_text](images/.png)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 18.`\|`4DIR`| :large_blue_diamond: :small_orange_diamond: :small_blue_diamond: :small_blue_diamond: :small_blue_diamond:

![alt_text](images/.png)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 19.`\|`4DIR`| :large_blue_diamond: :small_orange_diamond: :small_blue_diamond: :small_blue_diamond: :small_blue_diamond: :small_blue_diamond:

![alt_text](images/.png)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 20.`\|`4DIR`| :large_blue_diamond: :large_blue_diamond:

![alt_text](images/.png)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 21.`\|`4DIR`| :large_blue_diamond: :large_blue_diamond: :small_blue_diamond:

![alt_text](images/.png)

___


<img src="https://via.placeholder.com/1000x4/dba81a/dba81a" alt="drawing" height="4px" alt = ""/>

<img src="https://via.placeholder.com/1000x100/45D7CA/000000/?text=Next Up - ADD NEXT T4DIRE">

<img src="https://via.placeholder.com/1000x4/dba81a/dba81a" alt="drawing" height="4px" alt = ""/>

| [previous](../gamepad/README.md#user-content-using-a-gamepad)| [home](../README.md#user-content-gms2-move-in-4-directions) | [next](../)|
|---|---|---|
