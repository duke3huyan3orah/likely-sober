# Likely Sober

A small 2D pixel-art platformer built with Godot and GDScript. Run and jump through the level, collect coins, and avoid the slime and the fall zone. If you die, the level restarts and your coin count resets.

Made for **Jumpstart - Haven**.

Play the game from here: https://dietcokegamedev.itch.io/likely-sober

## Features

- Animated knight character with idle, run, and jump animations
- Coin pickups with a score counter and pickup sound
- A patrolling slime enemy
- A camera that follows the player
- A brief slow-motion effect on death, followed by an automatic restart
- Background music

## Controls

| Action | Keys |
| --- | --- |
| Move left | A or Left Arrow |
| Move right | D or Right Arrow |
| Jump | Space, W, or Up Arrow |

You can jump while standing on the ground or a platform.

## Run locally

### Requirements

- [Godot Engine 4.7](https://godotengine.org/download/), standard edition. The project uses GDScript, so the .NET edition is not required.
- Git to clone the repository, or download and extract the ZIP from GitHub instead.

The project is configured for Godot 4.7 with the Mobile renderer. Use that version to match the project settings; compatibility with older versions is not guaranteed.

### 1. Get the project

```sh
git clone https://github.com/duke3huyan3orah/likely-sober.git
cd likely-sober
```

If you downloaded the ZIP, extract it and use the extracted folder for the following steps.

### 2. Open it in Godot

1. Launch Godot and click **Import** in the Project Manager.
2. Select the `project.godot` file in the repository folder.
3. Import and open the project.
4. Wait for Godot to finish importing the sprites, fonts, and audio.

All game assets and scripts are included in the repository. There are no npm, pip, or other package-install steps.

### 3. Play

Press **F5** or click **Run Project**. The main scene is `scenes/game.tscn`.

If Godot asks you to choose a main scene, select `scenes/game.tscn`. Press **F8** to stop the game from the editor.

### Optional: use the command line

With the Godot editor executable available as `godot` in your terminal, run these commands from the repository folder:

```sh
# Import assets before the first run.
godot --path . --import

# Start the game.
godot --path .
```

To open the editor instead:

```sh
godot --path . --editor
```

If your executable is named `godot4`, use that instead of `godot`. You can also substitute the full path to the Godot executable. On macOS, the executable inside the app bundle is `Godot.app/Contents/MacOS/Godot`.

See the [Godot command-line documentation](https://docs.godotengine.org/en/stable/tutorials/editor/command_line_tutorial.html) for platform-specific details.

## Editor time-tracking plugin

The repository includes the **Godot Super-Wakatime** editor plugin, enabled in `project.godot`. It tracks development time and is not required to play the game.

If it prompts for an API key and you only want to run or explore the game, disable **Godot Super-Wakatime** under **Project > Project Settings > Plugins**. If you want to use time tracking, follow the [included plugin setup instructions](addons/godot_super-wakatime/README.md).

## Project structure

```text
likely-sober/
├── project.godot            # Godot project settings and input bindings
├── default_bus_layout.tres  # Audio bus configuration
├── scenes/                 # Level and reusable game objects
│   ├── game.tscn           # Main level
│   ├── player.tscn         # Player character
│   ├── coin.tscn           # Collectible coin
│   ├── slime.tscn          # Enemy
│   ├── killzone.tscn       # Death trigger and restart timer
│   ├── platform.tscn       # Platform
│   └── music.tscn          # Autoloaded background music
├── scripts/                # Movement, scoring, enemy, and death logic
├── assets/                 # Sprites, fonts, music, and sound effects
└── addons/                 # Editor time-tracking plugin
```

## Troubleshooting

- **Godot cannot find a resource or scene:** open the project in the editor and let asset importing finish before running it. If the main scene is missing, select `scenes/game.tscn` again.
- **The game fails to start with a graphics-driver error:** try selecting the **Compatibility** renderer in Godot, then restart the editor. The repository defaults to the Mobile renderer.
- **`godot` is not found in the terminal:** use the editor's Import/Run workflow, add the executable to your PATH, or use its full path in the commands above.

## License

No project-level license is currently included in this repository. The bundled Godot Super-Wakatime plugin has its own [MIT license](addons/godot_super-wakatime/LICENSE); that license does not establish the license of the game or its assets.
