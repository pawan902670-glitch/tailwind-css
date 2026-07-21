
# Tailwind CSS — Custom Breakpoints with `@theme`

## 1. What is a Breakpoint?

A **breakpoint** is a screen width at which Tailwind applies a different style.

For example:

```html
md:bg-red-800
```

means:

> When the screen reaches the `md` breakpoint, use `bg-red-800`.

Tailwind provides default breakpoints, but you can also **change them or create your own custom breakpoint**.

---

# 2. Your Tailwind CSS File

You wrote:

```css
@import "tailwindcss";

@theme {
    --breakpoint-sm: 700px;
    --breakpoint-md: 900px;
    --breakpoint-lg: 1000px;
    --breakpoint-big: 800px;
}
```

The important part is:

```css
@theme {
    --breakpoint-sm: 700px;
    --breakpoint-md: 900px;
    --breakpoint-lg: 1000px;
    --breakpoint-big: 800px;
}
```

Here you are defining your **custom breakpoint values**.

---

# 3. Understanding `--breakpoint-sm`

You wrote:

```css
--breakpoint-sm: 700px;
```

This means the `sm` breakpoint now starts at:

```text
700px
```

So:

```html
sm:bg-blue-500
```

means:

> Apply `bg-blue-500` when the viewport width is **700px or wider**.

---

# 4. Understanding `--breakpoint-md`

You wrote:

```css
--breakpoint-md: 900px;
```

Therefore:

```html
md:bg-red-800
```

means:

> Apply `bg-red-800` when the viewport width is **900px or wider**.

This is different from Tailwind's default `md` breakpoint because you changed its value.

---

# 5. Understanding `--breakpoint-lg`

You wrote:

```css
--breakpoint-lg: 1000px;
```

Therefore:

```html
lg:bg-green-500
```

means:

> Apply `bg-green-500` when the viewport width is **1000px or wider**.

---

# 6. Creating a Custom Breakpoint: `big`

This is the most important part.

You created:

```css
--breakpoint-big: 800px;
```

This creates a custom responsive prefix:

```html
big:
```

Now you can write:

```html
big:bg-black
```

This means:

> Apply `bg-black` when the viewport width is **800px or wider**.

So unlike your previous code, where `big:` was not a default Tailwind breakpoint, **now `big:` is available because you defined it yourself**.

---

# 7. Connection Between CSS and HTML

This is the main concept you need to understand.

### CSS

```css
@theme {
    --breakpoint-big: 800px;
}
```

↓

### Tailwind creates the responsive prefix

```text
big:
```

↓

### HTML

```html
big:bg-black
```

↓

### Result

```text
Viewport width ≥ 800px
        ↓
Background becomes black
```

So the complete connection is:

```text
@theme
   ↓
Define breakpoint
   ↓
--breakpoint-big: 800px
   ↓
Creates `big:` responsive variant
   ↓
Use it in HTML
   ↓
big:bg-black
```

---

# 8. Your HTML Code

You wrote:

```html
<div class="
    bg-pink-400
    text-4xl
    md:bg-red-800
    lg:bg-green-500
    lg:bg-orange-600
    big:bg-black-500
">
    Hello Tailwind
</div>
```

Let's analyze every class.

### `bg-pink-400`

This is the default background.

```text
Default
   ↓
Pink
```

### `text-4xl`

Makes the text large.

This applies at all screen sizes unless you override the text size.

### `md:bg-red-800`

Your custom `md` is:

```css
--breakpoint-md: 900px;
```

Therefore:

```text
900px and above
      ↓
Red background
```

### `lg:bg-green-500`

Your custom `lg` is:

```css
--breakpoint-lg: 1000px;
```

Therefore:

```text
1000px and above
      ↓
Green background
```

### `big:bg-black-500`

Your custom `big` is:

```css
--breakpoint-big: 800px;
```

Therefore:

```text
800px and above
      ↓
Black background
```

But there is an important issue.

`bg-black-500` is not the standard Tailwind utility.

Use:

```html
big:bg-black
```

instead.

---

# 9. Important Problem: Your Breakpoints Are Out of Order

You defined:

