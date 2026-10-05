# Nowhere Twice

An endless piece of music that plays itself by walking across a pattern that never repeats.

![A Penrose tiling at night, with a trail of lit edges where the point has walked](screenshot.jpg)

A point walks across a quasicrystal tiling, and every edge it steps along sounds a note. Nothing is random. Every note is computed from the time elapsed since the piece began, at 21:25 UTC on 5 October 2026, so anyone listening at the same moment hears the same thing.

## Run it

Open `index.html` in a browser and press **Listen**.

It is a single file with no build step and no dependencies. The two typefaces load from Google Fonts and fall back to system fonts when offline.

## Controls

| Input | What it does |
| --- | --- |
| Drag | Look around. The view drifts back to the point when you let go. |
| Scroll or pinch | Zoom |
| `Space` | Sound on or off |
| `1` `2` `3` `4` | 5-, 7-, 8- and 12-fold symmetry |
| `G` | Show the grid the tiling is built from |
| `?` or `I` | About |
| `F` | Full screen |

The symmetry is also kept in the address, so `index.html#7` opens the seven-fold tiling.

## How it works

**The tiling.** The pattern is built with de Bruijn's multigrid method. Take *n* families of evenly spaced parallel lines, each family turned by the same angle from the last. Every place two lines cross becomes one rhombus. Five families whose offsets sum to zero give a Penrose tiling. Seven give a seven-fold tiling, and four or six families (at 45° or 30° to each other) give eight-fold and twelve-fold ones. Each of these is a flat slice through the integer lattice in *n* dimensions, and the readout in the top right corner shows the point's *n* integer coordinates there.

**The walk.** The point moves smoothly across the grid. Each time it crosses a line of one family, the matching coordinate changes by one and the point steps along one edge of the tiling. That step is a note. Turn on the grid to watch it happen.

**The tuning.** Each family of lines has one pitch. The pitches are stacked in pure 3:2 fifths from 220 Hz and folded into a single octave, so five families give a pentatonic scale and seven give a Lydian one. Crossing a line one way sounds the upper octave, and crossing it the other way sounds the lower. Each vertex also has a position in the dimensions the slice leaves out. Vertices near the centre of that hidden region are centres of local symmetry, and landing on one adds a bass note. The same distance sets how loud and bright every other note is.

**The orbit.** The point's path is the sum of three circular motions with periods of 610 s, 610/φ s and 610/φ³ s, where φ is the golden ratio, plus a slow straight drift. Because of the drift the path never closes. Speed and heading change all the time, so each voice speeds up, slows down, falls silent and comes back in the other octave.

**The colours.** Each tile is tinted by its position in the hidden dimensions, so tiles with similar surroundings get similar colours.

## About

Made by Claude in October 2026, in answer to an open invitation to build whatever it wanted.
