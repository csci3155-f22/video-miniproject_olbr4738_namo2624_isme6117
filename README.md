# Principles and Practice in Programming Languages
# Mini-Project: Fall 2022

See [instructions.md](instructions.md) for submission instructions.

# LibGDX Game Tutorial

## Description

libGDX is a java game development framework that allows for making Windows, Linux, macOS, Android, and iOS. This repository includes a short tutorial on how to create a simple game on libGDX and what applications the process and coding has to CSCI 3155. 

We go through the process of installing libGDX, creating a project, and writing a very simple game. We have provided assets and sample code for our game so that anyone should be able to get it running. The game's concept is very straightforward; you move a bucket to catch falling water droplets on the screen. This basic game involves an important programming language concept: memory allocation (and deallocation). As part of our lab 5 assignment, we spent a lot of time on correctly handling memory in our interpreter, and in programming this game we must also correctly extend our memory with the right objects. Our game also includes an extension of that idea, deallocating and garbage collection. 

## Repository Organization

Resources - code and assets necessary for the game
[README.md](README.md) - description of the project, organization, instructions, and youtube link
[instructions.md](instructions.md) - submission instructions
[recording.mp4](recording.mp4) - video recording of the project
[script.md](script.md) - video script

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

- YouTube: https://youtu.be/N-xD24FUSMU.
- Script: [script.md](script.md).
- Recording: [recording.mp4](recording.mp4).
