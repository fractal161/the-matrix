# The Matrix

> Matrix (may-trix): n. the rectangular arrangement of cells creating the active game area, usually 10 columns wide by 20 rows high. Tetriminos fall from the top-middle just above the Skyline (off-screen) to the bottom.
> *\- Blue Planet Software, 2009*

> No one can be told what the Matrix is. You have to see it for yourself.
> *\- Morpheus, 1999*

A NES Tetris romhack that lets you see *everything*.

## Tools

### NESFab

[NESFab](https://pubby.games/nesfab.html) is a programming language specifically targeted for NES games. It abstracts many low-level tasks associated with 6502 programming, like memory allocation and bank-switching, while maintaining [reasonable performance](https://pubby.games/codegen.html) when compared to other modern approaches.

I've experimented with it on a couple of projects (like [rollTool](https://github.com/fractal161/rollTool)) and have enjoyed it immensely, finding it strikes a nice balance between high-level logic and the low-level control I expect when working with the NES, so I wanted to try it out on a larger project.

### NEXXT

[NEXXT Studio](https://frankengraphics.itch.io/nexxt) is a graphics editor for NES games. Its main feature is enforcing the graphical restrictions of the NES, which include [palette](https://www.nesdev.org/wiki/PPU_palettes) and [tile](https://www.nesdev.org/wiki/PPU_pattern_tables) restrictions, so anything you can design here can necessarily be replicated on original hardware.

Prior to this, I had been using GIMP to edit the [pattern tables](https://www.nesdev.org/wiki/PPU_pattern_tables) and GHex to edit [nametables](https://www.nesdev.org/wiki/PPU_nametables), which had many inconveniences, so I was particularly eager to make the leap to something more tailor-made to the NES game use-case.

### Famitracker

*Note: not really using this for the sfx since it can't exactly recreate certain details*

[Famitracker](http://famitracker.com/) is a popular music editor for composing NES/Famicom music. Like NEXXT, it's designed with the limitations of the target hardware in mind, and allows you to control the raw audio channels directly while still offering higher-level primitives than the direct [APU registers](https://www.nesdev.org/wiki/APU#Registers).

This project rewrites the music and sound effects using Famitracker, which are then integrated through NESFab's PUF music engine. The NES Tetris audio engine is probably the most confusing part of the code, feeling especially hacky and scattered, so it's an ideal candidate to be replaced.

## Setup

This project uses [submodules](https://git-scm.com/book/en/v2/Git-Tools-Submodules), so you'll want to clone this repository using `git clone --recurse-submodules`, or use `git submodule update --init --recursive` if you've already cloned it. From there, enter the `nesfab` directory and follow its [build instructions](https://github.com/pubby/nesfab?tab=readme-ov-file#building). To work with graphics or audio, you'll want to install [NEXXT](https://frankengraphics.itch.io/nexxt) or [Famitracker](http://famitracker.com/) respectively, though this isn't required to build the project.

From here, `the-matrix` can be built by running `make`.

## Benchmarks

Coming soon!
