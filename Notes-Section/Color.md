# Tailwind CSS Notes Based on Your Code

## 1. `text-red-50` to `text-red-900`

### What is it?

These classes change the **text color**.

### Syntax

```html
text-color-shade
```

Example:

```html
text-red-500
```

### Shade Meaning

| Class          | Color Strength     |
| -------------- | ------------------ |
| `text-red-50`  | Very light red     |
| `text-red-100` | Light red          |
| `text-red-200` | Slightly darker    |
| `text-red-300` | Medium light       |
| `text-red-400` | Medium             |
| `text-red-500` | Default red        |
| `text-red-600` | Dark red           |
| `text-red-700` | Darker red         |
| `text-red-800` | Very dark red      |
| `text-red-900` | Extremely dark red |

### Why use it?

* Makes text colorful.
* Helps highlight important content.
* Creates attractive UI designs.

---

## 2. `text-green-50` to `text-green-900`

### What is it?

Changes the text color to different shades of green.

Example:

```html
<li class="text-green-500">
```

### Why use it?

* Success messages
* Positive values
* Completed tasks
* Profit or earnings display

---

## 3. `border`

### What is it?

Adds a border around an element.

Example:

```html
<li class="border">
```

Output:

* Adds a default border of `1px`.

### Why use it?

* Separates content.
* Makes elements visible.
* Creates cards, boxes, and sections.

---

## 4. `border-4`

### What is it?

Sets border thickness to `4px`.

Correct usage:

```html
border-4
```

Your code:

```html
border -4
```

This is incorrect because Tailwind treats `border` and `-4` as separate classes.

Correct:

```html
<li class="text-green-500 border border-4">
```

---

## 5. `outline-8`

### What is it?

Adds an outline outside the border.

Example:

```html
outline outline-8
```

### Difference Between Border and Outline

| Border              | Outline                      |
| ------------------- | ---------------------------- |
| Takes space         | Does not take space          |
| Inside element size | Outside element              |
| Used for design     | Mostly used for focus effect |

Example:

```html
class="border border-4"
```

Example:

```html
class="outline outline-8"
```

---

## 6. Correct Version of Your Classes

### Red Section

```html
<li class="text-red-500">Learning Tailwind</li>
```

### Green Section

```html
<li class="text-green-500 border border-4">
    Learning Tailwind
</li>
```

### Orange Section

```html
<li class="text-orange-500 outline outline-8">
    Learning Tailwind
</li>
```

---

# Quick Revision

## Text Color

```html
text-red-500
text-green-500
text-orange-500
```

Used for:

* Changing text color.

---

## Border

```html
border
border-2
border-4
border-8
```

Used for:

* Creating boxes and sections.

---

## Outline

```html
outline
outline-2
outline-4
outline-8
```

Used for:

* Focus effects.
* Highlighting selected elements.

---

# Formula to Remember

```text
text-{color}-{shade}
bg-{color}-{shade}
border-{size}
outline-{size}
```

Examples:

```html
text-blue-500
bg-green-200
border-4
outline-8
```
