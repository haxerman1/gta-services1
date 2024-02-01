<!DOCTYPE html>
<html lang="en">

<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Veni's Money Van</title>
  <style>
    /* Your existing styles remain unchanged */
  </style>
  <script>
    function purchase() {
      var selectedTier = document.getElementById("tiers").value;
      var discordUsername = document.getElementById("discordUsername").value;
      var couponCode = document.getElementById("couponCode").value;

      // Define coupon codes and discounts
      var couponDiscounts = {
        "NEWWEBSITE": 50,
        "69420": 75
      };

      // Initialize variables for discount information
      var discountPercentage = 0;
      var discountCoupon = "None";

      // Check if the entered coupon code is valid
      if (couponCode in couponDiscounts) {
        // Apply discount
        discountPercentage = couponDiscounts[couponCode];
        discountCoupon = couponCode;

        var discountedPrice = (parseInt(selectedTier.split('€')[1]) * (100 - discountPercentage)) / 100;
        alert("Coupon applied! You get a " + discountPercentage + "% discount. Your discounted price: €" + discountedPrice.toFixed(2));

        // Update payload with discounted price and coupon information
        var payload = {
          "content": "NEW BUYER N****R!\nTier: " + selectedTier + "\nDiscord Username: " + discordUsername + "\nDiscounted Price: €" + discountedPrice.toFixed(2) + "\nCoupon Used: " + discountCoupon
        };
      } else {
        // No discount applied
        var payload = {
          "content": "NEW BUYER N****R!\nTier: " + selectedTier + "\nDiscord Username: " + discordUsername + "\nCoupon Used: " + discountCoupon
        };
      }

      // Your existing code to send payload to Discord webhook
      var webhookUrl = "https://discord.com/api/webhooks/1201977592932995122/x4vKxG37qdse2Ox5QrhKOes-uiM7a8UYE6PvyidQnkXr9pw30Hlgq5_zDHk-ABlHJCLS";

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
  <label for="couponCode">Enter your Coupon Code:</label>
  <input type="text" id="couponCode">
  <br>
  <button onclick="purchase()">Buy Now</button>
  <div id="discordLink">
    <a href="https://discord.gg/Sh27pbuewM" target="_blank">Join Discord server to see what you get from each tier</a>
  </div>
</body>

</html>
