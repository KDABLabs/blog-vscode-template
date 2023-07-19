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

# Semi-automatic approach

Here we'll let the IDE find the compiler for us. No need to call `vsvars64.bat`.

We still need, however, to set some Qt related variables:
- `QTDIR` is used for telling the debugger where to find Qt sources. So you can step into Qt.
- `PATH` Unlike macOS and Linux, Windows doesn't support rpath. For launching your application, the Qt libraries need to be in PATH as well.

```cmd
set QTDIR=C:\Qt\6.5.1\msvc2019_64\
set PATH=%PATH%;%QTDIR%\bin
cd blog-vscode-template/ # If you're not inside it already
code .
```

Now go ahead and choose either `debug-msvc`, `release-msvc` or `profile-msvc` preset, from the cmake toolbar at the bottom of your vscode window. Do NOT chose the other presets (debug/release/profile).
