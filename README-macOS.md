# Requirements

- It's expected that you have `cmake` and `ninja` in your PATH. Install them via `homebrew` or look in `~/Qt/Tools/`.
- It's expected that you have a working compiler. This this compile ?

```cpp
#include <vector>

int main() {
    return 0;
}
```

```$ clang++ main.cpp```

# Manual approach

Here we set up the env in a terminal and then launch vscode from within this env. Be sure you don't have any vscode instance running already!

Adjust the paths as needed.

```bash
export PATH=~/Qt/6.5.1/macos/:$PATH
cd blog-vscode-template/ # If you're not inside it already
code .
```

Now go ahead and choose either `debug`, `release` or `profile` preset, from the cmake toolbar at the bottom of your vscode window.

# Automatic approach

For this way, no Qt env variables need to be set. The advantage is you can start vscode from macOS launcher instead of terminal.

```
cd blog-vscode-template/ # If you're not inside it already
code .
```

Now open the `CMakeUserPresets.json` file and inspect the preset named `base-6.5.1-macos`.
Make sure the `CMAKE_PREFIX_PATH` is correctly pointing to your desired Qt. Edit it.

Note that typically CMakeUserPresets.json is not checked in to git, we have it here for example purposes. You are free to edit it. Put it in .gitignore so it's not deleted by mistake.

Now go ahead and choose either `debug-6.5.1-macos`, `release-6.5.1-macos` or `profile-6.5.1-macos` preset, from the cmake toolbar at the bottom of your vscode window. Do NOT chose the other presets (debug/release/profile), as those require env setup.
