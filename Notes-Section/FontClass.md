
# Tailwind CSS Notes — Typography

Tailwind CSS provides utility classes for controlling the appearance of text. The main typography utilities in your example are:

1. Font Family
2. Font Size
3. Font Weight
4. Hover State
5. Text Color

---

# 1. Font Family

A font family determines the typeface used to display text.

Your HTML:

```html
<p class="font-sans">Hello everyone</p>

<p class="font-serif">Hello everyone</p>

<p class="font-mono">Hello everyone</p>
```

> **Note:** Your original code uses `font-sens`, but the correct Tailwind class is `font-sans`.

Tailwind provides three default font-family utilities:

| Tailwind Class | Meaning         |
| -------------- | --------------- |
| `font-sans`    | Sans-serif font |
| `font-serif`   | Serif font      |
| `font-mono`    | Monospace font  |

### `font-sans`

```html
<p class="font-sans">
    Hello everyone
</p>
```

Equivalent CSS:

```css
.box {
    font-family: sans-serif;
}
```

Sans-serif fonts do not have decorative strokes at the ends of letters.

---

### `font-serif`

```html
<p class="font-serif">
    Hello everyone
</p>
```

Equivalent CSS:

```css
.box {
    font-family: serif;
}
```

Serif fonts have small decorative strokes on letters.

---

### `font-mono`

```html
<p class="font-mono">
    Hello everyone
</p>
```

Equivalent CSS:

```css
.box {
    font-family: monospace;
}
```

Monospace fonts give each character approximately the same width. They are commonly used for programming code.

---

# 2. Font Size

Tailwind provides utility classes for controlling text size.

For example:

```html
<p class="text-9xl">
    Hellooooooooo.
</p>
```

Here:

```text
text-9xl
    ↓
text = text-related utility
9xl  = font-size scale
```

The default Tailwind font-size scale goes from very small sizes to very large sizes.

### Common Font Sizes

| Tailwind Class | Approximate Font Size |
| -------------- | --------------------: |
| `text-xs`      |                  12px |
| `text-sm`      |                  14px |
| `text-base`    |                  16px |
| `text-lg`      |                  18px |
| `text-xl`      |                  20px |
| `text-2xl`     |                  24px |
| `text-3xl`     |                  30px |
| `text-4xl`     |                  36px |
| `text-5xl`     |                  48px |
| `text-6xl`     |                  60px |
| `text-7xl`     |                  72px |
| `text-8xl`     |                  96px |
| `text-9xl`     |                 128px |

### Example

```html
<p class="text-5xl">
    Hello
</p>
```

Equivalent CSS:

```css
.box {
    font-size: 3rem;
}
```

The exact value is based on Tailwind's default theme.

---

# 3. `text-md` vs `text-base`

Your example contains:

```html
<p class="text-md">Helllo!</p>
```

In the default Tailwind CSS v4 theme, `text-md` is **not one of the standard default font-size utilities**.

The standard class for the normal/default text size is:

```html
<p class="text-base">
    Hello!
</p>
```

Equivalent CSS:

```css
.box {
    font-size: 1rem;
}
```

So prefer:

```html
text-base
```

for normal body text.

---

# 4. Font Weight

Font weight controls how thick or bold the text appears.

Your example:

```html
<p class="text-5xl font-thin">
    I can do it
</p>
```

Here:

```text
text-5xl
    ↓
Font size

font-thin
    ↓
Font weight
```

Tailwind provides several font-weight utilities.

| Tailwind Class    | Font Weight |
| ----------------- | ----------: |
| `font-thin`       |         100 |
| `font-extralight` |         200 |
| `font-light`      |         300 |
| `font-normal`     |         400 |
| `font-medium`     |         500 |
| `font-semibold`   |         600 |
| `font-bold`       |         700 |
| `font-extrabold`  |         800 |
| `font-black`      |         900 |

---

# 5. `font-thin`

```html
<p class="font-thin">
    I can do it
</p>
```

Equivalent CSS:

```css
.box {
    font-weight: 100;
}
```

This produces very thin text.

---

# 6. `font-extralight`

```html
<p class="font-extralight">
    I can do it
</p>
```

Equivalent CSS:

```css
.box {
    font-weight: 200;
}
```

---

# 7. `font-light`

```html
<p class="font-light">
    I can do it
</p>
```

Equivalent CSS:

```css
.box {
    font-weight: 300;
}
```

---

# 8. `font-normal`

```html
<p class="font-normal">
    I can do it
</p>
```

Equivalent CSS:

```css
.box {
    font-weight: 400;
}
```

This is the normal font weight.

---

# 9. `font-medium`

```html
<p class="font-medium">
    I can do it
</p>
```

Equivalent CSS:

```css
.box {
    font-weight: 500;
}
```

---

# 10. `font-semibold`

```html
<p class="font-semibold">
    I can do it
</p>
```

