<!DOCTYPE html>
<html>
<head>
<title>Swiftdrop Couriers</title>
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<style>
body { font-family: Arial; text-align: center; background:#f4f4f4; }
.container { padding:20px; }
button { padding:12px; margin:10px; border:none; background:#25D366; color:white; border-radius:8px; }
input, select { padding:10px; margin:10px; width:80%; }
.card { background:white; padding:15px; margin:10px; border-radius:10px; }
</style>
</head>

<body>

<div class="container">

<h1>🚚 Swiftdrop Couriers</h1>
<p>King William’s Town & East London</p>

<!-- WhatsApp -->
<a href="https://wa.me/27836153310">
<button>Chat on WhatsApp</button>
</a>

<!-- TRACKING -->
<div class="card">
<h3>Track Parcel</h3>
<input id="trackInput" placeholder="Enter Tracking Number">
<button onclick="trackParcel()">Track</button>
<p id="result"></p>
</div>

<!-- PRICING -->
<div class="card">
<h3>Price Calculator</h3>
<select id="distance">
<option value="50">0-5km (R50)</option>
<option value="80">5-10km (R80)</option>
<option value="120">10-20km (R120)</option>
</select>
<button onclick="calc()">Calculate</button>
<p id="price"></p>
</div>

</div>

<script>

// fake database (you can update manually)
const parcels = {
  "SW123": "Pending",
  "SW124": "Collected",
  "SW125": "In Transit",
  "SW126": "Out for Delivery",
  "SW127": "Delivered"
};

function trackParcel() {
  let code = document.getElementById("trackInput").value;
  let result = parcels[code] || "Tracking number not found";
  document.getElementById("result").innerText = result;
}

function calc() {
  let price = document.getElementById("distance").value;
  document.getElementById("price").innerText = "Price: R" + price;
}

</script>

</body>
</html>
