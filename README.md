# Godot-VSCode-Files
The files you need for various debugging methods standardised for the best experience with working compilation db

To use this with Godot you need the following installed systemwide:
- Clang (for compiling godot with compilation db support)
- Bear (for a working compilation db)
- LLDB 
- GDB

Using both debuggers is advisable as if one spits an error out which is hard to debug the other can find it easier in some cases.
This is the case for example for deconstructor issues, which I noticed that LLDB can't properly detect whereas GDB can.
(in some cases not all)

Plugins for advanced debugging in vscode:
- C/C++ extension
- CodeLLDB (tighter integration than the default C++ llvm provider instead of only output scanning, we support both in this vscode setup)


Once you have the pre-requisites installed you need to update the following line to be your project you would like to launch on starting the C++ build of godot:
 "args": ["--path", "/home/gordon/Projects/CorpSquad/CorpSquad.ModelTest", "-e", "-v"],  
