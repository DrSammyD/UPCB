# Universal PCB - by Toodles

A universal arcade stick controller PCB (UPCB - Universal Programmed Controller Board), designed to provide compatibility with as many devices as possible.

Imagine you buy a new Sega Saturn, and you've never had one before. You do already have an arcade stick with the UPCB in it that you play all the time on other systems. In order to use your stick on the new Saturn, you would need:

1. A Saturn plug, either from an extension cable or a sacrificed or dead controller. 
2. A DB-15 plug and hood. 

Total cost to play the stick on the new system: somewhere between $1 and $5. That's the goal of project, to support as many systems extremely cheaply.

Months down the road, a new game system, the XCube3, comes out and you want to play your stick on it. The XCube3 wasn't even out when your UPCB was made, so you think you're stuck. But, as soon as the controller protocol is supported in UPCB, here's what you have to do: 

1. Plug the stick into your PC with the same USB cable you use to play PC games and MAME. 
2. Run a program that updates the UPCB firmware.
3. Make a cable just like the above example for the Saturn.

The UPCB can be updated anytime without even needing to open the stick, and with the same USB cable you've already got.

## Supported systems

- Tested, working
  - Xbox
  - Gamecube
  - PC USB
  - PSX
  - PS2
  - PS3
  - NeoGeo
  - NES
  - SNES
  - Sega Saturn
  - Sega Genesis (3 and 6 button)
  - N64
  - TurboGrafx-16/PC Engine (2 and 6 button)

- Coded and believed to work, but not tested:
  - Sega MasterSystem
  - Atari Jaguar
  - 3DO
  - FM-Towns
  - X68000 (2 button)
  - Amiga CD32
  - Most old DB-9 controller systems from the 80s like Commodore 64s.

## Other features:
- On-the-Fly button remapping using a Programming button
  
  Hold the button you want to remap, press the programming button, hold down the buttons you want the original button to be (or none if you want the button disabled), release the programming button. Supported by most systems.
- Ability to make your mappings permanent

  Hold down the programming button, press start three times. Mappings are different for each system, so your NeoGeo mapping can be totally different from your PSX mapping.
- 'Tournament Mode' to disable or enable the Start button via keypress

  Hold Select and Start, press Up to enable Tournament Mode. To disable Tournament Mode, hold Select and Start and press Down. Tournament mode settings are NOT saved, so Tournament Mode is always disabled when you first plug the stick in.
- 'Turbo', adjustable button rapid fire

  Press Program by itself, and hold it. Press and hold the button you want to change the speed of. Press Up to make the speed faster, and Down to make the speed slower. 'No turbo' is the same as 'fastest turbo', so to turn it on initially, you'll need to go Down.

## Building

### Requirements:
- [Ninja](https://ninja-build.org/)
- Microchip C18 compiler (with pa optimisation enabled - available in trial version for 60 days)

To compile the upcb.hex file, first edit the `base.ninja` file, and change the `mlib` variable to point at your microchip c18 headers path, e.g. `mlib = c:/microchip/c18/h`

Then run:

`ninja.exe -f build?.ninja`

Where '?' is your target UPCB option:

- X for no options
- XP for programming button
- B for extra buttons
- BP for extra buttons and programming button
- L for status LEDS
- LP for status LEDS and programming button
