# Tailwind CSS Dark Mode – Complete Notes

## 1. What is Dark Mode?

Dark Mode is a feature that changes the appearance of a website from a light theme to a dark theme.

### Light Mode

```text
Background → White
Text       → Black
Cards      → Light Colors
```

### Dark Mode

```text
Background → Dark
Text       → White
Cards      → Dark Colors
```

Dark Mode is commonly used because it:

* Provides a better experience in low-light environments.
* Reduces bright screen exposure.
* Gives websites a modern appearance.
* Allows users to choose their preferred theme.

---

# 2. Dark Mode in Tailwind CSS

Tailwind CSS provides the `dark:` variant to apply styles when Dark Mode is active.

### Basic Syntax

```html
<div class="bg-white dark:bg-slate-900">
    Content
</div>
```

### Explanation

```text
bg-white
    ↓
Used in Light Mode

dark:bg-slate-900
    ↓
Used in Dark Mode
```

So the same element can have different styles depending on the current theme.

---

# 3. Understanding the `dark:` Variant

The `dark:` prefix tells Tailwind CSS:

> Apply this utility class when Dark Mode is active.

### Example

```html
<p class="text-black dark:text-white">
    Hello World
</p>
```

### Light Mode

```text
text-black
    ↓
Black Text
```

### Dark Mode

```text
dark:text-white
    ↓
White Text
```

---

# 4. Common Dark Mode Classes

## Background Color

```html
<div class="bg-white dark:bg-slate-900">
```

Light Mode:

```text
White Background
```

Dark Mode:

```text
Slate 900 Background
```

---

## Text Color

```html
<p class="text-black dark:text-white">
```

Light Mode:

```text
Black Text
```

Dark Mode:

```text
White Text
```

---

## Border Color

```html
<div class="border border-gray-300 dark:border-gray-700">
```

Light Mode:

```text
Light Gray Border
```

Dark Mode:

```text
Dark Gray Border
```

---

## Background of a Box

```html
<div class="bg-blue-300 dark:bg-blue-700">
```

Light Mode:

```text
Blue 300
```

Dark Mode:

```text
Blue 700
```

---

# 5. Tailwind CSS v4 Dark Mode Setup

Your project uses Tailwind CSS v4 because you are using:

```css
@import "tailwindcss";
```

In Tailwind CSS v4, you can configure class-based Dark Mode directly in your CSS.

You don't need a `tailwind.config.js` file for this setup.

---

# 6. Create `input.css`

Create a file named:

```text
input.css
```

Add:

```css
@import "tailwindcss";

@custom-variant dark (&:where(.dark, .dark *));
```

### Explanation

```css
@custom-variant dark (&:where(.dark, .dark *));
```

This tells Tailwind CSS to activate the `dark:` variant when an element is inside an element with the `dark` class.

For example:

```html
<html class="dark">
```

Then:

```html
<body class="dark:bg-slate-900">
```

The Dark Mode style will be applied.

---

# 7. Project Structure

Your project should look like this:

```text
Tailwind-Project
│
├── index.html
├── input.css
└── output.css
```

### Files

`index.html`

Contains the HTML structure.

`input.css`

Contains Tailwind CSS configuration.

`output.css`

Contains the compiled Tailwind CSS.

---

# 8. Compile Tailwind CSS

Run this command in the terminal:

```bash
npx @tailwindcss/cli -i ./input.css -o ./output.css --watch
```

### Meaning

```text
-i ./input.css
    ↓
Input CSS file

-o ./output.css
    ↓
Output CSS file

--watch
    ↓
Automatically watches for changes
```

Keep the terminal running while working on the project.

---

# 9. Basic Dark Mode Example

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

    <title>Dark Mode</title>

</head>

<body class="bg-white text-black dark:bg-slate-900 dark:text-white">

    <h1 class="text-5xl">
        Dark Mode Test
    </h1>

</body>

</html>
```

Because the `<html>` element contains:

```html
class="dark"
```

Dark Mode is active.

---

# 10. How Dark Mode Works

The structure is:

```text
<html class="dark">
        ↓
Dark class is active
        ↓
dark: utilities become active
        ↓
