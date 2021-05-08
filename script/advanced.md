# Foreign Function Interface (FFI)
The [FFI library](https://luajit.org/ext_ffi.html) allows calling external C functions and using C data structures from pure Lua code.

### Safety precautions
It is recommended you do not load scripts that utilize FFI unless you trust the provider or have audited the source code. Failing to take the proper precautions can potentially lead to malicious code being ran on your computer.

# Precompile scripts
There are many reasons to precompile a script, two examples are: 
- Speed up execution time
- Obfuscate original source code

### Run bytecode
Scripts that are already compiled to bytecode will run the same as any other Lua script.

### Compile manually with LuaJIT
See <https://luajit.org/running.html#options>. Requires your own installation of LuaJIT.
```
luajit -b script.lua script.ljbc
```

### Save function bytecode from `string.dump()`
```lua
function Greeting()
  print("Hello!")
end

-- dump bytecode
local bytecode = string.dump(Greeting, false)

-- allocate buffer
local buf = ffi.new("char[?]", string.len(bytecode))

-- copy bytecode to buffer
ffi.copy(buf, bytecode, string.len(bytecode))

-- output bytecode to 'script.ljbc'
local file = ffi.C.fopen("bytecode.ljbc", "wb")
ffi.C.fwrite(buf, 1, ffi.sizeof(buf), file)
ffi.C.fclose(file)
```
