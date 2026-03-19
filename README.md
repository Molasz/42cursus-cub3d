# cub3d

_This project has been created as part of the 42 curriculum by molasz-a & anovio-c._

> Part of [42 Barcelona — molasz-a](https://github.com/Molasz/42), a monorepo centralizing every project completed at 42 Barcelona.

## Description

**cub3d** is a 3D game project from the 42 curriculum, inspired by the classic game Wolfenstein 3D. The goal is to create a realistic 3D graphical representation of a maze from a 2D map using the principles of raycasting.

This project introduces students to the fundamentals of 3D rendering, including raycasting, texture mapping, and creating a real-time game loop. It uses the `MLX42` graphics library, a modern version of `minilibx`.

---

## Features

- **Map Parsing:** The program can parse a `.cub` file that describes the maze, including wall textures, floor and ceiling colors, and the player's starting position.
- **Raycasting Engine:** A raycasting engine is implemented to render the 3D perspective from the player's point of view.
- **Texture Mapping:** The walls of the maze are rendered with textures loaded from image files.
- **Player Movement:** The player can move forward, backward, left, and right, and can rotate the camera.
- **Minimap:** A 2D map of the maze is displayed on the screen for navigation.
- **Mouse Control:** The camera can be controlled with the mouse for a smoother experience.

---

## Architecture

![Skills](https://skillicons.dev/icons?i=c,linux)

The core of `cub3d` is its raycasting engine. For each vertical stripe of the screen, a ray is cast from the player's position to determine the distance to the nearest wall. This distance is then used to calculate the height of the wall slice to be drawn on the screen, creating the illusion of depth.

The project is structured as follows:

- **`main.c`**: Initializes the game, sets up the window, and starts the game loop.
- **`parser_map/`**: Contains the logic for reading and parsing the `.cub` map file.
- **`render/`**: Includes the raycasting engine and functions for drawing the scene and applying textures.
- **`controls/`**: Handles keyboard and mouse input for player movement and camera control.
- **`minimap.c`**: Renders the 2D minimap.
- **`handle_errors.c`**: Manages error messages and program termination.

The project relies on the `MLX42` library for window management, image handling, and event listening.

---

## ⚙️ Instructions

The project uses `MLX42`, which will be automatically downloaded and compiled by the `Makefile`.

```bash
# Compile the project (this will also build libft and MLX42)
make

# Cleanup object files
make clean

# Cleanup object files and the executable
make fclean

# Recompile the entire project
make re
```

### Usage

To start the game, provide a map file as an argument:

```bash
./cub3D maps/map.cub
```

---

_molasz-a | anovio-c · 42 Barcelona_
