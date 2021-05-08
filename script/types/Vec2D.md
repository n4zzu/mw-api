# Vec2D
Vec2D is a 2-dimensional array typically used for 2D screen coordinates.

## ```Vec2D()```
Creates a new Vec2D object.

```Vec2D(x: number, y: number):vector```
| Argument | Type | Description |
| :--- | :--- | :--- |
| x | number | X coordinate |
| y | number | Y coordinate |

## Operators

### Addition
Adds two Vec2D objects and return the sum.
```lua
local vec2 = Vec2D(25.0, 50.0) + Vec2D(100.0, 25.0)
print(vec2.x .. ', ' .. vec2.y)
```
```Output: 125, 75```

### Subtraction
Subtracts two Vec2D objects and return the sum.
```lua
local vec2 = Vec2D(25.0, 50.0) - Vec2D(100.0, 25.0)
print(vec2.x .. ', ' .. vec2.y)
```
```Output: -75, 25```

### Subtraction
Subtracts two Vec2D objects and return the sum.
```lua
local vec2 = Vec2D(25.0, 50.0) - Vec2D(100.0, 25.0)
print(vec2.x .. ', ' .. vec2.y)
```
```Output: -75, 25```

### Multiplication
Multiplies two Vec2D objects and return the sum.
```lua
local vec2 = Vec2D(25.0, 50.0) * Vec2D(100.0, 25.0)
print(vec2.x .. ', ' .. vec2.y)
```
```Output: 2500, 1250```

### Division
Divides two Vec2D objects and return the sum.
```lua
local vec2 = Vec2D(25.0, 50.0) / Vec2D(100.0, 25.0)
print(vec2.x .. ', ' .. vec2.y)
```
```Output: 0.5, 2```

### Length
Returns the length/magnitude.
```lua
local vec2 = #Vec2D(10, 10)
print(vec2)
```
```Output: 14.1421```
