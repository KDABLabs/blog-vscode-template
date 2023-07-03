# hello_world

This small program is a template for working on Qt6 projects with Microsoft Visual Compiler and Visual Studio Code IDE.

## Requirements

In order for the template to work, you need to setup the environment on a console or a script, and run visual studio code from there.

Small cmd script example:
```
"C:\Program Files\Microsoft Visual Studio\2022\Professional\VC\Auxiliary\Build\vcvars64.bat
set QTDIR=C:\Qt\6.5.1\msvc2019_64\
set PATH=%PATH%;%QTDIR%\bin
```

Then, you can start Visual Studio Code from the command line:
```
code .
```

> Note: it's important to define the `QTDIR` environment variable, as it's used by the setup

## Microsoft C/C++ extension vs clangd extension

This template is currently using the clangd extension for code completion and navigation. You can use the official Microsoft one if you prefer, but checking out eab93db2dabe4bcfa3b75447a97d60ae4094a172.

I personnaly prefer the clangd extension for 2 main reasons:
- speed: the navigation and usage is faster (for me) than the Microsoft extension
- inlay hints: it can show you some interesting hints, like the name of the arguments for a method call, or the type of an auto

The Microsoft ones has also some interesting features, like the ability to create the definition of a method in the source file, from the declaration. Best is for you to test and find the one that fits you better.

> Note: even with the clang extension, you still need the Microsoft one for compiling and debugging, but the intellisense is disabled (see in settings.json)

## Setup your own project

This project is just a template, you can reuse it in your own project. You'll need to:
- copy the .vscode directory
- copy or create the CMakePresets.json file
- copy the qt6.natvis file


