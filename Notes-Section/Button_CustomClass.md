
# Tailwind CSS — `@layer` and `@apply` Notes

## 1. What are we implementing?

In your code, you are creating **reusable button styles** using Tailwind CSS.

Instead of writing many Tailwind utility classes directly in every HTML button:

```html
<button class="bg-blue-500 hover:bg-blue-400 text-white border border-blue-500">
    Primary
</button>
```

You create your own reusable class:

```css
.btn-primary {
    @apply bg-blue-500 hover:bg-blue-400 text-white border border-blue-500;
}
```

Then use it in HTML:

```html
<button class="btn-primary">Primary</button>
```

So the main implementation is:

> **Creating reusable custom CSS component classes using Tailwind's `@apply` directive.**

---

# 2. Main Concepts Used

Your code uses these important Tailwind CSS concepts:

1. **Utility-first CSS**
2. **`@apply`**
3. **`@layer`**
4. **Reusable component classes**
5. **Hover states**
6. **CSS class naming**
7. **Base button styles + variant styles**

Let's understand each one.

---

# 3. Utility-First CSS

Tailwind CSS follows a **utility-first approach**.

This means you style an element using small utility classes.

For example:

```html
<button class="bg-blue-500 text-white px-5 py-2 rounded">
    Primary
</button>
```

Each class performs one specific job:

| Class         | Purpose            |
| ------------- | ------------------ |
| `bg-blue-500` | Blue background    |
| `text-white`  | White text         |
| `px-5`        | Horizontal padding |
| `py-2`        | Vertical padding   |
| `rounded`     | Rounded corners    |

### Concept

Instead of creating CSS like:

```css
.primary-button {
    background-color: blue;
    color: white;
    padding: 10px 20px;
    border-radius: 5px;
}
```

Tailwind allows you to compose styles using utility classes.

### Purpose

The purpose is to:

* Build UI quickly
* Avoid writing repetitive CSS
* Use a consistent design system
* Make styling predictable

---

# 4. What is `@apply`?

`@apply` is a Tailwind CSS directive that allows you to combine multiple Tailwind utility classes into your own CSS class.

For example:

```css
.btn-primary {
    @apply bg-blue-500 hover:bg-blue-400 text-white border border-blue-500;
}
```

This is conceptually similar to writing:

```html
<button class="bg-blue-500 hover:bg-blue-400 text-white border border-blue-500">
    Primary
</button>
```

But now all those utilities are grouped into:

```css
.btn-primary
```

So you can simply write:

```html
<button class="btn-primary">Primary</button>
```

### Why use `@apply`?

It is useful when you have a group of utility classes that you repeatedly use.

For example:

```html
<button class="btn-primary">Save</button>
<button class="btn-primary">Submit</button>
<button class="btn-primary">Login</button>
```

Instead of repeating:

```html
class="bg-blue-500 hover:bg-blue-400 text-white border border-blue-500"
```

You create:

```css
.btn-primary {
    @apply bg-blue-500 hover:bg-blue-400 text-white border border-blue-500;
}
```

Then:

```html
class="btn-primary"
```

### Simple definition

> **`@apply` = Combine Tailwind utility classes into a reusable CSS class.**

---

# 5. What is `@layer`?

You wrote:

```css
@layer component {
```

The idea is to tell Tailwind that you are adding your custom styles as a specific layer.

However, there is an important correction:

```css
@layer components {
```

should normally be used instead of:

```css
@layer component {
```

Notice the **`s`**.

Correct:

```css
@layer components {
    .btn {
        @apply border border-slate-400 rounded px-5 py-1.5 hover:bg-slate-500;
    }
}
```

Tailwind's standard layers are:

```text
base
components
utilities
```

### `base`

Used for foundational styles.

Example:

```css
@layer base {
    body {
        @apply bg-gray-100 text-gray-900;
    }
}
```

### `components`

Used for reusable UI components.

Examples:

```text
Buttons
Cards
Navbar
Forms
Alerts
Badges
```

Example:

```css
@layer components {
    .btn {
        @apply rounded px-5 py-2;
    }
}
```

### `utilities`

Used for custom utility classes.

Example:

```css
@layer utilities {
    .content-auto {
        content-visibility: auto;
    }
}
```

### Simple definition

> **`@layer` organizes your custom Tailwind CSS styles into logical categories.**

---

# 6. Your `.btn` Class

You have:

