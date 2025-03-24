## Table of contents

- [gradient on a border](#gradient-on-a-border)
- [no grid, no flexbox for image gallery](#no-grid-no-flexbox-for-image-gallery)
- [accent-color, caret-color](#accent-color-caret-color)
- [inset](#inset)
- [dynamic content](#dynamic-content)
- [shadows](#shadows)
- [clip path](#clip-path)
- [dynamic psuedo elements](#dynamic-psuedo-elements)
- [resize](#resize)
- [new morphism](#new-morphism)
- [checkboxes](#checkboxes)
- [glass morphism](#glass-morphism)
- [:not() and :has()](#not-and-has)
- [gradient on text](#gradient-on-text)
- [dropdown](#dropdown)
- [numbering headings](#numbering-headings)
- [swipper](#swipper)

## gradient on a border

```css
button::after {
  content: "";
  background-image: linear-gradient(to right #0066ff, #ff32d6);
  position: absolute;
  height: 100%;
  width: 100%;
  padding: 0.1rem;
  left: 50%;
  top: 50%;
  translate: -50%, -50%;
  z-index: -1;
}

/* Alternatively */
button {
  border-image: linear-gradient(to right #0066ff, #ff32d6) 1 1 1 1; /* top right bottom left */
  /* or use 1 as border-width: for all */
}
```

## no grid, no flexbox for image gallery

```html
<div class="layout-container">
  <img width="300px" src="img-1.jpg" alt="" />
  <img width="300px" src="img-2.jpg" alt="" />
  <img width="300px" src="img-3.jpg" alt="" />
  <img width="300px" src="img-4.jpg" alt="" />
  <img width="300px" src="img-5.jpg" alt="" />
  <img width="300px" src="img-6.jpg" alt="" />
</div>
```

```css
.layout-container {
  width: min(100px, 100%);
  /* responsive with */
  margin: 0 auto;
  /* centers the layout */
  columns: 3 300px;
  column-gap: 1rem;
}

img {
  width: 100%;
  /* makes the images resize automatically */
  /* images are inline elements so they're bound to their line-height */

  display: block;
  margin-bottom: 1rem;
}
```

## accent-color, caret-color

```css
/* checkbox, radio button, progress bar, range selector */

input {
  accent-color: grey;
  caret-color: gold;
}
```

## inset

```css
.parent {
  border: 3px solid white;
  height: 300px;
  width: 300px;
  color: white;
  padding: 1rem;
  position: relative;
}

.child {
  width: 50px;
  height: 50%;
  background: #0071ff;
  position: absolute;
  inset: 10px 30px 0 100px;

  /* 
    inset: 0; covers the whole element 
    margin: auto;

    these two center the child
    */
}
```

## dynamic content

```css
.container {
  margin-top: 1rem;
  padding: 2rem;
  border-radius: 1rem;
  background: #282a32;
  color: #a3abbf;

  height: 100px;
  /* Fixed height */
  overflow-y: auto;
  /* only containers that have overflowing text */
}
```

## shadows

```css
.serch-icon {
  filter: drop-shadow(5px 5px 5px rgba(0, 0, 0, 0.3));
}
```

## clip path

```css
/* css clip path online generator */
img {
  clip-path: polygon(50% 0%, 0% 100%, 100% 100%);
}

input[type="checkbox"] {
  height: 20px;
  width: 20px;
  clip-path: circle(50%);
  accent-color: #9443d7;
  appearance: none;
  background: #cacaca;
}

input[type="checkbox"] {
  appearance: auto;
}
```

## dynamic psuedo elements

```css
.product::before {
  content: attr(data-label);
  position: absolute;
  top: 0;
  left: 50%;
  translate: -50%, -50%;
  background: #ffdd0035;
  border: 1px solid #ffdd00;
  color: #ffdd00;
  padding: 0.5em 2em;
  border-radius: 100px;
  text-transform: uppercase;
}
```

```html
<div data-label="free" class="product">
  <img height="200px" src="" alt="" />
  <h2>HTML Course</h2>
  <p></p>
</div>
<div data-label="best selling" class="product">
  <img height="200px" src="" alt="" />
  <h2>HTML & CSS Course</h2>
  <p></p>
</div>
<div data-label="coming soon" class="product">
  <img height="200px" src="" alt="" />
  <h2>JavaScript Course</h2>
  <p></p>
</div>
```

## resize

```css
.element {
  resize: both;
  /* works with overflow hidden */
}
```

## new morphism

```css
body {
  background: #f9f9f9;
  /* very light grey bg */
}

.element:hover {
  box-shadow: 12px 12px 12px rgba(0, 0, 0, 0.1), -10px -10px -10px white inset;
  /* toggle the word inset */

  /* make the top left shadow slightly lighter than the bg color */
}
```

## checkboxes

```html
<input type="checkbox" id="mycheckbox" />
<label for="mycheckbox">My Label</label>
```

```css
.container {
  display: none;
  width: min(800px, 90%);
  /* always returns the smaller value */
  /* 
    on desktop 800px the smaller while on smaller screens 90% is the smaller 
    */

  width: clamp(400px, 50vw, 800px);

  /* 
    400px is the min
    50vw is thr preferred
    800px is the max
    */
}

#mycheckbox:checked ~ .container {
  display: block;
}

#mycheckbox {
  display: none;
}
```

## glass morphism

```css
.glass {
  backdrop-filter: blur(10px);
}
```

## :not() and :has()

```css
.button:not(:first-child) {
  border-color: red;
  /* excludes */
}
```

```html
<button>Button</button>
<button>Button</button>
<button>Info <svg xmlns=" "> </button>
<button>Security <svg xmlns=" "> </button>
<button>Ideas <svg xmlns=" "> </button>
```

```css
.button:has(svg) {
  padding-right: 14px;
  display: flex;
  align-items: center;
  gap: 10px;
  fill: white;
}
```

```html
<select>
  <option value="light">lightmode</option>
  <option value="dark">darkmode</option>
</select>
```

```css
body:has(option[value="dark"]:checked) {
  background: black;
  color: white;
}
```

## gradient on text

```css
h1 {
  background: linear-gradient(to right, red, blue);
  background-clip: text;
  color: transparent;
}
```

## dropdown

```css
.dropdown {
  display: none;
}

.my-button:focus-within .dropdown {
  display: flex;
}
```

## numbering headings

```css
:root {
  counter-reset: headings;
}

h2 {
  counter-increment: headings;
}

h2::before {
  content: counter(headings);
  background: #0071ff;
  border-radius: 2px;
  padding: 0.15rem 0;
  width: 40px;
  text-align: center;
}
```

## swipper

```html
<div class="wrapper">
  <div class="card">
    <h2></h2>
    <p></p>
  </div>
  <div class="card">
    <h2></h2>
    <p></p>
  </div>
  <div class="card">
    <h2></h2>
    <p></p>
  </div>
</div>
```

```css
.wrapper {
  display: flex;
  gap: 20px;
  width: 300px;
  overflow-x: scroll;
  scroll-snap-type: x mandatory;
  /* mandatory || proximity */
}

.card {
  scroll-snap-align: center;
  box-sizing: border-box;
  padding: 20px 30px;
  flex-shrink: 0;
  width: 300px;
  background: white;
  border-radius: 14px;
  text-align: center;
}
```

[Back to top](#table-of-contents)

## Relative padding

```css
.element {
  padding: min(5rem, 8%);
  /* Ensures padding is responsive: 
     - 5rem is the maximum padding
     - 8% is the relative padding based on the container's width 
  */
  width: 400px;
  background: white;
  box-shadow: 0 3px 10px rgba(0, 0, 0, 0.1);
  box-rading: 1em;
}
```

# Responsive font-sizes

```css
h1 {
  font-size: clamp(1.8rem, calc(7vw + 1rem), 5rem);
  /* 
    1.8rem is the min
    calc(7vw + 1rem) is the preferred and responds to zooming
    5rem is the max
    */
}
```

# Responsive Images

```css
img {
  max-width: 100%;
  height: auto;
  /* keeps the aspect ratio */
  aspect-ratio: 1/1;
  object-fit: cover;
}
```

```html
<img
  width="500"
  height="750"
  src="https://images.pexels.com/photos/25252455/pexels-photo-25252455/free-photo-of-thick-clouds-in-black-and-white.jpeg?auto=compress&cs=tinysrgb&w=1260&h=750&dpr=1"
/>
```
