# **Disclaimer**
This code was tested on offline servers using the `-insecure` launch flag (which disables VAC). I have never cheated and I do not condone cheating. This project was done for fun. If you use my code and get VAC banned, I take no responsibility for it.

### Overview
This project was extremely interesting because I was able to go more into depth with things that aren't normally taught in my classes, namely the disassembler and memory. I had a ton of fun making this (and also playing around with my new godlike aim).

### Core Concepts
- Using IDA Pro and Sigmaker
    - These tools are extremely useful for finding important signatures and offsets in memory. Having this information is the basis of making my aimbot work. I was able to verify I did everything correctly with this handy-dandy [Github](https://github.com/frk1/hazedumper/blob/master/csgo.hpp).
- Vector Math and Trig
    - I guess this section is a TLDR of how the aimbot works. Use the offsets from before, we can go into memory and find the vectors of ourself and the enemy from the world's origin. Then, by subtracting our local position from the enemy position, we get a directional vector from where we stand to the enemy (this vector centers the origin to ourself!). Given this vector, we can get our pitch and yaw using some trig (see `ToAngle()` in `Vector3.h`). Then, we can write this to memory and we should now be looking at someone's head. 😊

### Setup
- Set desired aim smoothing and hotkey in `main.cpp`
- Build solution in Relase x86 (CS is 32-bit!)
- Run executable after loading into a game
### What Next?
I might add onto this by adding a no recoil feature. I'm already dealing with aim punch in this code, so it shouldn't be too difficult to add it on. And if I add multiple features, I may try to add an in-game overlay to make things look nice. I may also try some other more things like DLL injection which could make my cheats less obvious to anti-cheat systems. I'm not really sure how to test it against the anti-cheat though since I don't really feel like making a bunch of accounts that will likely get banned in my testing.