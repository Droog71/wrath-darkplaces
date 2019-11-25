# wrath-darkplaces

This is the fork of [LordHavoc's DarkPlaces Quake engine](https://icculus.org/twilight/darkplaces/) that is used in the game [WRATH: Aeon of Ruin](http://wrath.game/).
It's based on the [13/05/2014 DarkPlaces source snapshot](https://icculus.org/twilight/darkplaces/files/darkplacesengine20140513.zip), with some minor additions and alterations.

## This repository
This repository contains the up-to-date version of the source code used to build the WRATH binaries. It'll be updated with every Steam/GOG update that changes the binaries.

Pull requests to this repository are **not** accepted.

## Building
Currently the only version of the executable on Steam/GOG is the WGL x64 build. SDL/SDL2 builds work on both Windows and Linux, but have some mouse-related issues in the UI. The Linux GLX build has slight sound issues with the ALSA backend.

This has not been built or tested on MacOS X yet, but it might work.

### Dependencies
(or at least what the Steam/GOG binaries are built and shipped with)
* `mingw-w64` / `gcc` (Visual Studio projects/builds are currently somewhat broken);
* `libjpeg` or `libjpeg-turbo`;
* `libogg`, `libvorbis` and `libvorbisfile`;
* `libpng 1.6`;
* `libfreetype`;
* `libd0_blind_id`;
* `libcurl`;
* `libSDL 1.2` or `libSDL 2.0` for the SDL/SDL2 builds.

### Instructions
1. Install dependencies (if you're using msys2, you can get most of these using pacman; some libraries are loaded dynamically and you can just copy the DLLs from the game folder, or from a DarkPlaces release); 
1. `cd` to this directory;
2. Run `make` to get the list of available targets.
3. `make` your desired target.

`cl-release`/`cl-debug` will build the WGL executable on Windows and the GLX executable on Linux. Use `sdl2-release`/`sdl2-debug` to build the SDL2 version. Remove the `2` for the SDL1.2 version.

## Running
Rename your binary to `wrath` (or `wrath.exe` on Windows), place it into the game directory and run it.

Alternatively instead of renaming you can pass `-wrath` as a command line parameter: `./darkplaces-sdl -wrath`.

## License
DarkPlaces and this fork are licensed under version 2 of the GNU General Public License. A copy of the license is included in this repository (see [`COPYING`](https://github.com/KillPixelGames/wrath-darkplaces/blob/master/COPYING)).
