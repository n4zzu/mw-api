# Callbacks

!!! tip
    Familiarize yourself with the Source engine frame order.

    [https://developer.valvesoftware.com/wiki/Frame_Order](https://developer.valvesoftware.com/wiki/Frame_Order)
    
Callbacks allow you to run your script code when a game function is called. Some game functions will pass data back to your registered callback which can then be read and modified.

You can only have one callback for each available game function per script. Attempting to add more will not work.

## Registering a callback
Register a callback by using `mw.register_callback(string:callback, function)`

```lua
mw.register_callback("draw", function()
    print("draw was called!")
end)
```

## Retrieving data from a callback
Some game functions will pass data back to your registered callback which can then be read and modified.

```lua
mw.register_callback("run_command", function(cmd)
    print("choked_commands is: " .. cmd.choked_commands)
end)
```

## Removing a callback
You can remove a registered callback by using `mw.remove_callback(string:callback)`

```lua
mw.remove_callback("run_command")
```

## Available callbacks

### ``` draw()```
Called every frame. Use this for drawing.

### ```run_command(cmd)``` 
Called every game tick (64 ticks in Valve servers), ran before user prediction.

| Variable      | Description   |
| ------------- | ------------- |
| choked_commands | Amount of commands that has been choked  |
| command_number  | Current command number  |
