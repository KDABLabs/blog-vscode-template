# Requirements

- `cmake` and `ninja` in your PATH. Usually this is the default, assuming you've installed them from distro packages.
- A working compiler, `gcc` or `clang` is fine. Check if this compiles:

```cpp
#include <vector>

int main() {
    return 0;
}
```

```$ g++ main.cpp```

# Manual approach

Here we set up the env in a terminal and then launch vscode from within this env. Be sure you don't have any vscode instance running already!

Adjust the paths as needed.

This assumes you're using Qt from the official installer. If however you're using Qt from your distro packages, chances are it's already in your PATH, which
makes it unnecessary to modify PATH.

```bash
export PATH=~/Qt/6.5.1/gcc_64/:$PATH
cd blog-vscode-template/ # If you're not inside it already
code .
```

Now go ahead and choose either `debug`, `release` or `profile` preset, from the cmake toolbar at the bottom of your vscode window.

# Automatic approach

For this way, no Qt env variables need to be set. The advantage is you can start vscode from a desktop shortcut instead of terminal.

```
cd blog-vscode-template/ # If you're not inside it already
code .
```

Now open the `CMakeUserPresets.json` file and inspect the preset named `base-6.5.1-linux`.
Make sure the `CMAKE_PREFIX_PATH` is correctly pointing to your desired Qt. Edit it.

Note that typically CMakeUserPresets.json is not checked in to git, we have it here for example purposes. You are free to edit it. Put it in .gitignore so it's not deleted by mistake.

Now go ahead and choose either `debug-6.5.1-linux`, `release-6.5.1-linux` or `profile-6.5.1-linux` preset, from the cmake toolbar at the bottom of your vscode window. Do NOT chose the other presets (debug/release/profile), as those require env setup.
