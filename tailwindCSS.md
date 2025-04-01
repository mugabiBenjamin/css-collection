# Tailwind class tips

```css
/* Utility classes for sizing */
w-48 h-48 -> size-48

/* Divide children vertically with a red divider */
divide-y-8 divide-red-500 -> on the parent element, whose children are stacked vertically

/* Add vertical spacing between children */
space-y-8 on parent element

/* Limit text to two lines with ellipsis */
line-clamp-2

/* Truncate text to fit in one line with ellipsis */
truncate -> paragraph text on one live the rest is hidden

/* Gradient background with specific color stops */
h-48 w-full bg-gradient-to-r from-orange-500 to-black via-white from-20% via-70% to-90%
```

## Fluid text sizing

```css
/* Fluid text sizing using min() function */
<p class="text-[min(10vw,70px)]">Something Fluid</p>
```

## Customizing file inputs

```css
/* File input with custom styles */
<label class="m-4 block">
  <input type="file" class="block w-full text-sm text-slate-500 file:mr-4 file:rounded-full file:border-0 file:bg-violet-50 file:px-4 file:py-2 file:text-sm file:font-semibold file:text-violet-700 hover:file:bg-violet-100">
</label>
```

## Custom layers

```css
/* Define a custom theme color */
@theme {
  --color-chestnut: #782f29;
}

/* Base layer styles */
@layer base {
  h3 {
    @apply font-medium;
  }

  p {
    @apply mt-2 text-slate-500;
  }

  button {
    @apply mt-2 text-slate-500;
  }
}

/* Component layer styles */
@layer components {
  .card {
    @apply m-10 rounded-lg bg-white;
  }
}

/* Utility class for centering flex items */
@utility flex-center {
  @apply flex justify-center items-center;
}
```