dark:bg-slate-900
dark:text-white
dark:border-gray-700
```

For example:

```html
<body class="bg-white dark:bg-slate-900">
```

When `dark` is not present:

```text
Background → White
```

When `dark` is present:

```text
Background → Slate 900
```

---

# 11. Light Mode and Dark Mode Together

A common pattern is:

```html
class="bg-white text-black dark:bg-slate-900 dark:text-white"
```

This means:

### Light Mode

```text
Background → White
Text       → Black
```

### Dark Mode

```text
Background → Slate 900
Text       → White
```

This pattern is very commonly used in Tailwind projects.

---

# 12. Creating a Dark Mode Toggle Button

If you only add:

```html
<html class="dark">
```

Dark Mode will be active, but the user cannot change the theme.

To allow the user to switch between Light Mode and Dark Mode, we need:

```text
Button
+
JavaScript
+
Tailwind dark: variant
```

The JavaScript will add or remove the `dark` class.

---

# 13. Complete Dark Mode Toggle Project

## `input.css`

```css
@import "tailwindcss";

@custom-variant dark (&:where(.dark, .dark *));
```

---

## `index.html`

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

    <title>Dark Mode Toggle</title>

</head>

<body class="min-h-screen bg-white text-black dark:bg-slate-900 dark:text-white">

    <div class="p-10">

        <!-- Heading -->

        <h1 class="text-5xl font-bold">
            Tailwind CSS Dark Mode
        </h1>


        <!-- Description -->

        <p class="mt-4 text-2xl">
            Click the button to change the theme.
        </p>


        <!-- Theme Button -->

        <button
            id="themeButton"
            class="mt-8 rounded-lg bg-black px-6 py-3 text-lg font-semibold text-white hover:bg-gray-800 dark:bg-white dark:text-black dark:hover:bg-gray-200"
        >
            🌙 Dark Mode
        </button>


        <!-- Box -->

        <div
            class="mt-10 rounded-lg border border-gray-300 bg-gray-100 p-10 dark:border-gray-600 dark:bg-slate-700"
        >

            <!-- Small Box -->

            <div
                class="size-20 rounded bg-blue-300 dark:bg-blue-700"
            >
            </div>


            <!-- Box Text -->

            <p class="mt-5 text-2xl">
                Box with Dark Mode
            </p>

        </div>

    </div>


    <!-- JavaScript -->

    <script>

        // Select the button

        const themeButton =
            document.getElementById("themeButton");


        // Add click event

        themeButton.addEventListener("click", function () {


            // Add or remove the dark class

            document.documentElement.classList.toggle("dark");


            // Check if Dark Mode is active

            if (
                document.documentElement.classList.contains("dark")
            ) {

                // Change button text

                themeButton.innerHTML =
                    "☀️ Light Mode";

            } else {

                // Change button text

                themeButton.innerHTML =
                    "🌙 Dark Mode";

            }

        });

    </script>

</body>

</html>
```

---

# 14. Understanding the JavaScript

## Step 1: Select the Button

```javascript
const themeButton =
    document.getElementById("themeButton");
```

This selects the button from HTML.

HTML:

```html
<button id="themeButton">
    🌙 Dark Mode
</button>
```

Now JavaScript can control this button.

---

# 15. Add Click Event

```javascript
themeButton.addEventListener("click", function () {

});
```

This means:

> When the user clicks the button, execute the code inside the function.

---

# 16. Toggle the Dark Class

```javascript
document.documentElement.classList.toggle("dark");
```

This is the most important line.

`document.documentElement` refers to:

```html
<html>
```

So this:

```javascript
classList.toggle("dark")
```

does the following:

### If `dark` is not present

```html
<html>
```

It adds:

```html
<html class="dark">
```

### If `dark` is already present

```html
<html class="dark">
```

It removes:

```html
<html>
```

Therefore:

```text
Click 1
    ↓
Add dark class
    ↓
Dark Mode

Click 2
    ↓
Remove dark class
    ↓
Light Mode
```

---

# 17. Checking Dark Mode

We use:

```javascript
document.documentElement.classList.contains("dark")
```

