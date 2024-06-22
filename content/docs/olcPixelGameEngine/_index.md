---
weight: 2
bookFlatSection: true
title: "olc::PixelGameEngine"
---

# Introduction

{{< hint danger >}}
**THIS PAGE IS CURRENTLY UNFINISHED**  
Content on this page is not complete or finished. Check back later for updates.
{{< /hint >}}

## What is this?

olc::PixelGameEngine is a single file, cross platform graphics and userinput
framework used for games, visualisations, algorithm exploration and learning.
It was developed by YouTuber "javidx9" as an assistive tool for many of his
videos. The goal of this project is to provide high speed graphics with
minimal project setup complexity, to encourage new programmers, younger people,
and anyone else that wants to make fun things.

However, olc::PixelGameEngine is not a toy! It is a powerful and fast utility
capable of delivering high resolution, high speed, high quality applications
which behave the same way regardless of the operating system or platform.

olc::PixelGameEngine is packed with features, including window creation,
keyboard/mouse input, main game thread, timing, pixel drawing routines,
image/sprite loading and drawing routines, and a bunch of utility types to
make rapid development of games/visualisations possible.

## License (OLC-3)

olc::PixelGameEngine is released under the OLC-3 license, the terms are as follows:

Copyright 2018 - 2022 OneLoneCoder.com

Redistribution and use in source and binary forms, with or without modification,
are permitted provided that the following conditions are met:

1. Redistributions or derivations of source code must retain the above copyright
notice, this list of conditions and the following disclaimer.

2. Redistributions or derivative works in binary form must reproduce the above
copyright notice. This list of conditions and the following	disclaimer must be
reproduced in the documentation and/or other materials provided with the distribution.

3. Neither the name of the copyright holder nor the names of its contributors may
be used to endorse or promote products derived from this software without specific
prior written permission.

THIS SOFTWARE IS PROVIDED BY THE COPYRIGHT HOLDERS AND CONTRIBUTORS	"AS IS" AND ANY
EXPRESS OR IMPLIED WARRANTIES, INCLUDING, BUT NOT LIMITED TO, THE IMPLIED WARRANTIES
OF MERCHANTABILITY AND FITNESS FOR A PARTICULAR PURPOSE ARE DISCLAIMED. IN NO EVENT
SHALL THE COPYRIGHT	HOLDER OR CONTRIBUTORS BE LIABLE FOR ANY DIRECT, INDIRECT,
INCIDENTAL,	SPECIAL, EXEMPLARY, OR CONSEQUENTIAL DAMAGES (INCLUDING, BUT NOT LIMITED
TO, PROCUREMENT OF SUBSTITUTE GOODS OR SERVICES; LOSS OF USE, DATA, OR PROFITS; OR
BUSINESS INTERRUPTION) HOWEVER CAUSED AND ON ANY THEORY OF LIABILITY, WHETHER IN
CONTRACT, STRICT LIABILITY, OR TORT	(INCLUDING NEGLIGENCE OR OTHERWISE) ARISING IN
ANY WAY OUT OF THE USE OF THIS SOFTWARE, EVEN IF ADVISED OF THE POSSIBILITY OF
SUCH DAMAGE.


## Javid's Links

