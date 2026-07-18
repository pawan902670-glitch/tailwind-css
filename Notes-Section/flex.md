# 📘 Tailwind CSS Notes – Flexbox, Flex Wrap, Content Alignment & Sizing

---

# 1. Flexbox (`flex`)

## Definition

Flexbox is a one-dimensional layout system used to arrange elements in a **row** or **column**.

In Tailwind CSS, use the `flex` class to make an element a **Flex Container**.

```html
<div class="flex">
    <div>Box 1</div>
    <div>Box 2</div>
    <div>Box 3</div>
</div>
```

### Without `flex`

```
Box 1
Box 2
Box 3
```

Elements appear one below another.

### With `flex`

```
Box1   Box2   Box3
```

Elements appear in a single row.

---

# 2. Flex Direction

Flex direction decides **how items are arranged**.

## `flex-row` (Default)

Items are arranged horizontally.

```html
<div class="flex flex-row">
```

```
Box1  Box2  Box3
```

---

## `flex-col`

Items are arranged vertically.

```html
<div class="flex flex-col">
```

```
Box1
Box2
Box3
```

---

## `flex-row-reverse`

Reverse horizontal order.

```html
<div class="flex flex-row-reverse">
```

```
Box3 Box2 Box1
```

---

## `flex-col-reverse`

Reverse vertical order.

```html
<div class="flex flex-col-reverse">
```

```
Box3
Box2
Box1
```

---

# 3. Main Axis vs Cross Axis

Understanding these two axes is very important.

### For `flex-row`

```
Cross Axis
     ↑
     |
Box1 Box2 Box3 -----> Main Axis
```

* Main Axis → Horizontal
* Cross Axis → Vertical

---

### For `flex-col`

```
Main Axis
↓

Box1

Box2

Box3

Cross Axis →
```

Main axis becomes vertical.

---

# 4. Justify Content

Controls alignment on the **Main Axis**.

Syntax

```html
justify-start
justify-center
justify-end
justify-between
justify-around
justify-evenly
```

---

## justify-start

```
Box1 Box2 Box3
```

Items stay at the beginning.

```html
<div class="flex justify-start">
```

---

## justify-center

```
      Box1 Box2 Box3
```

Items move to the center.

---

## justify-end

```
                Box1 Box2 Box3
```

Items move to the end.

---

## justify-between

```
Box1          Box2          Box3
```

Space only between items.

---

## justify-around

```
  Box1    Box2    Box3
```

Equal space around each item.

---

## justify-evenly

```
 Box1   Box2   Box3
```

Equal space everywhere.

---

# 5. Align Items

Aligns items on the **Cross Axis**.

Classes

```html
items-start
items-center
items-end
items-baseline
items-stretch
```

---

## items-start

```
□□□□
□□□□
```

Items stay at the top.

---

## items-center

```

□□□□
□□□□

```

Items move to the center vertically.

---

## items-end

```

□□□□
□□□□
```

Items move to the bottom.

---

## items-stretch

Items stretch to fill available height.

---

## items-baseline

Aligns text according to its baseline.

---

# 6. Flex Wrap

Controls whether items move to the next line.

---

## flex-nowrap (Default)

```html
<div class="flex flex-nowrap">
```

```
□□□□□□□□□□□□□□
```

Everything remains in one line.

---

## flex-wrap

```html
<div class="flex flex-wrap">
```

```
□□□□
□□□□
□□□□
```

Items automatically move to the next row.

---

## flex-wrap-reverse

Rows appear in reverse order.

```html
<div class="flex flex-wrap-reverse">
```

---

# 7. Content Alignment

**Important**

These classes only work when

* `display:flex`
* `flex-wrap`
* Multiple rows exist

---

## content-start

```html
content-start
```

Rows stay at the top.

```
□□□□
□□□□

(empty space)
```

---

## content-center

Rows stay in the center.

```

□□□□
□□□□

```

---

## content-end

Rows stay at the bottom.

```

(empty)

□□□□
□□□□
```

---

## content-between

First row at top.

Last row at bottom.

```
□□□□

(empty)

□□□□
```

---

## content-around

Equal space around rows.

---

## content-evenly

