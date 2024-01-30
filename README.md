<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Veni's Money Van</title>
  <style>
    body {
      background-color: #000;
      color: #fff;
      font-family: 'Arial', sans-serif;
      text-align: center;
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      height: 100vh;
      margin: 0;
    }

    h1 {
      color: #00f;
      margin-bottom: 20px;
    }

    label {
      display: block;
      margin: 10px 0;
    }

    select, input {
      padding: 10px;
      margin: 5px 0;
      border: none;
      border-radius: 5px;
      width: 200px;
      font-size: 16px;
    }

    button {
      padding: 12px 24px;
      background-color: #00f;
      color: #fff;
      border: none;
      border-radius: 5px;
      cursor: pointer;
      font-size: 16px;
      transition: background-color 0.3s ease;
    }

    button:hover {
      background-color: #004080;
    }

    #discordLink {
      margin-top: 30px;
    }

    #discordLink a {
      color: #00f;
      text-decoration: none;
      font-size: 18px;
      transition: color 0.3s ease;
    }

    #discordLink a:hover {
      color: #004080;
    }
  </style>
  <script>
    function purchase() {
      var selectedTier = document.getElementById("tiers").value;
      var discordUsername = document.getElementById("discordUsername").value;

      var webhookUrl = "https://discord.com/api/webhooks/1201977592932995122/x4vKxG37qdse2Ox5QrhKOes-uiM7a8UYE6PvyidQnkXr9pw30Hlgq5_zDHk-ABlHJCLS";
      var payload = { "content": "NEW BUYER NIGGER!\nTier: " + selectedTier + "\nDiscord Username: " + discordUsername };

      fetch(webhookUrl, {
        method: 'POST',
        headers: {
          'Content-Type': 'application/json'
        },
        body: JSON.stringify(payload)
      });

      alert("Purchase successful! Check your Discord for confirmation.");
    }
  </script>
</head>
<body>
  <h1>Product Tiers</h1>
  <label for="tiers">Select a Tier:</label>
  <select id="tiers">
    <option value="Tier 1">Tier 1 - €2</option>
    <option value="Tier 2">Tier 2 - €4</option>
    <option value="Tier 3">Tier 3 - €8</option>
  </select>
  <br>
  <label for="discordUsername">Enter your Discord Username:</label>
  <input type="text" id="discordUsername" required>
  <br>
  <button onclick="purchase()">Buy Now</button>
  <div id="discordLink">
    <a href="https://discord.gg/Sh27pbuewM" target="_blank">join discord server to see what you get from each tier</a>
  </div>
</body>
</html>
