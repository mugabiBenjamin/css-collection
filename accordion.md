<!DOCTYPE html>
<html lang="en">

<head>
  <meta charset="UTF-8" />
  <meta http-equiv="X-UA-Compatible" content="IE=edge" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Accordion</title>
  <style>
    /* Resetting default styles */
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
      background: lightsteelblue;
      font-family: sans-serif;
    }

    ul.accordion {
      /* margin: 100px auto; */
      max-width: 600px;
      /* use max-width instead of width */
    }

    ul.accordion li {
      list-style: none;
      margin-bottom: 10px;
      background: #fff;
      padding: 10px;
      border-radius: 8px;
    }

    ul.accordion li label {
      padding: 10px;
      display: flex;
      justify-content: space-between;
      align-items: center;
      font-size: 18px;
      font-weight: 500;
      color: teal;
      cursor: pointer;
      font-weight: bold;
    }

    ul.accordion li label span.greater {
      transform: rotate(-90deg);
      font-size: 22px;
      /* color: dodgerblue; */
    }

    input[type="checkbox"] {
      display: none;
    }

    .accordion .content {
      padding: 0 10px;
      line-height: 26px;
      max-height: 0;
      overflow: hidden;
      transition: max-height 0.5s;
      color: gray;
    }

    input[type="checkbox"]:checked~.content {
      max-height: 400px;
      transition: 0.5s ease-in-out;
    }

    /* Apply styles when the checkbox is checked 
     Added these below
    */

    input[type="checkbox"]:is(:checked)+label span.greater {
      transform: rotate(90deg);
      transition: transform 0.3s ease-in-out;
    }

    /* input[type="checkbox"]:is():checked ul.accordion li {
      box-shadow: 1px 1px 20px rgba(0, 0, 0, 0.5);
    } */
  </style>
</head>

<body>
  <ul class="accordion">
    <li>
      <input type="checkbox" id="first" />
      <label for="first">What is HTML? <span class="greater">&gt;</span></label>
      <div class="content">
        <p>
          The HyperText Markup Language or HTML is the standard markup language for documents designed to be displayed
          in a web browser. It can be assisted by technologies such as Cascading Style Sheets and scripting languages
          such as JavaScript.
        </p>
      </div>
    </li>
    <li>
      <input type="checkbox" id="second" />
      <label for="second">What is CSS? <span class="greater">&gt;</span></label>
      <div class="content">
        <p>
          Cascading Style Sheets is a style sheet language used for describing the presentation of a document written in
          a markup language such as HTML. CSS is a cornerstone technology of the World Wide Web, alongside HTML and
          JavaScript.
        </p>
      </div>
    </li>
    <li>
      <input type="checkbox" id="third" />
      <label for="third">What is JavaScript? <span class="greater">&gt;</span></label>
      <div class="content">
        <p>
          JavaScript, often abbreviated JS, is a programming language that is one of the core technologies of the World
          Wide Web, alongside HTML and CSS. Over 97% of websites use JavaScript on the client side for web page
          behavior, often third-party libraries.
        </p>
      </div>
    </li>
    <li>
      <input type="checkbox" id="fourth" />
      <label for="fourth">What is React? <span class="greater">&gt;</span></label>
      <div class="content">
        <p>
          React is a free and open-source front-end JavaScript library for building user interfaces based on UI
          components. It is maintained by Meta and a community of individual developers and companies.
        </p>
      </div>
    </li>
    <li>
      <input type="checkbox" id="fifth" />
      <label for="fifth">What is Node.js? <span class="greater">&gt;</span></label>
      <div class="content">
        <p>
          Node.js is an open-source, cross-platform, back-end JavaScript runtime environment that runs on the V8 engine
          and executes JavaScript code outside a web browser.
        </p>
      </div>
    </li>
  </ul>
</body>

</html>