This checks whether the `<html>` element contains the `dark` class.

If yes:

```text
Dark Mode is Active
```

If no:

```text
Light Mode is Active
```

---

# 18. Changing Button Text

When Dark Mode is active:

```javascript
themeButton.innerHTML = "☀️ Light Mode";
```

When Light Mode is active:

```javascript
themeButton.innerHTML = "🌙 Dark Mode";
```

The complete logic is:

```javascript
if (document.documentElement.classList.contains("dark")) {

    themeButton.innerHTML = "☀️ Light Mode";

} else {

    themeButton.innerHTML = "🌙 Dark Mode";

}
```

---

# 19. Complete Working Flow

The complete process is:

```text
User opens website
        ↓
Light Mode
        ↓
Button shows 🌙 Dark Mode
        ↓
User clicks button
        ↓
JavaScript runs
        ↓
dark class is added to <html>
        ↓
Tailwind detects .dark
        ↓
dark: classes become active
        ↓
Website changes to Dark Mode
        ↓
Button changes to ☀️ Light Mode
```

When the user clicks again:

```text
User clicks button
        ↓
dark class is removed
        ↓
Tailwind Dark Mode styles stop
        ↓
Light Mode becomes active
        ↓
Button changes to 🌙 Dark Mode
```

---

# 20. How the Box Changes

Our box contains:

```html
<div
    class="mt-10 rounded-lg border border-gray-300 bg-gray-100 p-10 dark:border-gray-600 dark:bg-slate-700"
>
```

### Light Mode

```text
Background → Gray 100
Border     → Gray 300
```

### Dark Mode

```text
Background → Slate 700
Border     → Gray 600
```

The small blue box contains:

```html
<div class="size-20 rounded bg-blue-300 dark:bg-blue-700">
```

### Light Mode

```text
Blue 300
```

### Dark Mode

```text
Blue 700
```

---

# 21. Common Mistake #1

Incorrect:

```html
dark:bg-text-white
```

Correct:

```html
dark:text-white
```

### Why?

`text-` controls text color.

`bg-` controls background color.

Therefore:

```text
dark:text-white
    ↓
White Text

dark:bg-white
    ↓
White Background
```

---

# 22. Common Mistake #2

Incorrect:

```html
<div class="bg-blue-300 dark:bg-blue-700 dark:bg-black">
```

There are two Dark Mode background classes:

```text
dark:bg-blue-700
dark:bg-black
```

This is unnecessary.

Use:

```html
<div class="bg-blue-300 dark:bg-blue-700">
```

Now the behavior is clear.

---

# 23. Common Mistake #3

If you write:

```html
<html class="dark">
```

Dark Mode will always start as active.

If you want the user to control the theme with a button, don't add `dark` manually to `<html>`.

Use JavaScript:

```javascript
document.documentElement.classList.toggle("dark");
```

---

# 24. Common Mistake #4

Make sure your CSS is connected correctly:

```html
<link rel="stylesheet" href="./output.css">
```

Your project should have:

```text
index.html
input.css
output.css
```

If the path is wrong, Tailwind styles will not work.

---

# 25. Common Mistake #5

The Tailwind CLI must be running:

```bash
npx @tailwindcss/cli -i ./input.css -o ./output.css --watch
```

If you change your Tailwind classes but the CLI is not running, `output.css` may not contain your new styles.

---

# 26. `tailwind.config.js` vs Tailwind CSS v4

In older Tailwind CSS versions, you may see:

```javascript
// tailwind.config.js

module.exports = {
    darkMode: "class",
}
```

This is a common Tailwind CSS v3 approach.

In your Tailwind CSS v4 setup, you can use:

```css
@import "tailwindcss";

@custom-variant dark (&:where(.dark, .dark *));
```

This gives you class-based Dark Mode behavior.

So for your current project, you don't need to create `tailwind.config.js` just to implement this Dark Mode toggle.

---

# 27. Useful Dark Mode Examples

## Card

```html
<div class="bg-white dark:bg-gray-800">
```

## Text

```html
<p class="text-gray-900 dark:text-white">
```

## Border

```html
<div class="border-gray-300 dark:border-gray-700">
```

