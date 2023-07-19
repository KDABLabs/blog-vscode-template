# hello_world

This small program is a template for working on Qt6 projects with Visual Studio Code IDE.

`Windows`, `macOS` and `Linux` are supported. For Windows, we additionally set up debugger source mapping and support for Qt pretty printers.

We illustrate two approaches:
- Setting required `env variables` via terminal (such as Qt version and compiler)
- Letting the `IDE` set it up for you.


Click on the platform you're interested on to proceed:
- [README-Windows.md](README-Windows.md)
- [README-macOS.md](README-macOS.md)
- [README-Linux.md](README-Linux.md)


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
- copy or create the `CMakePresets.json` file
- copy or create the `CMakeUserPresets.json` file, however, do not commit it to your git repo, add it to .gitignore.
- copy the qt6.natvis file, if using the `MSVC` compiler


