# vec2d
vec2d (vector 2d) is a 2-dimensional array typically used for 2D screen coordinates.

## ```vec2d```
Creates a new vec2d object.

```vec2d(x: number, y: number):vec2d```

| Argument      | Type          | Description   |
| ------------- | ------------- | ------------- |
| x             | number        | X coordinate  |
| y             | number        | Y coordinate  |

---

## Operators

### Addition
Adds two vec2d objects and return the sum.
```lua
local vec2 = vec2d(25.0, 50.0) + vec2d(100.0, 25.0)
print(vec2.x .. ', ' .. vec2.y)
```
```Output: 125, 75```

### Subtraction
Subtracts two vec2d objects and return the sum.
```lua
local vec2 = vec2d(25.0, 50.0) - vec2d(100.0, 25.0)
print(vec2.x .. ', ' .. vec2.y)
```
```Output: -75, 25```

### Multiplication
Multiplies two vec2d objects and return the sum.
```lua
local vec2 = vec2d(25.0, 50.0) * vec2d(100.0, 25.0)
print(vec2.x .. ', ' .. vec2.y)
```
```Output: 2500, 1250```

### Division
Divides two vec2d objects and return the sum.
```lua
local vec2 = vec2d(25.0, 50.0) / vec2d(100.0, 25.0)
print(vec2.x .. ', ' .. vec2.y)
```
```Output: 0.5, 2```

### Length
Returns the length/magnitude.
```lua
local len = #vec2d(10.0, 10.0)
print(len)
```
```Output: 14.1421```

---

## Functions

### ```length()```
Returns the length/magnitude, returns exact same data as using the `#` operator.

```vec2d:dot():float```

```lua
local vec2 = vec2d(10.0, 10.0)
local len = vec2:length()
print(len)
```
```Output: 14.1421```

### ```length_sqr()```
Returns the length².

```vec2d:length_sqr():float```

```lua
local vec2 = vec2d(10.0, 10.0)
local len_sqr = vec2:length_sqr()
print(len)
```
```Output: 200```

### ```dot()```
Returns the dot product.

```vec2d:dot(other: vec2d):float```

| Argument      | Type          | Description   |
| ------------- | ------------- | ------------- |
| other         | vec2d         | Other ```vec2d()``` used to calculate the dot product  |

```lua
local vec2 = vec2d(2.0, 10.0)
local dot = vec2:dot(vec2d(4.0, 1.0))
print(dot)
```
```Output: 18```

### ```dist()```
Returns the distance.

```vec2d:dist(other: vec2d):float```

| Argument      | Type          | Description   |
| ------------- | ------------- | ------------- |
| other         | vec2d         | Other ```vec2d()``` used to calculate the distance  |

```lua
local vec2 = vec2d(0.0, 0.0)
local dist = vec2:dist(vec2d(10.0, 10.0))
print(dist)
```
```Output: 14.1421```

### ```normalize()```
Divides the vector by it's own length.

```vec2d:normalize()```

```lua
local vec2 = vec2d(50.0, 50.0)
vec2:normalize()
print(vec2.x .. ', ' .. vec2.y)
```
```Output: 0.7071```

### ```lerp()```
Interpolate by given percentage linearly. 

```vec2d:lerp(other: vec2d, percentage: number):vec2d```

| Argument      | Type          | Description   |
| ------------- | ------------- | ------------- |
| other         | vec2d         | Other ```vec2d()``` to interpolate to  |
| percentage    | number        | Percentage to interpolate by (0.0-1.0) |

```lua
local vec2 = vec2d(0.0, 0.0)
local lerped = vec2:lerp(vec2d(10.0, 10.0), 0.5) -- interpolate by 50%
print(lerped.x .. ', ' .. lerped.y)
```
```Output: 5, 5```
