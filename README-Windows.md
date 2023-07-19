WIP WIP WIP do not read yet

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