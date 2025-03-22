<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Shapes</title>
    <style>
        html {
            display: grid;
            place-items: center;
            height: 100vh;
        }

        .container {
            display: flex;
            gap: 20px;
        }

        .circle {
            background: red;
            height: 100px;
            width: 100px;
            border-radius: 50%;
        }

        .square {
            background: blue;
            height: 100px;
            width: 100px;
        }

        .rectangle {
            background: green;
            height: 100px;
            width: 180px;
        }

        .triangle {
            height: 0;
            width: 0;
            border-left: 50px solid transparent;
            border-right: 50px solid transparent;
            border-bottom: 100px maroon solid;
        }
    </style>
</head>

<body>
    <div class="container">
        <div class="circle"></div>
        <div class="square"></div>
        <div class="triangle"></div>
        <div class="rectangle"></div>
    </div>
</body>

</html>