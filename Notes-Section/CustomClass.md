# Tailwind CSS `@layer components` and `@apply`

## 1. What is `@layer components`?

Tailwind CSS provides the `@layer components` directive to define reusable component-level CSS classes.

It is useful when the same combination of Tailwind utility classes is used repeatedly in a project.

For example, instead of writing this button style again and again:

```html
<button class="bg-blue-500 rounded p-2 text-white hover:bg-blue-700">
    Submit
</button>
```

We can create a reusable class:

```css
@layer components {
    .btn-primary {
        @apply bg-blue-500 rounded p-2 text-white hover:bg-blue-700;
    }
}
```

Then use it anywhere:

```html
<button class="btn-primary">
    Submit
</button>
```

This makes the code cleaner and easier to maintain.

---

# 2. What is `@apply`?

The `@apply` directive allows us to combine existing Tailwind utility classes into our own custom CSS class.

### Example

```css
.btn-primary {
    @apply bg-blue-500 rounded p-2 text-white hover:bg-blue-700;
}
```

Here, the following Tailwind utility classes:

```text
bg-blue-500
rounded
p-2
text-white
hover:bg-blue-700
```

are combined into one reusable class:

```text
btn-primary
```

Now we can use:

```html
<button class="btn-primary">
    Submit
</button>
```

---

# 3. Why Use `@layer components`?

Suppose you have 10 buttons with the same design.

Without a reusable component class, you might write:

```html
<button class="bg-blue-500 rounded p-2 text-white hover:bg-blue-700">
    Submit
</button>

<button class="bg-blue-500 rounded p-2 text-white hover:bg-blue-700">
    Login
</button>

<button class="bg-blue-500 rounded p-2 text-white hover:bg-blue-700">
    Register
</button>
```

This creates repeated code.

Instead, create one reusable component:

```css
@layer components {
    .btn-primary {
        @apply bg-blue-500 rounded p-2 text-white hover:bg-blue-700;
    }
}
```

Then:

```html
<button class="btn-primary">
    Submit
</button>

<button class="btn-primary">
    Login
</button>

<button class="btn-primary">
    Register
</button>
```

Now one class controls the common button design.

---

# 4. Your Original Example

### HTML

```html
<!doctype html>
<html>

<head>

    <meta charset="UTF-8">

    <meta
        name="viewport"
        content="width=device-width, initial-scale=1.0"
    >

    <link rel="stylesheet" href="./output.css">

</head>

<body>

    <!-- Direct Utility Classes -->

    <button class="bg-blue-500 rounded p-2 text-white hover:bg-blue-700">
        Submit
    </button>


    <!-- Custom Component Class -->

    <button class="btn-primary">
        Submit
    </button>

    <button class="btn-primary">
        Submit
    </button>

    <button class="btn-primary">
        Submit
    </button>

</body>

</html>
```

### CSS

```css
@layer components {

    .btn-primary {
        @apply bg-blue-500 rounded p-2 text-white hover:bg-blue-700;
    }

}
```

---

# 5. Two Ways to Style the Button

## Method 1: Direct Utility Classes

```html
<button class="bg-blue-500 rounded p-2 text-white hover:bg-blue-700">
    Submit
</button>
```

Here, Tailwind utility classes are directly applied to the element.

The button uses:

```text
bg-blue-500
    ↓
Blue Background

rounded
    ↓
Rounded Corners

p-2
    ↓
Padding

text-white
    ↓
White Text

hover:bg-blue-700
    ↓
Darker Blue on Hover
```

---

## Method 2: Reusable Component Class

CSS:

```css
@layer components {

    .btn-primary {
        @apply bg-blue-500 rounded p-2 text-white hover:bg-blue-700;
    }

}
```

HTML:

```html
<button class="btn-primary">
    Submit
</button>
```

Now the same styles are applied through the reusable class.

---

# 6. Important Rule

### If you do not use the component class in HTML, its styling will not be applied to that element.

For example:

```css
@layer components {

    .btn-primary {
        @apply bg-blue-500 rounded p-2 text-white;
    }

}
```

But your HTML is:

```html
<button>
    Submit
</button>
```

The button will **not** receive the `.btn-primary` styles.

You must use:

```html
<button class="btn-primary">
    Submit
</button>
```

### Remember:

> **If you don't use the component class, the styling defined inside that component class will not be applied to the element.**

The class must be attached to the HTML element using:

```html
class="btn-primary"
```

This is an important concept when working with reusable component styles.

---

# 7. `@layer components` vs Normal CSS

You can also write:

```css
.btn-primary {
    background-color: blue;
    padding: 8px;
}
```

But Tailwind provides:

```css
@layer components {

    .btn-primary {
        @apply bg-blue-500 p-2;
    }

}
```

The advantage is that you can reuse Tailwind utility classes instead of writing traditional CSS properties manually.

