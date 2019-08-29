# BootGenie
Patches for Boot Sector Games for Cheating

Boot Genie works on many 512-byte Boot Sector game titles for archaic x86 systems with proper BIOS support. Most effects are created to be valid at the same time.

## Introducing Boot Genie Game Ehnhancer for Boot Sector Games

With Boot Genie, you can patch certain game-play features and create special effects on a selection of available Boot Sector games found on the github ecosystem. These patches will change the original source, if you want to revert, just note the patches you have made and re-run them all with the -R option to 'patch.' You could also re-clone/update the repo as well. These patches use the standard 'patch' utility found in most *nix platforms

## Patching
run the patch utility and redirect in the patch. For example, if the game is tetranglix and you want to apply the time cheat, then patch the source with the following command:
 patch < tetranglix_time.patch

Reverting to the original source by removing this particular time cheat is as easy as:
 patch -R < tetranglix_time.patch

## Re-Assemble
Note that you are patching the source file, not the game image. You must reassemble the patched game in order to see your effects. An example of reassembling the tetranglix game after patching is the same as if you were to assemble it for the first time. One example with nasm is as follows:
 nasm -f bin tetranglix.asm -o tetranglix

## Playing
You can then flash to a real floppy drive or emulate in things such as Virtual Box and Qemu. A Qemu example of running one of these games after patching is:
 qemu-system-i386 -hda tetranglix

## Code Symbols
There are several types of codes that you can use to enhance the game-play elements with Boot Genie patches. Below are some quick visual cues as to what the code may do, and each code in the individual game sections will have further descriptions.

<img src=https://github.com/XlogicX/BootGenie/blob/master/invincible.png> - Invincibility <br>
<img src=https://github.com/XlogicX/BootGenie/blob/master/expert.png> - Harder Difficulty <br>
<img src=https://github.com/XlogicX/BootGenie/blob/master/lives.png> - More Lives <br>
<img src=https://github.com/XlogicX/BootGenie/blob/master/speed.png> - Speed Modifications <br>
<img src=https://github.com/XlogicX/BootGenie/blob/master/time.png> - Time Modifications <br>
<img src=https://github.com/XlogicX/BootGenie/blob/master/score.png> - Score Modifications <br>
<img src=https://github.com/XlogicX/BootGenie/blob/master/rules.png> - Rule/Logic Changes <br>
<img src=https://github.com/XlogicX/BootGenie/blob/master/multiplier.png> - Multipliers <br>
<img src=https://github.com/XlogicX/BootGenie/blob/master/color.png> - Color/UI Changes <br>
<img src=https://github.com/XlogicX/BootGenie/blob/master/powerup.png> - Better/Improved Powerups <br>
<img src=https://github.com/XlogicX/BootGenie/blob/master/level.png> - Level Changes

## Games:

### Tetranglix - https://github.com/shikhin/tetranglix/tree/85e65dba4a1c4569baef1275d5afe7859d626d03
* tetranglix_color.patch <img src=https://github.com/XlogicX/BootGenie/blob/master/color.png>
  * Just a pallet change to a brighter green environment
* tetranglix_multiplier.patch <img src=https://github.com/XlogicX/BootGenie/blob/master/multiplier.png>
  * Makes score increment by 255 points instead of just 1 point per vertical movement <br>
* tetranglix_square.patch <img src=https://github.com/XlogicX/BootGenie/blob/master/rules.png>
  * This makes every tetronimo a square <br>
* tetranglix_score.patch <img src=https://github.com/XlogicX/BootGenie/blob/master/score.png>
  * This makes the top score 1,000, instead of 100,000 <br>
* tetranglix_time.patch <img src=https://github.com/XlogicX/BootGenie/blob/master/time.png>
  * This makes the game slow down to half speed <br>

### Invaders - https://github.com/nanochess/Invaders/tree/0de3b3bb4ab03f1b9d4562e6ac05eec30f9c1168
* invaders_advancement.patch <img src=https://github.com/XlogicX/BootGenie/blob/master/rules.png>
  * Invaders advance down about a 1/3rd of the vertical distance for each horizontal swipe <br>
