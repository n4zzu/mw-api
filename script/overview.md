# Scripting overview
The goal of this document is to give you enough technical specifics to understand how our scripting works, but this isn't intended to be a tutorial or reference. When you're ready to start a project, you can start with the tutorial or dive right into more detailed documentation.

## Intro
Millionware uses the Lua scripting language to allow users to expand cheat functionality. Millionware takes advantage of the LuaJIT Just-In-Time Compiler (JIT) to speed up performance and allow more advanced features such as Foreign Function Interface (FFI) and pre-compiled bytecode to be used.
- [Lua](https://www.lua.org/)
- [LuaJIT](https://luajit.org/)
  - [FFI](https://luajit.org/ext_ffi.html)

### Standard Lua libraries
All of the standard Lua libraries are loaded except for the ```I/O``` and ```Operating System``` libraries. If you wish to utilize features from these libraries that do not have replacements found in our API, you must use FFI.

## Simple scripts
Print text in the developer console.
```lua
mw.Print("Hello world")
```

Draw text in the top left corner.
```lua
mw.RegisterCallback("draw", function()
  draw.String(Vec2.new(10, 10), Color.new(255, 255, 255, 255), 1.0, "Hello world")
end)
```

## Loading scripts
Scripts should end with the `.lua` file extension and be placed in the `mw/scripts/` folder found within the root of your game directory. Scripts will be loaded recursively, so you do not need to worry about folder structure.

Scripts can be automatically loaded by enabling the `Autoload` checkbox in the Scripting menu.
You can prevent any scripts you have set to automatically load by adding -mw_no_autoload to your game's startup parameters.