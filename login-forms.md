<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Login | Codehal</title>
    <!-- Boxicons.com -->
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: Arial, Helvetica, sans-serif;
        }

        body {
            display: flex;
            justify-content: center;
            align-items: center;
            min-height: 100vh;
            background: url('https://images.pexels.com/photos/25252455/pexels-photo-25252455/free-photo-of-thick-clouds-in-black-and-white.jpeg?auto=compress&cs=tinysrgb&w=1260&h=750&dpr=1');
            background-size: cover;
            background-position: center;
            background-attachment: fixed;
            background-repeat: no-repeat;
        }

        .wrapper {
            width: 420px;
            background: transparent;
            border: 2px solid rgba(255, 255, 255, .2);
            backdrop-filter: blur(20px);
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.2);
            color: #fff;
            border-radius: 10px;
            padding: 30px 40px;

            /* position: absolute;
            inset: 0;
            margin: auto; */
        }

        .wrapper h1 {
            font-size: 36px;
            text-align: center;
        }

        .wrapper .input-box {
            position: relative;
            width: 100%;
            height: 50px;
            /* background: salmon; */
            margin: 30px 0;
        }

        .input-box input {
            width: 100%;
            height: 100%;
            background: transparent;
            border: none;
            outline: none;
            border: 2px solid rgba(255, 255, 255, .2);
            border-radius: 40px;
            font-size: 16px;
            color: #fff;
            padding: 20px 45px 20px 20px;
            caret-color: red;
            /* cursor color */
        }

        .input-box input::placeholder {
            color: #fff;
        }

        .input-box i {
            position: absolute;
            right: 20px;
            top: 50%;
            transform: translateY(-50%);
            font-size: 20px;
        }

        .wrapper .remember-forgot {
            display: flex;
            justify-content: space-between;
            font-size: 14px;
            margin: -15px 0 15px;
        }

        .remember-forgot label input {
            accent-color: red;
            margin-right: 3px;
            clip-path: circle(50%);
        }

        .remember-forgot a {
            color: #fff;
            text-decoration: none;
        }

        .remember-forgot a:hover {
            text-decoration: underline;
        }

        .wrapper .btn {
            width: 100%;
            height: 45px;
            background: #fff;
            border: none;
            outline: none;
            border-radius: 40px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
            cursor: pointer;
            font-size: 16px;
            color: #333;
            font-weight: 600;
        }

        .wrapper .register-link {
            font-size: 14px;
            text-align: center;
            margin: 20px 0 15px;
        }

        .register-link p a {
            color: #fff;
            text-decoration: none;
            font-weight: 600;
        }

        .register-link p a:hover {
            text-decoration: underline;

        }
    </style>
</head>

<body>
    <div class="wrapper">
        <form action="">
            <h1>Login</h1>
            <div class="input-box">
                <input type="text" name="" autocomplete="off" placeholder="Username">
                <i class="bx bxs-user"></i>
            </div>
            <div class="input-box">
                <input type="password" name="" autocomplete="off" placeholder="Password">
                <i class="bx bxs-lock-alt"></i>
            </div>
            <div class="remember-forgot">
                <label for="checkbox"><input type="checkbox" name="" id="">Remember Me</label>
                <a href="#">Forgot Password?</a>
            </div>

            <button type="submit" class="btn">Login</button>

            <div class="register-link">
                <p>Don't have an account? <a href="#">Register</a></p>
            </div>
    </div>
    </form>
    </div>
</body>

</html>





