# Tailwind CSS Notes – **Columns (`columns-*`)**

## Beginner → Project → Interview Notes

---

# 1. What is `columns`?

The **`columns`** utility in Tailwind CSS creates a **multi-column layout**.

Instead of placing items in rows (like Grid), it flows content **from top to bottom** and then starts the next column.

Think of a newspaper.

```
Column 1    Column 2    Column 3
---------   ---------   ---------
Image 1     Image 4     Image 7
Image 2     Image 5     Image 8
Image 3     Image 6     Image 9
```

---

# 2. Syntax

```html
<div class="columns-3">
    ...
</div>
```

Creates **3 equal columns**.

---

# 3. Column Number Classes

These create a fixed number of columns.

| Class      | Meaning    |
| ---------- | ---------- |
| columns-1  | 1 column   |
| columns-2  | 2 columns  |
| columns-3  | 3 columns  |
| columns-4  | 4 columns  |
| columns-5  | 5 columns  |
| columns-6  | 6 columns  |
| columns-7  | 7 columns  |
| columns-8  | 8 columns  |
| columns-9  | 9 columns  |
| columns-10 | 10 columns |
| columns-11 | 11 columns |
| columns-12 | 12 columns |

Example

```html
<div class="columns-4">
```

Output

```
| Col1 | Col2 | Col3 | Col4 |
```

---

# 4. Width-Based Columns

Instead of saying

```
Make 4 columns
```

You say

```
Each column should be around 320px wide.
```

The browser decides how many columns fit.

---

## Available Width Classes

| Class       | Approx Width |
| ----------- | ------------ |
| columns-3xs | 16rem        |
| columns-2xs | 18rem        |
| columns-xs  | 20rem        |
| columns-sm  | 24rem        |
| columns-md  | 28rem        |
| columns-lg  | 32rem        |
| columns-xl  | 36rem        |
| columns-2xl | 42rem        |
| columns-3xl | 48rem        |
| columns-4xl | 56rem        |
| columns-5xl | 64rem        |
| columns-6xl | 72rem        |
| columns-7xl | 80rem        |

Example

```html
<div class="columns-xl">
```

Means

```
Each column width ≈ 36rem.
```

NOT

```
One XL column
```

---

# 5. Responsive Prefixes

Tailwind is **Mobile First**.

Prefixes apply styles **only after that screen size**.

---

## Responsive Breakpoints

| Prefix | Screen Width | Example       |
| ------ | ------------ | ------------- |
| (none) | 0px+         | columns-1     |
| sm     | ≥640px       | sm:columns-2  |
| md     | ≥768px       | md:columns-3  |
| lg     | ≥1024px      | lg:columns-4  |
| xl     | ≥1280px      | xl:columns-5  |
| 2xl    | ≥1536px      | 2xl:columns-6 |

---

## Example

```html
<div class="
columns-1
sm:columns-2
md:columns-3
lg:columns-4
xl:columns-5
2xl:columns-6
">
```

### Mobile

```
Image
Image
Image
```

---

### Small Screen

```
Image   Image
Image   Image
```

---

### Medium Screen

```
Image   Image   Image
```

---

### Large Screen

```
Image Image Image Image
```

---

### Extra Large

```
Image Image Image Image Image
```

---

### 2XL

```
Image Image Image Image Image Image
```

---

# 6. Most Useful Responsive Commands

```html
sm:columns-2
```

Apply after **640px**

---

```html
md:columns-3
```

Apply after **768px**

---

```html
lg:columns-4
```

Apply after **1024px**

---

```html
xl:columns-5
```

Apply after **1280px**

---

```html
2xl:columns-6
```

Apply after **1536px**

---

# 7. Gap Between Columns

```
gap-4
```

Adds spacing.

Example

```html
<div class="columns-3 gap-4">
```

---

Gap Sizes

```
gap-1
gap-2
gap-3
gap-4
gap-5
gap-6
gap-8
gap-10
gap-12
gap-16
```

Most used

```
gap-4
gap-6
gap-8
```

---

# 8. Space Between Images

Columns don't automatically add vertical spacing.

Use

```html
mb-4
```

Example

```html
<img class="mb-4">
```

---

Common Margin Bottom

```
mb-1
mb-2
mb-3
mb-4
mb-5
mb-6
mb-8
```

---

# 9. Making Images Responsive

Always use

```html
class="w-full"
```

Example

```html
<img
class="w-full"
src="">
```

Without

```
w-full
```

Images may overflow.

---

# 10. Rounded Images

```
rounded
rounded-md
rounded-lg
rounded-xl
rounded-2xl
rounded-full
```