```css
.btn {
    @apply border border-slate-400 rounded px-5 py-1.5 hover:bg-slate-500;
}
```

This creates the **common button style**.

Let's break it down:

| Utility              | Meaning                              |
| -------------------- | ------------------------------------ |
| `border`             | Adds a border                        |
| `border-slate-400`   | Sets border color                    |
| `rounded`            | Adds rounded corners                 |
| `px-5`               | Horizontal padding                   |
| `py-1.5`             | Vertical padding                     |
| `hover:bg-slate-500` | Changes background when mouse hovers |

The result is a basic reusable button.

You can use:

```html
<button class="btn">Basic</button>
```

---

# 7. Primary Button

Your code:

```css
.btn-primary {
    @apply bg-blue-500 hover:bg-blue-400 text-white border border-blue-500;
}
```

This creates a **primary button variant**.

HTML:

```html
<button class="btn-primary">Primary</button>
```

The button has:

* Blue background
* Lighter blue on hover
* White text
* Blue border

---

# 8. Secondary Button

Your code:

```css
.btn-secondary {
    @apply bg-slate-500 hover:bg-slate-900 text-white border border-slate-500;
}
```

This creates a secondary button.

HTML:

```html
<button class="btn-secondary">Secondary</button>
```

The button has:

* Gray background
* Dark gray hover state
* White text
* Gray border

---

# 9. Success Button

You wrote:

```css
.btn-sucesss {
    @apply bg-green-500 hover:bg-green-900 text-white border-green-100;
}
```

There is a spelling mistake in the class name.

You wrote:

```text
btn-sucesss
```

Correct spelling:

```text
btn-success
```

So it should be:

```css
.btn-success {
    @apply bg-green-500 hover:bg-green-900 text-white border border-green-500;
}
```

HTML:

```html
<button class="btn-success">Success</button>
```

Also notice that I added:

```text
border
```

Your original code only had:

```text
border-green-100
```

`border-green-100` sets the border color, but `border` ensures the border itself is present.

---

# 10. The Important Design Concept: Base + Variant

A better way to structure your buttons is to separate:

### Common styles

```css
.btn
```

from:

### Button variants

```text
.btn-primary
.btn-secondary
.btn-success
.btn-danger
.btn-warning
.btn-info
.btn-basic
.btn-dark
```

Conceptually:

```text
             .btn
              │
       Common Button Styles
              │
     ┌────────┼────────┐
     │        │        │
 Primary  Secondary  Success
```

This is a very important concept in component-based UI design.

You don't want to repeat common styles everywhere.

For example, instead of:

```css
.btn-primary {
    @apply border rounded px-5 py-1.5 bg-blue-500 text-white;
}

.btn-secondary {
    @apply border rounded px-5 py-1.5 bg-slate-500 text-white;
}

.btn-success {
    @apply border rounded px-5 py-1.5 bg-green-500 text-white;
}
```

You can use:

```html
<button class="btn btn-primary">Primary</button>
<button class="btn btn-secondary">Secondary</button>
<button class="btn btn-success">Success</button>
```

And define:

```css
@layer components {
    .btn {
        @apply rounded border px-5 py-1.5 text-white;
    }

    .btn-primary {
        @apply border-blue-500 bg-blue-500 hover:bg-blue-400;
    }

    .btn-secondary {
        @apply border-slate-500 bg-slate-500 hover:bg-slate-900;
    }

    .btn-success {
        @apply border-green-500 bg-green-500 hover:bg-green-900;
    }
}
```

This is cleaner because:

```text
.btn
    ↓
Common styles

.btn-primary
    ↓
Primary-specific styles

.btn-secondary
    ↓
Secondary-specific styles

.btn-success
    ↓
Success-specific styles
```

---

# 11. Important Correction in Your HTML

Your current HTML is:

```html
<button class="btn-primary">Primary</button>
<button class="btn-secondary">Secondary</button>
<button class="btn-sucesss">Success</button>
<button class="btn">Danger</button>
<button class="btn">Warning</button>
<button class="btn">Info</button>
<button class="btn">Basic</button>
<button class="btn">Dark</button>
```

The last five buttons all use:

```html
class="btn"
```

Therefore, they will all look the **same**.

The text:

```text
Danger
Warning
Info
Basic
Dark
```

does not automatically change the styling.

If you want different colors, you need different classes.

For example:

```html
<button class="btn btn-danger">Danger</button>
<button class="btn btn-warning">Warning</button>
<button class="btn btn-info">Info</button>
<button class="btn btn-basic">Basic</button>
<button class="btn btn-dark">Dark</button>
```

