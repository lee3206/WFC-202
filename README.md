# WFC-202

## Team
Lee Taber

Kevin Weatherwax

Sean Fernandes


## Processing
Install [Processing](https://processing.org/) and make sure to install the Python package for processing.
Navigate to the Ultima Tiles sketch and open it through processing.

On Windows:
Where it says 
```bash
path = File("C:\Users\You\Navigate\To\Ultima_Tiles\Tiles").listFiles()
```
Enter the file path for your copy of Ultima_Tiles.

Look at the connectors array and note the numbers.
```bash
    2
 1 x x 3
   x x
    4
```
For each tile, the first number is 1, going clockwise around the tile. Each number is a valid connector. So tiles that have a 0 on the left and right sides are valid combinations.

Press play on the processing window to run. It will likely hang for a moment, then start drawing tile by tile. 

Note that there are a great many path tiles and they tend to be non-sensical. One way to improve this behavior would be to reduce the frequency of tiles or add some exclusion rules so that they cannot be right next to one another.

## Unity
All of this work was done using the [WFC for Unity by SelfSame](https://selfsame.itch.io/unitywfc)

Install Unity and import one of the following packages (Simple-Tiled or Overlapping)
All of the Ultima tiles and sprites are available in the Resources folder in Assets.
If you install both the Simple Tiled and Overlapping packages the assets for Simple Tiled are in the Simple Tiled folder and the Overlapping is in the main resources folder.

Map environment prefabs (grass, bridges, rivers, trees, mountains, etc.) are in the top level of the resources folder.
Prefabs of Buildings, dungeons, statues, signs, etc., are in the Decorations subfolder. 
The original PNG images are in the folders "z Original sprites" and "Scenery".

Note that only Prefabs can be added to the tile painter. If you wish to add new images to the scene drag them into the resources folder, then drag them into the scene to create a prefab, then drag the prefab back into resources and delete it from the scene. These may then be added to the tile painter pallete. Additionally, when importing Pixel style artwork into Unity you must select Filter Mode "Point (No Filter)" or they will be compressed and lose the pixel ratios and the ratio of any new image scale must be adjusted to fit inside the tile painter grid without overlap (e.g., a 16x16 pixel image must be adjusted to scale x and y 6.25)

### Simple Tiled
Simple Tiled will produce an image based on the sample tile-set to the left. 

![alt text](https://github.com/lee3206/WFC-202/blob/master/Pictures/tiled-unity-example1.png)

The tiles are painted using a palette of tiles.

Click on the object called "Canvas Small" and follow the directions in the Tile Painter Script

![alt text](https://github.com/lee3206/WFC-202/blob/master/Pictures/tiled-unity-example2.png)

Once you are happy about your canvas, click the compile and record neighbors buttons in the tiles object under "Canvas Small"

![alt text](https://github.com/lee3206/WFC-202/blob/master/Pictures/tiled-unity-example3.png)

Exit and restart, and the tiles file in Assets will have changed. 

![alt text](https://github.com/lee3206/WFC-202/blob/master/Pictures/tiled-unity-example4.png)

Now, click on Small World Test, and drag the tiles file into the xml box in the inspector.

![alt text](https://github.com/lee3206/WFC-202/blob/master/Pictures/tiled-unity-example5.png)

Click generate, then run and you should start creating some new combinations!

![alt text](https://github.com/lee3206/WFC-202/blob/master/Pictures/tiled-unity-example6.png)

If you want to change the settings, go into the tiles xml file and mess with the weights to change what objects tend to appear in the output.

![alt text](https://github.com/lee3206/WFC-202/blob/master/Pictures/tiled-unity-example7.png)

If you want the output to match the sample picture, try altering the weights such that grass is boosted to 2, while other objects that should be "rare" such as bridges are reduced to .25. Play around with different patterns of weights to find something that looks appealing.

Here are some examples of sample outputs. You can increase the size of the output in the "small world test" object, although increasing the size makes it more difficult to complete. Larger outputs tend to fail more.
![alt text](https://github.com/lee3206/WFC-202/blob/master/Pictures/SmallTile-1.png)
![alt text](https://github.com/lee3206/WFC-202/blob/master/Pictures/LargeTile-2.png)

### Overlapping
