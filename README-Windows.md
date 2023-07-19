# Requirements

- `cmake` and `ninja` in your PATH. See your `Qt\Tools\` folder or install them via `chocolatey` or equivalent.
- A working compiler. Be sure you enabled the C++ stuff when you installed Visual Studio.

# Manual approach

Here, we'll put the compiler (cl.exe) and Qt into PATH.
Adjust paths as needed.

```cmd
"C:\Program Files\Microsoft Visual Studio\2022\Professional\VC\Auxiliary\Build\vcvars64.bat
set QTDIR=C:\Qt\6.5.1\msvc2019_64\
set PATH=%PATH%;%QTDIR%\bin
```

Then, you can start Visual Studio Code from the same command line:
```cmd
cd blog-vscode-template/ # If you're not inside it already
code .
```

Be sure it wasn't running before, so it picks up the new env.

Now go ahead and choose either `debug`, `release` or `profile` preset, from the cmake toolbar at the bottom of your vscode window.

# Automatic approach

For this way, no Qt env variables need to be set. The advantage is you can start vscode from Windows start menu instead of terminal.

```
cd blog-vscode-template/ # If you're not inside it already
code .
```

Now open the `CMakeUserPresets.json` file and inspect the preset named `base-6.5.1-msvc`, on line 5.
Make sure the `CMAKE_PREFIX_PATH` is correctly pointing to your desired Qt. Edit it.

Note that typically CMakeUserPresets.json is not checked in to git, we have it here for example purposes. You are free to edit it. Put it in .gitignore so it's not deleted by mistake.

Now go ahead and choose either `debug-6.5.1-msvc`, `release-6.5.1-msvc` or `profile-6.5.1-msvc` preset, from the cmake toolbar at the bottom of your vscode window. Do NOT chose the other presets (debug/release/profile), as those require env setup.

> Note: It's still advised you set the `QTDIR` environment variable. It's used for telling the debugger where to find Qt sources. Ignore if you're not planing to debug into Qt libraries.