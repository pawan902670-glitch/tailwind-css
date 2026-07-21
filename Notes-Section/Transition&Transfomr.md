
# Tailwind CSS — Transitions, Duration, Opacity & Transforms

## 1. Transition

A **transition** makes a change happen smoothly instead of immediately.

### Without transition

```html
<button class="bg-blue-500 hover:bg-blue-900">
    Login
</button>
```

When you hover, the background color changes immediately.

### With transition

```html
<button class="bg-blue-500 hover:bg-blue-900 transition duration-1000">
    Login
</button>
```

Now the color change happens smoothly.

### Important classes

| Class                  | Meaning                               |
| ---------------------- | ------------------------------------- |
| `transition`           | Enables transition                    |
| `transition-colors`    | Transition only for colors            |
| `transition-transform` | Transition only for transform effects |
| `transition-all`       | Transition all changing properties    |

**Example:**

```html
<button class="transition-colors duration-500 hover:bg-blue-900">
    Login
</button>
```

---

# 2. Duration

`duration-*` controls **how long the transition takes**.

The time is written in milliseconds (`ms`).

```html
duration-100
duration-300
duration-500
duration-700
duration-1000
```

### Example

```html
<button class="bg-blue-500 hover:bg-blue-900 transition duration-1000">
    Login
</button>
```

Here:

* `transition` → makes the change smooth
* `duration-1000` → transition takes **1000ms = 1 second**

### Simple example

```html
<div class="bg-red-500 hover:bg-blue-500 transition duration-500">
    Box
</div>
```

When you hover over the box, the color changes smoothly in **0.5 seconds**.

---

# 3. Opacity

**Opacity** controls the transparency of an element.

* `opacity-100` → completely visible
* `opacity-50` → 50% visible
* `opacity-0` → completely transparent

### Example

```html
<button class="bg-blue-500 hover:opacity-50 transition duration-500">
    Login
</button>
```

When you hover, the button becomes **50% transparent**.

### Important correction in your code

You wrote:

```html
hover:opacity-5
```

Usually, if you want **50% opacity**, use:

```html
hover:opacity-50
```

Example:

```html
<button class="bg-blue-500 p-2 m-10 text-white rounded
hover:opacity-50 transition duration-1000">
    Login
</button>
```

---

# 4. Transform

A **transform** changes the visual position, size, or rotation of an element.

Tailwind provides transform utilities for:

* Rotate
* Scale
* Move/Translate
* Skew

Your code mainly practices **Rotate** and **Scale**.

---

# 5. Rotate

`rotate-*` rotates an element.

### Example

```html
<button class="bg-red-500 p-2 text-white rounded
hover:rotate-45 transition-transform duration-1000">
    Login
</button>
```

When you hover:

```text
rotate-45
```

The button rotates by **45 degrees**.

### Common classes

```html
rotate-0
rotate-45
rotate-90
rotate-180
```

### Negative rotation

You can also rotate in the opposite direction:

```html
hover:-rotate-45
```

---

# 6. Scale

`scale-*` changes the **size of an element**.

### Scale

```html
hover:scale-150
```

The element becomes **1.5 times larger**.

Example:

```html
<button class="bg-red-500 p-2 text-white rounded
hover:scale-150 transition-transform duration-500">
    Login
</button>
```

### Important correction

You wrote:

```html
hover:scale-145
```

Tailwind does not provide every random scale value by default. Use a supported utility such as:

```html
hover:scale-150
```

or an arbitrary value:

```html
hover:scale-[1.45]
```

---

# 7. Scale X

`scale-x-*` changes the size of an element **only on the X-axis**.

The X-axis means **horizontal direction**.

```text
        X →
  ┌─────────────┐
  │    Button   │
  └─────────────┘
```

### Example

```html
<button class="hover:scale-x-150 transition-transform duration-500">
    Login
</button>
```

The button becomes wider horizontally.

### Custom value

If you want exactly `1.45`:

```html
hover:scale-x-[1.45]
```

