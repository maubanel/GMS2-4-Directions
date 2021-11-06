<img src="https://via.placeholder.com/1000x4/45D7CA/45D7CA" alt="drawing" height="4px"/>

### Four Keys Tracked

<sub>[previous](../last-4dir/README.md#user-content-last-key-pressed-with-animated-player) • [home](../README.md#user-content-gms2-move-in-4-directions) • [next](../)</sub>

<img src="https://via.placeholder.com/1000x4/45D7CA/45D7CA" alt="drawing" height="4px"/>

Here is the gold standard for four key controls.  We will track the order that each key is pressed in.  This way if you have all four keys pressed the order you release the keys will be reflected in the game picking the correct direction.  This makes the whole process a lot more complicated as we need to do a lot more work to achieve this goal.

The last [walkthrough](../last-key/README.md#user-content-last-key-pressed) properly tracked two keys (fell apart when third or fourth key is pressed).  This one solves this issue.

<br>

---


##### `Step 1.`\|`4DIR`|:small_blue_diamond:

Create a sprite called `spr_player` (I have called mine `sp_player_3` as I have completed the previous walk throughs).  Press the <kbd>Edit Image</kbd> button and draw a player and pick a color for it.  Change the **Origin** to `Middle | Center`.

![create spr_player sprite](images/sprPlayer.png)


<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 2.`\|`4DIR`|:small_blue_diamond: :small_blue_diamond: 

*Right click* on **Objects** and select **New | Object** and name it `obj_player_track_4`. Set the **Sprite** to `spr_player` or `spr_player_3`.

![obj_player_track_2 object with spr_player](images/objPlayer.png)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 3.`\|`4DIR`|:small_blue_diamond: :small_blue_diamond: :small_blue_diamond:

If you don't have the two fonts from the last exercise *Right click* on **Fonts** and select **New | Font** and name it `fnt_title`. Make the **Size** `36` and the **Style** `Bold`.

Add another font called `fnt_hud` with a **Size** of `12` and **Style** `Regular`.

![added title font](images/fntTitle.png)

![added hud font](images/fntHud.png)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 4.`\|`4DIR`|:small_blue_diamond: :small_blue_diamond: :small_blue_diamond: :small_blue_diamond:

If you don't already have an **obj_game** *right click* on **Objects** and select **New | Object** and name it `obj_game`. Set **Persistent** to `true`. Press the <kbd>Add Event</kbd> and select a **Draw | Draw GUI** event.

* Set the font to **fnt_title**
* Center the text alignment
* Set the color to yellow
* Set up a temporary variable called `title`
* Switch on the room and set the **title** to `"4 Movement Keys Tracked"`
* Draw title

Don't include the `case rm_simple_movement:` if you do NOT have this room. Only include this if you have done the previous exercise.

![add rooms titles](images/objGame.png)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 5.`\|`4DIR`| :small_orange_diamond:

Open up **obj_game**. Press the <kbd>Add Event</kbd> and select a **Step | Step** event. Only add this if you want to switch between rooms with the different implementations of the 4 way movement.  

* Check if space is pressed and if there is another room to go to
* If so, then go to next room
* Else if space is pressed, go back to first room (if it exists)

![add step event and logic to move from room to room](images/switchRooms.png)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 6.`\|`4DIR`| :small_orange_diamond: :small_blue_diamond:

*Right click* on **Rooms** and select **New | Room** and name it `rm_track_4`. Change the **Room Order** to place this room on the top of the list or you can leave it in order and press the <kbd>Space Bar</kbd> to change rooms if you have done the previous exercise and added the **Step** event to **obj_game**.

Draw  copy of **obj_player_track_4** and **obj_game** to the level.

![add rm_track_2](images/addRm.png)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 7.`\|`4DIR`| :small_orange_diamond: :small_blue_diamond: :small_blue_diamond:

Open up **obj_player_track_4**. Press the <kbd>Add Event</kbd> and select a **Create** event. 
* Center the player in the level 
* Create 4 variables to store which key was pressed in which order.  So `left_key`, `right_key`, `up_key`, `down_key` will be give a number between `1` and `4` in the order it was pressed.
* Create a final variable `last_number_of_keys` which we will use to see if the number of keys we have pressed last frame is less than the number of keys we have pressed now.  You will see why later why we need to track this.

![create event for obj_player_track_4](images/trackCreate.png)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 8.`\|`4DIR`| :small_orange_diamond: :small_blue_diamond: :small_blue_diamond: :small_blue_diamond:

Press the <kbd>Add Event</kbd> and select a **Draw | Draw GUI** event.

* Change the alignment to left aligned
* Change the font color
* Change fonts to `fnt_hud`
* draw the four keys integer and it should be `0` if not pressed or `1` through `4` depending on the order

![add draw_gui and draw four keys to screen](images/drawGuiOne.png)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 9.`\|`4DIR`| :small_orange_diamond: :small_blue_diamond: :small_blue_diamond: :small_blue_diamond: :small_blue_diamond:

Press the <kbd>Add Event</kbd> and select a **Step | Step** event.

* Store the status of whether the left, right, down up up key is pressed
* Add up the total number of keys pressed this frame and store in `number_of_keys`.
* Check to see if a button was not pressed last frame and assign it the `number_of_keys`

![check keys, add up all pressed then assign number](images/4wayStepOne.png)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 10.`\|`4DIR`| :large_blue_diamond:

Now *press* the <kbd>Play</kbd> button in the top menu bar to launch the game. Press four keys one after another and see that each key gets the appropriate number.  The first key pressed gets `1` and the last key pressed gets `4`.  Now this only sets it when it wasn't set the last frame.  So we cannot retrack the order when we release the keys and press them again.

![store four key presses once](images/4KeysNoReset.gif)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 11.`\|`4DIR`| :large_blue_diamond: :small_blue_diamond: 

So how do we reset keys back to `0` when they are let go.  This is very simple.  Now since the key will be a `1` if `keyboard_check_pressed(key)` returns **true** or `0` if **false**. So if we multiply the key by the press if that key is pressed it will multiply the number by 1 and stay the same.  But if the key is let go it will multiply by 0 getting the behavior we desire.

![reset keys when not pressed](images/resetKeys.png)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>


##### `Step 12.`\|`4DIR`| :large_blue_diamond: :small_blue_diamond: :small_blue_diamond: 

Now *press* the <kbd>Play</kbd> button in the top menu bar to launch the game. Now if you press four keys, then let them go and press 4 more - we get the behavior we desire.  There are still lots of issues.  One is what if I press two keys during the same frame, that key gets the same number.

![press four keys to four numbers, two keys give duplicate numbers](images/FourKeysDupeIssues.gif)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 13.`\|`4DIR`| :large_blue_diamond: :small_blue_diamond: :small_blue_diamond:  :small_blue_diamond: 

Now lets make a copy of **number_of_keys** and store it in `key_holder`.  I don't want to alter the **number_of_keys** variable as we want it to represent what it says.  So each time we set a key to **key_holder** we will subtract `1` from it. That way it will put a different number on each key and the order that it will be selected if they are pressed at the same time is **left** first to *up* last (*left* would be `4` if all 4 are pressed at the same time and *up* would be `1`).

![subtract 1 to have no duplicate frames](images/fixDupeIssue.png)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 14.`\|`4DIR`| :large_blue_diamond: :small_blue_diamond: :small_blue_diamond: :small_blue_diamond:  :small_blue_diamond: 

Now no matter how many keys you press at the same time, they will all get assigned a different number.

![play game and see no more duplicate numbers when multiple keys are pressed at once](images/NoDupes.gif)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 15.`\|`4DIR`| :large_blue_diamond: :small_orange_diamond: 

We have a large remaining problem.  Lets say we have three buttons held.  We let go of button 1 and 2.  So we only have button 3 left.  The number stays at 3.  So if we press two more buttons after the order is wrong and there are two buttons with number 3. 

![show issue with button not released not reordering](images/NumberNotReordered.gif)

<img src="https://via.placeholder.com/500x2/45D7CA/45D7CA" alt="drawing" height="2px" alt = ""/>

##### `Step 16.`\|`4DIR`| :large_blue_diamond: :small_orange_diamond:   :small_blue_diamond: 

We are going to write our first custom **[function](https://manual.yoyogames.com/GameMaker_Language/GML_Overview/Script_Functions.htm)**. I can create a script in the scripts folder and make that function global, but since I only need this for the player I can wraite the function in the same block of code and make it local to this game object.

This function will return the lowest numbered key based on a starting number.  So I I pass **starting_num** as `2` it will return the lowest key number that is `2` or higher.  So if I only have a key with `3` it will return that key from the function.

![return_lowest_num function](images/addFunctionLowestKey.png)

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

| [previous](../last-4dir/README.md#user-content-last-key-pressed-with-animated-player)| [home](../README.md#user-content-gms2-move-in-4-directions) | [next](../)|
|---|---|---|