Example

```html
<img class="rounded-xl">
```

---

# 11. Shadow

```
shadow
shadow-md
shadow-lg
shadow-xl
shadow-2xl
```

Example

```html
<img class="shadow-lg">
```

---

# 12. Hover Effect

Zoom

```html
hover:scale-105
```

Rotation

```html
hover:rotate-3
```

Brightness

```html
hover:brightness-110
```

Opacity

```html
hover:opacity-80
```

---

# 13. Smooth Animation

```
transition
duration-300
ease-in-out
```

Example

```html
class="
transition
duration-300
hover:scale-105
"
```

---

# 14. Complete Project Example

```html
<div
class="
columns-1
sm:columns-2
md:columns-3
lg:columns-4
xl:columns-5
gap-5
">

<img
class="
w-full
mb-5
rounded-xl
shadow-lg
transition
duration-300
hover:scale-105
"
src="image.jpg">

</div>
```

---

# 15. Real Projects Using Columns

✅ Photo Gallery

✅ Travel Blog

✅ Food Gallery

✅ Portfolio

✅ News Website

✅ Photography Website

✅ Pinterest Clone

---

# 16. Columns vs Grid

## Columns

```
Image
Image
Image

↓

Next Column
```

Content flows vertically.

Best for

* Gallery
* Blog
* Masonry

---

## Grid

```
Image Image Image
Image Image Image
```

Perfect alignment.

Best for

* Cards
* Dashboard
* Pricing
* Forms

---

# 17. Common Mistakes

Wrong

```html
<div class="column-3">
```

Correct

```html
<div class="columns-3">
```

---

Wrong

```html
<div class="colummns-2md">
```

Correct

```html
<div class="md:columns-2">
```

---

Wrong

```html
<img src="">
```

Better

```html
<img
class="w-full mb-4 rounded-lg"
src="">
```

---

# 18. Interview Questions

### Q1 What is columns?

Creates multi-column layouts.

---

### Q2 Difference between Grid and Columns?

Grid

* Fixed rows

Columns

* Automatic vertical flow

---

### Q3 Difference between

```
columns-3
```

and

```
columns-3xl
```

columns-3

```
Exactly 3 columns.
```

columns-3xl

```
Each column width is about 48rem.
Browser decides the number of columns.
```

---

### Q4 Which responsive prefixes are available?

```
sm
md
lg
xl
2xl
```

---

### Q5 Which classes are commonly used with columns?

```
gap-4
mb-4
w-full
rounded-lg
shadow-lg
transition
duration-300
hover:scale-105
```

---

# 19. Quick Cheat Sheet

| Utility         | Purpose                          |
| --------------- | -------------------------------- |
| columns-1       | 1 column                         |
| columns-2       | 2 columns                        |
| columns-3       | 3 columns                        |
| columns-4       | 4 columns                        |
| columns-5       | 5 columns                        |
| columns-6       | 6 columns                        |
| columns-xs      | Width-based column               |
| columns-sm      | Width-based column               |
| columns-md      | Width-based column               |
| columns-lg      | Width-based column               |
| columns-xl      | Width-based column               |
| columns-2xl     | Width-based column               |
| columns-3xl     | Width-based column               |
| sm:columns-2    | 2 columns on small screens       |
| md:columns-3    | 3 columns on medium screens      |
| lg:columns-4    | 4 columns on large screens       |
| xl:columns-5    | 5 columns on extra-large screens |
| 2xl:columns-6   | 6 columns on 2XL screens         |
| gap-4           | Space between columns            |
| mb-4            | Space below items                |
| w-full          | Full width image                 |
| rounded-lg      | Rounded corners                  |
| shadow-lg       | Large shadow                     |
| hover:scale-105 | Zoom on hover                    |
| transition      | Enable animation                 |
| duration-300    | Animation speed                  |

---

# 20. Best Practices

* ✔ Start with `columns-1` for mobile.
* ✔ Add responsive prefixes (`sm`, `md`, `lg`, `xl`, `2xl`).
* ✔ Use `gap-*` for spacing between columns.
* ✔ Add `mb-*` to each image for vertical spacing.
* ✔ Use `w-full` so images fit their columns.
* ✔ Add `rounded-*`, `shadow-*`, and `hover:*` for a polished UI.
* ✔ Use `loading="lazy"` on images to improve performance.
* ✔ Use meaningful `alt` text for accessibility.
* ✔ Use **Columns** for image galleries and article layouts.
* ✔ Use **Grid** or **Flexbox** for dashboards, forms, and card layouts where alignment is important.

