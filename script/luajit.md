# Advanced

## Precompile scripts
There are many reasons to precompile a script, two examples are:

- Speed up execution time
- Obfuscate original source code

### Run bytecode
!!! danger
    It is recommended you never load untrusted bytecode.

Scripts that are already compiled to bytecode will run the same as any other Lua script.

### Compile manually with LuaJIT
See <https://luajit.org/running.html#options>. Requires your own installation of LuaJIT.
```
luajit -b script.lua script.ljbc
```

### Save function bytecode from `string.dump()`
See [here](#save-function-bytecode-from-stringdump).

## Foreign Function Interface (FFI)
The [FFI library](https://luajit.org/ext_ffi.html) allows calling external C functions and using C data structures from pure Lua code.

!!! danger
    It is recommended you do not load scripts that utilize FFI unless you trust the provider or have audited the source code. Failing to take the proper precautions can potentially lead to malicious code being ran on your computer.

```lua
local ffi = require("ffi")

ffi.cdef[[
  int MessageBoxA(void *w, const char *txt, const char *cap, int type);
]]

ffi.C.MessageBoxA(nil, "Hello world!", "Test", 0)
```

### Save function bytecode from `string.dump()`
```lua
local ffi = require("ffi")

ffi.cdef[[
    void *fopen(const char *filename, const char *mode);
    size_t fwrite(const void *ptr, size_t size, size_t count, void *stream );
    int fclose(void *stream);
]]

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