## Button

```html
<button class="bg-black text-white dark:bg-white dark:text-black">
```

## Hover

```html
<button class="hover:bg-gray-200 dark:hover:bg-gray-700">
```

## Input

```html
<input
    class="bg-white text-black dark:bg-gray-800 dark:text-white"
/>
```

---

# 28. Real-World Dark Mode Pattern

A professional website often uses:

```html
<body class="
    bg-white
    text-gray-900
    dark:bg-gray-900
    dark:text-white
">
```

Components use:

```html
<div class="
    bg-gray-100
    border-gray-200
    dark:bg-gray-800
    dark:border-gray-700
">
```

This creates a consistent theme throughout the application.

---

# 29. Interview Questions

## Q1. What is Dark Mode?

Dark Mode is a UI feature that changes the website's color scheme from light colors to dark colors.

---

## Q2. What is the `dark:` variant in Tailwind CSS?

The `dark:` variant is used to apply Tailwind utility classes when Dark Mode is active.

Example:

```html
<div class="bg-white dark:bg-black">
```

---

## Q3. How do you activate class-based Dark Mode?

In your Tailwind CSS v4 setup, define:

```css
@custom-variant dark (&:where(.dark, .dark *));
```

Then add the `dark` class to a parent element:

```html
<html class="dark">
```

---

## Q4. How do you create a Dark Mode toggle?

You can use JavaScript to add or remove the `dark` class.

```javascript
document.documentElement.classList.toggle("dark");
```

---

## Q5. What does `classList.toggle()` do?

`classList.toggle()` adds a class if it doesn't exist and removes it if it already exists.

Example:

```javascript
element.classList.toggle("dark");
```

---

## Q6. What does `document.documentElement` refer to?

It refers to the root `<html>` element of the document.

Example:

```html
<html>
```

---

# 30. Quick Revision

### Tailwind Dark Mode

```text
dark:
    ↓
Dark Mode Variant
```

### Background

```html
dark:bg-slate-900
```

### Text

```html
dark:text-white
```

### Border

```html
dark:border-gray-700
```

### Dark Mode Configuration

```css
@custom-variant dark (&:where(.dark, .dark *));
```

### Add Dark Mode

```javascript
document.documentElement.classList.add("dark");
```

### Remove Dark Mode

```javascript
document.documentElement.classList.remove("dark");
```

### Toggle Dark Mode

```javascript
document.documentElement.classList.toggle("dark");
```

### Check Dark Mode

```javascript
document.documentElement.classList.contains("dark");
```

---

# 31. Practice Task

Create a complete Dark Mode website containing:

```text
Navbar
    ↓
Dark Mode Toggle Button
    ↓
Hero Section
    ↓
3 Cards
    ↓
Contact Form
    ↓
Footer
```

Implement Dark Mode for:

```text
Body Background
Text
Navbar
Buttons
Cards
Card Borders
Input Fields
Footer
Hover Effects
```

Use the following pattern:

```html
light-style dark:dark-style
```

Example:

```html
class="bg-white text-black dark:bg-slate-900 dark:text-white"
```

---

# 32. Advanced Next Step – Save Theme

The current JavaScript only changes the theme temporarily.

If the user refreshes the page, the theme will reset.

To create a professional Dark Mode system, the next step is to use:

```text
localStorage
    ↓
Save user's theme preference
    ↓
Refresh page
    ↓
Read saved preference
    ↓
Apply Light/Dark Mode automatically
```

This is the next important concept to learn after understanding `dark:` and `classList.toggle()`.

---

# Final Concept

Remember this complete flow:

```text
Tailwind CSS
      ↓
@custom-variant dark
      ↓
dark: utility classes
      ↓
.dark class
      ↓
JavaScript Toggle
      ↓
Add / Remove .dark
      ↓
Tailwind changes styles
      ↓
Light Mode ↔ Dark Mode
```

### Most Important Code

```css
@import "tailwindcss";

@custom-variant dark (&:where(.dark, .dark *));
```

```html
<body class="bg-white text-black dark:bg-slate-900 dark:text-white">
```

```javascript
document.documentElement.classList.toggle("dark");
```

