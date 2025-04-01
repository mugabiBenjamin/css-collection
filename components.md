# Components

## Table of contents

- [Accordion Menu I](#accordion-menu-i)
- [Loader](#loader)
- [Shapes](#shapes)
- [Conic gradient (border)](#conic-gradient-border)
- [Switches](#switches)

## Accordion Menu I

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Accordion</title>
    <style>
      :root {
        --primary-color: teal;
        --bg-color: lightsteelblue;
        --text-color: gray;
        --hover-color: #f0f0f0;
      }

      *,
      ::after,
      ::before {
        box-sizing: border-box;
        margin: 0;
        padding: 0;
      }

      body {
        display: grid;
        place-items: center;
        height: 100vh;
        background: var(--bg-color);
        font-family: sans-serif;
      }

      ul.accordion {
        max-width: 600px;
        width: 90%;
      }

      ul.accordion li {
        list-style: none;
        margin-bottom: 10px;
        background: #fff;
        border-radius: 8px;
        overflow: hidden;
        transition: box-shadow 0.3s ease-in-out;
      }

      ul.accordion li label {
        padding: 15px;
        display: flex;
        justify-content: space-between;
        align-items: center;
        font-size: 18px;
        font-weight: bold;
        color: var(--primary-color);
        cursor: pointer;
        transition: background 0.3s;
        user-select: none;
      }

      ul.accordion li label:hover {
        background: var(--hover-color);
      }

      ul.accordion li label span.greater {
        transform: rotate(-90deg);
        font-size: 22px;
        transition: transform 0.3s ease-in-out;
      }

      input[type="checkbox"] {
        display: none;
      }

      .accordion .content {
        padding: 0 15px;
        line-height: 26px;
        height: 0;
        opacity: 0;
        overflow: hidden;
        transition: height 0.4s ease-in-out, opacity 0.4s ease-in-out;
        color: var(--text-color);
      }

      input[type="checkbox"]:checked ~ .content {
        height: auto;
        opacity: 1;
        padding: 15px;
      }

      input[type="checkbox"]:checked + label span.greater {
        transform: rotate(90deg);
      }

      input[type="checkbox"]:checked + label {
        background: var(--hover-color);
      }

      input[type="checkbox"]:checked ~ .content {
        box-shadow: 0 2px 10px rgba(0, 0, 0, 0.2);
      }
    </style>
  </head>

  <body>
    <ul class="accordion">
      <li>
        <input type="checkbox" id="first" />
        <label for="first" role="button" aria-expanded="false"
          >What is HTML? <span class="greater">&gt;</span></label
        >
        <div class="content" id="content-first">
          <p>
            HTML is the standard markup language for creating web pages. The
            HyperText Markup Language is the standard markup language for
            documents designed to be displayed in a web browser. It can be
            assisted by technologies such as Cascading Style Sheets and
            scripting languages such as JavaScript.
          </p>
        </div>
      </li>
      <li>
        <input type="checkbox" id="second" />
        <label for="second" role="button" aria-expanded="false"
          >What is CSS? <span class="greater">&gt;</span></label
        >
        <div class="content" id="content-second">
          <p>
            CSS is used to style web pages and make them visually appealing.
            Cascading Style Sheets is a style sheet language used for describing
            the presentation of a document written in a markup language such as
            HTML. CSS is a cornerstone technology of the World Wide Web,
            alongside HTML and JavaScript.
          </p>
        </div>
      </li>
      <li>
        <input type="checkbox" id="third" />
        <label for="third" role="button" aria-expanded="false"
          >What is JavaScript? <span class="greater">&gt;</span></label
        >
        <div class="content" id="content-third">
          <p>
            JavaScript is a programming language that makes web pages
            interactive. JavaScript, often abbreviated JS alongside HTML and
            CSS. Over 97% of websites use JavaScript on the client side for web
            page behavior, often third-party libraries.
          </p>
        </div>
      </li>
      <li>
        <input type="checkbox" id="fourth" />
        <label for="fourth" role="button" aria-expanded="false"
          >What is React? <span class="greater">&gt;</span></label
        >
        <div class="content" id="content-fourth">
          <p>
            React is a JavaScript library for building dynamic user interfaces.
            It is maintained by Meta and a community of individual developers
            and companies. React can be used as a base in the development of
            single-page or mobile applications. It is free and open-source.
          </p>
        </div>
      </li>
      <li>
        <input type="checkbox" id="fifth" />
        <label for="fifth" role="button" aria-expanded="false"
          >What is Node.js? <span class="greater">&gt;</span></label
        >
        <div class="content" id="content-fifth">
          <p>
            Node.js is a runtime environment that allows JavaScript to run
            server-side. Node.js is an open-source, cross-platform, back-end
            JavaScript runtime environment that runs on the V8 JavaScript engine
            and executes JavaScript code outside a web browser. Node.js lets
            developers use JavaScript to write command line tools and for
            server-side scripts.
          </p>
        </div>
      </li>
    </ul>

    <script>
      document
        .querySelectorAll("input[type='checkbox']")
        .forEach((checkbox) => {
          checkbox.addEventListener("change", function () {
            document
              .querySelectorAll("input[type='checkbox']")
              .forEach((cb) => {
                if (cb !== this) {
                  cb.checked = false;
                  cb.nextElementSibling.setAttribute("aria-expanded", "false");
                }
              });

            this.nextElementSibling.setAttribute(
              "aria-expanded",
              this.checked ? "true" : "false"
            );
          });
        });
    </script>
  </body>
</html>
```

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

## Conic gradient (border)

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

## Switches

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Enhanced Switch Buttons</title>
    <style>
        :root {
            --switch-width: 3.75rem;
            /* 60px */
            --switch-height: 2.125rem;
            /* 34px */
            --switch-bg: #ccc;
            --switch-active-bg: maroon;
            --switch-handle: #fff;
            --switch-transition: 0.3s ease-in-out;
        }

        *,
        ::before,
        ::after {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
        }

        body {
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            font-family: Arial, sans-serif;
            background: #f4f4f4;
        }

        .switch-container {
            display: flex;
            justify-content: center;
            align-items: center;
            gap: 2.5rem;
            /* 40px */
        }

        .switch {
            position: relative;
            display: inline-flex;
            width: var(--switch-width);
            height: var(--switch-height);
            align-items: center;
            cursor: pointer;
            border-radius: 50px;
            overflow: hidden;
        }

        .switch-input {
            display: none;
        }

        .switch-bg {
            width: 100%;
            height: 100%;
            background: var(--switch-bg);
            border-radius: 50px;
            transition: background var(--switch-transition), box-shadow 0.3s ease-in-out;
        }

        .switch-handle {
            position: absolute;
            top: 4px;
            left: 4px;
            width: calc(var(--switch-height) - 8px);
            height: calc(var(--switch-height) - 8px);
            background: var(--switch-handle);
            border-radius: 50%;
            box-shadow: 0px 2px 5px rgba(0, 0, 0, 0.2);
            transition: transform var(--switch-transition), box-shadow 0.3s ease-in-out;
        }

        /* Checked State */
        .switch-input:checked+.switch-bg {
            background: var(--switch-active-bg);
            box-shadow: 0px 0px 10px rgba(128, 0, 0, 0.5);
        }

        .switch-input:checked~.switch-handle {
            transform: translateX(calc(var(--switch-width) - var(--switch-height)));
            box-shadow: 0px 4px 10px rgba(0, 0, 0, 0.3);
        }

        /* Fix: Hover effect on .switch */
        .switch:hover .switch-bg {
            box-shadow: 0px 0px 10px rgba(0, 0, 0, 0.3);
        }

        /* Focus styles for keyboard accessibility */
        .switch-input:focus-visible+.switch-bg {
            outline: 2px solid #000;
            outline-offset: 2px;
        }

        /* Optional: Smooth bounce effect */
        .switch-input:checked~.switch-handle {
            transition: transform var(--switch-transition), box-shadow 0.2s ease-in-out;
        }
    </style>
</head>

<body>
    <div class="switch-container">
        <label class="switch">
            <input type="checkbox" class="switch-input" aria-label="Enable feature 1">
            <span class="switch-bg"></span>
            <span class="switch-handle"></span>
        </label>
        <label class="switch">
            <input type="checkbox" class="switch-input" aria-label="Enable feature 2">
            <span class="switch-bg"></span>
            <span class="switch-handle"></span>
        </label>
        <label class="switch">
            <input type="checkbox" class="switch-input" aria-label="Enable feature 3">
            <span class="switch-bg"></span>
            <span class="switch-handle"></span>
        </label>
    </div>
</body>

</html>
```

[Back to top](#table-of-contents)
