
# Tailwind CSS Notes — Borders, Width, Size, Radius, and Border Styles

Tailwind CSS provides utility classes that allow you to style HTML elements directly using class names.

For example:

```html
<div class="border m-10 p-4">
    Tailwind
</div>
```

Instead of writing a separate CSS class, Tailwind lets you apply styles directly in the HTML.

---

# 1. `border`

### Tailwind

```html
<div class="border">
    Tailwind
</div>
```

The `border` class adds a **1px solid border** around the element.

### Equivalent CSS

```css
.box {
    border-width: 1px;
    border-style: solid;
}
```

HTML:

```html
<div class="box">
    Tailwind
</div>
```

---

# 2. `border-4`

### Tailwind

```html
<div class="border-4">
    Tailwind
</div>
```

The `border-4` class sets the border width to **4px**.

### Equivalent CSS

```css
.box {
    border-width: 4px;
}
```

If you want to define the border completely:

```css
.box {
    border: 4px solid;
}
```

---

# 3. `border-blue-600`

### Tailwind

```html
<div class="border-4 border-blue-600">
    Tailwind
</div>
```

Here:

* `border-4` → border width is 4px
* `border-blue-600` → border color is blue

### Equivalent CSS

```css
.box {
    border: 4px solid;
    border-color: #2563eb;
}
```

The exact generated color depends on Tailwind's color palette.

---

# 4. Border on Individual Sides

Tailwind allows you to apply borders to specific sides.

### Top Border

```html
<div class="border-t-blue-600">
    Tailwind
</div>
```

CSS:

```css
.box {
    border-top-color: #2563eb;
}
```

---

### Bottom Border

```html
<div class="border-b-red-500">
    Tailwind
</div>
```

CSS:

```css
.box {
    border-bottom-color: #ef4444;
}
```

---

### Left Border

```html
<div class="border-l-lime-400">
    Tailwind
</div>
```

CSS:

```css
.box {
    border-left-color: #a3e635;
}
```

---

### Right Border

```html
<div class="border-r-green-700">
    Tailwind
</div>
```

CSS:

```css
.box {
    border-right-color: #15803d;
}
```

### Your example

```html
<div class="m-10 p-4 w-96 border-4 
            border-t-blue-600 
            border-b-red-500 
            border-l-lime-400 
            border-r-green-700">
    Tailwind
</div>
```

The four sides have different colors.

Equivalent CSS:

```css
.box {
    margin: 40px;
    padding: 16px;
    width: 384px;

    border-width: 4px;
    border-style: solid;

    border-top-color: #2563eb;
    border-bottom-color: #ef4444;
    border-left-color: #a3e635;
    border-right-color: #15803d;
}
```

---

# 5. Margin — `m-10`

### Tailwind

```html
<div class="m-10">
    Tailwind
</div>
```

`m-10` applies margin to **all four sides**.

In the default Tailwind spacing scale:

```text
m-10 = 40px
```

### Equivalent CSS

```css
.box {
    margin: 40px;
}
```

---

# 6. Padding — `p-4`

### Tailwind

```html
<div class="p-4">
    Tailwind
</div>
```

`p-4` adds padding to all four sides.

```text
p-4 = 16px
```

### Equivalent CSS

```css
.box {
    padding: 16px;
}
```

---

# 7. Width — `w-96`

### Tailwind

```html
<div class="w-96">
    Tailwind
</div>
```

`w-96` sets the element's width.

In the default Tailwind spacing scale:

```text
w-96 = 24rem = 384px
```

### Equivalent CSS

```css
.box {
    width: 384px;
}
```

---

# 8. `size-32`

The `size-*` utility sets both:

* `width`
* `height`

### Tailwind

```html
<div class="size-32">
    Tailwind
</div>
```

`size-32` means:

```text
width: 128px;
height: 128px;
```

### Equivalent CSS

```css
.box {
    width: 128px;
    height: 128px;
}
```

