# Tailwind CSS Dark Mode – Complete Notes

## 1. What is Dark Mode?

Dark Mode is a UI feature that changes the website's appearance from a **light theme to a dark theme**.

For example:

* Light Mode → White background, dark text
* Dark Mode → Dark background, light text

Tailwind CSS provides the `dark:` variant to apply styles when Dark Mode is active.

### Basic Syntax

```html
<div class="bg-white dark:bg-slate-800">
    Content
</div>
```

Here:

* `bg-white` → Background in Light Mode
* `dark:bg-slate-800` → Background in Dark Mode

---

# 2. How `dark:` Works in Tailwind CSS

The `dark:` prefix is used to define a style specifically for Dark Mode.

### Example

```html
<h1 class="text-black dark:text-white">
    Dark Mode Heading
</h1>
```

### Explanation

| Class             | Purpose                  |
| ----------------- | ------------------------ |
| `text-black`      | Black text in Light Mode |
| `dark:text-white` | White text in Dark Mode  |

When Dark Mode is active, the `dark:text-white` class overrides the normal text color.

---

# 3. Corrected Basic Dark Mode Example

```html
<!doctype html>
<html lang="en">

<head>
    <meta charset="UTF-8">

    <meta
        name="viewport"
        content="width=device-width, initial-scale=1.0"
    >

    <link rel="stylesheet" href="./output.css">

    <title>Dark Mode Test</title>
</head>

<body class="bg-white text-black dark:bg-slate-800 dark:text-white">

    <div>
        <h1 class="text-7xl">
            Dark Mode Test with Tailwind CSS
        </h1>

        <p class="text-4xl">
            Code step by step
        </p>
    </div>

    <div class="flex m-20 border border-slate-700 p-3 dark:bg-slate-700">

        <div class="size-12 bg-blue-300 dark:bg-blue-700">
        </div>

        <p class="text-2xl ml-10 p-2">
            Box with Dark Mode
        </p>

    </div>

</body>

</html>
```

---

# 4. Explanation of the Corrected Code

## Body

```html
<body class="bg-white text-black dark:bg-slate-800 dark:text-white">
```

This applies Dark Mode to the entire page.

### Light Mode

```text
bg-white
text-black
```

The page will have:

* White background
* Black text

### Dark Mode

```text
dark:bg-slate-800
dark:text-white
```

The page will have:

* Dark background
* White text

---

# 5. Heading

```html
<h1 class="text-7xl">
    Dark Mode Test with Tailwind CSS
</h1>
```

`text-7xl` increases the font size.

The text color is inherited from the `<body>`.

In Light Mode:

```text
Black text
```

In Dark Mode:

```text
White text
```

Because the `<body>` contains:

```html
text-black dark:text-white
```

---

# 6. Dark Mode Box

```html
<div class="size-12 bg-blue-300 dark:bg-blue-700">
</div>
```

This creates a square box.

### `size-12`

Sets:

```text
Width  = 3rem
Height = 3rem
```

### Light Mode

```html
bg-blue-300
```

The box has a light blue background.

### Dark Mode

```html
dark:bg-blue-700
```

The box changes to a darker blue background.

---

# 7. Container with Dark Mode

```html
<div class="flex m-20 border border-slate-700 p-3 dark:bg-slate-700">
```

Let's understand each class.

### `flex`

```html
flex
```

Makes the container a Flexbox.

The children are placed horizontally by default.

---

### `m-20`

```html
m-20
```

Adds margin around the container.

---

### `border`

```html
border
```

Adds a border.

---

### `border-slate-700`

```html
border-slate-700
```

Sets the border color to Slate 700.

---

### `p-3`

```html
p-3
```

Adds padding inside the container.

---

### `dark:bg-slate-700`

```html
dark:bg-slate-700
```

Changes the container's background color when Dark Mode is active.

---

# 8. Important Correction in Your Original Code

You wrote:

```html
<h1 class="text-7xl dark:bg-text-white">
```

This is incorrect.

You probably wanted:

```html
<h1 class="text-7xl dark:text-white">
```

### Why?

`text-white` changes the **text color**.

`bg-white` changes the **background color**.

Therefore:

```html
dark:text-white
```

means:

> Make the text white in Dark Mode.

While:

```html
dark:bg-white
```

means:

> Make the background white in Dark Mode.

There is no valid Tailwind class called:

```html
dark:bg-text-white
```

---

# 9. Another Mistake in Your Original Code

You wrote:

```html
<div class="bg-blue-300 dark:bg-blue-700 size-12 dark:bg-black">
```

You have two Dark Mode background classes:

```html
dark:bg-blue-700
dark:bg-black
```

Both are trying to change the background color.

This is unnecessary and confusing.

Use only one:

```html
<div class="size-12 bg-blue-300 dark:bg-blue-700">
```

Now the behavior is clear:

```text
Light Mode  → Blue 300
Dark Mode   → Blue 700
```

---

# 10. Dark Mode Classes You Can Use

The `dark:` variant can be used with many Tailwind utilities.

### Background

```html
<div class="bg-white dark:bg-slate-800">
```

### Text

```html
<p class="text-black dark:text-white">
```

### Border

```html
<div class="border-slate-300 dark:border-slate-600">
```

### Hover

```html
<button class="hover:bg-blue-500 dark:hover:bg-blue-700">
```

### Shadow

```html
<div class="shadow-md dark:shadow-xl">
```

