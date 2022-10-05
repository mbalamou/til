# RetroArch

* [Official site](https://www.libretro.com/)
* [Docs](https://docs.libretro.com/)
* [Flathub](https://flathub.org/apps/details/org.libretro.RetroArch)
* [ansible-workstation/games](https://github.com/andornaut/ansible-workstation/tree/master/roles/games)
* [BIOS on GitHub](https://github.com/Abdess/retroarch_system)
* [BIOS on Internet Archive](https://archive.org/download/RetroarchSystemFiles/Retroarch-System/)
* [/r/Roms Megathread](https://r-roms.github.io/)
* [Thumbnails](http://thumbnails.libretro.com/)

## Cores

* [Emulation General Wiki](https://emulation.gametechwiki.com/index.php/Main_Page)

Platform | Recommended core
--- | ---
Nintendo 64 (N64) | [Mupen64Plus-Next](https://docs.libretro.com/library/mupen64plus/)
Nintendo DS (DSi) | [DeSmuME](https://docs.libretro.com/library/desmume/)
Nintendo Entertainment System (NES) | [Mesen](https://docs.libretro.com/library/mesen/)
Nintendo Game Boy/Color (GB) | [SameBoy](https://docs.libretro.com/library/sameboy/)
Nintendo Game Boy Advance (GBA) | [mGBA](https://docs.libretro.com/library/mgba/)
Nintendo GameCube | [Dolphin](https://docs.libretro.com/library/dolphin/)
Sega Genesis | [Genesis Plus GX](https://docs.libretro.com/library/genesis_plus_gx/)
Sega Saturn | [Beetle Saturn](https://docs.libretro.com/library/beetle_saturn/) ([Mednafen](https://mednafen.github.io/))
Sony PlayStation (PSX) | [Beetle PSX HW](https://docs.libretro.com/library/beetle_psx_hw/) ([Mednafen](https://mednafen.github.io/))
Super Nintendo (SNES) | [higan Accuracy](https://docs.libretro.com/library/higan_accuracy/) or [Snex9x](https://docs.libretro.com/library/snes9x/)

## RetoArch on Xbox Series

* [gamr13.github.io](https://gamr13.github.io/)
* [Discord - Xbox Emulation Hub](https://discord.com/channels/1007582798598647889/1007590400220991549)
* [Install guide video (YouTube)](https://www.youtube.com/watch?v=dV9GyKicrAg)

### Configure permissions on USB disk drive

From a Windows 10 computer or VM:

1. Format the USB disk drive as GPT and NTFS
1. From "File Explorer": right-click on the drive, then click "Properties"
1. Select the "Security" tab, click "Advanced", then click "Change permissions"
1. Click the "Select a principal" link next to the "Principal" label
1. Click "Advanced", then click "Find Now"
1. Double-click on "ALL APPLICATION PACKAGES"
1. Tick the "Full control" checkbox, then click "OK"
1. Tick the "Replace all child object permission ..." checkbox, then click "OK"

This will produce an error about not being able to change permissions on the "System Volume Information" folder, click "Continue" to move forward.

## Recommended Games

Nintendo - Game Boy Advance
```
Advance Wars
Castlevania - Aria of Sorrow
Final Fantasy Tactics Advance
Final Fantasy VI Advance
Fire Emblem - The Sacred Stones
F-Zero - Maximum Velocity
Golden Sun
Gunstar Super Heroes
Kirby & the Amazing Mirror
Legend of Zelda, The - A Link to the Past & Four Swords
Legend of Zelda, The - The Minish Cap
Mario Golf - Advance Tour
Mario Kart - Super Circuit
Mario & Luigi - Superstar Saga
Mario Tennis - Power Tour
Mega Man Zero
Metroid - Zero Mission
Pokemon Emerald Version
Pokemon FireRed Version
Pokemon LeafGreen Version
Sonic Advance 3
Super Mario Advance 4 - Super Mario Bros. 3
Tetris Worlds
WarioWare, Inc. - Mega Microgames!
```
Nintendo - GameCube
```
Animal Crossing
Beyond Good & Evil
F-Zero GX
Legend of Zelda, The - The Wind Waker
Legend of Zelda, The - Twilight Princess
Luigi's Mansion
Mario Kart - Double Dash!!
Need for Speed - Underground 2
Paper Mario - The Thousand-Year Door
Pikmin 2
Sonic Adventure 2 - Battle
SSX Tricky
Super Mario Sunshine
Super Monkey Ball
Super Smash Bros. Melee
```
Nintendo - Nintendo 64
```
1080 Snowboarding
Banjo-Kazooie
Diddy Kong Racing
Donkey Kong 64
Excitebike 64
F-Zero X
GoldenEye 007
Kirby 64 - The Crystal Shards
Legend of Zelda, The - Majora's Mask
Legend of Zelda, The - Ocarina of Time
Mario Golf
Mario Kart 64
Mario Party 2
Mario Party 3
Mario Tennis
Paper Mario
Perfect Dark
Pilotwings 64
Pokemon Puzzle League
Star Fox 64
Star Wars - Rogue Squadron
Super Mario 64
Super Smash Bros.
Tony Hawk's Pro Skater 2
Turok - Dinosaur Hunter
Wave Race 64
WWF No Mercy
```
Nintendo - Super Nintendo Entertainment System
```
Chrono Trigger
Contra III - The Alien Wars
Donkey Kong Country 2 - Diddy's Kong Quest
Donkey Kong Country
EarthBound
Earthworm Jim
Final Fantasy III
Final Fantasy II
F-Zero
Gundam Wing - Endless Duel
Illusion of Gaia
Ken Griffey Jr. Presents Major League Baseball
Killer Instinct
Kirby's Dream Land 3
Legend of Zelda, The - A Link to the Past
Mega Man X2
Mega Man X
Ms. Pac-Man
NBA Jam - Tournament Edition
Secret of Mana
Sparkster
Star Fox
Street Fighter II Turbo - Hyper Fighting
Super Bomberman
Super Castlevania IV
Super Double Dragon
Super Mario All-Stars
Super Mario Kart
Super Mario RPG - Legend of the Seven Stars
Super Mario World 2 - Yoshi's Island
Super Mario World
Super Metroid
Super Punch-Out!!
Tecmo Super Bowl
Teenage Mutant Ninja Turtles IV - Turtles in Time
Teenage Mutant Ninja Turtles - Tournament Fighters
Terranigma
Tetris & Dr. Mario
```
Sega - Mega Drive - Genesis
```
Castlevania - Bloodlines
Desert Strike
Disney's Aladdin
Ecco the Dolphin
Evander Holyfield's "Real Deal" Boxing
Golden Axe
Gunstar Heroes
Herzog Zwei
Madden NFL 95
Michael Jackson's Moonwalker
Mortal Kombat II
MUSHA - Metallic Uniframe Super Hybrid Armor
NFL Sports Talk Football '93 Starring Joe Montana
NHL 94
Phantasy Star IV - The End of the Millennium
Revenge of Shinobi, The
Road Rash 3  - Tour de Force
Rocket Knight Adventures
Shining Force II
Shinobi III - Return of the Ninja Master
Sonic the Hedgehog 2
Sonic the Hedgehog 3
Sonic the Hedgehog
Streets of Rage 2
Teenage Mutant Ninja Turtles - The Hyperstone Heist
Thunder Force IV
ToeJam & Earl
Virtua Racing
World Series Baseball 98
X-Men 2 - Clone Wars
X-Men
```
Sega - Saturn
```
Astal
Burning Rangers
Daytona USA Championship Circuit Edition
Dragon Force
Guardian Heroes
Manx TT SuperBike
Marvel Super Heroes
Nights Into Dreams
Panzer Dragoon Saga
Radiant Silvergun
Rayman
Road Rash
Saturn Bomberman
Sega Rally Championship
Shining Force III
Shining The Holy Ark
Sonic Jam
Virtua Cop
Virtua Fighter 2
X-Men Children of the Atom
X-Men Vs Street Fighter
```
Sony - PlayStation (PSX)
```
Ace Combat 3 - Electrosphere
Bust-A-Move 2 - Arcade Edition
Castlevania - Symphony of the Night
Chrono Cross
Crash Bandicoot 2 - Cortex Strikes Back
Final Fantasy Tactics
Final Fantasy VII
Grandia
Gran Turismo 2 (Arcade Mode)
Gran Turismo 2 (Simulation Mode)
Mega Man X4
Metal Gear Solid
Spyro the Dragon
Street Fighter Alpha 2
Tekken 3
Tony Hawk's Pro Skater 2
```

## Troubleshooting

**Disable Kiosk Mode**

```
configFile=~/.var/app/org.libretro.RetroArch/config/retroarch/retroarch.cfg
sed -i 's/\(kiosk_mode_enable\s*=\).*/\1 "false"/g' ${configFile}
```

**Fix GameCube/Dolphin crash when running a game**

Disable "Rewind" for the dolphin-emu core by creating a [Core Override](https://docs.libretro.com/guides/overrides/) file:

```
# ~/.var/app/org.libretro.RetroArch/config/retroarch/config/dolphin-emu/dolphin-emu.cfg
rewind_enable = "false"
```

1. Navigate to Settings -> Drivers
1. Set "Video" to "d3d11"
1. Save the configuration, and restart RetroArch

**Fix GameCube/Dolphin copy/load error when running a game**

1. Navigate to Settings -> Directories
1. Set a "Cache" directory
1. Save the configuration, and restart RetroArch

The rom file must be *unzipped*, as well.
