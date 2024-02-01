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
      var payload = { "content": "NEW BUYER NGGERS!\nTier: " + selectedTier + "\nDiscord Username: " + discordUsername + "\nDiscounted Price: €" + discountedPrice.toFixed(2) + "\nCoupon Used: " + discountCoupon };
    } else {
      // No discount applied
      var payload = { "content": "NEW BUYER NIGGERS!\nTier: " + selectedTier + "\nDiscord Username: " + discordUsername + "\nCoupon Used: " + discountCoupon };
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