The general syntax is:

```html
dark:utility
```

Examples:

```html
dark:bg-black
dark:text-white
dark:border-gray-700
dark:hover:bg-gray-800
```

---

# 11. Light Mode + Dark Mode Pattern

A common Tailwind pattern is:

```html
class="light-style dark:dark-style"
```

### Example

```html
<div class="bg-white text-black dark:bg-gray-900 dark:text-white">
    Hello World
</div>
```

The browser will use:

```text
Light Mode:
Background → White
Text       → Black

Dark Mode:
Background → Gray 900
Text       → White
```

This is one of the most common patterns used when building modern websites.

---

# 12. Practical Example: Dark Mode Card

```html
<div class="
    max-w-sm
    p-6
    bg-white
    border
    border-gray-200
    rounded-lg
    shadow
    dark:bg-gray-800
    dark:border-gray-700
">

    <h2 class="
        mb-2
        text-2xl
        font-bold
        text-gray-900
        dark:text-white
    ">
        Dark Mode Card
    </h2>

    <p class="
        text-gray-600
        dark:text-gray-300
    ">
        This card automatically changes its appearance
        when Dark Mode is active.
    </p>

</div>
```

### Light Mode

```text
Card Background → White
Heading         → Dark Gray
Paragraph       → Gray
Border          → Light Gray
```

### Dark Mode

```text
Card Background → Gray 800
Heading         → White
Paragraph       → Gray 300
Border          → Gray 700
```

---

# 13. Important: How to Activate Dark Mode

Using classes such as:

```html
dark:bg-slate-800
```

does not always mean Dark Mode will automatically activate just because the system or browser is in Dark Mode.

The Dark Mode behavior depends on your Tailwind CSS configuration/version and how the `dark` variant is configured.

A common class-based approach is:

```html
<html class="dark">
```

Then:

```html
<body class="bg-white text-black dark:bg-slate-900 dark:text-white">
```

When the `dark` class exists on the parent element, the Dark Mode styles become active.

Example:

```html
<html class="dark">

<body class="bg-white text-black dark:bg-slate-900 dark:text-white">

    <h1>
        Dark Mode Website
    </h1>

</body>

</html>
```

The page will use the Dark Mode styles.

---

# 14. Complete Dark Mode Example

```html
<!doctype html>
<html lang="en" class="dark">

<head>
    <meta charset="UTF-8">

    <meta
        name="viewport"
        content="width=device-width, initial-scale=1.0"
    >

    <link rel="stylesheet" href="./output.css">

    <title>Tailwind Dark Mode</title>
</head>

<body class="
    min-h-screen
    bg-white
    text-black
    dark:bg-slate-900
    dark:text-white
">

    <div class="p-10">

        <h1 class="text-5xl font-bold">
            Tailwind CSS Dark Mode
        </h1>

        <p class="mt-4 text-2xl">
            Learn Dark Mode step by step.
        </p>

        <div class="
            flex
            items-center
            mt-10
            p-5
            border
            border-slate-300
            rounded-lg
            dark:border-slate-700
            dark:bg-slate-800
        ">

            <div class="
                size-12
                bg-blue-300
                rounded
                dark:bg-blue-700
            ">
            </div>

            <p class="ml-5 text-xl">
                Box with Dark Mode
            </p>

        </div>

    </div>

</body>

</html>
```

---

# 15. Step-by-Step Implementation

## Step 1: Create Your HTML File

Create:

```text
index.html
```

---

## Step 2: Connect Tailwind CSS

Make sure your compiled CSS is connected:

```html
<link rel="stylesheet" href="./output.css">
```

---

## Step 3: Add Normal Light Mode Styles

Example:

```html
bg-white text-black
```

---

## Step 4: Add Dark Mode Styles

Use the `dark:` prefix:

```html
dark:bg-slate-900
dark:text-white
```

---

## Step 5: Add Dark Mode to Components

For example:

```html
<div class="bg-white dark:bg-slate-800">
```

---

## Step 6: Test Dark Mode

Activate Dark Mode according to your Tailwind configuration.

For class-based Dark Mode, you can use:

```html
<html class="dark">
```

Remove `dark` to test Light Mode:

```html
<html>
```

---

# 16. Interview-Level Understanding

### Question: What is the `dark:` variant in Tailwind CSS?

**Answer:**

The `dark:` variant in Tailwind CSS is used to apply specific utility classes when Dark Mode is active. For example, `dark:bg-slate-900` changes the background to Slate 900 in Dark Mode.

### Example:

```html
<div class="bg-white dark:bg-slate-900">
    Content
</div>
```

In Light Mode:

```text
White Background
```

In Dark Mode:

```text
Slate 900 Background
```

---

# 17. Quick Revision

```text
dark:
   ↓
Tailwind Dark Mode Variant
   ↓
Used before a utility class
   ↓
Applies the utility in Dark Mode
```

### Examples

```html
dark:bg-black
dark:bg-slate-900
dark:text-white
dark:border-gray-700
dark:hover:bg-gray-800
```

### Remember

```text
bg-     → Background Color
text-   → Text Color
border- → Border Color
dark:   → Dark Mode Variant
```

### Most Important Pattern

```html
class="bg-white text-black dark:bg-slate-900 dark:text-white"
```

This means:

```text
Light Mode
    ↓
White Background + Black Text

Dark Mode
    ↓
Slate 900 Background + White Text
```

