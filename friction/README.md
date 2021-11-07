<img src="https://via.placeholder.com/1000x4/45D7CA/45D7CA" alt="drawing" height="4px"/>

### Breaking Friction

<sub>[previous](../acceleration/README.md#user-content-acceleration) • [home](../README.md#user-content-gms2-move-in-4-directions) • [next](../rotate-down/README.md#user-content-rotate-top-down-animation)</sub>

<img src="https://via.placeholder.com/1000x4/45D7CA/45D7CA" alt="drawing" height="4px"/>

Lets expand the physics model and alter the breaking friction of the character based on the surface they are traveling on.

<br>

---


##### `Step 1.`\|`4DIR`|:small_blue_diamond:

Complete the [Acceleration](../acceleration/README.md#user-content-acceleration) walk through.  We will use this as our starting off point and add friction. 

Duplicate **obj_player_acceleration_4Dir** and name the object `obj_player_friction_4Dir`.

![duplicate obj_player_friction_4dir](images/DupeFriction.gif)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 2.`\|`4DIR`|:small_blue_diamond: :small_blue_diamond: 

*Right click* on **Rooms** and select **New | Room** and name it `rm_friction. Change the **Room Order** to place this room on the top of the list or use the space bar.

*Drag and drop* **obj_game** and **obj_player_friction_4Dir** into the level.

![add rm_friction as well as obj_game and obj_player_friction_4Dir](images/breakingFriction.png)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 3.`\|`4DIR`|:small_blue_diamond: :small_blue_diamond: :small_blue_diamond:

Go to **obj_game | Draw GUI** and add a title for this level.

![add title](images/addTitles.png)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 4.`\|`4DIR`|:small_blue_diamond: :small_blue_diamond: :small_blue_diamond: :small_blue_diamond:

Open up **obj_player_friction_4Dir | Create** event and add a `p_friction` variable and set it to a very low number like `.01` to test. 

![add p_friction var to create in player](images/addFrictionVar.png)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 5.`\|`4DIR`| :small_orange_diamond:

Now open up **obj_player_friction_4Dir | Step** and just before we apply physis lets remove a little bit from the `speed` as a frictional force that will slow the player down.

![reduce speed by p_friction](images/applyFriction.png)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 6.`\|`4DIR`| :small_orange_diamond: :small_blue_diamond:

At the bottom of the script we need to get rid of the instant breaking to `0` when you don't press buttons.  Delete the `speed = 0` and let the friction deplete the speed down to nothing.

![get rid of breaking](images/getRidOfBreaking.png)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 7.`\|`4DIR`| :small_orange_diamond: :small_blue_diamond: :small_blue_diamond:

Now *press* the <kbd>Play</kbd> button in the top menu bar to launch the game. Now when you let go the player will very slowly come to a stop.

![play game, let go of controls then see the player come to a slow stop](images/frictionOne.gif)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 8.`\|`4DIR`| :small_orange_diamond: :small_blue_diamond: :small_blue_diamond: :small_blue_diamond:

Now you can adjut the `p_friction` in the player object's create event to your liking.

![adjust p_friction](images/tuneFriction.png)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 9.`\|`4DIR`| :small_orange_diamond: :small_blue_diamond: :small_blue_diamond: :small_blue_diamond: :small_blue_diamond:

Now *press* the <kbd>Play</kbd> button in the top menu bar to launch the game. Now you have a full physics model with acceleration and breaking friction working in your four directions of movement on both a keyboard and gamepad!

![final friction in game](images/FinalFriction.gif)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 10.`\|`4DIR`| :large_blue_diamond:

Select the **File | Save Project** then press **File | Quit** to make sure everything in the game is saved. If you are using **GitHub** open up **GitHub Desktop** and add a title and longer description (if necessary) and press the <kbd>Commit to main</kbd> button. Finish by pressing **Push origin** to update the server with the latest changes.

![save, quit, commit and push to github](images/GitHub.png)

___


<img src="https://via.placeholder.com/1000x4/dba81a/dba81a" alt="drawing" height="4px" alt = ""/>

<img src="https://via.placeholder.com/1000x100/45D7CA/000000/?text=Next Up - Rotating Animations">

<img src="https://via.placeholder.com/1000x4/dba81a/dba81a" alt="drawing" height="4px" alt = ""/>

| [previous](../acceleration/README.md#user-content-acceleration)| [home](../README.md#user-content-gms2-move-in-4-directions) | [next](../rotate-down/README.md#user-content-rotate-top-down-animation)|
|---|---|---|
