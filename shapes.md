## Shapes

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Shapes</title>
    <style>
      :root {
        --shape-size: 100px;
        --rect-width: 180px;
        --circle-color: red;
        --square-color: blue;
        --triangle-color: maroon;
        --rectangle-color: green;
      }

      body {
        display: flex;
        align-items: center;
        justify-content: center;
        height: 100vh;
        background: #f4f4f4;
      }

      .container {
        display: flex;
        gap: 20px;
        flex-wrap: wrap;
        justify-content: center;
      }

      .shape {
        display: flex;
        align-items: center;
        justify-content: center;
        transition: transform 0.3s ease-in-out, filter 0.3s ease-in-out;
      }

      /* Drop shadow instead of box-shadow */
      .shape:hover {
        transform: scale(1.1);
        filter: drop-shadow(4px 4px 8px rgba(0, 0, 0, 0.3));
      }

      .circle {
        background: var(--circle-color);
        height: var(--shape-size);
        width: var(--shape-size);
        border-radius: 50%;
      }

      .square {
        background: var(--square-color);
        height: var(--shape-size);
        width: var(--shape-size);
      }

      .rectangle {
        background: var(--rectangle-color);
        height: var(--shape-size);
        width: var(--rect-width);
      }

      .triangle {
        height: 0;
        width: 0;
        border-left: calc(var(--shape-size) / 2) solid transparent;
        border-right: calc(var(--shape-size) / 2) solid transparent;
        border-bottom: var(--shape-size) solid var(--triangle-color);
      }
    </style>
  </head>

  <body>
    <div class="container">
      <div class="shape circle"></div>
      <div class="shape square"></div>
      <div class="shape triangle"></div>
      <div class="shape rectangle"></div>
    </div>
  </body>
</html>
```
