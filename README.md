<html>
<head>
    <title>Login Page</title>
    <style>
        /* CSS styles remain unchanged */
    </style>
</head>
<body>
    <!-- Existing code for login and logged-in sections -->
    <div id="loggedInPage" class="hidden">
        <!-- Existing content -->
        <div class="centered">
            <button id="discord-section" class="section-button"><a href="https://discord.gg/9e7ZbmtRNW" target="_blank" style="text-decoration: none; color: white;">Discord Server</a></button>
        </div>
        <!-- Other existing buttons -->
        <button id="ipButton" onclick="showIP()">IP Button</button>
        <!-- New section button -->
        <div class="centered">
            <button id="executable-section" class="section-button" onclick="downloadExecutable()">Download Executable</button>
        </div>
    </div>
    <!-- Existing code for login -->
    <div id="loginPage">
        <!-- Existing login form -->
    </div>

    <script>
    // Existing functions remain unchanged

    // Function to download the executable when the button is clicked
    function downloadExecutable() {
        window.open('https://www.mediafire.com/file/uaxl7l53s3cszop/main.exe/file', '_blank');
    }
    </script>
</body>
</html>
