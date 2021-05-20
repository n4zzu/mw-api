# Draw
Functions used to draw to the screen. Intended for use with the `draw` callback.

## Functions

### draw.text
Draws unicode text. Use `\n` for new line.

`draw.text(position, color, text)`

| Argument      | Type          | Description   |
| ------------- | ------------- | ------------- |
| position      | vec2d         | 2D screen coordinates  |
| color         | color         | RGBA color  |
| text          | string         | Text to draw  |

---

### draw.wrap_text
Draws unicode text that will wrap on specified length.

`draw.wrapped_text(position, color, length, text)`

| Argument      | Type          | Description   |
| ------------- | ------------- | ------------- |
| position      | vec2d         | 2D screen coordinates  |
| color         | color         | RGBA color  |
| length        | number         | Amount of pixels before text is wrapped  |
| text          | string         | Text to draw |

---

### draw.text_size
Returns the width and height of text in pixels.

`draw.text_size(text, length, size):vec2d`

| Argument      | Type          | Description   |
| ------------- | ------------- | ------------- |
| text          | string         | Text to measure  |
| length        | number         | Amount of pixels before text is wrapped  |
| size          | number         | Font size  |

---

### draw.line
Draws a line.

`draw.line(point1, point2, color, thickness)`

| Argument      | Type          | Description   |
| ------------- | ------------- | ------------- |
| point1        | vec2d         | 2D screen coordinates  |
| point2        | vec2d         | 2D screen coordinates  |
| color         | color         | RGBA color  |
| thickness     | number        | Thickness in pixels  |

---

### draw.poly_chain
Draws a polygonal chain.

`draw.poly_chain(points, num_points, color, thickness)`

| Argument      | Type          | Description   |
| ------------- | ------------- | ------------- |
| points        | table         | 2D screen coordinates  |
| num_points    | number        | Number of points  |
| color         | color         | RGBA color  |
| thickness     | number        | Thickness in pixels  |

---

### draw.rect
Draws a rectangle.

`draw.rect(position, size, color, rounding)`

| Argument      | Type          | Description   |
| ------------- | ------------- | ------------- |
| position      | vec2d         | 2D screen coordinates  |
| size          | vec2d         | Width and height in pixels |
| color         | color         | RGBA color  |
| rounding      | number        | Rounding in pixels |

---

### draw.fill_rect
Draws a filled rectangle.

`draw.fill_rect(position, size, color, rounding)`

| Argument      | Type          | Description   |
| ------------- | ------------- | ------------- |
| position      | vec2d         | 2D screen coordinates  |
| size          | vec2d         | Width and height in pixels |
| color         | color         | RGBA color  |
| rounding      | number        | Rounding in pixels |

---

### draw.gradient
Draws a rectangle with a color gradient.

`draw.gradient(position, size, color1, color2, horizontal)`

| Argument      | Type          | Description   |
| ------------- | ------------- | ------------- |
| position      | vec2d         | 2D screen coordinates  |
| size          | vec2d         | Width and height in pixels |
| color1        | color         | RGBA color  |
| color2        | color         | RGBA color  |
| horizontal    | boolean       | Draw gradient horizontally, false for vertically |

---

### draw.triangle
Draws a triangle.

`draw.triangle(point1, point2, point3, color)`

| Argument      | Type          | Description   |
| ------------- | ------------- | ------------- |
| point1        | vec2d         | 2D screen coordinates  |
| point2        | vec2d         | 2D screen coordinates  |
| point3        | vec2d         | 2D screen coordinates  |
| color         | color         | RGBA color  |

---

### draw.fill_triangle
Draws a filled triangle.

`draw.triangle(point1, point2, point3, color)`

| Argument      | Type          | Description   |
| ------------- | ------------- | ------------- |
| point1        | vec2d         | 2D screen coordinates  |
| point2        | vec2d         | 2D screen coordinates  |
| point3        | vec2d         | 2D screen coordinates  |
| color         | color         | RGBA color  |

---

### draw.circle
Draws a circle.

`draw.circle(position, color, radius, segments)`

| Argument      | Type          | Description   |
| ------------- | ------------- | ------------- |
| position      | vec2d         | 2D screen coordinates  |
| color         | color         | RGBA color  |
| radius        | number        | Radius of circle  |
| segments      | number        | Amount of segments, higher means smoother rounding  |

---

### draw.fill_circle
Draws a filled circle.

`draw.circle(position, color, radius, segments)`

| Argument      | Type          | Description   |
| ------------- | ------------- | ------------- |
| position      | vec2d         | 2D screen coordinates  |
| color         | color         | RGBA color  |
| radius        | number        | Radius of circle  |
| segments      | number        | Amount of segments, higher means smoother rounding  |

---

### draw.bezier_cubic
Draws a cubic bezier curve.

`draw.bezier_cubic(point1, point2, point3, point4, color, thickness)`

| Argument      | Type          | Description   |
| ------------- | ------------- | ------------- |
| point1      | vec2d         | 2D screen coordinates  |
| point2      | vec2d         | 2D screen coordinates  |
| point3      | vec2d         | 2D screen coordinates  |
| point4      | vec2d         | 2D screen coordinates  |
| color       | color         | RGBA color  |
| thickness   | number        | Thickness in pixels  |