Equal spacing everywhere.

---

## content-stretch

Rows stretch to occupy remaining space.

---

# 8. Size Utility

Instead of writing width and height separately, Tailwind provides `size-*`.

Example

```html
<div class="size-20"></div>
```

Equivalent CSS

```css
width:5rem;
height:5rem;
```

---

Common Sizes

| Class     | Width & Height |
| --------- | -------------- |
| size-8    | 2rem           |
| size-10   | 2.5rem         |
| size-12   | 3rem           |
| size-16   | 4rem           |
| size-20   | 5rem           |
| size-24   | 6rem           |
| size-32   | 8rem           |
| size-40   | 10rem          |
| size-48   | 12rem          |
| size-64   | 16rem          |
| size-80   | 20rem          |
| size-96   | 24rem          |
| size-full | 100%           |

---

# 9. Width & Height

## size-full

```html
<div class="size-full">
```

Equivalent

```css
width:100%;
height:100%;
```

---

## h-screen

```html
<div class="h-screen">
```

Means

```css
height:100vh;
```

Occupies the full screen height.

---

# 10. Background Colors

Used to change background color.

Examples

```html
bg-red-200
bg-pink-200
bg-green-200
bg-blue-200
bg-gray-200
bg-orange-200
bg-yellow-200
bg-black
bg-white
```

Example

```html
<div class="bg-red-200"></div>
```

---

# 11. Understanding Your Code

```html
<div class="size-full bg-pink-200 flex flex-wrap content-start">
```

### Meaning

| Class         | Purpose                            |
| ------------- | ---------------------------------- |
| size-full     | Takes full width and height        |
| bg-pink-200   | Pink background                    |
| flex          | Makes the container a flexbox      |
| flex-wrap     | Allows items to wrap onto new rows |
| content-start | Places wrapped rows at the top     |

Child boxes

```html
<div class="bg-red-200 size-32"></div>
```

Means

* Background color → Red
* Width → 8rem
* Height → 8rem

---

# 12. Mistakes in Your Code

### ❌ Missing closing `>`

Wrong

```html
<div class="size-full bg-pink-200 flex flex-wrap content-start"
```

Correct

```html
<div class="size-full bg-pink-200 flex flex-wrap content-start">
```

---

### ❌ Missing Closing `</div>`

Every opening `<div>` should have a closing `</div>`.

---

### ❌ Invalid Class

Wrong

```html
bg-black-200
```

Correct

```html
bg-black
```

Tailwind does not provide `bg-black-200`.

---

# 13. Real-Life Example

Imagine a classroom with desks.

* **Flex Container** = Classroom
* **Flex Items** = Desks
* **justify-content** = Move desks left, center, or right
* **align-items** = Raise or lower desks vertically
* **flex-wrap** = If one row is full, start a new row
* **content-start** = Keep all rows at the top
* **size-32** = Size of each desk
* **bg-red-200** = Desk color

---

# 14. Quick Revision

| Class           | Purpose                          |
| --------------- | -------------------------------- |
| flex            | Enable Flexbox                   |
| flex-row        | Horizontal layout                |
| flex-col        | Vertical layout                  |
| justify-center  | Center items horizontally        |
| justify-between | Space between items              |
| items-center    | Center items vertically          |
| flex-wrap       | Move items to the next line      |
| flex-nowrap     | Keep items on one line           |
| content-start   | Place wrapped rows at the top    |
| content-center  | Center wrapped rows              |
| content-end     | Place wrapped rows at the bottom |
| size-32         | Width & Height = 8rem            |
| size-full       | Width & Height = 100%            |
| h-screen        | Full viewport height             |
| bg-red-200      | Red background                   |

---

# 15. Interview & Exam Questions

1. What is Flexbox?
2. What is the difference between `justify-content` and `align-items`?
3. Explain the Main Axis and Cross Axis.
4. What is the default flex direction?
5. What is the purpose of `flex-wrap`?
6. When does `content-start` work?
7. What is the difference between `items-center` and `content-center`?
8. What is the purpose of `size-*` utilities?
9. What is the difference between `size-full` and `h-screen`?
10. Why is `bg-black-200` invalid in Tailwind CSS?

