# SpaceMonger Version 1.4.0 "living" fork

## Introduction

SpaceMonger 1 is a free old tool developed by [seanofw](https://github.com/seanofw) for keeping track of the disk space on your computer.

This fork is just a a version directly compabile with Visual Studio 2019 Community.

By compatible we mean:
* you can compile it
* you can modify it
* you can fork it

## How to

Install Visual Studio 2019 Community and select "Windows desktop development with C++" and inside, "C++ MFC".
![Visual Studio 2019 needed features](VS2019ModifyScreen.png?raw=true "Visual Studio 2019 needed features")

Then get the source (using your favorite tools) and double click SpaceMonger.sln. Visual Studio should open and you may be able to generate/build the project.

## Available modifications through branchs

The aim was to produce an everynight map of a share disk for users to better understand their usage. We needed autoscan, to hide filenames, a maximum file report and snapshot of the result even when run in session0 (Task Scheduler).

Every feature get its own branch:
* [OneProgramData](../../tree/OneProgramData): Show ProgramData only once. So not twice with dupes in C:\Users\All Users\.
* [SanitizeFilenames](../../tree/SanitizeFilenames): Remove filenames, but keep extensions when possible. Exception for the "Trash" filename. Be careful: we hope there is no secrets in users directory names or filename extensions like ".mypasswordis123456" or ".IHateMyBoss".
* [SetDensityTo3](../../tree/SetDensityTo3): If you only run SpaceMonger through a "virtual" account (Service or Task Scheduler) it may have different settings.
* [AutoScanC](../../tree/AutoScanC): Autostart a scan on "C:" on startup.
* [AutoCapture1920x1080](../../tree/AutoCapture1920x1080): Take a snapshot of the result at 1920x1080 resolution and write it to disk. Work even if in session0.

Then the [e-gaulue](../../tree/e-gaulue) is my all in one (through cherry-pick) + autoclose the application when finished.

## Project status

Not sure I'll have any time to follow this project, even if I think plenty of things could be done as:
* compilation optimisation
* use with command line options
* ...
