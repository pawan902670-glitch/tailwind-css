
# Tailwind CSS: `group` and `group-hover`

## 1. What is `group`?

In Tailwind CSS, the `group` class is used when we want to change the style of a **child element based on the state of its parent element**.

For example, if we want to show a hidden menu when the user hovers over its parent, we can use:

```html
<div class="group">
    <!-- Parent -->
    
    <div class="hidden group-hover:block">
        <!-- Child -->
    </div>
</div>
```

Here:

* `group` is added to the **parent**.
* `group-hover:block` is added to the **child**.
* When the parent is hovered, the child changes from `hidden` to `block`.

---

## 2. What is `group-hover`?

`group-hover` is a Tailwind CSS variant that allows us to apply a CSS class when the element's parent having the `group` class is hovered.

### Syntax

```text
group-hover:utility
```

Example:

```html
<div class="group">
    <p class="text-black group-hover:text-blue-500">
        Hover over the parent
    </p>
</div>
```

When the parent is hovered, the paragraph changes its text color to blue.

---

# 3. Example: City List Dropdown

```html
<div class="group">
    
    <div class="cursor-pointer text-blue-400">
        City List
    </div>

    <div class="hidden group-hover:block">
        <ul>
            <li>Delhi</li>
            <li>Noida</li>
            <li>Gurgaon</li>
            <li>Hisar</li>
        </ul>
    </div>

</div>
```

### Explanation

### Parent

```html
<div class="group">
```

The `group` class tells Tailwind:

> "This element is a group whose state can control its child elements."

---

### City List

```html
<div class="cursor-pointer text-blue-400">
    City List
</div>
```

* `cursor-pointer` → Changes the mouse cursor to a pointer.
* `text-blue-400` → Makes the text blue.

---

### Hidden Menu

```html
<div class="hidden group-hover:block">
```

There are two classes here.

#### `hidden`

```text
hidden
```

The city list is hidden by default.

Equivalent CSS:

```css
display: none;
```

#### `group-hover:block`

```text
group-hover:block
```

When the parent element with `group` is hovered, the child becomes visible.

Equivalent idea:

```css
display: block;
```

So the behavior is:

```text
Normal state
     ↓
City List is hidden
     ↓
User hovers over the group
     ↓
group-hover:block is activated
     ↓
City List becomes visible
```

---

# 4. Important Correction

You originally used:

```html
<div class="hidden group-hover:black">
```

This is **incorrect**.

```text
group-hover:black
```

is not a valid Tailwind CSS display utility.

You should use:

```html
<div class="hidden group-hover:block">
```

The correct class is:

```text
group-hover:block
```

because `block` changes the element's display property to `display: block`.

---

# 5. Complete Example

```html
<!doctype html>
<html>
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <link rel="stylesheet" href="./output.css">
</head>

<body>

    <div class="group m-20">

        <!-- Title -->
        <div class="cursor-pointer text-blue-400">
            City List
        </div>

        <!-- City List -->
        <div class="hidden group-hover:block">
            <ul>
                <li>
                    <a href="#">Delhi</a>
                </li>

                <li>
                    <a href="#">Noida</a>
                </li>

                <li>
                    <a href="#">Gurgaon</a>
                </li>

                <li>
                    <a href="#">Hisar</a>
                </li>
            </ul>
        </div>

    </div>

</body>
</html>
```

## How it works

```text
             Parent
        ┌───────────────┐
        │    group      │
        │               │
        │  City List    │ ← Hover here
        │               │
        │  City Menu    │ ← hidden
        └───────────────┘
                 │
                 │ Hover
                 ↓
        group-hover:block
                 │
                 ↓
          Menu becomes visible
```

---

# 6. Common `group-hover` Examples

### Change text color

```html
<div class="group">
    <p class="group-hover:text-blue-500">
        Hello
    </p>
</div>
```

### Change background color

```html
<div class="group">
    <div class="group-hover:bg-blue-500">
        Box
    </div>
</div>
```

### Show hidden element

```html
<div class="group">
    <div class="hidden group-hover:block">
        Hello
    </div>
</div>
```

### Change opacity

```html
<div class="group">
    <div class="opacity-0 group-hover:opacity-100">
        Tooltip
    </div>
</div>
```

---

## Quick Revision Notes

| Class               | Meaning                                     |
| ------------------- | ------------------------------------------- |
| `group`             | Makes an element a group parent             |
| `group-hover:*`     | Applies a utility when the group is hovered |
| `hidden`            | `display: none`                             |
| `block`             | `display: block`                            |
| `group-hover:block` | Shows an element when the group is hovered  |
| `cursor-pointer`    | Changes cursor to pointer                   |
| `text-blue-400`     | Applies blue text color                     |

### Remember

```html
<!-- Parent -->
<div class="group">

    <!-- Child -->
    <div class="hidden group-hover:block">
        Content
    </div>

</div>
```

**Formula:**

> **Parent = `group`**
> **Child = `group-hover:utility`**

