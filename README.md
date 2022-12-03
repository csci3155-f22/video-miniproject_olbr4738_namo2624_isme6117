# Principles and Practice in Programming Languages
# Mini-Project: Fall 2022

See [instructions.md](instructions.md) for submission instructions.

# LibGDX Game Tutorial

## Description

libGDX is a java game development framework that allows for making Windows, Linux, macOS, Android, and iOS. This repository includes a short tutorial on how to create a simple game on libGDX and what applications the process and coding has to CSCI 3155.
## Repository Organization

TODO: Replace this with a description of the organization of your repository.

## Building and Testing Instructions

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

## Presentation

TODO: Update the following links and remove this line.

- YouTube: https://youtu.be/TODO.
- Script: [script.md](script.md) or [script.pdf](script.pdf).
- Recording: [recording.mp4](recording.mp4).
- Slides (if you use them in your recording): [slides.pdf](slides.pdf) and slide sources (e.g., [slides.pptx](slides.pptx) or [slides.key](slides.key)).
