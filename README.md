# p6-SDL2-applets
Various little Perl 6 SDL2 applets, mostly for Rosettacode entries.

## vibrating-rectangles.p6

Written for Rosettacode http://rosettacode.org/wiki/Vibrating_rectangles#SDL_Animation

Simple animation with a series of concentric rectangles that change color with a rotating palette.

Will adjust size to fill / fit window size.

Displays a simple frames-per-second calculation, updated every second.

- Press space bar to reverse the palette rotation direction.
- Press Q to quit.

## raster-bars.p6

Written for Rosettacode http://rosettacode.org/wiki/Raster_bars#Perl_6

Displays a series of randomly colored bars and scrolls them with an array of options.

Will adjust size to fill / fit window size.

Displays a simple frames-per-second calculation, updated every second.

- Use Up / Down arrows to change the scroll speed.
- Use Left / Right arroes to adjust the gap between the raster bars.
- Use Pg Up / Pg Dn to adjust raster bar height.
- Use Z / X to change the angle of the raster bars.
- Use Space bar to pause / resume scrolling.
- Use Left Ctrl to toggle the scroll direction.
- Press R to toggle Randomize on / off.
- If Randomize is active, adjust the randomize delay with < / >
- Press Q to exit.

May pass in options at the command line to select desired parameters. Setting randomize to something less than 1 second may induce dizziness.

```
Usage:
  raster-bars.p6 [-b|--bar-height=<Int>] [-d|--dir=<Int>] [-s|--step=<Int>] [-g|--gap=<Int>] [-a|--angle=<Int>] [-r|--rnd=<Real>]

    -b|--bar-height=<Int>    Height of the individual "Raster bars", minimum 32 (pixels)
    -d|--dir=<Int>           Scroll direction: -1 is "up" 1 is "down"
    -s|--step=<Int>          Scroll speed (pixels per step
    -g|--gap=<Int>           Gap between bars (pixels)
    -a|--angle=<Int>         Angle to orient bars off horizontal (-60 to 60 degrees)
    -r|--rnd=<Real>          Delay between randomize events
```

## polyspiral.p6

Written for Rosettacode http://rosettacode.org/wiki/Polyspiral#SDL_full_animation

Generates a fully animated polyspiral. Slightly hard to explain what a polyspiral is, easier to run it and see.

Will adjust size to fill / fit window size. Rotates the palette as it updates.
Displays a simple frames-per-second calculation, updated every second.

- Use the Up / Down arrow keys to speed up / slow down the update speed.
- Use PgUp / PgDn keys to increment / decrement animation speed by large amounts.
- Use Left / Right arrow keys to reverse the "direction" of angle change.
- Press Space bar to toggle animation / reset to minimum speed.
- Press Left Control key to toggle stationary / rotating center.
- Use + / - keys to add remove line segments.
- Press Q to exit.

## Author

Steve Schulze aka thundergnat

## License

Artistic 2.0; See LICENSE.