This is equivalent to:

```html
<div class="w-32 h-32">
    Tailwind
</div>
```

---

# 9. `rounded-full`

### Tailwind

```html
<div class="size-32 rounded-full">
    Tailwind
</div>
```

`rounded-full` gives the element a very large border radius.

When the element is square, it creates a **circle**.

### Equivalent CSS

```css
.box {
    width: 128px;
    height: 128px;
    border-radius: 9999px;
}
```

You can also think of it as:

```css
border-radius: 50%;
```

For a square element, `50%` creates a perfect circle.

---

# 10. `rounded-t-full`

### Tailwind

```html
<div class="size-32 rounded-t-full">
    Tailwind
</div>
```

This rounds the **top-left and top-right corners**.

### Equivalent CSS

```css
.box {
    border-top-left-radius: 9999px;
    border-top-right-radius: 9999px;
}
```

The bottom corners remain unchanged.

---

# 11. `rounded-b-full`

### Tailwind

```html
<div class="size-32 rounded-b-full">
    Tailwind
</div>
```

This rounds the bottom corners.

### Equivalent CSS

```css
.box {
    border-bottom-left-radius: 9999px;
    border-bottom-right-radius: 9999px;
}
```

---

# 12. `rounded-sm`

### Tailwind

```html
<div class="size-32 rounded-sm">
    Tailwind
</div>
```

This adds a small border radius.

### Equivalent CSS

```css
.box {
    border-radius: 0.125rem;
}
```

---

# 13. `rounded-3xl`

### Tailwind

```html
<div class="size-32 rounded-3xl">
    Tailwind
</div>
```

This gives the element a large border radius.

### Equivalent CSS

```css
.box {
    border-radius: 1.5rem;
}
```

---

# 14. `rounded-ss-2xl`

The `ss` means **start-start**.

In a standard left-to-right layout, this generally refers to the **top-left corner**.

### Tailwind

```html
<div class="size-32 rounded-ss-2xl">
    Tailwind
</div>
```

### Equivalent CSS

```css
.box {
    border-start-start-radius: 1rem;
}
```

In a standard left-to-right writing direction, this behaves like:

```css
border-top-left-radius: 1rem;
```

The logical property is useful because it can adapt to different writing directions.

---

# 15. `rounded-se-3xl`

The `se` means **start-end**.

In a standard left-to-right layout, this generally refers to the **top-right corner**.

### Tailwind

```html
<div class="size-32 rounded-se-3xl">
    Tailwind
</div>
```

### Equivalent CSS

```css
.box {
    border-start-end-radius: 1.5rem;
}
```

In a standard left-to-right layout, this is approximately:

```css
border-top-right-radius: 1.5rem;
```

---

# 16. `border-dashed`

### Tailwind

```html
<div class="border-4 border-dashed">
    Tailwind
</div>
```

This changes the border style to dashed.

### Equivalent CSS

```css
.box {
    border-width: 4px;
    border-style: dashed;
}
```

---

# 17. `border-dotted`

### Tailwind

```html
<div class="border-4 border-dotted">
    Tailwind
</div>
```

This creates a dotted border.

### Equivalent CSS

```css
.box {
    border-width: 4px;
    border-style: dotted;
}
```

---

# 18. Complete Example

Here is your Tailwind code with comments:

```html
<div class="border m-10 p-4">
    Basic border
</div>

<div class="m-10 p-4 w-96 border-4">
    4px border
</div>

<div class="m-10 p-4 w-96 border-4 border-blue-600">
    Blue border
</div>

<div class="m-10 p-4 w-96 border-4
            border-t-blue-600
            border-b-red-500
            border-l-lime-400
            border-r-green-700">
    Different color on each side
</div>

<div class="m-10 p-4 size-32 border-4
            border-yellow-600 rounded-full">
    Circle
</div>

<div class="m-10 p-4 size-32 border-4
            border-red-500 rounded-t-full">
    Rounded top
</div>

<div class="m-10 p-4 size-32 border-4
            border-green-600 rounded-b-full">
    Rounded bottom
</div>

<div class="m-10 p-4 size-32 border-4
            border-slate-600 rounded-sm">
    Small radius
</div>

<div class="m-10 p-4 size-32 border-4
            border-orange-600 rounded-3xl">
    Large radius
</div>

<div class="m-10 p-4 size-32 border-4
            border-green-600 rounded-ss-2xl">
    Start-start radius
</div>

<div class="m-10 p-4 size-32 border-4
            border-green-600 rounded-se-3xl">
    Start-end radius
</div>

<div class="m-10 p-4 size-32 border-4
            border-green-600 rounded-b-full border-dashed">
    Dashed border
</div>

<div class="m-10 p-4 size-32 border-4
            border-green-600 rounded-ss-4xl border-dotted">
    Dotted border
</div>
```

---

# 19. The Same Concept Using Normal CSS

Instead of writing:

```html
<div class="m-10 p-4 w-96 border-4 border-blue-600">
    Tailwind
</div>
```

You could create a CSS class:

```css
.box {
    margin: 40px;
    padding: 16px;
    width: 384px;
    border-width: 4px;
    border-style: solid;
    border-color: #2563eb;
}
```

Then HTML becomes:

```html
<div class="box">
    Tailwind
</div>
```

So the main difference is:

### Tailwind

```html
<div class="m-10 p-4 w-96 border-4 border-blue-600">
```

### Normal CSS

```html
<div class="box">
```

```css
.box {
    margin: 40px;
    padding: 16px;
    width: 384px;
    border: 4px solid #2563eb;
}
```

---

# Quick Reference Table

| Tailwind Class       | CSS Equivalent                | Purpose                    |
| -------------------- | ----------------------------- | -------------------------- |
| `border`             | `border-width: 1px`           | Basic border               |
| `border-4`           | `border-width: 4px`           | 4px border                 |
| `border-blue-600`    | `border-color: ...`           | Border color               |
| `border-t-blue-600`  | `border-top-color: ...`       | Top border color           |
| `border-b-red-500`   | `border-bottom-color: ...`    | Bottom border color        |
| `border-l-lime-400`  | `border-left-color: ...`      | Left border color          |
| `border-r-green-700` | `border-right-color: ...`     | Right border color         |
| `m-10`               | `margin: 40px`                | Margin                     |
| `p-4`                | `padding: 16px`               | Padding                    |
| `w-96`               | `width: 384px`                | Width                      |
| `size-32`            | `width: 128px; height: 128px` | Width + height             |
| `rounded-full`       | `border-radius: 9999px`       | Fully rounded              |
| `rounded-t-full`     | Top corner radius             | Rounded top                |
| `rounded-b-full`     | Bottom corner radius          | Rounded bottom             |
| `rounded-sm`         | Small radius                  | Slight rounding            |
| `rounded-3xl`        | `border-radius: 1.5rem`       | Large rounding             |
| `rounded-ss-2xl`     | `border-start-start-radius`   | Logical start-start corner |
| `rounded-se-3xl`     | `border-start-end-radius`     | Logical start-end corner   |
| `border-dashed`      | `border-style: dashed`        | Dashed border              |
| `border-dotted`      | `border-style: dotted`        | Dotted border              |

---

## The Main Concept to Remember

Think of a Tailwind class as a **short name for a CSS property**.

```text
Tailwind Class
      ↓
CSS Property
      ↓
Browser Styling
```

For example:

```text
m-10
  ↓
margin: 40px

p-4
  ↓
padding: 16px

w-96
  ↓
width: 384px

size-32
  ↓
width + height: 128px

border-4
  ↓
border-width: 4px

border-blue-600
  ↓
border-color: blue

rounded-full
  ↓
border-radius: very large

border-dashed
  ↓
border-style: dashed
```

