# GMS2 Move in 4 Directions


<!-- OVERVIEW -->
This tutorial is intended for those wanting an introduction to <i>GameMaker Studio 2</i> using their scrpting language <i>GML</i>. This assumes no prior knowledge of the software or scripting. 

Lets look at various ways of moving a human character in 4 directions.

* Tested on GameMake Studio2.3.5.589
* An existing [GML Project](https://github.com/maubanel/GMS2-Snippets/blob/main/rename-project/README.md#user-content-rename-gms2-project)

<br>


<!-- TOC -->
## Table of Contents
<kbd></kbd> &nbsp;&nbsp; [Simple Movement](simple-movement/README.md#user-content-simple-movement) <br>
<kbd></kbd> &nbsp;&nbsp; [Simple Movement with Animated Player](simple-4dir/README.md#user-content-simple-movement-with-animated-player) <br>
<kbd></kbd> &nbsp;&nbsp; [Last Key Pressed](last-key/README.md#user-content-last-key-pressed) <br>
<kbd></kbd> &nbsp;&nbsp; [Last Key Pressed with Animated Player](last-4dir/README.md#user-content-last-key-pressed-with-animated-player) <br>
<kbd></kbd> &nbsp;&nbsp; [Four Keys Tracked](four-keys/README.md#user-content-four-keys-tracked) <br>
<kbd></kbd> &nbsp;&nbsp; [Four Keys Tracked with Animated Player](four-4dir/README.md#user-content-four-keys-tracked-with-animated-player) <br>
<kbd></kbd> &nbsp;&nbsp; [Using a Gamepad](gamepad/README.md#user-content-using-a-gamepad) <br>
<kbd></kbd> &nbsp;&nbsp; [Acceleration](acceleration/README.md#user-content-acceleration) <br>
<kbd></kbd> &nbsp;&nbsp; [Breaking Friction](friction/README.md#user-content-breaking-friction) <br>
<kbd></kbd> &nbsp;&nbsp; [Rotate Top Down Animation](rotate-down/README.md#user-content-rotate-top-down-animation) <br>



## Core Algorithm
1. Get Controls
2. Update player phyics 
3. Move and rotate player based on above physics (resolve physics if using speed/hspeed/vspeed automatically happens between step and end step events)
4. Resolve collision -> Decide on final state (walking, running, stopped etc...)
5. Select Animation

<!-- LICENSE -->
## License
Distributed under the MIT License. See `LICENSE` for more information: [link](LICENSE).


</p>
</details>
<details><summary>Dev Tips</summary>
make git m="add commit message"
</details>

