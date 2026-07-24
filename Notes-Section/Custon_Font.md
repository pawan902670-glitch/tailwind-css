
# Tailwind CSS — Custom Fonts, Themes & Breakpoints

## Complete Code

```css
@import url('https://fonts.googleapis.com/css2?family=Moon+Dance&display=swap');

@import "tailwindcss";

@theme {
    --breakpoint-sm: 700px;
    --breakpoint-big: 800px;
    --breakpoint-md: 900px;
    --breakpoint-lg: 1000px;

    --font-moonDance: "Moon Dance", cursive;
}
```

---

# 1. `@import`

### Definition

`@import` is a CSS rule used to import an external stylesheet or CSS resource into the current CSS file.

### Example

```css
@import url('https://example.com/style.css');
```

In your code, you are using `@import` twice.

---

# 2. Google Fonts Import

```css
@import url('https://fonts.googleapis.com/css2?family=Moon+Dance&display=swap');
```

### Explanation

This imports the **Moon Dance** font from Google Fonts.

After importing the font, you can use it in your website.

### Breakdown

```text
@import
    ↓
CSS import rule

url(...)
    ↓
Specifies the location of the external resource

Google Fonts URL
    ↓
Loads the Moon Dance font
```

---

# 3. `@import "tailwindcss"`

```css
@import "tailwindcss";
```

### Explanation

This imports Tailwind CSS into your stylesheet.

After importing Tailwind CSS, you can use Tailwind utility classes such as:

```html
<div class="text-blue-500 p-4">
    Hello
</div>
```

Here:

* `text-blue-500` → Changes the text color.
* `p-4` → Adds padding.

---

# 4. `@theme`

```css
@theme {
    ...
}
```

### Definition

`@theme` is a Tailwind CSS v4 directive used to define **custom theme variables**, also called **design tokens**.

You can define things such as:

* Fonts
* Colors
* Breakpoints
* Spacing
* Animations

### Example

```css
@theme {
    --font-moonDance: "Moon Dance", cursive;
}
```

This tells Tailwind that you are defining a custom font theme variable.

---

# 5. CSS Custom Property

```css
--font-moonDance
```

This is a **CSS custom property**, commonly called a **CSS variable**.

CSS custom properties start with two hyphens:

```text
--
```

### Example

```css
--my-color: red;
```

You can use a CSS variable with:

```css
color: var(--my-color);
```

In Tailwind CSS v4, theme variables follow specific naming conventions. Tailwind uses these names to generate corresponding utility classes.

---

# 6. `--font-`

In this code:

```css
--font-moonDance
```

The part:

```text
--font-
```

is the **font namespace** used by Tailwind.

It tells Tailwind that this theme variable represents a font family.

The remaining part:

```text
moonDance
```

is your custom name.

Therefore:

```css
--font-moonDance: "Moon Dance", cursive;
```

generates the utility:

```html
font-moonDance
```

### Formula

```text
--font-moonDance
       ↓
--font- + moonDance
       ↓
font-moonDance
```

---

# 7. `moonDance`

```text
moonDance
```

This is the **custom name** you chose for your font theme variable.

You could choose another name, for example:

```css
--font-myFont: "Moon Dance", cursive;
```

Then you would use:

```html
<div class="font-myFont">
    Hello
</div>
```

Or:

```css
--font-fancy: "Moon Dance", cursive;
```

Then:

```html
<div class="font-fancy">
    Hello
</div>
```

So, the name `moonDance` is not the actual font name. It is simply the **custom name of your Tailwind theme variable**.

---

# 8. `"Moon Dance"`

```css
"Moon Dance"
```

This is the **actual font family name**.

It is the font that you imported from Google Fonts.

Compare these two:

```css
--font-moonDance: "Moon Dance", cursive;
```

| Part           | Meaning                         |
| -------------- | ------------------------------- |
| `--font-`      | Tailwind font namespace         |
| `moonDance`    | Your custom theme variable name |
| `"Moon Dance"` | Actual font family              |
| `cursive`      | Fallback font family            |

Therefore, these are **not the same thing**:

```text
moonDance
```

and

```text
Moon Dance
```

`moonDance` is your custom name, while `"Moon Dance"` is the actual font family.

---

# 9. `font-moonDance`

In HTML:

```html
<div class="font-moonDance">
    Custom Font
</div>
```

`font-moonDance` is the **Tailwind utility class** generated from:

```css
--font-moonDance: "Moon Dance", cursive;
```

The complete flow is:

```text
@theme
    ↓
--font-moonDance
    ↓
Custom font theme variable
    ↓
font-moonDance
    ↓
Tailwind utility class
    ↓
Applied to HTML element
```

