# Godot-VSCode-Files
The files you need for various debugging methods standardised for the best experience with working compilation db
- VS C++ compiler (for windows / non mingw)
- Clang (for compiling godot with compilation db support)
- LLDB 
- GDB

Optional patches to give you compilation db natively from scons, this is much faster than BEAR. (Bear takes a couple of minutes, and intercept build takes 20 minutes, where as the native PR just spits it out in a few seconds)
- https://github.com/godotengine/godot/pull/32848

Recent updates:
- F5 debugging will always trigger a build now in the recent edit
- Saving will trigger clang formatting
- We added visual studio support

Incoming update:
- configuration for osx

Ideally I want to have a UI to ask you "What godot project do you want to launch, for debugging" even just a generic dropdown in vscode, I don't have time away from working on Godot FBX to implement this so for now you have to manually set the path in the configuration, but it's not hard.

# Linux Support

Using both debuggers is advisable as if one spits an error out which is hard to debug the other can find it easier in some cases.
This is the case for example for deconstructor issues, which I noticed that LLDB can't properly detect whereas GDB can.
(in some cases not all)

Plugins for advanced debugging in vscode:
- C/C++ extension
- CodeLLDB (tighter integration than the default C++ llvm provider instead of only output scanning, we support both in this vscode setup)


Once you have the pre-requisites installed, you need to update all the lines with the correct project path:
```json
 "args": ["--path", "/home/gordon/Projects/CorpSquad/CorpSquad.ModelTest", "-e", "-v"],  
```

This adds several tasks make sure to run the full rebuild:
- Run vscode task 'clean scons'
- Run vscode task build.

You can select from 3 seperate debugging integrations within vscode, which has advantages mentioned above.
Press F5 to debug.

Happy hacking!
