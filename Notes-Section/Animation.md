
# Tailwind CSS — Animations

CSS animations are used to make an element **move or change automatically** without needing to hover or click.

Tailwind CSS provides ready-made animation utilities such as:

* `animate-spin`
* `animate-ping`
* `animate-pulse`
* `animate-bounce`

---

# 1. `animate-bounce`

The `animate-bounce` class makes an element **move up and down like a bouncing ball**.

### Example

```html
<div class="size-10 bg-red-600 rounded-full p-5 m-5 animate-bounce"></div>
```

### Explanation

| Class            | Purpose                      |
| ---------------- | ---------------------------- |
| `size-10`        | Sets width and height        |
| `bg-red-600`     | Sets red background          |
| `rounded-full`   | Makes the element circular   |
| `p-5`            | Adds padding                 |
| `m-5`            | Adds margin                  |
| `animate-bounce` | Creates a bouncing animation |

### Result

```text
    ●
    ↓
    ●
    ↓
    ●
```

The element continuously moves up and down.

---

# 2. `animate-spin`

The `animate-spin` class continuously **rotates an element**.

### Example

```html
<div class="size-10 bg-red-600 p-5 m-5 animate-spin"></div>
```

The element continuously rotates:

```text
   ┌─────┐
   │  ■  │  ↻
   └─────┘
```

### Common use cases

`animate-spin` is useful for:

* Loading indicators
* Loading buttons
* Spinners
* Progress indicators

### Example

```html
<div class="size-10 border-4 border-gray-300 border-t-blue-500 rounded-full animate-spin"></div>
```

This can be used as a **loading spinner**.

---

# 3. `animate-pulse`

The `animate-pulse` class makes an element **fade in and out continuously**.

### Example

```html
<div class="size-32 bg-red-600 m-52 rounded-full animate-pulse"></div>
```

The element continuously changes its opacity.

```text
Visible
   ↓
Less Visible
   ↓
Visible
   ↓
Less Visible
```

### Common use cases

`animate-pulse` is commonly used for:

* Loading placeholders
* Skeleton screens
* Loading cards
* Loading text

Example:

```html
<div class="h-4 w-32 bg-gray-300 animate-pulse"></div>
```

This can represent text that is still loading.

---

# 4. Animation on an Image

You can also apply animations to images or elements that contain background images.

Your example:

```html
<div
    class="size-32
    bg-[url('IMAGE_URL')]
    bg-no-repeat
    bg-center
    bg-contain
    animate-spin">
</div>
```

Here:

* `size-32` → Creates a 32 × 32 size element
* `bg-[url(...)]` → Adds a background image
* `bg-no-repeat` → Prevents image repetition
* `bg-center` → Centers the image
* `bg-contain` → Fits the complete image inside the element
* `animate-spin` → Continuously rotates the element

So the complete element, including its background image, will rotate.

---

# 5. Using Multiple Animation Classes

In your code, you wrote:

```html
<div class="size-10 bg-red-600 p-5 m-5 animate-bounce animate-spin"></div>
```

You have applied:

```text
animate-bounce
        +
animate-spin
```

Both classes try to apply an animation to the same element.

### Important concept

You generally **should not use multiple animation utilities together** if they both define the CSS `animation` property.

For example:

```html
animate-bounce animate-spin
```

Both define an animation, so one animation may override the other depending on the generated CSS order.

Instead, use one:

```html
animate-bounce
```

or:

```html
animate-spin
```

If you want a **custom animation that combines bouncing and spinning**, you should create a custom CSS animation.

---

# 6. Difference Between Animation and Transition

This is an important concept.

### Transition

A transition usually happens when there is a **state change**.

For example:

```html
<button class="bg-blue-500 hover:bg-blue-900 transition duration-500">
    Login
</button>
```

The transition happens when:

```text
Normal
  ↓
Hover
  ↓
Color changes smoothly
```

### Animation

An animation can run **automatically**.

```html
<div class="animate-spin"></div>
```

The element starts spinning automatically.

### Comparison

| Transition                   | Animation                       |
| ---------------------------- | ------------------------------- |
| Usually needs a state change | Can run automatically           |
| Commonly used with `hover:`  | Uses `animate-*`                |
| `transition`                 | `animate-spin`                  |
| `duration-500`               | Animation has predefined timing |
| Good for UI interactions     | Good for continuous effects     |

---

# 7. Main Tailwind Animation Classes

| Class            | Effect              | Common Use                |
| ---------------- | ------------------- | ------------------------- |
| `animate-spin`   | Continuous rotation | Loading spinner           |
| `animate-ping`   | Expands and fades   | Notifications, indicators |
| `animate-pulse`  | Fades in and out    | Loading skeleton          |
| `animate-bounce` | Moves up and down   | Attention effects         |

---

# 8. Quick Examples

### Bounce

```html
<div class="size-10 bg-red-500 rounded-full animate-bounce"></div>
```

**Effect:** Moves up and down.

---

### Spin

```html
<div class="size-10 bg-blue-500 animate-spin"></div>
```

**Effect:** Continuously rotates.

---

### Pulse

```html
<div class="size-10 bg-green-500 animate-pulse"></div>
```

**Effect:** Fades in and out.

---

### Ping

```html
<div class="size-10 bg-purple-500 rounded-full animate-ping"></div>
```

**Effect:** Expands and fades away repeatedly.

---

# Quick Revision

```text
animate-bounce
       ↓
   Bounces

animate-spin
       ↓
   Rotates

animate-pulse
       ↓
   Fades in/out

animate-ping
       ↓
   Expands + fades
```

### Remember

**`transition-*`** → Used for **smooth changes between states**.

**`duration-*`** → Controls **how long a transition takes**.

**`animate-*`** → Used for **predefined continuous animations**.

**`hover:*`** → Applies a utility when the mouse is over an element.

For example:

```html
hover:scale-150
```

means **scale when hovered**, while:

```html
animate-spin
```

means **keep spinning automatically**.
