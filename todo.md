# Important shortcuts

## i3

Win+Shift+E: logout
Win+Enter: terminal
Win+Space: launcher
Win+Shift+Space: desktop launcher
Win+F: toggle fullscreen
Win+W: tabbed layout
Win+E: tiled layout
Win+J: left a tab
Win+;: right a tab
Win+Shift+W: switch theme
Win+Shift+R: restart i3 and reload config
Win+1..0: switch to workspace 1..10
Win+Shift+1..0: move window to workspace 1..10
Win+Shift+T: brightness up
Win+Shift+G: brightness down
Win+Shift+Q: kill window

## urxvt

Alt+C: copy
Alt+V: paste

# TODO

- figure out urxvt keyboard-select
- set up polybar
- set up a symbol font for polybar?
- set up a firefox userContent.css themed from pywal
- set up a gtk theme based on pywal - need wpgtk command line tools
- pick a good file manager - thunar seems good? nautilus is p heavyweight
- or fix pcmanfm, icons are messed up and thumbnails don't work
- commit a script for the wallpaper conversion:
  mogrify -resize 800x480^ -gravity Center -extent 800x480 -path ~/Wallpapers/resized *.*
- set up music player, scenesat radio, animenfo radio. some cli player?
- do something to firefox or userChrome.css to shrink the UI? and remove toolbar things I don't need.
- set up screenshot and screen recording software
- set up retropie or some other emulator frontend
- set up dwarf fortress? any games playable on pi?
- set up vim to yank to system clipboard

- set up... something...so this can also be a usb keyboard? although I can just unplug the keyboard part and plug it into something else

For games, I'll need to control them sensibly-all I have is the touch screen and the keyboard, and the keyboard is full of chording magic that will mess up as soon as I try to play something.
- I have no modtap keys on the top or bottom rows. I could have a row of directions on e.g. the bottom row, and actions on the right hand bottom row, if the game is simple enough and configurable enough.
- a pure roguelike like nethack would also be fine
- Later, I could flash the keyboard to have a "gaming" layer that stays activated and just gives me standard keys.
  - installing what I need to reflash the keyboard on the pi itself would be optimal. right now for whatever reason I need my windows machine for the flashing to actually work.
  - I'll need a tiny wire or something to bridge the top-of-board reset pins (assuming they even work). Once I've done it once, I can include a reset chord into the keymap and make sure it works on both keyboard halves once unplugged (right now left half is determined by which has the usb plugged in; I think if I plug it into the right half I just get a mirrored keymap.)

- set up qmk firmware building and flashing on the pi

# Descent controls
qwer - rotation
vb - primary and secondary fire
uiop - strafing
nm - forward and back
ideally ty would select prev/next primary and gh prev/next secondary but those aren't binds, instead you have to have a bind for each weapon?

# NOTES

## Boot screens

I am working through https://yingtongli.me/blog/2016/12/21/splash.html for the boot screen setup. It goes into system folders and not dotfiles so I can't commit the changes.


Edit: I only did the paths up to the boot commandline, then used the below for other splashscreens

Okay, looks like I also need steps from https://github.com/raspberrypi/firmware/issues/580 because I set up using NOOBS.

Okay, and https://github.com/recalbox/recalbox-os/wiki/Skip-noobs-screen-(EN)
I used `boot_partition=6` and that worked.

Now going to create a copy of the plymouth theme so it isn't overwritten by updates:
https://www.raspberrypi.org/forums/viewtopic.php?t=197472

## Fonts

Installed Luxi Mono by going to wikipedia article and using the download link, then using `tar xjvf` and copying them to `~/.fonts`...? Then doing `fc-cache -v -f`?
