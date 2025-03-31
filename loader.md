## Loader

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Loader</title>

    <style>
      :root {
        --loader-size: 60px;
        --border-width: 6px;
        --primary-color: teal;
      }

      body {
        height: 100vh;
        width: 100vw;
        display: flex;
        align-items: center;
        justify-content: center;
        background: #f4f4f4;
      }

      .loader {
        width: var(--loader-size);
        height: var(--loader-size);
        border: var(--border-width) solid rgba(0, 128, 128, 0.3);
        border-top: var(--border-width) solid var(--primary-color);
        border-radius: 50%;
        animation: rotate 1s infinite linear;
        will-change: transform;
        box-shadow: 0 0 10px rgba(0, 128, 128, 0.5);
      }

      @keyframes rotate {
        0% {
          transform: rotate(0deg);
        }

        100% {
          transform: rotate(360deg);
        }
      }
    </style>
  </head>

  <body>
    <div class="loader"></div>
  </body>
</html>
```
