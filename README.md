<p align="center">
  <a href="https://amethyst.rs">
    <img
        alt="Amethyst"
        src="https://amethyst.rs/brand/logo-standard.svg"
        width="60"
    />
  </a>
</p>
<h1 align="center">
  Amethyst 2D Starter
</h1>

This project template will get you from 0 to drawing something on the screen in no time. If you're looking for a more in-depth introduction to the engine, please have a look at [our book](https://book.amethyst.rs/stable/)!

## Quickstart

- install [ffizer](https://github.com/ffizer/ffizer/)
  ```bash
  cargo install ffizer --force --features cli
  ```

- Generate the project project from the template

  ```sh
  ffizer apply -s https://github.com/davidB/amethyst-starter-2d.git --rev variant/ffizer -d my-game
  cd my-game
  ```

- View the content
  
  ```sh
  cat README.md
  ls
  ```

- Build and run the project

  ```sh
  cargo run
  ```

#### For Mac Users

This starter uses vulkan as a renderer by default. You'll want to change the backend to use `metal`, which can be done by opening the `Cargo.toml` file and changing

```toml
[features]
default = ["vulkan"]
```

to

```toml
[features]
default = ["metal"]
```

#### For Linux Users

You might need to install some dependencies. Please refer to [this section](https://github.com/amethyst/amethyst#dependencies) of the README for more details.

## Features

This project contains the minimum amount of code needed to draw sprites to the screen. Here's a small summary of what you'll find in the source files:

- `resources/display_config.ron`  
  Contains the window configuration (size, title).

- `src/main.rs`  
  Creates the render graph, adds the required bundles, builds the game data with our own state and finally, starts the game's main event loop.

- `src/state.rs`  
  Implements the main game state. In the `on_start` hook, the camera is initialized, and the sprites that will be drawn are loaded and their entities created.  
   In the `handle_event` hook, we print any keys that were pressed and close the window if the user presses escape or the OS requests that we quit.