```css
sm  = 700px
md  = 900px
lg  = 1000px
big = 800px
```

Notice:

```text
sm  → 700px
big → 800px
md  → 900px
lg  → 1000px
```

The names do not follow the numerical order you might expect.

You have:

```text
sm
md
lg
big
```

but the actual screen sizes are:

```text
sm = 700
big = 800
md = 900
lg = 1000
```

This can make your responsive design confusing.

### Better approach

If you want:

```text
sm → 700px
md → 800px
lg → 900px
big → 1000px
```

you can define:

```css
@theme {
    --breakpoint-sm: 700px;
    --breakpoint-md: 800px;
    --breakpoint-lg: 900px;
    --breakpoint-big: 1000px;
}
```

Now the order is logical:

```text
sm
 ↓
700px

md
 ↓
800px

lg
 ↓
900px

big
 ↓
1000px
```

---

# 10. Responsive Flow

Using the improved breakpoints:

```css
@theme {
    --breakpoint-sm: 700px;
    --breakpoint-md: 800px;
    --breakpoint-lg: 900px;
    --breakpoint-big: 1000px;
}
```

And HTML:

```html
<div class="
    bg-pink-400
    sm:bg-blue-500
    md:bg-red-800
    lg:bg-green-500
    big:bg-black
">
    Hello Tailwind
</div>
```

The behavior will be:

```text
0px ─────── 699px
Pink

700px ───── 799px
Blue

800px ───── 899px
Red

900px ───── 999px
Green

1000px+
Black
```

This is a very good example of **responsive design**.

---

# 11. Your `.box` CSS Class

You also wrote:

```css
.box {
    background-color: yellow;
    padding: 20px;
    border-radius: 10px;
}
```

This is **normal CSS**, not a Tailwind utility.

You can use it in HTML like this:

```html
<div class="box">
    Hello
</div>
```

It will apply:

* `background-color: yellow` → Yellow background
* `padding: 20px` → 20px inner spacing
* `border-radius: 10px` → Rounded corners

You could write the same thing using Tailwind:

```html
<div class="bg-yellow-400 p-5 rounded-lg">
    Hello
</div>
```

So:

```text
Traditional CSS
      ↓
.box {
    background-color: yellow;
    padding: 20px;
    border-radius: 10px;
}
```

Equivalent Tailwind:

```text
Tailwind CSS
      ↓
bg-yellow-400 p-5 rounded-lg
```

---

# 12. Complete Connected Example

### `input.css`

```css
@import "tailwindcss";

@theme {
    --breakpoint-sm: 700px;
    --breakpoint-md: 800px;
    --breakpoint-lg: 900px;
    --breakpoint-big: 1000px;
}

.box {
    background-color: yellow;
    padding: 20px;
    border-radius: 10px;
}
```

### HTML

```html
<!doctype html>
<html>
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <link rel="stylesheet" href="./output.css">
</head>

<body>

<div class="
    bg-pink-400
    text-4xl
    sm:bg-blue-500
    md:bg-red-800
    lg:bg-green-500
    big:bg-black
">
    Hello Tailwind
</div>

<div class="box">
    Normal CSS Box
</div>

</body>
</html>
```

---

# 13. Final Concept Map

```text
Tailwind CSS
      │
      ├── Responsive Design
      │       │
      │       ├── sm:
      │       ├── md:
      │       ├── lg:
      │       └── Custom breakpoint
      │
      └── @theme
              │
              └── Define breakpoint values
                      │
                      ├── --breakpoint-sm: 700px
                      ├── --breakpoint-md: 800px
                      ├── --breakpoint-lg: 900px
                      └── --breakpoint-big: 1000px
                                      │
                                      ↓
                              Use in HTML
                                      │
                                      ├── sm:bg-blue-500
                                      ├── md:bg-red-800
                                      ├── lg:bg-green-500
                                      └── big:bg-black
```

### ⭐ Most important thing to remember

`@theme` **defines the breakpoint**:

```css
--breakpoint-big: 1000px;
```

The responsive prefix **uses the breakpoint**:

```html
big:bg-black
```

So you can remember it as:

> **Define in CSS → Use in HTML → Style changes at that screen width.**

