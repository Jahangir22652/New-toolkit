<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Web Toolkit - Login</title>
    <style>
        body {
            font-family: 'Poppins', sans-serif;
            text-align: center;
            background-color: #f4f4f4;
            padding: 50px;
        }

        .hidden {
            display: none;
        }

        .container {
            max-width: 400px;
            margin: auto;
            padding: 20px;
            background: white;
            border-radius: 10px;
            box-shadow: 0px 4px 10px rgba(0, 0, 0, 0.1);
            transition: all 0.3s ease;
        }

        input {
            width: calc(100% - 20px);
            padding: 12px;
            margin: 10px 0;
            border: 1px solid #ccc;
            border-radius: 5px;
            font-size: 16px;
            transition: border-color 0.3s;
            box-sizing: border-box;
            display: block;
            margin-left: auto;
            margin-right: auto;
        }

            input:focus {
                border-color: #28a745;
                outline: none;
            }

        button {
            width: 100%;
            padding: 12px;
            background: #28a745;
            color: white;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            font-size: 18px;
            transition: background 0.3s;
        }

            button:hover {
                background: #218838;
            }

        #error {
            color: red;
            font-size: 14px;
            margin-top: 10px;
        }

        ul {
            list-style-type: none;
            padding: 0;
        }

            ul li {
                background: #e9ecef;
                padding: 10px;
                margin: 5px 0;
                border-radius: 5px;
                transition: background 0.3s;
            }

                ul li:hover {
                    background: #d6d8db;
                }
    </style>
</head>
<body>
    <div id="loginPage" class="container">
        <h2>🔐 Login to Web Toolkit</h2>
        <input type="text" id="username" placeholder="👤 Enter username">
        <input type="password" id="password" placeholder="🔑 Enter password">
        <button onclick="checkLogin()">Login</button>
        <p id="error"></p>
    </div>

    <div id="toolkitPage" class="container hidden">
        <h2>🎉 Welcome, <span id="userDisplay"></span></h2>
        <p>Here are your tools:</p>
        <ul>
            <li><a href="tool1.html" target="_blank">Tool 1</a></li>
            <li><a href="tool2.html" target="_blank">Tool 2</a></li>
            <li><a href="tool1.html" target="_blank">Tool 1</a></li>
            <li><a href="tool1.html" target="_blank">Tool 1</a></li>
            <li><a href="tool1.html" target="_blank">Tool 1</a></li>
            <li><a href="tool1.html" target="_blank">Tool 1</a></li>
            <li><a href="tool1.html" target="_blank">Tool 1</a></li>
            <li><a href="tool3.html" target="_blank">Tool 3</a></li>
            <li><a href="https://abdullah-ebon-delta.vercel.app/" target="_blank">Sim Data base</a></li>
            <li><a href="file-manager.html" target="_blank">File Manager</a></li>
        </ul>
        <button onclick="logout()" style="background: #dc3545;">Logout</button>
    </div>

    <script>
        // Multiple Users List (Each user has a username & password)
        const users = [
            { username: "admin", password: "admin123" },
            { username: "user1", password: "pass1" },
            { username: "user2", password: "pass2" },
            { username: "jahangir", password: "digital2025" },
            { username: "customer", password: "shop123" },
            { username: "1", password: "1" }
        ];

        function checkLogin() {
            var username = document.getElementById("username").value;
            var password = document.getElementById("password").value;

            // Check if entered username & password match any user in the list
            const validUser = users.find(user => user.username === username && user.password === password);

            if (validUser) {
                document.getElementById("loginPage").classList.add("hidden");
                document.getElementById("toolkitPage").classList.remove("hidden");
                document.getElementById("userDisplay").innerText = username;
            } else {
                document.getElementById("error").innerText = "❌ Incorrect username or password!";
            }
        }

        function logout() {
            document.getElementById("toolkitPage").classList.add("hidden");
            document.getElementById("loginPage").classList.remove("hidden");
            document.getElementById("error").innerText = "";
            document.getElementById("username").value = "";
            document.getElementById("password").value = "";
        }
    </script>
</body>
</html>