<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Animated Login</title>
    <link href="https://unpkg.com/boxicons@2.1.4/css/boxicons.min.css" rel="stylesheet">
    <!-- Boxicons -->

    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: Arial, Helvetica, sans-serif;
        }

        body {
            background: url('https://images.pexels.com/photos/1309766/pexels-photo-1309766.jpeg');
            min-height: 100vh;
            background-size: cover;
            background-position: center;
            background-repeat: no-repeat;
            background-attachment: fixed;
            overflow: hidden;

            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
        }

        .form-box {
            width: 380px;
            height: 480px;
            margin: 6% auto;
            background: rgba(255, 255, 255, .1);
            border: 2px solid rgba(255, 255, 255, .2);
            backdrop-filter: blur(20px);
            padding: 10px;
            border-radius: 2em;
            overflow: hidden;
            box-shadow: 0 0 20px rgba(0, 0, 0, .75);
        }

        #btn {
            top: 0;
            left: 0;
            position: absolute;
            width: 100px;
            height: 100%;
            background: white;
            border-radius: 30px;
            transition: .5s ease-in-out;
        }

        .button-box {
            width: 200px;
            margin: 35px auto;
            position: relative;
            background: rgba(255, 255, 255, .2);
            box-shadow: 0 0 25px 5px #0000003b;
            border-radius: 30px;
        }

        .toggle {
            display: flex;
            justify-content: space-around;
            column-gap: 5px;
        }

        .toggle-btn {
            cursor: pointer;
            background: transparent;
            border: 0;
            outline: none;
            position: relative;
            color: black;
            transition: .3s ease-in-out;
            font-weight: 900;
        }

        .toggle-btn:hover {
            transform: scale(1.05);
        }

        .login {
            padding: 10px 30px;
        }

        .register {
            padding: 10px 20px;
        }

        .social-icons {
            margin: 35px auto;
            color: white;
            cursor: pointer;
            display: flex;
            justify-content: center;
            column-gap: 40px;
            font-size: 35px;
            transition: .2s ease-out;
        }

        .social-icons i:hover {
            transform: scale(1.05);
            filter: drop-shadow(1px 1px 20px rgba(0, 0, 0, .75));
        }

        .input-group {
            margin-top: -20px;
            position: absolute;
            width: 280px;
            transition: .5s ease-in-out;
        }

        .input-field {
            width: 100%;
            padding: 10px 0;
            margin: 10px 0;
            border-left: 0;
            border-top: 0;
            border-right: 0;
            border-bottom: 1px solid #fff;
            outline: none;
            background: transparent;
            color: white;
            caret-color: white;
            font-size: 15px;
        }

        .submit-btn {
            width: 85%;
            padding: 10px 30px;
            cursor: pointer;
            display: block;
            margin: auto;
            color: black;
            background: white;
            border: 0;
            outline: none;
            border-radius: 30px;
            border: 2px solid transparent;
            transition: .3s ease-in-out;
            font-weight: bold;
            font-size: 14px;
        }

        .submit-btn:hover {
            background: transparent;
            color: white;
            border: 2px solid white;
        }

        .check-box {
            margin: 30px 10px 30px 0;
        }

        span {
            font-size: 14px;
            bottom: 68px;
            position: absolute;
            color: white;
        }

        #login {
            left: 450px;
        }

        #register {
            left: 50px;
        }

        input::placeholder {
            color: white;
            font-size: 15px;
        }

        .terms {
            color: white;
        }
    </style>
</head>

<body>
    <div class="form-box">
        <div class="button-box">
            <div id="btn"></div>
            <div class="toggle">
                <button type="button" class="toggle-btn login" onclick="login()">Login</button>
                <button type="button" class="toggle-btn register" onclick="register()">Register</button>
            </div>
        </div>

        <div class="social-icons">
            <i class='bx bxl-linkedin'></i>
            <i class="bx bxl-instagram"></i>
            <i class='bx bxl-github'></i>
        </div>

        <form action="" id="login" class="input-group">
            <input type="text" class="input-field" placeholder="Username">
            <input type="text" class="input-field" placeholder="Enter password">
            <input type="checkbox" class="check-box">
            <span>Remember Password</span>
            <button type="submit" class="submit-btn">Login</button>
        </form>

        <form action="" id="register" class="input-group">
            <input type="text" class="input-field" placeholder="Username">
            <input type="email" class="input-field" placeholder="Email">
            <input type="password" class="input-field" placeholder="Enter password">
            <input type="checkbox" class="check-box">
            <span>I agree to the <a href="#">Terms & Conditions</a></span>
            <button type="submit" class="submit-btn">Register</button>
        </form>
    </div>

    <script>
        const log = document.getElementById("login");
        const reg = document.getElementById("register");
        const button = document.getElementById("btn");
        // const loginBtn = document.querySelector(".login");
        // const registerBtn = document.querySelector(".register");

        function login() {
            log.style.left = "50px";
            reg.style.left = "450px";
            button.style.left = "0";
            // loginBtn.style.fontWeight = "900";
            // registerBtn.style.fontWeight = "normal";
        }
        function register() {
            log.style.left = "-400px";
            reg.style.left = "50px"
            button.style.left = "100px";
            // registerBtn.style.fontWeight = "900";
            // loginBtn.style.fontWeight = "normal";
        }


    </script>
</body>

