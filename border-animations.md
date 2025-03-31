## Conic gradient

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Border Animations</title>
    <style>
      body {
        position: absolute;
        top: 50%;
        left: 50%;
        transform: translate(-50%, -50%);
        background: black;
        color: lightgrey;
        font-family: Arial, Helvetica, sans-serif;
      }

      @property --angle {
        syntax: "<angle>";
        initial-value: 0deg;
        inherits: false;
      }

      .card {
        margin: 0 auto;
        padding: 2em;
        width: 300px;
        /* height: 300px; */
        background: grey;
        text-align: center;
        border-radius: 10px;
        position: relative;
      }

      .card::after,
      .card::before {
        content: "";
        position: absolute;
        height: 100%;
        width: 100%;
        /* background-image: conic-gradient(from var(--angle), red, blue, green, red); */
        background-image: conic-gradient(
          from var(--angle),
          transparent 60%,
          red
        );
        top: 50%;
        left: 50%;
        transform: translate(-50%, -50%);
        z-index: -1;
        padding: 5px;
        border-radius: 10px;
        animation: spin 3s linear infinite;
      }

      .card::before {
        filter: blur(1.5rem);
        /* opacity: 0.5; */
      }

      @keyframes spin {
        from {
          --angle: 0deg;
        }

        to {
          --angle: 360deg;
        }
      }
    </style>
  </head>

  <body>
    <div class="card">
      <h2>Animated Borders</h2>
      <p>
        Lorem ipsum dolor sit amet, consectetur adipisicing elit. Magnam, quas
        odio laborum tempora assumenda sit animi blanditiis dolore adipisci
        pariatur iste architecto debitis? Alias doloribus modi rerum voluptates
        velit quod?
      </p>
    </div>
  </body>
</html>
```
