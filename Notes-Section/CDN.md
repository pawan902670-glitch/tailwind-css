# Tailwind CSS using CDN

## What is Tailwind CSS?

Tailwind CSS is a utility-first CSS framework that provides ready-made classes for styling web pages.

Instead of writing custom CSS like:

```css
background-color: blue;
color: white;
padding: 20px;
```

you can simply use classes such as:

```html
bg-blue-500 text-white p-5
```

This makes development faster and easier.

---

## Why use Tailwind CSS?

* Faster UI development.
* No need to write large CSS files.
* Responsive design becomes easier.
* Consistent spacing, colors, and sizing.
* Easy to maintain and modify designs.

---

## Step 1: Create an HTML file

Create a file named:

```text
index.html
```

---

## Step 2: Add the Tailwind CDN link

Inside the `<head>` section, add the following script:

```html
<script src="https://cdn.tailwindcss.com"></script>
```

This loads Tailwind CSS directly from the internet.

---

## Step 3: Create the basic HTML structure

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Tailwind CSS CDN</title>

    <!-- Tailwind CDN Link -->
    <script src="https://cdn.tailwindcss.com"></script>
</head>
<body>

</body>
</html>
```

---

## Step 4: Add Tailwind classes

Example:

```html
<h1 class="bg-blue-500 text-white p-5 text-3xl font-bold">
    Welcome to Tailwind CSS
</h1>
```

---

## Explanation of Classes

| Class         | Purpose                     |
| ------------- | --------------------------- |
| `bg-blue-500` | Adds blue background color  |
| `text-white`  | Changes text color to white |
| `p-5`         | Adds padding on all sides   |
| `text-3xl`    | Makes the text larger       |
| `font-bold`   | Makes the text bold         |

---

## Complete Example

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Tailwind CSS CDN</title>

    <script src="https://cdn.tailwindcss.com"></script>
</head>
<body>

    <h1 class="bg-blue-500 text-white p-5 text-3xl font-bold">
        Welcome to Tailwind CSS
    </h1>

</body>
</html>
```

---

## When should we use CDN?

Use CDN when:

* Learning Tailwind CSS.
* Practicing examples.
* Creating small projects.
* Building quick prototypes.

---

## Limitations of CDN

* Requires an internet connection.
* Loads the complete Tailwind library.
* Not recommended for large production projects.

For professional projects, the CLI method is preferred because it generates only the CSS that your project uses.
