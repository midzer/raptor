# Raptor
Based on the reverse-engineered codebase from Raptor Call Of The Shadows by nukeykt

## Media
Click on the thumbnail to watch some videos showing the project in action  

[![IMAGE ALT TEXT HERE](https://img.youtube.com/vi/Nt2HfchiudY/0.jpg)](https://www.youtube.com/channel/UCedmTTlonJK5DvkiMpA_teQ)
## Information
Original Raptor Call Of The Shadows author Scott Host is working on a new modernized version of the classic called Raptor Remixed. If you are a Raptor fan it would be cool if you would support the project on Kickstarter. For more information visit [www.mking.com](https://www.mking.com)

## Quick start
Release builds are available for Windows and macOS.
All release builds contain only the assets (GLB files) of the shareware version 1.2.
If you want to play the full version you have to get the assets (GLB files) of the full version 1.2 yourself and copy them to the installation directory.
To download the latest release build for your platform, click [Download](https://github.com/skynettx/raptor/releases/latest).
Then install the downloaded release build on your system by following the instructions of the installer.
That's it now Raptor is ready to play.
For those who want to build themselves or who want more configuration information, continue below otherwise you're done here.

## Installing
You need the original assets (GLB files) from Raptor Call Of The Shadows v1.2 shareware or full version.
Important only the DOS version v1.2 is compatible!
You have to take care of these files yourself.

### Shareware
1. Copy the following files to Raptor directory:  
   ```
   FILE0000.GLB  
   FILE0001.GLB  
   ```
2. Copy the `raptor.exe` (Windows) or `raptor` (Linux or macOS) and `SETUP(ADLIB).INI or SETUP(MIDI).INI` files from build directory to Raptor directory. 
   For Midi support over TinySoundFont copy the soundfont `TimGM6mb.sf2` from `include\TimGM6mb\` to Raptor directory.
   Under Windows copy the `SDL.dll` from `include\SDL2-devel-2.28.2-VC\SDL2-2.28.2\lib\x86\`
   `include\SDL2-devel-2.28.2-VC\SDL2-2.28.2\lib\x64\` folder or from `include\SDL2-devel-2.28.2-mingw\SDL2-2.28.2\i686-w64-mingw32\bin\` 
   `include\SDL2-devel-2.28.2-mingw\SDL2-2.28.2\x86_64-w64-mingw32\bin\`folder (depending on which version you prefer) to Raptor directory.
   Under Linux install lib-sdl2 from the packagemanager of your respective distro. When you use macOS install lib-sdl2 from dmg or from a packagemanager like brew etc. 
3. The final folder should look like this:  
   ```
   FILE0000.GLB  
   FILE0001.GLB  
   SDL2.dll (only under Windows required)  
   SETUP(ADLIB).INI or SETUP(MIDI).INI  
   TimGM6mb.sf2  
   raptor.exe (under Windows) or raptor (under Linux or macOS)
   ```

### Full version
1. Copy the following files to Raptor directory:  
   ```
   FILE0000.GLB  
   FILE0001.GLB  
   FILE0002.GLB  
   FILE0003.GLB  
   FILE0004.GLB  
   ```
2. Copy the `raptor.exe` (Windows) or `raptor` (Linux or macOS) and `SETUP(ADLIB).INI or SETUP(MIDI).INI` files from build directory to Raptor directory.
   For Midi support over TinySoundFont copy the soundfont `TimGM6mb.sf2` from `include\TimGM6mb\` to Raptor directory.
   Under Windows copy the `SDL.dll` from `include\SDL2-devel-2.28.2-VC\SDL2-2.28.2\lib\x86\`
   `include\SDL2-devel-2.28.2-VC\SDL2-2.28.2\lib\x64\` folder or from `include\SDL2-devel-2.28.2-mingw\SDL2-2.28.2\i686-w64-mingw32\bin\` 
   `include\SDL2-devel-2.28.2-mingw\SDL2-2.28.2\x86_64-w64-mingw32\bin\`folder (depending on which version you prefer) to Raptor directory.
   Under Linux install lib-sdl2 from the packagemanager of your respective distro. When you use macOS install lib-sdl2 from dmg or from a packagemanager like brew etc.
3. The final folder should look like this:  
   ```
   FILE0000.GLB  
   FILE0001.GLB  
   FILE0002.GLB  
   FILE0003.GLB  
   FILE0004.GLB  
   SDL2.dll (only under Windows required)  
   SETUP(ADLIB).INI or SETUP(MIDI).INI  
   TimGM6mb.sf2  
   raptor.exe (under Windows) or raptor (under Linux or macOS)
   ```

### Configuration
You can build or download [Raptor Setup](https://github.com/skynettx/raptorsetup.git) to create and edit the
`SETUP.INI`, or edit it manually as follows.
Rename the `SETUP(ADLIB).INI` or the `SETUP(MIDI).INI` file to `SETUP.INI` in Raptor directory.  
If you want Midi over the TinySoundFont lib rename the `TimGM6mb.sf2` to `SoundFont.sf2` or specify the filename in the `SETUP.INI` file:  
`SoundFont=SoundFont.sf2`  
You can use any other GM compatible soundfont in sf2 format. For a better Midi sound quality I recommend the FluidR3_GM.sf2.
This font is 140 MB in size, so it is not in the repository.  
To play with one of the following input devices set `Control=0` under the [Setup] section in the `SETUP.INI` file to:  
`Control=0` Keyboard  
`Control=1` Mouse  
`Control=2` Joystick (Game Controller)  
Haptic (Game Controller rumble support) can be switched off or on under the [Setup] section in the `SETUP.INI` file:  
`Haptic=0`  
`Haptic=1`  
If you want to turn off the menu pointer control via the joystick in mode `Control=2` and enable the new joystick menu control in all 
input modes, set under the [Setup] section in the `SETUP.INI` file:  
`joy_ipt_MenuNew=0`  
`joy_ipt_MenuNew=1`  
System Midi support (Windows Multimedia, Linux ALSA and macOS CoreAudio) can be switched off or on in the [Setup] section in the `SETUP.INI` file:  
`sys_midi=0`  
`sys_midi=1`  
For ALSA Midi support on Linux, install timidity and soundfont-fluid from the packagemanager of your distro. When timidity is running
get the timidity client and port with `aplaymidi -l` and set it in the [Setup] section in the `SETUP.INI` file:  
`alsa_output_client=128`  
`alsa_output_port=0`  
To display the text mode ending screen after the game quits in fullscreen mode set under the [Video] section in the `SETUP.INI` file:  
`txt_fullscreen=0`  
`txt_fullscreen=1`  

## Build
The project supports the compilers msvc, gcc and clang.  
When you have installed git on your system you can clone the repository by type in `git clone https://github.com/skynettx/raptor.git`.

### Windows
You can use the projectfile for Visual Studio 2022 under `msvc\` or the projectfile for CodeBlocks under `gcc\`.

### Linux
Please remember to install the required dependencies lib-sdl2. In some distros there is an extra libsdl2-dev package like Debian or Ubuntu.  
You can use the projectfile for CodeBlocks under `gcc\`.
Otherwise you can use cmake. To use cmake type in the root of the repository:   
```
mkdir build  
cd build  
cmake ..  
make  
```

### macOS
Install the required dependencies lib-sdl2. To build use cmake, type in the root of the repository:
```
mkdir build  
cd build  
cmake ..  
make  
```

## FAQ
1. No audio under Linux:  
Make sure you get all the necessary Alsa and or PulseAudio dependencies from the packagemanager of your distro. 
2. Where can i change the video settings:  
The video settings can be set in the config file `SETUP.INI`. To toggle fullscreen mode on edit under the [Video] section `fullscreen=0`
to `fullscreen=1`. Or aspect ratio mode off `aspect_ratio_correct=1` to `aspect_ratio_correct=0`. 

## Thanks
Special thanks to [nukeykt](https://github.com/nukeykt) and [wel97459](https://github.com/wel97459) for their great work on the reconstructed source code.
Big thanks to [Scott Host](https://www.mking.com) for his great support.
Also many thanks to [schellingb](https://github.com/schellingb) for the great TinySoundFont library and to all contributors from the
[chocolate-doom project](https://github.com/chocolate-doom) for the awesome libtextscreen. Furthermore, many thanks to Tim Brechbill for the TimGM6mb
soundfont.


 