* invaders_lives.patch <img src=https://github.com/XlogicX/BootGenie/blob/master/lives.png>
  * 127 lives instead of the original 4 lives <br>
* invaders_speed.patch <img src=https://github.com/XlogicX/BootGenie/blob/master/speed.png>
  * Invaders move much slower than normal <br>

### fbird - https://github.com/nanochess/fbird/tree/7a7c27ac0081ea21b169964e2592a99d9b33eb9d
* fbird_faster.patch <img src=https://github.com/XlogicX/BootGenie/blob/master/speed.png> <img src=https://github.com/XlogicX/BootGenie/blob/master/expert.png>
  * The game plays much faster <br>
* fbird_morepipes.patch <img src=https://github.com/XlogicX/BootGenie/blob/master/score.png> <img src=https://github.com/XlogicX/BootGenie/blob/master/expert.png>
  * pipes come in much more frequently <br>
* fbird_pipe.patch <img src=https://github.com/XlogicX/BootGenie/blob/master/rules.png>
  * rediculous clearance in each pipe <br>
* fbird_highscore.patch <img src=https://github.com/XlogicX/BootGenie/blob/master/score.png>
  * Sets initial score to 65532, may not play well with other patches

### tronsolitare - https://github.com/XlogicX/tronsolitare/tree/37088a6498adab3deaa862ce6ffb25dbdd39606c
* tronsolitare_highscore.patch <img src=https://github.com/XlogicX/BootGenie/blob/master/score.png>
  * Initializes the score to 0x0e00 <br>
* tronsolitare_speed.patch <img src=https://github.com/XlogicX/BootGenie/blob/master/speed.png>
  * Game plays at half speed <br>
* tronsolitare_speed2.patch <img src=https://github.com/XlogicX/BootGenie/blob/master/speed.png>
  * Game plays at half speed and doesn't get incrementally faster <br>
* tronsolitare_noclipping.patch <img src=https://github.com/XlogicX/BootGenie/blob/master/invincible.png>
  * Bounds checking is off, you are invincible <br>
* tronsolitare_lowscore.patch <img src=https://github.com/XlogicX/BootGenie/blob/master/score.png>
  * Makes the winning highscore 0x2000 instead of 0xf600 <br>
* tronsolare_nopoison.patch <img src=https://github.com/XlogicX/BootGenie/blob/master/powerup.png>
  * Only good/green powerups will show up

### Boot-Man - https://github.com/guyhill/Boot-Man/tree/72d9d831887a5ff1b538ee3186236cef6de8cedb
* boot-man_speed.patch <img src=https://github.com/XlogicX/BootGenie/blob/master/speed.png>
  * Slows time down drastically
* boot-man_invincible.patch <img src=https://github.com/XlogicX/BootGenie/blob/master/invincible.png>
  * Turns collision detection routines off, effectively making BootMan invincible
* boot-man_level.patch <img src=https://github.com/XlogicX/BootGenie/blob/master/level.png>
  * New level, new color
* boot-man_strongpill.patch <img src=https://github.com/XlogicX/BootGenie/blob/master/powerup.png>
  * The power pills now last 8 times as long

### Snake - https://github.com/JulianSlzr/project512/tree/586c472b3e4999e536f208209c9da15a46985e16
* snake_speed1.patch <img src=https://github.com/XlogicX/BootGenie/blob/master/speed.png>
  * Makes game slower
* snake_speed2.patch <img src=https://github.com/XlogicX/BootGenie/blob/master/speed.png>
  * Makes game significantly slower
* snake_speed3.patch <img src=https://github.com/XlogicX/BootGenie/blob/master/speed.png>
  * Makes game nearly unplayably faster

## Patch Tips
* Try to keep patched version same amount of lines of code if possible, this allows for patches to be applied all at once and to not interfere with other patches/cheats.