---

# 8. Scale Y

`scale-y-*` changes the size of an element **only on the Y-axis**.

The Y-axis means **vertical direction**.

```text
       Y
       ↓
   ┌─────────┐
   │ Button  │
   └─────────┘
```

### Example

```html
<button class="hover:scale-y-150 transition-transform duration-500">
    Login
</button>
```

The button becomes taller vertically.

### Custom value

```html
hover:scale-y-[1.45]
```

---

# 9. Scale X + Scale Y Together

You can apply both horizontal and vertical scaling.

```html
<button class="bg-red-500 p-2 text-white rounded
hover:scale-x-150
hover:scale-y-125
transition-transform duration-500">
    Login
</button>
```

Here:

* `scale-x-150` → increases width
* `scale-y-125` → increases height
* `transition-transform` → makes the transformation smooth
* `duration-500` → takes 0.5 seconds

You can also use normal `scale-*` when you want to scale both axes equally:

```html
hover:scale-150
```

---

# 10. Background Image

You used a background image in your `<div>`.

```html
<div class="size-32
bg-[url('IMAGE_URL')]
bg-no-repeat
bg-center
bg-contain">
</div>
```

Let's understand each class.

### `size-32`

Sets both:

```text
width = 8rem
height = 8rem
```

So the element becomes a square.

---

### `bg-[url('...')]`

Adds a background image.

```html
bg-[url('https://example.com/image.jpg')]
```

The `[]` syntax is called an **arbitrary value** in Tailwind.

---

### `bg-no-repeat`

Prevents the background image from repeating.

```html
bg-no-repeat
```

Without this, a small background image may repeat multiple times.

---

### `bg-center`

Places the background image in the center.

```html
bg-center
```

---

### `bg-contain`

Makes the complete image fit inside the container.

```html
bg-contain
```

The entire image remains visible, but there may be empty space around it.

---

# 11. Combining Everything

Your final `<div>` uses multiple concepts together:

```html
<div class="
    size-32
    bg-[url('IMAGE_URL')]
    bg-no-repeat
    bg-center
    bg-contain
    hover:rotate-45
    hover:scale-x-150
    hover:scale-y-150
    transition-transform
    duration-1000
">
    Code step by step
</div>
```

### What happens?

When you move the mouse over the `<div>`:

1. The element rotates by **45 degrees**.
2. It becomes wider using `scale-x`.
3. It becomes taller using `scale-y`.
4. The transformation happens smoothly.
5. The transformation takes **1 second**.

---

# Quick Revision

| Topic                | Class                  | Purpose                       |
| -------------------- | ---------------------- | ----------------------------- |
| Transition           | `transition`           | Makes changes smooth          |
| Color transition     | `transition-colors`    | Smooth color changes          |
| Transform transition | `transition-transform` | Smooth transform changes      |
| Duration             | `duration-500`         | Transition takes 500ms        |
| Opacity              | `opacity-50`           | Makes element 50% transparent |
| Rotate               | `rotate-45`            | Rotates element 45°           |
| Scale                | `scale-150`            | Increases overall size        |
| Scale X              | `scale-x-150`          | Increases horizontal size     |
| Scale Y              | `scale-y-150`          | Increases vertical size       |
| Background URL       | `bg-[url(...)]`        | Adds background image         |
| No Repeat            | `bg-no-repeat`         | Stops image repetition        |
| Center               | `bg-center`            | Centers background image      |
| Contain              | `bg-contain`           | Fits complete image inside    |

### Main Concept

```text
Transition
    ↓
Controls smoothness

Duration
    ↓
Controls speed/time

Transform
    ↓
Changes element visually

Rotate
    ↓
Turns the element

Scale
    ↓
Changes element size

Opacity
    ↓
Controls transparency

Background utilities
    ↓
Control background image position and size
```

**Practice tip:** In your code, try changing `duration-1000` to `duration-300`, `duration-700`, and `duration-2000`. This will help you clearly understand how **duration affects the speed of the transition**.
