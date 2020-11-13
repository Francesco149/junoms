this was an exercise in writing a cool demo with no stdlib. it's very far from being a usable
emulator, it's more like a local proof of concept. I have a more full featured emulator in the
works but at the moment I don't feel like doing maple dev

JunoMS is a MapleStory v62 server emulator written in C without the standard 
library or any dependency at all. Currently, the executable is under 30kb and 
supports linux i386 and AMD64 only. Windows support is planned once the core features are
in place.

I have learned many things from developing 
[kagami](https://github.com/Francesco149/kagami), and this project's current aim
is matching kagami's current functionality with way smaller executable size, 
no dependencies, no stdlib and proceed from there.

# License
This code is public domain and comes with no warranty. You are free
to do whatever you want with it.

You can contact me at
[lolisamurai@tfwno.gf](mailto:lolisamurai@tfwno.gf) but don't
expect any support.

I hope you will find the code useful or at least interesting to
read. Have fun!

# Current status

* Only handles 1 player at once for testing purposes
* Most of the login server functionality is there, but with hardcoded accounts 
  and characters (and no character creation)
* Equips are correctly displayed in character selection
* Gets in-game and spawns in you in Henesys
* Equips and inventory contents are correctly displayed in-game

![](http://hnng.moe/f/GmU)

* Implemented movement packets 
[->video<-](https://www.youtube.com/watch?v=dq9u9c4WoXM)

![](http://hnng.moe/f/Gqd)

Goal roadmap:
* Implement most basic in-game functionality using the current hardcoded 
  accounts/character testbed
* Implement wz data handling
* Implement a basic plaintext or binary database module to quickly set up tests
  without mysql and shape the code around a database
* Implement a mysql module
* Separate all the platform-specific code into a platform layer
* Windows port

# Building (Linux 64-bit)
```bash
git clone https://github.com/Francesco149/junoms.git
cd junoms
chmod +x ./i386build.sh
./i386build.sh
./juno
```

# Building (Linux 32-bit)
```bash
git clone https://github.com/Francesco149/junoms.git
cd junoms
chmod +x ./amd64build.sh
./amd64build.sh
./juno
```

# Usage
You can check executable size with:

```bash
wc -c juno
```

Once juno is running, start a maplestory v62 localhost and connect.

There are a few hardcoded accounts that you can use to test stuff:

* user: errorN (where N is the desired error number) password: doesn't matter - 
  displays failed login errors (check the source to see which ones are valid, as
  some might crash the client).
* user: banN (where N is the desired ban message number) password: doesn't 
  matter - displays ban messages.
* user: asdasd password: asdasd - use this to log in, select the hardcoded 
  character and get in game.
