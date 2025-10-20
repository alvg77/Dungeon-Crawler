# Terminal Based Dungeon Crawler Game

A C++ dungeon crawler game with a level editor for automatically generating maps. This is a project for my university
OOP course.

## 🚀 How to Start the Project

### 1. Prerequisites

Make sure the following are installed:

- [vcpkg](https://vcpkg.io/en/) package manager for C++

- A C++ compiler (e.g., GCC or Clang)
- Python (required for Conan)

---

### 2. Installing Dependencies and Building the Project

[You can follow this guide on installing packages with vcpkg](https://learn.microsoft.com/en-us/vcpkg/get_started/get-started?pivots=shell-bash)

**tl;dr**

Create `CMakeUserPresets.json` in the root of the project:

```json
{
  "version": 2,
  "configurePresets": [
    {
      "name": "default",
      "inherits": "vcpkg",
      "environment": {
        "VCPKG_ROOT": "<path to vcpkg>"
      }
    }
  ]
}
```

Configure the build using CMake:

```bash
cmake --preset=default
```

Build the project:

```bash
cmake --build build
```

The compiled executables will be located in their respective subdirectories in `build/`. For example, the game executable can be found in the `game/` subdirectory.

---

### 3. Ensure you have the required JSON files for the game

At the root of the project there should be a `data` folder. Inside it there will be 3 folders (a fourth one for the save
files will be created after saving the game for the first time). The 3 folders will be:

```
/levels
  level1.json
  level2.json
  ...
/items
  items1.json
  items2.json
  ...
/monsters
  monsters1.json
  monsters2.json
  ...
```

Each of those contains json files with data about a level in the game. Without those files you cannot start the game. As
of now there are 4 distinct levels that the player has to complete so each folder should contain 4 json files, each one
corresponding to a level. To create new maps for a level (1-4), you can use the level editor utility, which generates a
random map for the level, there you can also specify the number of monsters and treasures you can encounter on the
level.

---

### 4. Generating Documentation with Doxygen

1. **Install Doxygen and Graphviz**

   Visit the official websites to download and install the latest versions for your platform:

- [Doxygen](https://www.doxygen.nl/download.html)
- [Graphviz](https://graphviz.org/download/)

2. **Generate a Default Configuration File**

   From the project root directory, run:

   ```bash
   doxygen -g
   ```

   This creates a `Doxyfile` with default settings.

3. **Configure the `Doxyfile`**

   Open `Doxyfile` in a text editor and set key options such as:

   ```ini
   OUTPUT_DIRECTORY = docs
   RECURSIVE = YES
   EXCLUDE = conanfile.py \
             conanfile.txt \
             conandata.yml \
             conan_provider.cmake
   ```

4. **Generate Documentation**

   Run:

   ```bash
   doxygen Doxyfile
   ```

   The generated documentation will be in the `docs/html` folder. Open `index.html` in your browser to view it.
