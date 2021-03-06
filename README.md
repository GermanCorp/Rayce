# Rayce

<p align="center">
<img src="https://k62.kn3.net/25094E777.gif" width="55%" height="55%"> 
</br>
<img src="https://k62.kn3.net/D990CBE47.png" width="26%" height="26%"> 
<img src="https://k62.kn3.net/213A64F02.png" width="26%" height="26%">
</p>

[Spanish README](https://github.com/Usbac/Rayce/blob/master/README.es.md)

Ray Casting engine based in the library of [LibGDX](https://github.com/libgdx/libgdx).

## Features
* Texture mapping in walls.
* Multiple sprites.
* Shadow distance.
* Collision detection (objects and walls).
* Optimized Ray Casting algorithm.
* Forward, back, and lateral movement with horizontal rotation.
* Algorithm that creates a map from a .tmx file (1st Layer: Walls, 2nd Layer: Collisionable objects, 3rd Layer: Non collisionable objects.

## Code Explanation
  The Ray Casting algorithm draws all of the environment column by column using rays, in this case the columns are not draw directly but instead are stored in three arrays that saves the characteristics of the ray/colum (one for the distance, one for the position of the texture and other one for the texture itself). In this case, it's done because the colums are drawn from farthest to nearest.

  In the RayCasting method the rays are fired from the player's position and when it collides with a wall, their characteristics are stored in the 3 arrays.

  In the generalRender method, the entities are sort from farthest to nearest (for drawing it in the correct order), then the rays are drawn in the same way from farthest to nearest, when any of the entities are closer than the previous ray, It is drawn on the screen.

  The rayRender method simply draws the ray in the indicated index.

## Compile and run
1. Install the Gradle plugin in your IDE.
1. Go to the folder with the source code (desktop\src\com\mygdx\game\desktop).
1. Open DesktopLauncher.java and run.