[Javidx9 on Youtube](https://www.youtube.com/javidx9)

[Javidx9extra on Youtube](https://www.youtube.com/javidx9extra)

[OneLoneCoder Discord Server](https://discord.gg/WhwHUMV)

[Javidx9 on Twitter](https://www.twitter.com/javidx9)

[Javidx9 on Twitch](https://www.twitch.tv/javidx9)

[OneLoneCoder on Discord](https://www.github.com/onelonecoder)

[OneLoneCoder Website](https://www.onelonecoder.com)

[Javidx9 on Patreon](https://www.patreon.com/javidx9)

[OneLoneCoder Community Blog](https://community.onelonecoder.com)

## Compiling in Linux

You will need a modern C++ compiler, so update yours!
To compile use the command:

```bash
g++ -o YourProgName YourSource.cpp -lX11 -lGL -lpthread -lpng -lstdc++fs -std=c++17
```

On some Linux configurations, the frame rate is locked to the refresh
rate of the monitor. This engine tries to unlock it but may not be
able to, in which case try launching your program like this:

```bash
vblank_mode=0 ./YourProgName
```

## Compiling in Code::Blocks on Windows

Well I wont judge you, but make sure your Code::Blocks installation
is really up to date - you may even consider updating your C++ toolchain
to use MinGW32-W64.

Guide for installing recent GCC for Windows:

https://www.msys2.org/

Guide for configuring code::blocks:

https://solarianprogrammer.com/2019/11/05/install-gcc-windows/

https://solarianprogrammer.com/2019/11/16/install-codeblocks-gcc-windows-build-c-cpp-fortran-programs/

Add these libraries to "Linker Options":
user32 gdi32 opengl32 gdiplus Shlwapi dwmapi stdc++fs

Set these compiler options: -std=c++17

## Compiling on Mac

### DISCLAIMER

olc::PixelGameEngine on Mac is EXPERIMENTAL and has bugs.

Yes yes, people use Macs for C++ programming! Who knew? Anyway, enough arguing, thanks
to Mumflr the PGE is now supported on Mac. Now I know nothing about Mac, so if you
need support, I suggest checking out the [instructions here](https://github.com/MumflrFumperdink/olcPGEMac)

```bash
clang++ -arch x86_64 -std=c++17 -mmacosx-version-min=10.15 -Wall -framework OpenGL -framework GLUT -framework Carbon -lpng YourSource.cpp -o YourProgName
```
## Compiling with Emscripten (New & Experimental)
	
Emscripten compiler will turn your awesome C++ PixelGameEngine project into WASM!
This means you can run your application in the browser, great for distributing
and submission in to jams and things! It's a bit new at the moment. 

```bash
em++ -std=c++17 -O2 -s ALLOW_MEMORY_GROWTH=1 -s MAX_WEBGL_VERSION=2 -s MIN_WEBGL_VERSION=2 -s USE_LIBPNG=1 ./YourSource.cpp -o pge.html
```

## Using stb_image.h
	
The PGE will load png images by default (with help from libpng on non-windows systems).
However, the excellent "stb_image.h" can be used instead, supporting a variety of
image formats, and has no library dependence - something we like at OLC studios ;)
To use stb_image.h, make sure it's in your code base, and simply:

```cpp
#define OLC_IMAGE_STB
```

Before including the olcPixelGameEngine.h header file. stb_image.h works on many systems
and can be [downloaded here](https://github.com/nothings/stb/blob/master/stb_image.h).

## Multiple cpp file projects?

As a single header solution, the OLC_PGE_APPLICATION definition is used to
insert the engine implementation at a project location of your choosing.
The simplest way to setup multifile projects is to create a file called
"olcPixelGameEngine.cpp" which includes the following:

```cpp
#define OLC_PGE_APPLICATION
#include "olcPixelGameEngine.h"
```

That's all it should include. You can also include PGEX includes and 
defines in here too. With this in place, you dont need to 
#define OLC_PGE_APPLICATION anywhere, and can simply include this 
header file as an when you need to.

##	Ports

olc::PixelGameEngine has been ported and tested with varying degrees of
success to: WinXP, Win7, Win8, Win10, Various Linux, Raspberry Pi,
Chromebook, Playstation Portable (PSP) and Nintendo Switch. If you are
interested in the details of these ports, come and visit the Discord!

##  Thanks
I'd like to extend thanks to Ian McKay, Bispoo, Eremiell, slavka, Kwizatz77, gurkanctn, Phantim,
IProgramInCPP, JackOJC, KrossX, Huhlig, Dragoneye, Appa, JustinRichardsMusic, SliceNDice, 
dandistine,	Ralakus, Gorbit99, raoul, joshinils, benedani, Moros1138, Alexio, SaladinAkara 
& MagetzUb for advice, ideas and testing, and I'd like to extend my appreciation to the
250K YouTube followers,	80+ Patreons, 4.8K Twitch followers and 10K Discord server members 
who give me	the motivation to keep going with all this :D

Significant Contributors: @Moros1138, @SaladinAkara, @MaGetzUb, @slavka, @Dragoneye, @Gorbit99,
@dandistine & @Mumflr

Special thanks to those who bring gifts!
GnarGnarHead.......Domina
Gorbit99...........Bastion, Ori & The Blind Forest, Terraria, Spelunky 2, Skully
Marti Morta........Gris
Danicron...........Terraria
SaladinAkara.......Aseprite, Inside, Quern: Undying Thoughts, Outer Wilds
AlterEgo...........Final Fantasy XII - The Zodiac Age
SlicEnDicE.........Noita, Inside
TGD................Voucher Gift
Dragoneye..........Lucas Arts Adventure Game Pack
Anonymous Pirate...Return To Monkey Island

Special thanks to my Patreons too - I wont name you on here, but I've
certainly enjoyed my tea and flapjacks :D

**In Memory of SaladinAkara 25.06.2023**


## Author

David Barr, aka javidx9, (c) OneLoneCoder 2018, 2019, 2020, 2021, 2022, 2023, 2024

## Example Program

```cpp
// O------------------------------------------------------------------------------O
// | Example "Hello World" Program (main.cpp)                                     |
// O------------------------------------------------------------------------------O

#define OLC_PGE_APPLICATION
#include "olcPixelGameEngine.h"

// Override base class with your custom functionality
class Example : public olc::PixelGameEngine
{
public:
	Example()
	{
		// Name your application
		sAppName = "Example";
	}

public:
	bool OnUserCreate() override
	{
		// Called once at the start, so create things here
		return true;
	}

	bool OnUserUpdate(float fElapsedTime) override
	{
		// Called once per frame, draws random coloured pixels
		for (int x = 0; x < ScreenWidth(); x++)
			for (int y = 0; y < ScreenHeight(); y++)
				Draw(x, y, olc::Pixel(rand() % 256, rand() % 256, rand() % 256));
		return true;
	}
};

int main()
{
	Example demo;
	if (demo.Construct(256, 240, 4, 4))
		demo.Start();
	return 0;
}
```

<!---

// O------------------------------------------------------------------------------O
// | olcPixelGameEngine INTERFACE DECLARATION                                     |
// O------------------------------------------------------------------------------O
#pragma region pge_declaration
namespace olc
{
	class PixelGameEngine;
	class Sprite;

	// Pixel Game Engine Advanced Configuration
	constexpr uint8_t  nMouseButtons = 5;
	constexpr uint8_t  nDefaultAlpha = 0xFF;
	constexpr uint32_t nDefaultPixel = (nDefaultAlpha << 24);
	constexpr uint8_t  nTabSizeInSpaces = 4;
	constexpr size_t OLC_MAX_VERTS = 128;
	enum rcode { FAIL = 0, OK = 1, NO_FILE = -1 };

	// O------------------------------------------------------------------------------O
	// | olc::Pixel - Represents a 32-Bit RGBA colour                                 |
	// O------------------------------------------------------------------------------O
#if !defined(OLC_IGNORE_PIXEL)
	struct Pixel
	{
		union
		{
			uint32_t n = nDefaultPixel;
			struct { uint8_t r; uint8_t g; uint8_t b; uint8_t a; };
		};

		enum Mode { NORMAL, MASK, ALPHA, CUSTOM };

		Pixel();
		Pixel(uint8_t red, uint8_t green, uint8_t blue, uint8_t alpha = nDefaultAlpha);
		Pixel(uint32_t p);
		Pixel& operator = (const Pixel& v) = default;
		bool   operator ==(const Pixel& p) const;
		bool   operator !=(const Pixel& p) const;
		Pixel  operator * (const float i) const;
		Pixel  operator / (const float i) const;
		Pixel& operator *=(const float i);
		Pixel& operator /=(const float i);
		Pixel  operator + (const Pixel& p) const;
		Pixel  operator - (const Pixel& p) const;
		Pixel& operator +=(const Pixel& p);
		Pixel& operator -=(const Pixel& p);
		Pixel  operator * (const Pixel& p) const;
		Pixel& operator *=(const Pixel& p);
		Pixel  inv() const;
	};

	Pixel PixelF(float red, float green, float blue, float alpha = 1.0f);
	Pixel PixelLerp(const olc::Pixel& p1, const olc::Pixel& p2, float t);


	// O------------------------------------------------------------------------------O
	// | USEFUL CONSTANTS                                                             |
	// O------------------------------------------------------------------------------O
	static const Pixel
		GREY(192, 192, 192), DARK_GREY(128, 128, 128), VERY_DARK_GREY(64, 64, 64),
		RED(255, 0, 0), DARK_RED(128, 0, 0), VERY_DARK_RED(64, 0, 0),
		YELLOW(255, 255, 0), DARK_YELLOW(128, 128, 0), VERY_DARK_YELLOW(64, 64, 0),
		GREEN(0, 255, 0), DARK_GREEN(0, 128, 0), VERY_DARK_GREEN(0, 64, 0),
		CYAN(0, 255, 255), DARK_CYAN(0, 128, 128), VERY_DARK_CYAN(0, 64, 64),
		BLUE(0, 0, 255), DARK_BLUE(0, 0, 128), VERY_DARK_BLUE(0, 0, 64),
		MAGENTA(255, 0, 255), DARK_MAGENTA(128, 0, 128), VERY_DARK_MAGENTA(64, 0, 64),
		WHITE(255, 255, 255), BLACK(0, 0, 0), BLANK(0, 0, 0, 0);
#endif
	// Thanks to scripticuk and others for updating the key maps
	// NOTE: The GLUT platform will need updating, open to contributions ;)
	enum Key
	{
		NONE,
		A, B, C, D, E, F, G, H, I, J, K, L, M, N, O, P, Q, R, S, T, U, V, W, X, Y, Z,
		K0, K1, K2, K3, K4, K5, K6, K7, K8, K9,
		F1, F2, F3, F4, F5, F6, F7, F8, F9, F10, F11, F12,
		UP, DOWN, LEFT, RIGHT,
		SPACE, TAB, SHIFT, CTRL, INS, DEL, HOME, END, PGUP, PGDN,
		BACK, ESCAPE, RETURN, ENTER, PAUSE, SCROLL,
		NP0, NP1, NP2, NP3, NP4, NP5, NP6, NP7, NP8, NP9,
		NP_MUL, NP_DIV, NP_ADD, NP_SUB, NP_DECIMAL, PERIOD,
		EQUALS, COMMA, MINUS,
		OEM_1, OEM_2, OEM_3, OEM_4, OEM_5, OEM_6, OEM_7, OEM_8,
		CAPS_LOCK, ENUM_END
	};

	namespace Mouse
	{
		static constexpr int32_t LEFT = 0;
		static constexpr int32_t RIGHT = 1;
		static constexpr int32_t MIDDLE = 2;
	};

	// O------------------------------------------------------------------------------O
	// | olc::HWButton - Represents the state of a hardware button (mouse/key/joy)    |
	// O------------------------------------------------------------------------------O
	struct HWButton
	{
		bool bPressed = false;	// Set once during the frame the event occurs
		bool bReleased = false;	// Set once during the frame the event occurs
		bool bHeld = false;		// Set true for all frames between pressed and released events
	};




	// O------------------------------------------------------------------------------O
	// | olc::vX2d - A generic 2D vector type                                         |
	// O------------------------------------------------------------------------------O
#if !defined(OLC_IGNORE_VEC2D)
	template <class T>
	struct v2d_generic
	{
		T x = 0;
		T y = 0;
		v2d_generic() : x(0), y(0) {}
		v2d_generic(T _x, T _y) : x(_x), y(_y) {}
		v2d_generic(const v2d_generic& v) : x(v.x), y(v.y) {}
		v2d_generic& operator=(const v2d_generic& v) = default;
		T mag() const { return T(std::sqrt(x * x + y * y)); }
		T mag2() const { return x * x + y * y; }
		v2d_generic  norm() const { T r = 1 / mag(); return v2d_generic(x * r, y * r); }
		v2d_generic  perp() const { return v2d_generic(-y, x); }
		v2d_generic  floor() const { return v2d_generic(std::floor(x), std::floor(y)); }
		v2d_generic  ceil() const { return v2d_generic(std::ceil(x), std::ceil(y)); }
		v2d_generic  max(const v2d_generic& v) const { return v2d_generic(std::max(x, v.x), std::max(y, v.y)); }
		v2d_generic  min(const v2d_generic& v) const { return v2d_generic(std::min(x, v.x), std::min(y, v.y)); }
		v2d_generic  cart() { return { std::cos(y) * x, std::sin(y) * x }; }
		v2d_generic  polar() { return { mag(), std::atan2(y, x) }; }
		v2d_generic  clamp(const v2d_generic& v1, const v2d_generic& v2) const { return this->max(v1).min(v2); }
		v2d_generic	 lerp(const v2d_generic& v1, const double t) { return this->operator*(T(1.0 - t)) + (v1 * T(t)); }
		T dot(const v2d_generic& rhs) const { return this->x * rhs.x + this->y * rhs.y; }
		T cross(const v2d_generic& rhs) const { return this->x * rhs.y - this->y * rhs.x; }
		v2d_generic  operator +  (const v2d_generic& rhs) const { return v2d_generic(this->x + rhs.x, this->y + rhs.y); }
		v2d_generic  operator -  (const v2d_generic& rhs) const { return v2d_generic(this->x - rhs.x, this->y - rhs.y); }
		v2d_generic  operator *  (const T& rhs)           const { return v2d_generic(this->x * rhs, this->y * rhs); }
		v2d_generic  operator *  (const v2d_generic& rhs) const { return v2d_generic(this->x * rhs.x, this->y * rhs.y); }
		v2d_generic  operator /  (const T& rhs)           const { return v2d_generic(this->x / rhs, this->y / rhs); }
		v2d_generic  operator /  (const v2d_generic& rhs) const { return v2d_generic(this->x / rhs.x, this->y / rhs.y); }
		v2d_generic& operator += (const v2d_generic& rhs) { this->x += rhs.x; this->y += rhs.y; return *this; }
		v2d_generic& operator -= (const v2d_generic& rhs) { this->x -= rhs.x; this->y -= rhs.y; return *this; }
		v2d_generic& operator *= (const T& rhs) { this->x *= rhs; this->y *= rhs; return *this; }
		v2d_generic& operator /= (const T& rhs) { this->x /= rhs; this->y /= rhs; return *this; }
		v2d_generic& operator *= (const v2d_generic& rhs) { this->x *= rhs.x; this->y *= rhs.y; return *this; }
		v2d_generic& operator /= (const v2d_generic& rhs) { this->x /= rhs.x; this->y /= rhs.y; return *this; }
		v2d_generic  operator +  () const { return { +x, +y }; }
		v2d_generic  operator -  () const { return { -x, -y }; }
		bool operator == (const v2d_generic& rhs) const { return (this->x == rhs.x && this->y == rhs.y); }
		bool operator != (const v2d_generic& rhs) const { return (this->x != rhs.x || this->y != rhs.y); }
		const std::string str() const { return std::string("(") + std::to_string(this->x) + "," + std::to_string(this->y) + ")"; }
		friend std::ostream& operator << (std::ostream& os, const v2d_generic& rhs) { os << rhs.str(); return os; }
		operator v2d_generic<int32_t>() const { return { static_cast<int32_t>(this->x), static_cast<int32_t>(this->y) }; }
		operator v2d_generic<float>() const { return { static_cast<float>(this->x), static_cast<float>(this->y) }; }
		operator v2d_generic<double>() const { return { static_cast<double>(this->x), static_cast<double>(this->y) }; }
	};

	// Note: joshinils has some good suggestions here, but they are complicated to implement at this moment, 
	// however they will appear in a future version of PGE
	template<class T> inline v2d_generic<T> operator * (const float& lhs, const v2d_generic<T>& rhs)
	{ return v2d_generic<T>((T)(lhs * (float)rhs.x), (T)(lhs * (float)rhs.y)); }
	template<class T> inline v2d_generic<T> operator * (const double& lhs, const v2d_generic<T>& rhs)
	{ return v2d_generic<T>((T)(lhs * (double)rhs.x), (T)(lhs * (double)rhs.y)); }
	template<class T> inline v2d_generic<T> operator * (const int& lhs, const v2d_generic<T>& rhs)
	{ return v2d_generic<T>((T)(lhs * (int)rhs.x), (T)(lhs * (int)rhs.y)); }
	template<class T> inline v2d_generic<T> operator / (const float& lhs, const v2d_generic<T>& rhs)
	{ return v2d_generic<T>((T)(lhs / (float)rhs.x), (T)(lhs / (float)rhs.y)); }
	template<class T> inline v2d_generic<T> operator / (const double& lhs, const v2d_generic<T>& rhs)
	{ return v2d_generic<T>((T)(lhs / (double)rhs.x), (T)(lhs / (double)rhs.y)); }
	template<class T> inline v2d_generic<T> operator / (const int& lhs, const v2d_generic<T>& rhs)
	{ return v2d_generic<T>((T)(lhs / (int)rhs.x), (T)(lhs / (int)rhs.y)); }

	// To stop dandistine crying...
	template<class T, class U> inline bool operator < (const v2d_generic<T>& lhs, const v2d_generic<U>& rhs)
	{ return lhs.y < rhs.y || (lhs.y == rhs.y && lhs.x < rhs.x); }
	template<class T, class U> inline bool operator > (const v2d_generic<T>& lhs, const v2d_generic<U>& rhs)
	{ return lhs.y > rhs.y || (lhs.y == rhs.y && lhs.x > rhs.x); }

	typedef v2d_generic<int32_t> vi2d;
	typedef v2d_generic<uint32_t> vu2d;
	typedef v2d_generic<float> vf2d;
	typedef v2d_generic<double> vd2d;
#endif



	


	// O------------------------------------------------------------------------------O
	// | olc::ResourcePack - A virtual scrambled filesystem to pack your assets into  |
	// O------------------------------------------------------------------------------O
	struct ResourceBuffer : public std::streambuf
	{
		ResourceBuffer(std::ifstream& ifs, uint32_t offset, uint32_t size);
		std::vector<char> vMemory;
	};

	class ResourcePack : public std::streambuf
	{
	public:
		ResourcePack();
		~ResourcePack();
		bool AddFile(const std::string& sFile);
		bool LoadPack(const std::string& sFile, const std::string& sKey);
		bool SavePack(const std::string& sFile, const std::string& sKey);
		ResourceBuffer GetFileBuffer(const std::string& sFile);
		bool Loaded();
	private:
		struct sResourceFile { uint32_t nSize; uint32_t nOffset; };
		std::map<std::string, sResourceFile> mapFiles;
		std::ifstream baseFile;
		std::vector<char> scramble(const std::vector<char>& data, const std::string& key);
		std::string makeposix(const std::string& path);
	};


	// O------------------------------------------------------------------------------O
	// | olc::Sprite - An image represented by a 2D array of olc::Pixel               |
	// O------------------------------------------------------------------------------O
	class Sprite
	{
	public:
		Sprite();
		Sprite(const std::string& sImageFile, olc::ResourcePack* pack = nullptr);
		Sprite(int32_t w, int32_t h);
		Sprite(const olc::Sprite&) = delete;
		~Sprite();

	public:
		olc::rcode LoadFromFile(const std::string& sImageFile, olc::ResourcePack* pack = nullptr);

	public:
		int32_t width = 0;
		int32_t height = 0;
		enum Mode { NORMAL, PERIODIC, CLAMP };
		enum Flip { NONE = 0, HORIZ = 1, VERT = 2 };

	public:
		void SetSampleMode(olc::Sprite::Mode mode = olc::Sprite::Mode::NORMAL);
		Pixel GetPixel(int32_t x, int32_t y) const;
		bool  SetPixel(int32_t x, int32_t y, Pixel p);
		Pixel GetPixel(const olc::vi2d& a) const;
		bool  SetPixel(const olc::vi2d& a, Pixel p);
		Pixel Sample(float x, float y) const;
		Pixel Sample(const olc::vf2d& uv) const;
		Pixel SampleBL(float u, float v) const;
		Pixel SampleBL(const olc::vf2d& uv) const;
		Pixel* GetData();
		olc::Sprite* Duplicate();
		olc::Sprite* Duplicate(const olc::vi2d& vPos, const olc::vi2d& vSize);
		olc::vi2d Size() const;
		std::vector<olc::Pixel> pColData;
		Mode modeSample = Mode::NORMAL;

		static std::unique_ptr<olc::ImageLoader> loader;
	};

	// O------------------------------------------------------------------------------O
	// | olc::Decal - A GPU resident storage of an olc::Sprite                        |
	// O------------------------------------------------------------------------------O
	class Decal
	{
	public:
		Decal(olc::Sprite* spr, bool filter = false, bool clamp = true);
		Decal(const uint32_t nExistingTextureResource, olc::Sprite* spr);
		virtual ~Decal();
		void Update();
		void UpdateSprite();

	public: // But dont touch
		int32_t id = -1;
		olc::Sprite* sprite = nullptr;
		olc::vf2d vUVScale = { 1.0f, 1.0f };
	};

	enum class DecalMode
	{
		NORMAL,
		ADDITIVE,
		MULTIPLICATIVE,
		STENCIL,
		ILLUMINATE,
		WIREFRAME,
	};

	enum class DecalStructure
	{
		LINE,
		FAN,
		STRIP,
		LIST
	};

	// O------------------------------------------------------------------------------O
	// | olc::Renderable - Convenience class to keep a sprite and decal together      |
	// O------------------------------------------------------------------------------O
	class Renderable
	{
	public:
		Renderable() = default;		
		Renderable(Renderable&& r) : pSprite(std::move(r.pSprite)), pDecal(std::move(r.pDecal)) {}		
		Renderable(const Renderable&) = delete;
		olc::rcode Load(const std::string& sFile, ResourcePack* pack = nullptr, bool filter = false, bool clamp = true);
		void Create(uint32_t width, uint32_t height, bool filter = false, bool clamp = true);
		olc::Decal* Decal() const;
		olc::Sprite* Sprite() const;

	private:
		std::unique_ptr<olc::Sprite> pSprite = nullptr;
		std::unique_ptr<olc::Decal> pDecal = nullptr;
	};



	// O------------------------------------------------------------------------------O
	// | olc::PixelGameEngine - The main BASE class for your application              |
	// O------------------------------------------------------------------------------O
	class PixelGameEngine
	{
	public:
		PixelGameEngine();
		virtual ~PixelGameEngine();
	public:
		olc::rcode Construct(int32_t screen_w, int32_t screen_h, int32_t pixel_w, int32_t pixel_h,
			bool full_screen = false, bool vsync = false, bool cohesion = false);
		olc::rcode Start();

	public: // User Override Interfaces
		// Called once on application startup, use to load your resources
		virtual bool OnUserCreate();
		// Called every frame, and provides you with a time per frame value
		virtual bool OnUserUpdate(float fElapsedTime);
		// Called once on application termination, so you can be one clean coder
		virtual bool OnUserDestroy();

		// Called when a text entry is confirmed with "enter" key
		virtual void OnTextEntryComplete(const std::string& sText);
		// Called when a console command is executed
		virtual bool OnConsoleCommand(const std::string& sCommand);


	public: // Hardware Interfaces
		// Returns true if window is currently in focus
		bool IsFocused() const;
		// Get the state of a specific keyboard button
		HWButton GetKey(Key k) const;
		// Get the state of a specific mouse button
		HWButton GetMouse(uint32_t b) const;
		// Get Mouse X coordinate in "pixel" space
		int32_t GetMouseX() const;
		// Get Mouse Y coordinate in "pixel" space
		int32_t GetMouseY() const;
		// Get Mouse Wheel Delta
		int32_t GetMouseWheel() const;
		// Get the mouse in window space
		const olc::vi2d& GetWindowMouse() const;
		// Gets the mouse as a vector to keep Tarriest happy
		const olc::vi2d& GetMousePos() const;

		static const std::map<size_t, uint8_t>& GetKeyMap() { return mapKeys; }

	public: // Utility
		// Returns the width of the screen in "pixels"
		int32_t ScreenWidth() const;
		// Returns the height of the screen in "pixels"
		int32_t ScreenHeight() const;
		// Returns the width of the currently selected drawing target in "pixels"
		int32_t GetDrawTargetWidth() const;
		// Returns the height of the currently selected drawing target in "pixels"
		int32_t GetDrawTargetHeight() const;
		// Returns the currently active draw target
		olc::Sprite* GetDrawTarget() const;
		// Resize the primary screen sprite
		void SetScreenSize(int w, int h);
		// Specify which Sprite should be the target of drawing functions, use nullptr
		// to specify the primary screen
		void SetDrawTarget(Sprite* target);
		// Gets the current Frames Per Second
		uint32_t GetFPS() const;
		// Gets last update of elapsed time
		float GetElapsedTime() const;
		// Gets Actual Window size
		const olc::vi2d& GetWindowSize() const;
		// Gets pixel scale
		const olc::vi2d& GetPixelSize() const;
		// Gets actual pixel scale
		const olc::vi2d& GetScreenPixelSize() const;
		// Gets "screen" size
		const olc::vi2d& GetScreenSize() const;
		// Gets any files dropped this frame
		const std::vector<std::string>& GetDroppedFiles() const;
		const olc::vi2d& GetDroppedFilesPoint() const;

	public: // CONFIGURATION ROUTINES
		// Layer targeting functions
		void SetDrawTarget(uint8_t layer, bool bDirty = true);
		void EnableLayer(uint8_t layer, bool b);
		void SetLayerOffset(uint8_t layer, const olc::vf2d& offset);
		void SetLayerOffset(uint8_t layer, float x, float y);
		void SetLayerScale(uint8_t layer, const olc::vf2d& scale);
		void SetLayerScale(uint8_t layer, float x, float y);
		void SetLayerTint(uint8_t layer, const olc::Pixel& tint);
		void SetLayerCustomRenderFunction(uint8_t layer, std::function<void()> f);

		std::vector<LayerDesc>& GetLayers();
		uint32_t CreateLayer();

		// Change the pixel mode for different optimisations
		// olc::Pixel::NORMAL = No transparency
		// olc::Pixel::MASK   = Transparent if alpha is < 255
		// olc::Pixel::ALPHA  = Full transparency
		void SetPixelMode(Pixel::Mode m);
		Pixel::Mode GetPixelMode();
		// Use a custom blend function
		void SetPixelMode(std::function<olc::Pixel(const int x, const int y, const olc::Pixel& pSource, const olc::Pixel& pDest)> pixelMode);
		// Change the blend factor from between 0.0f to 1.0f;
		void SetPixelBlend(float fBlend);



	public: // DRAWING ROUTINES
		// Draws a single Pixel
		virtual bool Draw(int32_t x, int32_t y, Pixel p = olc::WHITE);
		bool Draw(const olc::vi2d& pos, Pixel p = olc::WHITE);
		// Draws a line from (x1,y1) to (x2,y2)
		void DrawLine(int32_t x1, int32_t y1, int32_t x2, int32_t y2, Pixel p = olc::WHITE, uint32_t pattern = 0xFFFFFFFF);
		void DrawLine(const olc::vi2d& pos1, const olc::vi2d& pos2, Pixel p = olc::WHITE, uint32_t pattern = 0xFFFFFFFF);
		// Draws a circle located at (x,y) with radius
		void DrawCircle(int32_t x, int32_t y, int32_t radius, Pixel p = olc::WHITE, uint8_t mask = 0xFF);
		void DrawCircle(const olc::vi2d& pos, int32_t radius, Pixel p = olc::WHITE, uint8_t mask = 0xFF);
		// Fills a circle located at (x,y) with radius
		void FillCircle(int32_t x, int32_t y, int32_t radius, Pixel p = olc::WHITE);
		void FillCircle(const olc::vi2d& pos, int32_t radius, Pixel p = olc::WHITE);
		// Draws a rectangle at (x,y) to (x+w,y+h)
		void DrawRect(int32_t x, int32_t y, int32_t w, int32_t h, Pixel p = olc::WHITE);
		void DrawRect(const olc::vi2d& pos, const olc::vi2d& size, Pixel p = olc::WHITE);
		// Fills a rectangle at (x,y) to (x+w,y+h)
		void FillRect(int32_t x, int32_t y, int32_t w, int32_t h, Pixel p = olc::WHITE);
		void FillRect(const olc::vi2d& pos, const olc::vi2d& size, Pixel p = olc::WHITE);
		// Draws a triangle between points (x1,y1), (x2,y2) and (x3,y3)
		void DrawTriangle(int32_t x1, int32_t y1, int32_t x2, int32_t y2, int32_t x3, int32_t y3, Pixel p = olc::WHITE);
		void DrawTriangle(const olc::vi2d& pos1, const olc::vi2d& pos2, const olc::vi2d& pos3, Pixel p = olc::WHITE);
		// Flat fills a triangle between points (x1,y1), (x2,y2) and (x3,y3)
		void FillTriangle(int32_t x1, int32_t y1, int32_t x2, int32_t y2, int32_t x3, int32_t y3, Pixel p = olc::WHITE);
		void FillTriangle(const olc::vi2d& pos1, const olc::vi2d& pos2, const olc::vi2d& pos3, Pixel p = olc::WHITE);
		// Fill a textured and coloured triangle
		void FillTexturedTriangle(std::vector<olc::vf2d> vPoints, std::vector<olc::vf2d> vTex, std::vector<olc::Pixel> vColour, olc::Sprite* sprTex);
		void FillTexturedPolygon(const std::vector<olc::vf2d>& vPoints, const std::vector<olc::vf2d>& vTex, const std::vector<olc::Pixel>& vColour, olc::Sprite* sprTex, olc::DecalStructure structure = olc::DecalStructure::LIST);
		// Draws an entire sprite at location (x,y)
		void DrawSprite(int32_t x, int32_t y, Sprite* sprite, uint32_t scale = 1, uint8_t flip = olc::Sprite::NONE);
		void DrawSprite(const olc::vi2d& pos, Sprite* sprite, uint32_t scale = 1, uint8_t flip = olc::Sprite::NONE);
		// Draws an area of a sprite at location (x,y), where the
		// selected area is (ox,oy) to (ox+w,oy+h)
		void DrawPartialSprite(int32_t x, int32_t y, Sprite* sprite, int32_t ox, int32_t oy, int32_t w, int32_t h, uint32_t scale = 1, uint8_t flip = olc::Sprite::NONE);
		void DrawPartialSprite(const olc::vi2d& pos, Sprite* sprite, const olc::vi2d& sourcepos, const olc::vi2d& size, uint32_t scale = 1, uint8_t flip = olc::Sprite::NONE);
		// Draws a single line of text - traditional monospaced
		void DrawString(int32_t x, int32_t y, const std::string& sText, Pixel col = olc::WHITE, uint32_t scale = 1);
		void DrawString(const olc::vi2d& pos, const std::string& sText, Pixel col = olc::WHITE, uint32_t scale = 1);
		olc::vi2d GetTextSize(const std::string& s);
		// Draws a single line of text - non-monospaced
		void DrawStringProp(int32_t x, int32_t y, const std::string& sText, Pixel col = olc::WHITE, uint32_t scale = 1);
		void DrawStringProp(const olc::vi2d& pos, const std::string& sText, Pixel col = olc::WHITE, uint32_t scale = 1);
		olc::vi2d GetTextSizeProp(const std::string& s);

		// Decal Quad functions
		void SetDecalMode(const olc::DecalMode& mode);
		void SetDecalStructure(const olc::DecalStructure& structure);
		// Draws a whole decal, with optional scale and tinting
		void DrawDecal(const olc::vf2d& pos, olc::Decal* decal, const olc::vf2d& scale = { 1.0f,1.0f }, const olc::Pixel& tint = olc::WHITE);
		// Draws a region of a decal, with optional scale and tinting
		void DrawPartialDecal(const olc::vf2d& pos, olc::Decal* decal, const olc::vf2d& source_pos, const olc::vf2d& source_size, const olc::vf2d& scale = { 1.0f,1.0f }, const olc::Pixel& tint = olc::WHITE);
		void DrawPartialDecal(const olc::vf2d& pos, const olc::vf2d& size, olc::Decal* decal, const olc::vf2d& source_pos, const olc::vf2d& source_size, const olc::Pixel& tint = olc::WHITE);
		// Draws fully user controlled 4 vertices, pos(pixels), uv(pixels), colours
		void DrawExplicitDecal(olc::Decal* decal, const olc::vf2d* pos, const olc::vf2d* uv, const olc::Pixel* col, uint32_t elements = 4);
		// Draws a decal with 4 arbitrary points, warping the texture to look "correct"
		void DrawWarpedDecal(olc::Decal* decal, const olc::vf2d(&pos)[4], const olc::Pixel& tint = olc::WHITE);
		void DrawWarpedDecal(olc::Decal* decal, const olc::vf2d* pos, const olc::Pixel& tint = olc::WHITE);
		void DrawWarpedDecal(olc::Decal* decal, const std::array<olc::vf2d, 4>& pos, const olc::Pixel& tint = olc::WHITE);
		// As above, but you can specify a region of a decal source sprite
		void DrawPartialWarpedDecal(olc::Decal* decal, const olc::vf2d(&pos)[4], const olc::vf2d& source_pos, const olc::vf2d& source_size, const olc::Pixel& tint = olc::WHITE);
		void DrawPartialWarpedDecal(olc::Decal* decal, const olc::vf2d* pos, const olc::vf2d& source_pos, const olc::vf2d& source_size, const olc::Pixel& tint = olc::WHITE);
		void DrawPartialWarpedDecal(olc::Decal* decal, const std::array<olc::vf2d, 4>& pos, const olc::vf2d& source_pos, const olc::vf2d& source_size, const olc::Pixel& tint = olc::WHITE);
		// Draws a decal rotated to specified angle, wit point of rotation offset
		void DrawRotatedDecal(const olc::vf2d& pos, olc::Decal* decal, const float fAngle, const olc::vf2d& center = { 0.0f, 0.0f }, const olc::vf2d& scale = { 1.0f,1.0f }, const olc::Pixel& tint = olc::WHITE);
		void DrawPartialRotatedDecal(const olc::vf2d& pos, olc::Decal* decal, const float fAngle, const olc::vf2d& center, const olc::vf2d& source_pos, const olc::vf2d& source_size, const olc::vf2d& scale = { 1.0f, 1.0f }, const olc::Pixel& tint = olc::WHITE);
		// Draws a multiline string as a decal, with tiniting and scaling
		void DrawStringDecal(const olc::vf2d& pos, const std::string& sText, const Pixel col = olc::WHITE, const olc::vf2d& scale = { 1.0f, 1.0f });
		void DrawStringPropDecal(const olc::vf2d& pos, const std::string& sText, const Pixel col = olc::WHITE, const olc::vf2d& scale = { 1.0f, 1.0f });
		// Draws a single shaded filled rectangle as a decal
		void DrawRectDecal(const olc::vf2d& pos, const olc::vf2d& size, const olc::Pixel col = olc::WHITE);
		void FillRectDecal(const olc::vf2d& pos, const olc::vf2d& size, const olc::Pixel col = olc::WHITE);
		// Draws a corner shaded rectangle as a decal
		void GradientFillRectDecal(const olc::vf2d& pos, const olc::vf2d& size, const olc::Pixel colTL, const olc::Pixel colBL, const olc::Pixel colBR, const olc::Pixel colTR);
		// Draws an arbitrary convex textured polygon using GPU
		void DrawPolygonDecal(olc::Decal* decal, const std::vector<olc::vf2d>& pos, const std::vector<olc::vf2d>& uv, const olc::Pixel tint = olc::WHITE);
		void DrawPolygonDecal(olc::Decal* decal, const std::vector<olc::vf2d>& pos, const std::vector<float>& depth, const std::vector<olc::vf2d>& uv, const olc::Pixel tint = olc::WHITE);
		void DrawPolygonDecal(olc::Decal* decal, const std::vector<olc::vf2d>& pos, const std::vector<olc::vf2d>& uv, const std::vector<olc::Pixel>& tint);
		void DrawPolygonDecal(olc::Decal* decal, const std::vector<olc::vf2d>& pos, const std::vector<olc::vf2d>& uv, const std::vector<olc::Pixel>& colours, const olc::Pixel tint);
		void DrawPolygonDecal(olc::Decal* decal, const std::vector<olc::vf2d>& pos, const std::vector<float>& depth, const std::vector<olc::vf2d>& uv, const std::vector<olc::Pixel>& colours, const olc::Pixel tint);

		// Draws a line in Decal Space
		void DrawLineDecal(const olc::vf2d& pos1, const olc::vf2d& pos2, Pixel p = olc::WHITE);
		void DrawRotatedStringDecal(const olc::vf2d& pos, const std::string& sText, const float fAngle, const olc::vf2d& center = { 0.0f, 0.0f }, const olc::Pixel col = olc::WHITE, const olc::vf2d& scale = { 1.0f, 1.0f });
		void DrawRotatedStringPropDecal(const olc::vf2d& pos, const std::string& sText, const float fAngle, const olc::vf2d& center = { 0.0f, 0.0f }, const olc::Pixel col = olc::WHITE, const olc::vf2d& scale = { 1.0f, 1.0f });
		// Clears entire draw target to Pixel
		void Clear(Pixel p);
		// Clears the rendering back buffer
		void ClearBuffer(Pixel p, bool bDepth = true);
		// Returns the font image
		olc::Sprite* GetFontSprite();

		// Clip a line segment to visible area
		bool ClipLineToScreen(olc::vi2d& in_p1, olc::vi2d& in_p2);

		// Dont allow PGE to mark layers as dirty, so pixel graphics don't update
		void EnablePixelTransfer(const bool bEnable = true);

		// Command Console Routines
		void ConsoleShow(const olc::Key &keyExit, bool bSuspendTime = true);
		bool IsConsoleShowing() const;
		void ConsoleClear();
		std::stringstream& ConsoleOut();
		void ConsoleCaptureStdOut(const bool bCapture);

		// Text Entry Routines
		void TextEntryEnable(const bool bEnable, const std::string& sText = "");
		std::string TextEntryGetString() const;
		int32_t TextEntryGetCursor() const;
		bool IsTextEntryEnabled() const;



	private:
		void UpdateTextEntry();
		void UpdateConsole();

	public:

	public: // Branding
		std::string sAppName;

	public: // PGEX Stuff
		friend class PGEX;
		void pgex_Register(olc::PGEX* pgex);

	private:
		std::vector<olc::PGEX*> vExtensions;
	};



	// O------------------------------------------------------------------------------O
	// | PGE EXTENSION BASE CLASS - Permits access to PGE functions from extension    |
	// O------------------------------------------------------------------------------O
	class PGEX
	{
		friend class olc::PixelGameEngine;
	public:
		PGEX(bool bHook = false);

	protected:
		virtual void OnBeforeUserCreate();
		virtual void OnAfterUserCreate();
		virtual bool OnBeforeUserUpdate(float &fElapsedTime);
		virtual void OnAfterUserUpdate(float fElapsedTime);

	protected:
		static PixelGameEngine* pge;
	};
}


-->
