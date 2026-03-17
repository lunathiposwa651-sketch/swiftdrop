<script>

// STORAGE (saves on your phone/browser)
let parcels = JSON.parse(localStorage.getItem("parcels")) || {
  "SW123": "Pending",
  "SW124": "Collected"
};

function trackParcel() {
  let code = document.getElementById("trackInput").value;
  let result = parcels[code] || "Tracking number not found";
  document.getElementById("result").innerText = result;
}

// ADMIN ADD PARCEL
function addParcel() {
  let code = document.getElementById("newCode").value;
  let status = document.getElementById("newStatus").value;

  parcels[code] = status;
  localStorage.setItem("parcels", JSON.stringify(parcels));

  alert("Parcel Added!");
}

</script>
<div class="card">
<h3>Admin Panel</h3>

<input id="newCode" placeholder="Tracking Code (e.g SW200)">
<select id="newStatus">
<option>Pending</option>
<option>Collected</option>
<option>In Transit</option>
<option>Out for Delivery</option>
<option>Delivered</option>
</select>

<button onclick="addParcel()">Add Parcel</button>
</div>
<div class="card">
<h3>Book a Delivery</h3>

<input id="name" placeholder="Your Name">
<input id="pickup" placeholder="Pickup Location">
<input id="dropoff" placeholder="Dropoff Location">

<button onclick="sendBooking()">Request Pickup</button>
</div>
function sendBooking() {
  let name = document.getElementById("name").value;
  let pickup = document.getElementById("pickup").value;
  let dropoff = document.getElementById("dropoff").value;

  let message = `New Delivery Request:%0AName: ${name}%0APickup: ${pickup}%0ADropoff: ${dropoff}`;

  window.open(`https://wa.me/27836153310?text=${message}`);
}
