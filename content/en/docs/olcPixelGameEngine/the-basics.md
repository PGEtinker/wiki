---
title: "The Basics"
weight: 2
# geekdocFlatSection: false
# geekdocToc: 6
# geekdocHidden: false
---

## Drawing Primitive Shapes

### Points

Draws a point at (**x**,**y**) with the provided **color**.

```cpp
// with integers
Draw(5, 5, olc::WHITE);

// with the olc::vi2d
Draw(olc::vi2d{5, 5}, olc::WHITE);
```

**Color:** Color has a default value of ``olc::WHITE``

<a class="gdoc-markdown__link" href="https://pgetinker.com/s/bluvB6PHs4" target="_blank">See an example on PGEtinker</a>

### Lines

Draws a line from the point (**x1**,**y1**) to (**x2**,**y2**) with the provided color.

```cpp
// with integers
DrawLine(10, 10, 20, 20, olc::WHITE);

// with olc::vi2d
DrawLine(olc::vi2d{10, 10}, olc::vi2d{20, 20}, olc::WHITE);
```

**Color:** Color has a default value of ``olc::WHITE``

<a class="gdoc-markdown__link" href="https://pgetinker.com/s/nz1PhTB89Qt" target="_blank">See an example on PGEtinker</a>

### Circles

Draws a circle at the point (**x**,**y**) with provided **radius** and **color**.

```cpp
// with integers
DrawCircle(10, 10, 20, olc::WHITE);
FillCircle(10, 10, 20, olc::WHITE);

// with olc::vi2d
DrawCircle(olc::vi2d{10, 10}, 20, olc::WHITE);
FillCircle(olc::vi2d{10, 10}, 20, olc::WHITE);
```

**Color:** Color has a default value of ``olc::WHITE``

<a class="gdoc-markdown__link" href="https://pgetinker.com/s/LAfpOSplvT6" target="_blank">See an example on PGEtinker</a>

### Rectangles

Draws or fills a rectangle at the point (**x**,**y**) with the provide **width**, **height**, and **color**.

```cpp
// with integers
DrawRect(10, 10, 20, 20, olc::WHITE);
FillRect(10, 10, 20, 20, olc::WHITE);

// with old::vi2d
DrawRect(olc::vi2d{10, 10}, olc::vi2d{20, 20}, olc::WHITE);
FillRect(olc::vi2d{10, 10}, olc::vi2d{20, 20}, olc::WHITE);
```

**Color:** Color has a default value of ``olc::WHITE``

<a class="gdoc-markdown__link" href="https://pgetinker.com/s/IbofyLvSjnQ" target="_blank">See an example on PGEtinker</a>

### Triangles

Draws or fills a triangle between points (x1,y1), (x2,y2) and (x3,y3)

```cpp
// with integers
DrawTriangle(10, 30, 30, 10, 50, 30, olc::WHITE);
FillTriangle(10, 30, 30, 10, 50, 30, olc::WHITE);

// with olc::vi2d
DrawTriangle(olc::vi2d{10, 30}, olc::vi2d{30, 10}, olc::vi2d{50, 30}, olc::WHITE);
FillTriangle(olc::vi2d{10, 30}, olc::vi2d{30, 10}, olc::vi2d{50, 30}, olc::WHITE);
```

**Color:** Color has a default value of ``olc::WHITE``

<a class="gdoc-markdown__link" href="https://pgetinker.com/s/SVZaEo1yFBC" target="_blank">See an example on PGEtinker</a>

## Drawing Text

### DrawString

Draws a single line of text - traditional monospaced

```cpp
// with integers
DrawString(10, 10, "Hello, World", olc::WHITE, 1);

// with olc::vi2d
DrawString(olc::vi2d{10, 10}, "Hello, World", olc::WHITE, 1);
```

**Color:** Color has a default value of ``olc::WHITE``<br>
**Scale:** Scale has a default value of ``1``

<a class="gdoc-markdown__link" href="https://pgetinker.com/s/A8FZbptTm77" target="_blank">See an example on PGEtinker</a>

### GetTextSize

For convenience, there's also  function to calculate the pixel size
of a given string. This is the traditional monospaced version.

```cpp
olc::vi2d textSize = GetTextSize("Hello, World");
```

The ``textSize.x`` property will contain the width.<br>
The ``textSize.y`` property will contain the height.

**Note:** this function does not account for scaling.

<a class="gdoc-markdown__link" href="https://pgetinker.com/s/A8FZbptTm77" target="_blank">See an example on PGEtinker</a>

### DrawStringProp

Draws a single line of text - non-monospaced

```cpp
// with integers
DrawStringProp(10, 10, "Hello, World", olc::WHITE);

// with olc::vi2d
DrawStringProp(olc::vi2d{10, 10}, "Hello, World", olc::WHITE);
```

<a class="gdoc-markdown__link" href="https://pgetinker.com/s/53iEqiXd0t" target="_blank">See an example on PGEtinker</a>

### GetTextSizeProp

For convenience, there's also  function to calculate the pixel size
of a given string. This is the non-monospaced version.

```cpp
olc::vi2d textSize = GetTextSizeProp("Hello, World");
```

The ``textSize.x`` property will contain the width.<br>
The ``textSize.y`` property will contain the height.

**Note:** this function does not account for scaling.

<a class="gdoc-markdown__link" href="https://pgetinker.com/s/53iEqiXd0t" target="_blank">See an example on PGEtinker</a>