### Example

```html
<h1 class="font-moonDance">
    Welcome
</h1>
```

The `h1` will use the **Moon Dance** font.

---

# 10. `cursive`

```css
cursive
```

`cursive` is a **generic CSS font family**.

It works as a **fallback**.

For example:

```css
font-family: "Moon Dance", cursive;
```

The browser follows this order:

```text
Is Moon Dance available?
        ↓
       YES
        ↓
Use Moon Dance

       NO
        ↓
Use a cursive-style fallback font
```

This is why it is good practice to provide a fallback font.

---

# 11. `--breakpoint-sm`

```css
--breakpoint-sm: 700px;
```

This defines a custom `sm` breakpoint at **700px**.

You can use it with:

```html
<div class="text-red-500 sm:text-blue-500">
    Hello
</div>
```

The behavior is:

```text
Below 700px
    ↓
Red text

700px and above
    ↓
Blue text
```

---

# 12. `--breakpoint-md`

```css
--breakpoint-md: 900px;
```

This defines the `md` breakpoint at **900px**.

Example:

```html
<div class="text-red-500 md:text-blue-500">
    Hello
</div>
```

Behavior:

```text
Below 900px
    ↓
Red

900px and above
    ↓
Blue
```

---

# 13. `--breakpoint-lg`

```css
--breakpoint-lg: 1000px;
```

This defines the `lg` breakpoint at **1000px**.

Example:

```html
<div class="text-red-500 lg:text-green-500">
    Hello
</div>
```

Behavior:

```text
Below 1000px
    ↓
Red

1000px and above
    ↓
Green
```

---

# 14. Custom Breakpoint: `big`

You created your own breakpoint:

```css
--breakpoint-big: 800px;
```

Because you named it `big`, you can use:

```html
<div class="text-red-500 big:text-green-500">
    Hello
</div>
```

Behavior:

```text
Below 800px
    ↓
Red

800px and above
    ↓
Green
```

The important point is that `big` is a **custom breakpoint name**.

---

# 15. Responsive Prefix

In Tailwind, a breakpoint is used as a prefix before a utility class.

Example:

```html
sm:text-blue-500
```

Breakdown:

```text
sm
 ↓
Breakpoint

:
 ↓
Separator

text-blue-500
 ↓
Utility class
```

Meaning:

> Apply `text-blue-500` at the `sm` breakpoint and above.

---

# 16. Complete Example

### CSS

```css
@import url('https://fonts.googleapis.com/css2?family=Moon+Dance&display=swap');

@import "tailwindcss";

@theme {
    --breakpoint-sm: 700px;
    --breakpoint-big: 800px;
    --breakpoint-md: 900px;
    --breakpoint-lg: 1000px;

    --font-moonDance: "Moon Dance", cursive;
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

    <div>
        Simple Font
    </div>

    <div class="font-moonDance">
        Custom Font
    </div>

    <div class="text-red-500 sm:text-blue-500 big:text-green-500 md:text-yellow-500 lg:text-purple-500">
        Responsive Text
    </div>

</body>
</html>
```

---

# Quick Revision Table

| Term               | Meaning                                                    |
| ------------------ | ---------------------------------------------------------- |
| `@import`          | Imports an external CSS resource                           |
| `url()`            | Specifies the location of an external resource             |
| `@theme`           | Defines custom Tailwind theme variables                    |
| `--`               | Prefix for CSS custom properties                           |
| `--font-`          | Tailwind's font theme namespace                            |
| `moonDance`        | Your custom font theme variable name                       |
| `"Moon Dance"`     | The actual font family name                                |
| `cursive`          | Fallback generic font family                               |
| `font-moonDance`   | Tailwind utility for applying the custom font              |
| `--breakpoint-sm`  | Defines the `sm` breakpoint                                |
| `--breakpoint-md`  | Defines the `md` breakpoint                                |
| `--breakpoint-lg`  | Defines the `lg` breakpoint                                |
| `--breakpoint-big` | Defines your custom `big` breakpoint                       |
| `sm:`              | Applies a utility at the `sm` breakpoint and above         |
| `big:`             | Applies a utility at the custom `big` breakpoint and above |

## ⭐ Most Important Concept

```text
--font-moonDance
       ↓
--font-        → Tailwind font namespace
moonDance      → Your custom name
       ↓
font-moonDance → Generated Tailwind utility
       ↓
Used in HTML
```

So remember:

> **`moonDance`** = your custom theme variable name
> **`"Moon Dance"`** = the actual Google Font family
> **`font-moonDance`** = the Tailwind utility class used in HTML
