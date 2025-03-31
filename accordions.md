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

## Accordion Menu II

```html

```
