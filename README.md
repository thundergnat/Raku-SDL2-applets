# p6-SDL2-applets
Various little Raku SDL2 applets, mostly for Rosettacode entries.

* [forest-fire](#forest-fire)
* [raster-bars](#raster-bars)
* [pendulum](#pendulum)
* [polyspiral](#polyspiral)
* [whitenoise](#whitenoise)
* [vibrating-rectangles](#vibrating-rectangles)
* [sdl2ttf](#sdl2ttf)
* [abelian-sandpile](#abelian-sandpile)


---
## <a name="forest-fire"></a>forest-fire.p6

An SDL2 implementation of a "Forest fire" simulation. Parameters are set to give
about 10-15 frames per second (on my system), which seems to me to be the best
update rate. May need to be adjusted if updates are too slow or fast.

Change the $w, $h parameters to change update speed. Smaller numbers will run
faster but at lower resolution. Need not be square, but should be multiple of 4
for best rendering. Note that the display widow dimensions are independent of
the rendering buffer dimensions.

May also adjust tree spawn rate, "humidity" (the chance that a tree next to a
fire will resist catching fire) and fire spawn rate. The parameters have been
chosen so that things happen quickly but fires grow organically, and don't look
quite so programmed.

---
## <a name="raster-bars"></a>raster-bars.p6

Written for Rosettacode http://rosettacode.org/wiki/Raster_bars#Raku

Displays a series of randomly colored bars and scrolls them with an array of options.

Will adjust size to fill / fit window size.

Displays a simple frames-per-second calculation, updated every second.

- Use Up / Down arrows to change the scroll speed.
- Use Left / Right arrows to adjust the gap between the raster bars.
- Use Pg Up / Pg Dn to adjust raster bar height.
- Use Z / X to change the angle of the raster bars.
- Use Space bar to pause / resume scrolling.
- Use Left Ctrl to toggle the scroll direction.
- Press R to toggle Randomize on / off.
- If Randomize is active, adjust the randomize delay with < / >
- Press S to toggle Swaying on / off.
- If Swaying is active, adjust the period with D / F
- Press Q to exit.

May pass in options at the command line to select desired parameters. Setting
randomize to something less than 1 second may induce dizziness.

```
Usage:
  raster-bars.p6 [-b|--bar-height=<Int>] [-d|--dir=<Int>] [-s|--step=<Int>] [-g|--gap=<Int>] [-a|--angle=<Real>] [--sw|--sway=<Int>] [-r|--rnd=<Real>]

    -b|--bar-height=<Int>    Height of the individual "Raster bars", minimum 32 (pixels)
    -d|--dir=<Int>           Scroll direction: -1 is "up" 1 is "down"
    -s|--step=<Int>          Scroll speed (pixels per step
    -g|--gap=<Int>           Gap between bars (pixels)
    -a|--angle=<Real>        Angle to orient bars off horizontal (-45 to 45 degrees)
    --sw|--sway=<Int>        Swaying on / off
    -r|--rnd=<Real>          Delay between randomize events

```
---
## <a name="pendulum"></a>pendulum.p6

Written for Rosettacode http://rosettacode.org/wiki/Animate_a_pendulum#Raku

A simple animation of a pendulum in a gravitational field. Changing the window
size will change the period of the pendulum. (The length is tied to the window
height.)

---
## <a name="polyspiral"></a>polyspiral.p6

A useless but fun and kinda pretty implementation of a polyspiral in Raku
using SDL2 bindings. Generates a fully animated polyspiral. Slightly hard to
explain what a polyspiral is, easier to run it and see.

Written for Rosettacode http://rosettacode.org/wiki/Polyspiral#SDL_full_animation

By default, starts in a 900 x 900 pixel window, spiral made up of 240 line
segments, angle incrementing clockwise, at a moderately fast rate, with a
stationary center.

Window may be resized / maximized and the render will be re-centered and scaled
to mostly fill the window yet stay within the viewable bounds.

There are multiple controls to modify various parameters.

* Up and down arrows will increase / decrease the angle increment speed a single step at a time.
* Page up / Page down change the angle increment speed by 50 steps at a time.
* Left / Right arrows change the direction of increment counterclockwise / clockwise.
* Space bar toggles freeze angle update / set angle increment to minimum.
* Left Control changes from stationary center / rotating outer to (mostly) stationary outer / rotating center.
* plus key ( + ) will add 5 line segments, up to a maximum of 360, and will reset the palette.
* minus key ( - ) will remove 5 line segments, down to a minimum of 60, and will reset the palette.

Note that holding down the plus or minus key will slow down the rendering
substantially as the palette is recalculated every time the number of lines is
modified.

When the rotation is changed to be center based rather than outside based, the
image will seem to get a "wobble", especially during the first 10 or so wraps.
The image is not perfectly symmetrical (it is a spiral after all) and it is
particularly noticeable near the start, mostly because of the scaling changes to
keep the image inside the viewport.

The "wobble" is still there when the rotation is outside based, it is just much
less noticeable since it is on the rim rather than at the center.

The palette is rotated one step for every frame of rendering. Fewer lines will
result in a fairly fast rotate through the palette giving a trippy, flashy,
psychedelic effect, more lines will cause the rotation through a full cycle to
take longer (though still pretty groovy, baby!)

---
## <a name="whitenoise"></a>whitenoise.p6

Uploaded to Rosettacode http://rosettacode.org/wiki/Image_noise#Raku

Plain old static. A modification / update of the whitenoise.p6 demo included
with the SDL2::Raw module. Rosettacode requires the 320 x 240 dimensions but
will  run quite nicely at higher resolutions.

---
## <a name="vibrating-rectangles"></a>vibrating-rectangles.p6

Written for Rosettacode http://rosettacode.org/wiki/Vibrating_rectangles#SDL_Animation

Simple animation with a series of concentric rectangles that change color with a
rotating palette.

Will adjust size to fill / fit window size.

Displays a simple frames-per-second calculation, updated every second.

- Press space bar to reverse the palette rotation direction.
- Press Q to quit.

---
## <a name="sdl2ttf"></a>sdl2ttf.p6

Example script for SDL2-ttf module https://github.com/thundergnat/SDL2-ttf

Render a bunch of text textures and animate them.

Will adjust size to fill / fit window size.

Displays a simple frames-per-second calculation, updated every second.

- Press space bar change animation.
- Press Q to quit.

---
## <a name="abelian-sandpile"></a>abelian-sandpile.p6

Alternate example for Rosettacode http://rosettacode.org/wiki/Abelian_sandpile_model#SDL_Animation

Implements a fully animated Abelian sandpile model in SDL2. Pass in a stack size
to adjust how many particle to process - defaults to 10_000. More than about
48_000 will start to overflow the edges, which isn't a problem, but you won't be
able to see the patterns anyway.

---

## Author

Steve Schulze aka thundergnat

## License

Artistic 2.0; See LICENSE.
