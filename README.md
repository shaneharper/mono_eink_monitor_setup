Mono E Ink Monitor Setup
========================

A lot of what follows regards configuring a computer to use a monochrome monitor for software development.

## Table of Contents
1. [Onyx Boox Mira monitor settings](#onyx-boox-mira-monitor-settings)
2. [Visual Studio](#visual-studio)
3. [Misc. Utilities](#misc-utilities)
   

## [Onyx Boox Mira](https://onyxboox.com/boox_mira) monitor settings

### Resolution
On Windows 11 using the native resolution of the panel and setting display scaling to 175% seems to work best. ([Onyx recommend](https://help.boox.com/hc/en-us/articles/4408558469652-What-is-the-recommended-resolution-for-Mira-) using 1400 x 1050 resolution with Microsoft Windows; I can't see any reason to use that "low" resolution though.)

The bezel of my display covers some of the edges of the E Ink panel. (The diagonal of the inside of the bezel excluding the rounded corners is 13.18" across while the panel is 13.3" along the diagonal.) I have set things up so that the edges of the panel that are covered by the bezel won't be used by running 2184 x 1626 pixels with the image centered and not scaled<!-- (so it won't fill the 2200 x 1650 panel)-->. I have used Intel Graphics Command Center to set up the custom resolution.

### Display Mode
Each display mode can be useful at times.

*Normal* (&#9635;<!-- Unicode character 9635 is "white square containing a small black square". xxx The symbol isn't quite right; the icon for the Normal display mode has rounded corners but Unicode character 9635 does not have rounded corners. Use an image (an SVG?) instead. -->) works well most of the time.

*Text* mode uses only black and white - no greys, no dithering.

The *Video* mode has less ghosting than Normal mode but has more dithering than the other modes.

The *Reading* (or *Slideshow*) mode displays shades of grey without noticeable dithering; it looks great but screen updates are way too slow for most interactive use.

### Foot pedal to request screen refresh
Refreshing the screen clears ghosting. Pressing a foot pedal is easier than having to reach for the button on the bottom right of the display.

Onyx's Mira Windows app allows a keyboard shortcut to be specified for refreshing the display. A foot pedal can be programmed to generate that shortcut. ([miractl](https://github.com/elithper/miractl) could be used instead of the app by Onyx; `miractl.py --clear` <!-- It's a shame it's "--clear" and not "--refresh"! --> refreshes the display.)

(Multiple foot pedals can be connected; One or more could be set up to change the display mode<!-- as an option to using the monitor's on-screen display-->.)


## Visual Studio

* Disable some syntax highlighting.
  <br>From `Tools / Options / Environment / Fonts and Colors` set `Item foreground` to `Automatic` (which will be black when using either the "Blue" or "Light" color themes) for each of the following in the `Display items` list:
  - C++ Keyword - Control
  - C++ new/delete Operator Functions
  - Keyword
  - Keyword - Control
  - Preprocessor Keyword
  <!-- (I find colouring those items unhelpful and distracting even on a color display.) -->


## Misc. utilities

* [Vim Mono E Ink Color Scheme](https://github.com/shaneharper/vim-mono_eink_color_scheme).
  <br>The color scheme includes support for [displaying diffs](https://github.com/shaneharper/vim-mono_eink_color_scheme#tips). (Many common color schemes use red for deleted lines and green for added lines which doesn't help on a monochrome display.)

* [ls command setup](https://github.com/shaneharper/dotfiles/blob/master/dircolors).
