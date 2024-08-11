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

<a class="gdoc-markdown__link" href="https://pgetinker.com/s/Mq8vp5I6CFL" target="_blank">See an example on PGEtinker</a>

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

<a class="gdoc-markdown__link" href="https://pgetinker.com/s/zlr5yCaTTP2" target="_blank">See an example on PGEtinker</a>