Equivalent CSS:

```css
.box {
    font-weight: 600;
}
```

This is slightly lighter than bold.

---

# 11. `font-bold`

```html
<p class="font-bold">
    I can do it
</p>
```

Equivalent CSS:

```css
.box {
    font-weight: 700;
}
```

This is commonly used for headings and important text.

---

# 12. `font-extrabold`

```html
<p class="font-extrabold">
    I can do it
</p>
```

Equivalent CSS:

```css
.box {
    font-weight: 800;
}
```

---

# 13. `font-black`

```html
<p class="font-black">
    I can do it
</p>
```

Equivalent CSS:

```css
.box {
    font-weight: 900;
}
```

This is one of the heaviest font weights.

---

# 14. Combining Font Size and Font Weight

You can combine multiple Tailwind utilities on the same element.

Example:

```html
<p class="text-5xl font-bold">
    I can do it
</p>
```

This means:

```text
text-5xl
    ↓
Large text

font-bold
    ↓
Bold text
```

Equivalent CSS:

```css
.box {
    font-size: 3rem;
    font-weight: 700;
}
```

This is one of the main ideas behind Tailwind CSS: **you can combine multiple utility classes to build the final design.**

---

# 15. Hover State

Your last example is:

```html
<p class="text-5xl font-bold hover:text-green-900">
    I can do it
</p>
```

Here:

```text
text-5xl
    ↓
Large text

font-bold
    ↓
Bold text

hover:text-green-900
    ↓
When mouse hovers over text,
change text color
```

The `hover:` prefix means:

> Apply this utility only when the user hovers over the element.

Equivalent CSS:

```css
.box {
    font-size: 3rem;
    font-weight: 700;
}

.box:hover {
    color: #14532d;
}
```

So:

```html
hover:text-green-900
```

is conceptually equivalent to:

```css
.box:hover {
    color: green;
}
```

The exact Tailwind color value comes from the Tailwind color palette.

---

# 16. Understanding Tailwind Prefixes

One of the most important concepts is understanding the structure of Tailwind classes.

For example:

```html
hover:text-green-900
```

Break it down:

```text
hover:
   ↓
State

text-
   ↓
Text color property

green-
   ↓
Color family

900
   ↓
Color shade
```

Another example:

```html
md:text-5xl
```

Breakdown:

```text
md:
   ↓
Medium breakpoint

text-
   ↓
Font size

5xl
   ↓
Font size value
```

So Tailwind classes often follow a pattern:

```text
variant : utility - value
```

Example:

```text
hover:text-green-900
  │        │      │
  │        │      └── Value
  │        └───────── Utility
  └────────────────── Variant
```

---

# 17. Your Complete Example Explained

```html
<p class="font-sans">
    Hello everyone
</p>
```

➡️ Uses a sans-serif font.

```html
<p class="font-serif">
    Hello everyone
</p>
```

➡️ Uses a serif font.

```html
<p class="font-mono">
    Hello everyone
</p>
```

➡️ Uses a monospace font.

```html
<p class="text-9xl">
    Hellooooooooo.
</p>
```

➡️ Creates extremely large text.

```html
<p class="text-5xl font-bold">
    I can do it
</p>
```

➡️ Creates large, bold text.

```html
<p class="text-5xl font-bold hover:text-green-900">
    I can do it
</p>
```

➡️ Creates large, bold text that changes to green when the mouse hovers over it.

---

# 18. The Same Example in Normal CSS

Tailwind:

```html
<p class="text-5xl font-bold hover:text-green-900">
    I can do it
</p>
```

Normal CSS:

```html
<p class="my-text">
    I can do it
</p>
```

```css
.my-text {
    font-size: 3rem;
    font-weight: 700;
}

.my-text:hover {
    color: #14532d;
}
```

So the relationship is:

```text
Tailwind CSS
──────────────────────────────

text-5xl
    ↓
font-size

font-bold
    ↓
font-weight

hover:
    ↓
:hover

text-green-900
    ↓
color
```

---

# Quick Revision

```text
FONT FAMILY
font-sans       → Sans-serif
font-serif      → Serif
font-mono       → Monospace


FONT SIZE
text-xs         → Extra small
text-sm         → Small
text-base       → Normal
text-lg         → Large
text-xl         → Extra large
text-2xl        → 2x large
...
text-9xl        → Very large


FONT WEIGHT
font-thin       → 100
font-extralight → 200
font-light      → 300
font-normal     → 400
font-medium     → 500
font-semibold   → 600
font-bold       → 700
font-extrabold  → 800
font-black      → 900


STATE
hover:          → Apply when mouse hovers
```

### Most important concept

Tailwind typography is built by combining utilities:

```html
<p class="font-sans text-5xl font-bold hover:text-green-900">
    I can do it
</p>
```

You can read it as:

> **Use a sans-serif font + make the text very large + make it bold + change its color when hovered.**