</html>






<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Neon</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: Arial, Helvetica, sans-serif;
        }

        body {
            display: grid;
            place-items: center;
            height: 100vh;
            background: #000;
        }

        .wrapper {
            width: 400px;
            height: 500px;
            background: #000;
            box-shadow: 0 0 50px #0ef;
            border-radius: 20px;
            padding: 40px;
            overflow: hidden;

            display: flex;
            flex-direction: column;
        }

        .wrapper .form-wrapper {
            width: 100%;
            margin: 38px 0 0 0;
            transition: 1s ease-in-out;
        }

        .wrapper:hover {
            animation: animate 5s linear infinite;
        }

        @keyframes animate {
            100% {
                filter: hue-rotate(360deg);
            }
        }

        .wrapper.active .form-wrapper.sign-in {
            transform: translateY(-500px);
        }

        .wrapper .form-wrapper.sign-up {
            margin: 70px 0 0 0;
        }

        .wrapper.active .form-wrapper.sign-up {
            transform: translateY(-460px);
        }

        h2 {
            font-size: 30px;
            color: #fff;
            text-align: center;
        }

        .input-group {
            position: relative;
            margin: 40px 0;
            border-bottom: 2px solid #fff;
        }

        .input-group label {
            position: absolute;
            top: 50%;
            left: 5px;
            transform: translateY(-50%);
            font-size: 16px;
            color: #fff;
            pointer-events: none;
            transition: .5s ease-in-out;
        }

        .input-group input {
            width: 100%;
            height: 40px;
            font-size: 16px;
            color: #fff;
            padding: 0 5px;
            background: transparent;
            border: none;
            outline: none;
        }

        .input-group input:focus~label,
        .input-group input:valid~label {
            top: -5px;
        }

        .remember {
            margin: -5px 0 15px 5px;
        }

        .remember label {
            color: #fff;
            font-size: 14px;
        }

        .remember label input {
            accent-color: #0ef;
            margin-right: 10px;
        }

        button {
            position: relative;
            width: 100%;
            height: 40px;
            background: #0ef;
            box-shadow: 0 0 10px #0ef;
            font-size: 16px;
            color: #000;
            font-weight: 500;
            cursor: pointer;
            border-radius: 30px;
            border: none;
            outline: none;
        }

        .signup-link {
            font-size: 14px;
            text-align: center;
            margin: 15px 0;
        }

        .signup-link p {
            color: #fff;
        }

        .signup-link p a {
            color: #0ef;
            text-decoration: none;
            font-weight: 500;
        }

        .signup-link p a:hover {
            text-decoration: underline;
        }
    </style>
</head>

<body>

    <div class="wrapper">
        <div class="form-wrapper sign-in">
            <form action="">
                <h2>Login</h2>
                <div class="input-group">
                    <input type="text" required>
                    <label for="">Username</label>
                </div>
                <div class="input-group">
                    <input type="password" required>
                    <label for="">Password</label>
                </div>
                <div class="remember">
                    <label for=""><input type="checkbox">Remember me</label>
                </div>
                <button type="submit">Login</button>
                <div class="signup-link">
                    <p>Don't have an account? <a href="#" class="signUpBtn-link">Sign Up</a></p>
                </div>
            </form>
        </div>

        <div class="form-wrapper sign-up">
            <form action="">
                <h2>Sign Up</h2>
                <div class="input-group">
                    <input type="text" required>
                    <label for="">Username</label>
                </div>
                <div class="input-group">
                    <input type="email" required>
                    <label for="">Email</label>
                </div>
                <div class="input-group">
                    <input type="password" required>
                    <label for="">Password</label>
                </div>
                <div class="remember">
                    <label for=""><input type="checkbox">I agree to the terms & conditions</label>
                </div>
                <button type="submit">Sign Up</button>
                <div class="signup-link">
                    <p>Already have an account? <a href="#" class="signInBtn-link">Sign In</a></p>
                </div>
            </form>
        </div>
    </div>

    <script>
        const signInBtnLink = document.querySelector('.signInBtn-link');
        const signUpBtnLink = document.querySelector('.signUpBtn-link');
        const wrapper = document.querySelector('.wrapper');

        signUpBtnLink.addEventListener('click', () => {
            wrapper.classList.toggle('active');
        });

        signInBtnLink.addEventListener('click', () => {
            wrapper.classList.toggle('active');
        });
    </script>
</body>

</html>