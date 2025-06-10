---
title: "Getting Started"
weight: 1
# geekdocFlatSection: true
# geekdocToc: 6
# geekdocHidden: false
---

Using PGEtinker should be pretty straight forward. In it's default
layout you type code in the left, click the Run button to see it
running on the right. The rest is going to be dictated by your familiarity,
or lack thereof, of C/C++.

## Libraries

PGEtinker currently supports the following libraries:

- [miniaudio (v0.11.21)](https://miniaud.io/docs/manual/index.html)
- [olcPGEX_Gamepad (master@f5958a5)](https://github.com/gorbit99/olcPGEX_Gamepad)
- [olcPGEX_MiniAudio (v1.5 ... v2.0)](https://github.com/Moros1138/olcPGEX_MiniAudio)
- [olcPixelGameEngine (v2.23 ... v2.29)](https://github.com/OneLoneCoder/olcPixelGameEngine)
- [olcSoundWaveEngine (v0.02)](https://github.com/OneLoneCoder/olcSoundWaveEngine)
- [raylib (v5.5-web-patched)](https://www.raylib.com/)
- SDL v1
- [SDL v2](https://wiki.libsdl.org/SDL2/FrontPage)
    - SDL2_gfx
        - Graphics Primitives
        - Surface Rotozoomer
        - Framerate Control
        - MMX image filters
        - Built-in 8x8 Font
    - SDL2_image (gif,jpg,png)
    - SDL2_mixer
    - SDL2_net
    - SDL2_ttf
- [SDL v3](https://wiki.libsdl.org/SDL3/FrontPage)

PGEtinker detects which header files are included and links in the appropriate
libraries.

**To use:** miniaudio
```cpp
#define MINIAUDIO_IMPLEMENTATION
#include "miniaudio.h"
```

**To use:** olcPGEX_Gamepad
```cpp
#define OLC_PGE_GAMEPAD
#include "olcPGEX_Gamepad.h"
```

**To use:** olcPGEX_MiniAudio
```cpp
#define OLC_PGEX_MINIAUDIO
#include "olcPGEX_MiniAudio.h"
```

**To use:** olcPixelGameEngine
```cpp
#define OLC_PGE_APPLICATION
#include "olcPixelGameEngine.h"
```

**To use:** olcSoundWaveEngine
```cpp
#define OLC_SOUNDWAVE
#include "olcSoundWaveEngine.h"
```

**To use:** SDL v2 and extensions
```cpp
#include <SDL2/SDL.h>
#include <SDL2/SDL_image.h>
#include <SDL2/SDL_mixer.h>
#include <SDL2/SDL_net.h>
#include <SDL2/SDL_ttf.h>
```

**To use:** SDL v3
```cpp
#include <SDL3/SDL.h>
```

## Choosing Library Versions

PGEtinker lets you choose which version of certain libraries
to use. Go into the Settings Dialog. You will see the current
versions of the libraries in a list.

You can change which versions are in use by clicking the "Select
Library Versions" button.

![Settings Dialog with Libraries Focused](/images/settings-dialog-libraries.png)
