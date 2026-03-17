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
