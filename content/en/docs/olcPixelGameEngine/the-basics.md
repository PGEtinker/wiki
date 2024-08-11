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

<a class="gdoc-markdown__link" href="#" target="_blank">See an example on PGEtinker</a>

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

<a class="gdoc-markdown__link" href="#" target="_blank">See an example on PGEtinker</a>

