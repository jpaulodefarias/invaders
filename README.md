# Invaders

`invaders` is a small Space Invaders-style game that runs directly in your terminal. It is written in Rust and uses keyboard input, terminal rendering, and sound effects.

## Requirements

- Rust and Cargo (install the stable toolchain with [rustup](https://rustup.rs/))
- A terminal that supports raw mode and ANSI/alternate-screen output
- A terminal window at least 40 columns wide and 20 rows tall
- Working system audio for sound effects (optional; the game can still be played without sound on systems where audio playback is unavailable)

## Run the game

Clone the repository and enter the project directory:

```sh
git clone <repository-url>
cd invaders
```

Start the game with Cargo:

```sh
cargo run
```

Cargo downloads the Rust dependencies, builds the executable, and launches the game. The sound files are loaded using paths relative to the project directory, so run the command from the repository root.

For a faster launch after the first build, use the optimized release build:

```sh
cargo run --release
```

## Controls

| Key | Action |
| --- | --- |
| `Left Arrow` | Move left |
| `Right Arrow` | Move right |
| `Space` or `Enter` | Fire |
| `Esc` or `q` | Quit |

Destroy all invaders to win. The game ends when the invaders reach the bottom of the playfield.

## Development

Check the project without running it:

```sh
cargo check
```

Format the source code:

```sh
cargo fmt
```

Run the compiler's built-in lints:

```sh
cargo clippy
```

Build a distributable debug or release binary:

```sh
cargo build
cargo build --release
```

The release executable is written to `target/release/invaders`.

## Project layout

```text
src/
├── main.rs       # Terminal setup, input, game loop, and audio
├── frame.rs      # Playfield representation
├── render.rs     # Terminal rendering
├── player.rs     # Player movement, shots, and collisions
├── invaders.rs   # Invader movement and win/lose conditions
└── shot.rs       # Projectile behavior
sounds/           # WAV sound effects used by the game
```

## Troubleshooting

- If the display looks clipped, enlarge the terminal to at least 40×20 characters and run the game again.
- If sound is missing, verify that your operating system has an available audio output and that the terminal session is allowed to play audio. The WAV files are expected under `sounds/`.
- If the terminal is left in an unusual state after an interrupted run, run `reset` (Unix-like systems) or close and reopen the terminal.

## License

This project is released under the [MIT License](LICENSE).