---

# 8. Creating Multiple Components

You can create multiple reusable components inside `@layer components`.

```css
@layer components {

    .btn-primary {
        @apply bg-blue-500 rounded p-2 text-white hover:bg-blue-700;
    }

    .btn-secondary {
        @apply bg-gray-500 rounded p-2 text-white hover:bg-gray-700;
    }

    .btn-danger {
        @apply bg-red-500 rounded p-2 text-white hover:bg-red-700;
    }

}
```

Then use them:

```html
<button class="btn-primary">
    Primary
</button>

<button class="btn-secondary">
    Secondary
</button>

<button class="btn-danger">
    Delete
</button>
```

This creates reusable button components.

---

# 9. Why Is This Useful?

`@layer components` is useful when:

* You have repeated UI patterns.
* You want reusable component classes.
* You want to reduce repeated utility classes.
* You want consistent styling.
* You want to maintain common styles from one place.

Common examples include:

```text
Buttons
Cards
Navbar
Forms
Input Fields
Badges
Alerts
Modals
```

---

# 10. Example: Card Component

```css
@layer components {

    .card {
        @apply rounded-lg bg-white p-6 shadow-lg;
    }

}
```

HTML:

```html
<div class="card">

    <h2 class="text-2xl font-bold">
        Product Card
    </h2>

    <p class="mt-2 text-gray-600">
        This is a reusable card component.
    </p>

</div>
```

---

# 11. Example: Input Component

```css
@layer components {

    .input-field {
        @apply rounded border border-gray-300 p-2 outline-none focus:border-blue-500;
    }

}
```

HTML:

```html
<input
    type="text"
    placeholder="Enter your name"
    class="input-field"
/>
```

---

# 12. Component Layer Structure

The basic structure is:

```css
@layer components {

    .component-name {
        @apply utility-class-1 utility-class-2 utility-class-3;
    }

}
```

Example:

```css
@layer components {

    .btn-primary {
        @apply bg-blue-500 rounded p-2 text-white;
    }

}
```

Then use it:

```html
<button class="btn-primary">
    Submit
</button>
```

---

# 13. Important Difference: Utility vs Component

### Utility Class

```html
<button class="bg-blue-500 p-2 text-white rounded">
    Submit
</button>
```

The styles are directly written in the HTML.

### Component Class

```html
<button class="btn-primary">
    Submit
</button>
```

The styles are defined separately:

```css
@layer components {

    .btn-primary {
        @apply bg-blue-500 p-2 text-white rounded;
    }

}
```

### Comparison

| Utility Classes                 | Component Class              |
| ------------------------------- | ---------------------------- |
| Styles written directly in HTML | Styles defined in CSS        |
| Fast for one-off designs        | Good for repeated components |
| Can become long                 | Keeps HTML cleaner           |
| Easy to customize per element   | Good for consistency         |

---

# 14. Best Practice

Use utility classes directly when a style is needed only once or needs unique customization.

Example:

```html
<div class="mt-10 p-5 bg-gray-100">
```

Create a component class when the same style is repeated many times.

Example:

```css
@layer components {

    .btn-primary {
        @apply rounded bg-blue-500 p-2 text-white;
    }

}
```

Then:

```html
<button class="btn-primary">
    Submit
</button>

<button class="btn-primary">
    Login
</button>

<button class="btn-primary">
    Register
</button>
```

---

# 15. Interview-Level Explanation

### Question: What is `@layer components` in Tailwind CSS?

**Answer:**

`@layer components` is used to define reusable component-level CSS classes in Tailwind CSS. It is useful for creating reusable UI patterns such as buttons, cards, forms, and navigation elements.

For example:

```css
@layer components {

    .btn-primary {
        @apply bg-blue-500 rounded p-2 text-white;
    }

}
```

The class can then be reused:

```html
<button class="btn-primary">
    Submit
</button>
```

### Important Point

> **If we don't use the component class in our HTML element, the styling defined inside that component class will not be applied to that element.**

For example, if we define:

```css
.btn-primary {
    @apply bg-blue-500 p-2;
}
```

but write:

```html
<button>
    Submit
</button>
```

the styles will not be applied.

We must write:

```html
<button class="btn-primary">
    Submit
</button>
```

---

# 16. Quick Revision

```text
@layer components
        ↓
Create reusable component styles
        ↓
@apply
        ↓
Combine Tailwind utility classes
        ↓
Create custom class
        ↓
Use custom class in HTML
```

### Example

```css
@layer components {

    .btn-primary {
        @apply bg-blue-500 rounded p-2 text-white hover:bg-blue-700;
    }

}
```

```html
<button class="btn-primary">
    Submit
</button>
```

### Remember

```text
@layer components
        +
@apply
        +
Reusable Class
        +
Use class in HTML
        =
Reusable Component Styling
```

