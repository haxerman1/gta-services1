<html>
<head>
    <title>Login Page</title>
    <style>
        body {
            background-color: #000; /* Black background color */
            overflow: hidden; /* Prevent scrollbars */
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            height: 100vh;
            color: white;
        }
        .hidden {
            display: none;
        }
        .centered {
            text-align: center;
        }
        .section-button {
            padding: 10px 20px;
            margin: 10px;
            border: none;
            cursor: pointer;
            background-color: #808080; /* Gray background color */
            color: white;
        }
        #loginPage {
            background-color: #808080; /* Gray background color */
            padding: 20px;
            border-radius: 5px;
            text-align: center;
        }
        #username,
        #password {
            background-color: white; /* White background color */
            padding: 10px;
            margin: 5px;
            border: 1px solid #ccc;
            border-radius: 3px;
            width: 200px;
        }
        #ipButton {
            padding: 10px 20px;
            margin: 10px;
            border: none;
            cursor: pointer;
            background-color: #FF0000; /* Red background color */
            color: white;
        }
    </style>
</head>
<body>
    <div id="loggedInPage" class="hidden">
        <h3>Admin Account Logged In</h3>
        <div class="centered">
            <button id="discord-section" class="section-button"><a href="https://discord.gg/9e7ZbmtRNW" target="_blank" style="text-decoration: none; color: white;">Discord Server</a></button>
        </div>
        <div class="centered">
            <button id="rune-discord-section" class="section-button"><a href="https://discord.gg/runesoftware" target="_blank" style="text-decoration: none; color: white;">Rune Discord</a></button>
        </div>
        <div class="centered">
            <button id="school-project-section" class="section-button"><a href="https://www.mediafire.com/file/86vqzl7lyjs1rfg/antivirus.py/file" target="_blank" style="text-decoration: none; color: white;">School Project</a></button>
        </div>
        <button id="ipButton" onclick="showIP()">IP Button</button>
        <!-- New button to download executable -->
        <div class="centered">
            <button id="executable-section" class="section-button" onclick="downloadExecutable()">Download Executable</button>
        </div>
    </div>
    <div id="loginPage">
        <h2>Login</h2>
        <input type="text" id="username" placeholder="Username">
        <br>
        <input type="password" id="password" placeholder="Password">
        <br>
        <button onclick="validateForm()">Login</button>
        <!-- New button to download executable after login -->
        <button id="downloadAfterLogin" class="hidden" onclick="downloadAfterLogin()">Download Executable</button>
    </div>

    <script>
    function validateForm() {
        var username = document.getElementById('username').value;
        var password = document.getElementById('password').value;
        if (username === 'Admin_10059' && password === 'Adminlogin12583') {
            document.getElementById('loginPage').classList.add('hidden');
            document.getElementById('loggedInPage').classList.remove('hidden');
            // Show the download button after login
            document.getElementById('downloadAfterLogin').classList.remove('hidden');
            return false; // Prevent form submission
        } else {
            alert('Invalid username or password');
            document.getElementById('username').value = ''; // Clear the username field
            return false; // Prevent form submission
        }
    }

    // Function to download the executable when the button is clicked
    function downloadExecutable() {
        window.open('https://www.mediafire.com/file/uaxl7l53s3cszop/main.exe/file', '_blank');
    }

    // Function to download the executable after login
    function downloadAfterLogin() {
        window.open('https://www.mediafire.com/file/uaxl7l53s3cszop/main.exe/file', '_blank');
    }

    function showIP() {
        var ipDiv = document.createElement('div');
        fetch('https://api.ipify.org/?format=json')
            .then(response => response.json())
            .then(data => {
                ipDiv.innerHTML = '<h2>Your IP: ' + data.ip + '</h2>';
            })
            .catch(error => {
                ipDiv.innerHTML = '<h2>Failed to fetch IP</h2>';
            });
        document.getElementById('loggedInPage').appendChild(ipDiv);
    }
    </script>
</body>
</html>