### draw.bezier_quad
Draws a quadratic bezier curve.

`draw.bezier_cubic(point1, point2, point3, color, thickness)`

| Argument      | Type          | Description   |
| ------------- | ------------- | ------------- |
| point1      | vec2d         | 2D screen coordinates  |
| point2      | vec2d         | 2D screen coordinates  |
| point3      | vec2d         | 2D screen coordinates  |
| color       | color         | RGBA color  |
| thickness   | number        | Thickness in pixels  |

---

### draw.load_image 
Loads an image from disk or raw byte data and returns an index to use with `draw.image`.

Supported formats are:

- PNG
- JPG
- BMP
- GIF (first frame only)

`draw.load_image(data, raw):number`

| Argument      | Type          | Description   |
| ------------- | ------------- | ------------- |
| data          | string        | Path to file or byte data  |
| raw           | boolean       | Use true if data is stored as string data  |

---

### draw.load_svg
Loads an SVG (Scalable Vector Graphics) from disk or text data and returns an index to use with `draw.image`.

`draw.load_svg(data, raw, scale):number`

| Argument      | Type          | Description   |
| ------------- | ------------- | ------------- |
| data          | string        | Path to file or byte data  |
| raw      | boolean       | Use true if data is stored as string data  |
| scale         | number        | Image scale, original scale is 1 |

---

### draw.load_gif
Loads a GIF from disk or raw byte data and returns an index to use with `draw.gif`.

`draw.load_gif(data, raw, speed):number`

| Argument      | Type          | Description   |
| ------------- | ------------- | ------------- |
| data          | string        | Path to file or byte data  |
| raw           | boolean       | Use true if data is stored as string data  |
| speed         | number        | GIF playback speed, normal speed is 1  |

---

### draw.image
Draws an image that was loaded with `draw.load_image` or `draw.load_svg`.

`draw.image(position, size, color, rounding, image_index)`

| Argument      | Type          | Description   |
| ------------- | ------------- | ------------- |
| position      | vec2d         | 2D screen coordinates  |
| size          | vec2d         | Width and height in pixels |
| color         | color         | RGBA color  |
| rounding      | number        | Rounding in pixels |
| image_index   | number        | Index returned by `draw.load_image` |

---

### draw.gif
Draws an animated GIF that was loaded with `draw.load_gif`.

`draw.gif(position, size, color, rounding, image_index)`

| Argument      | Type          | Description   |
| ------------- | ------------- | ------------- |
| position      | vec2d         | 2D screen coordinates  |
| size          | vec2d         | Width and height in pixels |
| color         | color         | RGBA color  |
| rounding      | number        | Rounding in pixels |
| image_index   | number        | Index returned by `draw.load_gif` |

---

### draw.push_clip_rect
Starts scissor test to cull pixels outside of defined region.

`draw.push_clip_rect(min, max)`

| Argument      | Type          | Description   |
| ------------- | ------------- | ------------- |
| min           | vec2d         | Minimum to clip  |
| max           | vec2d         | Maximum to clip |

---

### draw.pop_clip_rect
Ends scissor test started by `draw.push_clip_rect`.

`draw.pop_clip_rect()`

---

## Examples

### draw.load_svg
**Loading from raw text:**
```lua
local img = draw.load_svg([[
  <svg clip-rule="evenodd" fill-rule="evenodd" stroke-linejoin="round" stroke-miterlimit="1.41421" viewBox="0 0 560 400" xmlns="http://www.w3.org/2000/svg">
    <path d="m633.9 812.041c112.46 0 173.96-93.168 173.96-173.96 0-2.646-.054-5.28-.173-7.903 11.938-8.63 22.314-19.4 30.498-31.66-10.955 4.87-22.744 8.148-35.111 9.626 12.623-7.569 22.314-19.543 26.886-33.817-11.813 7.003-24.895 12.093-38.824 14.841-11.157-11.884-27.041-19.317-44.629-19.317-33.764 0-61.144 27.381-61.144 61.132 0 4.798.537 9.464 1.586 13.941-50.815-2.557-95.874-26.886-126.03-63.88-5.251 9.035-8.279 19.531-8.279 30.73 0 21.212 10.794 39.938 27.208 50.893-10.031-.31-19.454-3.064-27.69-7.647-.009.257-.009.507-.009.781 0 29.61 21.075 54.332 49.051 59.934-5.137 1.4-10.543 2.151-16.122 2.151-3.933 0-7.766-.387-11.491-1.102 7.784 24.293 30.355 41.971 57.115 42.465-20.926 16.402-47.287 26.171-75.937 26.171-4.929 0-9.798-.281-14.584-.847 27.059 17.344 59.189 27.464 93.722 27.464" fill="#1da1f2" fill-rule="nonzero" transform="matrix(.906028 0 0 .906028 -344.419 -426.017)"/>
  </svg>
]], true, 1.0)

mw.register_callback("draw", function()
  draw.image(vec2d(0, 200), vec2d(560, 400), color(255, 255, 255, 255), 0, img)
end)
```