Then define those classes.

---

# 12. Complete Improved Example

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

    <button class="btn btn-primary">Primary</button>

    <button class="btn btn-secondary">Secondary</button>

    <button class="btn btn-success">Success</button>

    <button class="btn btn-danger">Danger</button>

    <button class="btn btn-warning">Warning</button>

    <button class="btn btn-info">Info</button>

    <button class="btn btn-basic">Basic</button>

    <button class="btn btn-dark">Dark</button>

</body>
</html>
```

### CSS

```css
@layer components {
    .btn {
        @apply rounded border px-5 py-1.5;
    }

    .btn-primary {
        @apply border-blue-500 bg-blue-500 text-white hover:bg-blue-400;
    }

    .btn-secondary {
        @apply border-slate-500 bg-slate-500 text-white hover:bg-slate-900;
    }

    .btn-success {
        @apply border-green-500 bg-green-500 text-white hover:bg-green-900;
    }

    .btn-danger {
        @apply border-red-500 bg-red-500 text-white hover:bg-red-700;
    }

    .btn-warning {
        @apply border-yellow-500 bg-yellow-500 text-white hover:bg-yellow-600;
    }

    .btn-info {
        @apply border-cyan-500 bg-cyan-500 text-white hover:bg-cyan-700;
    }

    .btn-basic {
        @apply border-slate-400 bg-white text-slate-900 hover:bg-slate-100;
    }

    .btn-dark {
        @apply border-slate-900 bg-slate-900 text-white hover:bg-slate-700;
    }
}
```

---

# 13. Why Do We Use This Approach?

Imagine you have **100 buttons** in your application.

Without reusable classes:

```html
<button class="rounded border px-5 py-1.5 bg-blue-500 text-white">
    Button 1
</button>

<button class="rounded border px-5 py-1.5 bg-blue-500 text-white">
    Button 2
</button>

<button class="rounded border px-5 py-1.5 bg-blue-500 text-white">
    Button 3
</button>
```

This becomes repetitive.

With reusable classes:

```html
<button class="btn btn-primary">Button 1</button>
<button class="btn btn-primary">Button 2</button>
<button class="btn btn-primary">Button 3</button>
```

Much cleaner.

If you later change:

```css
.btn {
    @apply rounded border px-5 py-2;
}
```

all buttons using `.btn` automatically receive the new common styling.

---

# 14. What Is the Purpose?

The overall purpose of your implementation is:

> **To create a reusable and maintainable button component system using Tailwind CSS.**

The architecture is:

```text
Tailwind Utility Classes
        ↓
       @apply
        ↓
Reusable CSS Classes
        ↓
     HTML Buttons
```

For example:

```text
bg-blue-500
text-white
border
rounded
px-5
py-1.5
        ↓
     @apply
        ↓
   .btn-primary
        ↓
<button class="btn-primary">
```

---

# 15. Quick Revision Notes

### `@apply`

**What?**

Combines Tailwind utility classes into a custom CSS class.

**Why?**

To create reusable styles.

**Example:**

```css
.btn-primary {
    @apply bg-blue-500 text-white;
}
```

---

### `@layer`

**What?**

Organizes custom CSS into Tailwind's CSS layers.

**Common layers:**

```text
base
components
utilities
```

**For buttons:**

```css
@layer components {
    .btn {
        @apply rounded px-5 py-2;
    }
}
```

---

### `.btn`

**Purpose:** Common styles shared by all buttons.

```css
.btn {
    @apply rounded border px-5 py-1.5;
}
```

---

### `.btn-primary`

**Purpose:** Primary button-specific styles.

```css
.btn-primary {
    @apply bg-blue-500 text-white;
}
```

---

### `hover:`

**Purpose:** Apply styles when the user hovers over an element.

```css
hover:bg-blue-400
```

Means:

> When the mouse is over the button, change the background to blue-400.

---

### Reusable component pattern

```html
<button class="btn btn-primary">Primary</button>
```

Think of it as:

```text
.btn
  +
.btn-primary
  =
Complete Primary Button
```

---

## Final Mental Model

Remember this simple formula:

> **Tailwind utilities** → small individual styles
> **`@apply`** → combines utilities
> **`@layer components`** → organizes reusable components
> **`.btn`** → common button styles
> **`.btn-primary`** → specific button variant
> **HTML** → uses those reusable classes

