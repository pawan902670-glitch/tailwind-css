
# Tailwind CSS v4 — `@theme`, Spacing & `@media screen`

## 1. Tailwind CSS v4 mein `@theme` kya hai?

Tailwind CSS v4 mein customization ke liye CSS ke andar `@theme` use kar sakte hain.

```css
@import "tailwindcss";

@theme {
  --spacing-custom: 32px;
}
```

Yahan:

```css
--spacing-custom: 32px;
```

ek **custom design token** hai.

Iska matlab hai ki humne `custom` naam ka spacing value define kiya hai:

```text
custom = 32px
```

---

## 2. `@theme` ka use kahan hota hai?

`@theme` ke andar aap project ke design values define kar sakte ho, jaise:

```css
@theme {
  --spacing-custom: 32px;
  --spacing-sidebar: 280px;

  --color-primary: #2563eb;

  --font-display: "Inter", sans-serif;
}
```

Concept:

```text
@theme
   │
   ├── Spacing
   ├── Colors
   ├── Fonts
   └── Other design tokens
```

---

# 3. Custom spacing kaise define karein?

Example:

```css
@theme {
  --spacing-custom: 32px;
}
```

Ab `custom` spacing ki value:

```text
32px
```

hai.

Aap is value ko CSS mein directly bhi use kar sakte ho:

```css
.custom-container {
  padding: var(--spacing-custom);
}
```

Yahan:

```css
var(--spacing-custom)
```

ka matlab hai:

> `--spacing-custom` ki value lekar aao.

Result:

```css
padding: 32px;
```

---

# 4. `var()` kya karta hai?

Agar aapne define kiya:

```css
--spacing-custom: 32px;
```

To use karne ke liye:

```css
var(--spacing-custom)
```

likhte hain.

Example:

```css
.box {
  padding: var(--spacing-custom);
}
```

Browser isko roughly aise samjhega:

```css
.box {
  padding: 32px;
}
```

---

# 5. `@media screen` kya hai?

`@media screen` CSS ka **responsive design** feature hai.

Iska use screen size ke according CSS apply karne ke liye hota hai.

Example:

```css
@media screen and (min-width: 768px) {
  .custom-container {
    padding: 32px;
  }
}
```

Iska matlab:

> Agar screen ki width 768px ya usse zyada hai, tab `.custom-container` par ye CSS apply karo.

---

# 6. `min-width` kya karta hai?

```css
@media screen and (min-width: 768px)
```

Yahan:

```text
min-width: 768px
```

ka matlab:

```text
768px ya usse badi screen
```

Example:

```text
500px   → Media query apply nahi hogi

767px   → Media query apply nahi hogi

768px   → Media query apply hogi

1024px  → Media query apply hogi

1440px  → Media query apply hogi
```

---

# 7. Complete Example

### `input.css`

```css
@import "tailwindcss";

@theme {
  --spacing-custom: 32px;
}

.custom-container {
  @apply bg-green-500;
}

@media screen and (min-width: 768px) {
  .custom-container {
    padding: var(--spacing-custom);
  }
}
```

### `function.html`

```html
<!doctype html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">

    <link rel="stylesheet" href="./output.css">

    <title>Tailwind v4</title>
</head>

<body>

    <div class="custom-container">
        Hello
    </div>

</body>
</html>
```

---

# 8. Ye code kaise kaam karta hai?

Sabse pehle:

```css
@theme {
  --spacing-custom: 32px;
}
```

Humne custom spacing define ki:

```text
spacing-custom = 32px
```

Phir:

```css
.custom-container {
  @apply bg-green-500;
}
```

Isse `.custom-container` ko Tailwind ka green background milta hai.

Phir:

```css
@media screen and (min-width: 768px) {
```

Hum bol rahe hain:

> 768px ya usse badi screen par neeche wala CSS activate karo.

Phir:

```css
.custom-container {
  padding: var(--spacing-custom);
}
```

`var(--spacing-custom)` ki value hai:

```text
32px
```

Isliye final result:

```css
.custom-container {
  padding: 32px;
}
```

---

# 9. Complete Flow

Isko yaad rakhne ka simple tarika:

```text
@theme
   ↓
--spacing-custom: 32px
   ↓
CSS variable create
   ↓
var(--spacing-custom)
   ↓
32px
   ↓
@media screen
   ↓
Screen ≥ 768px
   ↓
.custom-container
   ↓
padding: 32px
```

---

# 10. `@apply` kya karta hai?

Tailwind utility ko custom CSS class ke andar use karne ke liye `@apply` use kar sakte ho.

Example:

```css
.custom-container {
  @apply bg-green-500;
}
```

Iska concept roughly:

```css
.custom-container {
  background-color: ...;
}
```

Yaani:

```text
Tailwind Utility
      ↓
bg-green-500
      ↓
@apply
      ↓
.custom-container
```

HTML:

```html
<div class="custom-container">
    Hello
</div>
```

---

# 11. `@media` + `@theme` + `@apply` ek saath

Aap teen concepts ko ek saath use kar sakte ho:

```css
@import "tailwindcss";

@theme {
  --spacing-custom: 32px;
}

.custom-container {
  @apply bg-green-500;
}

@media screen and (min-width: 768px) {
  .custom-container {
    padding: var(--spacing-custom);
  }
}
```

Yahan:

```text
@theme
→ Value define karta hai

@apply
→ Tailwind utility ko custom class mein apply karta hai

@media
→ Decide karta hai ki CSS kis screen size par apply hogi
```

---

# 12. Tailwind `md:` vs CSS `@media`

Dono ka purpose responsive styling hai, lekin syntax alag hai.

### Tailwind approach

```html
<div class="p-4 md:p-8">
    Hello
</div>
```

Yahan `md:` Tailwind ka responsive variant hai.

### Normal CSS approach

```css
@media screen and (min-width: 768px) {
  .box {
    padding: 32px;
  }
}
```

HTML:

```html
<div class="box">
    Hello
</div>
```

Concept:

```text
Tailwind
md:p-8
   ↓
Tailwind responsive utility


CSS
@media screen
   ↓
Normal CSS media query
```

**Important:** Aapko dono approaches ek hi project mein use karna zaroori nahi hai. Tailwind utility classes ke liye `md:` convenient hai, aur custom CSS rules ke liye `@media` useful hai.

---

## Quick Revision

```css
@theme {
  --spacing-custom: 32px;
}
```

➡️ Custom value define karta hai.

```css
var(--spacing-custom)
```

➡️ Custom value ko access karta hai.

```css
@apply bg-green-500;
```

➡️ Tailwind utility ko custom CSS class mein apply karta hai.

```css
@media screen and (min-width: 768px)
```

➡️ 768px+ screen par CSS apply karta hai.

```html
<div class="custom-container">
```

➡️ HTML element par custom CSS class apply karta hai.

**Main concept:** `function.html` mein class lagti hai → `input.css` mein class ki styling hoti hai → Tailwind CSS compile karke `output.css` banata hai → browser `output.css` load karke final design show karta hai.
