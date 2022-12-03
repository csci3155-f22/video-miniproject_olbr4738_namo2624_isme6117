Hello, we're Nazhone Morgan, Isabelle Meredith, and Olivia Brobin. In this tutorial, we
will be showing you how to make a simple game using libGDX. libGDX is a java game development framework that allows for making Windows, Linux, macOS, Android, and iOS.

Step 1: Go to https://libgdx.com/wiki/start/setup

Step 2: Install Eclipse.

Step 3: Go to the "Generate a Project" tab and click download libGDX Project Setup Tool.

Click generate to set-up a libGDX project.
Choose a name for your project, along with the directory you will be working in, and a name for the game class. (the name of our simple game will be ‘drop’)
Unselect Android as a development option, as supporting Android will require additional downloads for the Android development kit and we’d need extra code that will complicate this tutorial
Click generate project

Step 4: Open Eclipse.
Go to file -> import -> Gradle -> Existing Gradle project
Hit next, and then select the directory you just created the project in

Step 5: Click Run As, Run Configurations.
Select Java Application, and create a new run configuration.
Select the DesktopLauncher class and click on the arguments tab.
Delete other as Working directory and then select the asset folder located in assets.

Step 6: Go to DesktopLauncher.java. We are going to be using this as the class that runs the game. We need to edit some of the configurations before coding the game
We import everything needed for the Drop game
config.setTitle(“Drop”); sets the title of the game to “Drop”
config.setWindowedMode(800, 480); will set the dimensions of the window to 800x480

Step 7: Go to our project resources, and copy and paste our example game code in for the class Desktop Launcher in the MyGDX Game-desktop. Also, copy our example game code in for the class MyGdxGame in the MyGDX Game-core . Then add the project assets from GitHub to the assets folder.



Now, here’s an explanation of how the code actually works:

Load Assets
Drop is a public class extended by ApplicationAdapter. This means the Drop subclass inherits the attributes and methods from the ApplicationAdapter superclass. 
The attributes of the ApplicationAdapter are:
   private Texture dropImage;
   private Texture bucketImage;
   private Sound dropSound;
   private Music rainMusic;
   private SpriteBatch batch;
   private OrthographicCamera camera;
   private Rectangle bucket;
   private Array<Rectangle> raindrops;
   private long lastDropTime;
This extension is similar to how our AST classes were extensions of other classes. For example:
Lab 6: RNoString extends RegExpr. RNoString inherited the attributes and methods from RegExpr
Lab 5: case object Neg extends Uop. Neg (for negative -e1) inherited the attributes and methods from the sealed abstract class Uop

The images (dropImage, bucketImage) and sounds (dropSound, rainMusic) are loaded in as textures and sounds to be used in the game
The music, if implemented, will loop and play immediately upon running the game

GDX makes use of a camera called OrthographicCamera() which allow for setting the size of the window.

Inside of the create() method, we’re able to make the objects we want to put on screen.
For example, the make a bucket we can declare it as a Rectangle and then set its x and y coordinates. When rendering the bucket in the render() method, we simple do batch.begin(), batch.draw(bucketImage, bucket.x, bucket.y) such that the bucket image is where the bucket is, and then batch.end();

To make the bucket move, we make use of Gdx.input in two different ways. To control the bucket with the mouse mouse, we write,  
if(Gdx.input.isTouched()) {
      Vector3 touchPos = new Vector3();
      touchPos.set(Gdx.input.getX(), Gdx.input.getY(), 0);
      camera.unproject(touchPos);
      bucket.x = touchPos.x - 64 / 2;
   }



To make the bucket move with the keyboard, we write
if(Gdx.input.isKeyPressed(Input.Keys.LEFT)) bucket.x -= 200 * Gdx.graphics.getDeltaTime();
if(Gdx.input.isKeyPressed(Input.Keys.RIGHT)) bucket.x += 200 * Gdx.graphics.getDeltaTime();

To make the rain drops, we have to make a rectangle and randomly place raindrops inside of it while making the raindrops fall.

Lastly, to make sure that there isn’t any lost memory, we dispose of each of the sprites.

This connects back to the process of writing interpreters, as we also needed to allocate memory for each new variable we encountered in lab 5. The process of garbage collection and deallocating memory is also connected to writing interpreters, where it is a common feature. We’re having to write our own garbage collection here, which we would also need to do when creating an interpreter with that feature. We weren’t able to get into advanced features like this during class, so it’s a good extension of this idea.
