# all4<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1" />
<title>JKS Group Complete Website</title>
<style>
  body {
    font-family: Arial, sans-serif;
    background: #f7fafc;
    margin: 0;
    color: #205081;
  }
  .header {
    display: flex;
    justify-content: space-between;
    align-items: center;
    background: #e3effa;
    padding: 16px 36px;
    font-size: 1.12em;
    font-weight: 600;
    color: #2e6aa7;
    border-bottom: 3px solid #7fd0f0;
  }
  .main-menu {
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    gap: 28px;
    margin: 20px auto 30px;
    width: 90%;
  }
  .menu-box {
    background: #f4fafe;
    border: 2px solid #85bbeb;
    border-radius: 10px;
    min-width: 180px;
    padding: 30px 20px;
    text-align: center;
    font-size: 1.1em;
    font-weight: 600;
    color: #205081;
    box-shadow: 0 2px 8px #dde8f9;
    cursor: pointer;
    transition: background 0.3s ease;
  }
  .menu-box:hover {
    background: #d0e6fb;
  }
  .section-container {
    max-width: 900px;
    margin: 0 auto 40px;
    background: #fff;
    border-radius: 10px;
    box-shadow: 0 3px 14px #d3d7dbcc;
    padding: 20px 30px 30px;
    display: none;
  }
  .section-container.active {
    display: block;
  }
  h2.section-title {
    color: #295bb6;
    text-align: center;
    margin-bottom: 20px;
    font-weight: 700;
    font-size: 1.5em;
  }
  .display-bar {
    margin: 20px auto 25px auto;
    width: 100%;
    text-align: center;
    border: 2px solid #5ba9d5;
    border-radius: 7px;
    background: #f6fdfe;
    padding: 17px 0;
    color: #284067;
    font-size: 1.15em;
    font-weight: 500;
  }
  .sections-grid {
    display: flex;
    justify-content: space-around;
    flex-wrap: wrap;
    gap: 30px;
  }
  .box {
    background: #fcfdff;
    border: 2px solid #6eb7e7;
    border-radius: 11px;
    padding: 25px 20px 20px;
    min-width: 310px;
    max-width: 350px;
    box-shadow: 0 2px 14px #daeefd60;
  }
  .box-title {
    background: #479ede;
    color: #fff;
    font-size: 1.18em;
    font-weight: 600;
    padding: 10px 0;
    border-radius: 8px;
    text-align: center;
    margin-bottom: 18px;
  }
  ul {
    margin-left: 20px;
    padding-left: 15px;
    color: #273965;
    font-size: 1.03em;
  }
  ul li {
    margin-bottom: 6px;
  }
  .back-button {
    display: block;
    margin: 20px auto 0;
    background-color: #003f7d;
    border: none;
    color: white;
    padding: 12px 50px;
    border-radius: 12px;
    font-weight: 600;
    font-size: 1em;
    cursor: pointer;
    box-shadow: 0 2px 8px #5a95d6;
  }
  /* Additional styles for online grocery */
  header.page-header {
    background: #87ceeb;
    color: white;
    font-size: 24px;
    font-weight: bold;
    margin-bottom: 25px;
    border-radius: 10px;
    text-align: center;
  }
  nav.grocery-nav {
    background: #d3ecff;
    display: flex;
    gap: 15px;
    margin-bottom: 25px;
    justify-content: center;
  }
  nav.grocery-nav button {
    background: #3498db;
    border: none;
    color: white;
    padding: 10px 15px;
    cursor: pointer;
    border-radius: 4px;
  }
  nav.grocery-nav button:hover {
    background: #2471a3;
  }
  .grid-images {
    display: grid;
    grid-template-columns: repeat(auto-fill,minmax(150px,1fr));
    gap: 15px;
    margin-top: 15px;
  }
  .grid-images img {
    width: 100%;
    height: 100px;
    object-fit: cover;
    border-radius: 6px;
  }
  .folder-section {
    margin-top: 20px;
    text-align: center;
  }
  .folder-section button {
    padding: 10px 12px;
    border: 1.5px solid #3498db;
    color: #3498db;
    background: white;
    cursor: pointer;
    border-radius: 4px;
    margin: 0 5px;
  }
  .folder-section button.active {
    background: #3498db;
    color: white;
  }
  form {
    margin-top: 20px;
    max-width: 400px;
    margin-left: auto;
    margin-right: auto;
  }
  form label {
    display: block;
    margin-top: 10px;
    font-weight: bold;
  }
  form input, form textarea {
    width: 100%;
    padding: 8px;
    margin-top: 4px;
    border: 1px solid #ccc;
    border-radius: 4px;
  }
  form button {
    margin-top: 15px;
    padding: 10px 15px;
    background: #3498db;
    color: white;
    border: none;
    cursor: pointer;
    border-radius: 4px;
  }
  form button:hover {
    background: #2471a3;
  }
  .error-message {
    color: red;
    display: none;
  }
  footer.page-footer {
    background: #87ceeb;
    color: white;
    text-align: center;
    padding: 8px;
  }
</style>
</head>
<body>

<div class="header">
  <span>Profile</span>
  <span>Add Cash</span>
</div>

<!-- Main navigation menu -->
<div class="main-menu">
  <div class="menu-box" onclick="showSection('dashboard')">Dashboard Home</div>
  <div class="menu-box" onclick="showSection('loansInsurance')">Loans & Insurance</div>
  <div class="menu-box" onclick="showSection('jobService')">Job Consultancy & Services</div>
  <div class="menu-box" onclick="showSection('toursTravel')">Tours & Travels</div>
  <div class="menu-box" onclick="showSection('investmentBusiness')">Investments & Business</div>
  <div class="menu-box" onclick="showSection('courierRide')">Courier & Ride Booking</div>
  <div class="menu-box" onclick="showSection('eventsCatering')">Events & Catering</div>
  <div class="menu-box" onclick="showSection('onlineGrocery')">My E-commerce</div>
</div>

<!-- Dashboard -->
<div id="dashboard" class="section-container active">
  <h2 class="section-title">JKS Group Dashboard</h2>
  <div style="text-align:center; font-size:1.2em; font-weight: 500; color:#316796; padding: 25px 0; border: 2px solid #7fd0f0; border-radius: 8px; max-width:700px; margin:0 auto 20px;">
    Add (or) product display
  </div>
  <div class="sections-grid">
    <div class="box" onclick="showSection('onlineGrocery')">My E-commerce</div>
    <div class="box">My Event & Catering</div>
    <div class="box">My Courier & My Riders</div>
    <div class="box">My Job Consultancy & My Services</div>
    <div class="box">Recharge & Pay Bills</div>
    <div class="box">Tours & My Travels</div>
    <div class="box">Real Estate & Construction</div>
    <div class="box">Investments & Business</div>
    <div class="box">My Franchise & My Micro Money</div>
    <div class="box">My Loans & My Insurance</div>
    <div class="box">My Games & My Entertainment</div>
  </div>
</div>

<!-- Loans & Insurance -->
<div id="loansInsurance" class="section-container">
  <h2 class="section-title">Loans & Insurance</h2>
  <div class="display-bar">add display</div>
  <div class="sections-grid">
    <div class="box">
      <div class="box-title">Loans</div>
      <ul>
        <li>Loan</li><li>Car</li><li>Bike</li><li>House</li>
        <li>Personal</li><li>Business</li><li>etc</li>
      </ul>
    </div>
    <div class="box">
      <div class="box-title">Insurance</div>
      <ul>
        <li>Health</li><li>Mobile</li><li>Car</li><li>Bike</li><li>etc</li>
      </ul>
    </div>
  </div>
</div>

<!-- Other sections placeholders -->
<div id="jobService" class="section-container">
  <h2 class="section-title">Job Consultancy & Services</h2>
  <p>Job & Services content here...</p>
</div>

<div id="toursTravel" class="section-container">
  <h2 class="section-title">Tours & Travels</h2>
  <p>Tours & Travels content here...</p>
</div>

<div id="investmentBusiness" class="section-container">
  <h2 class="section-title">Investments & Business</h2>
  <p>Investments & Business content here...</p>
</div>

<div id="courierRide" class="section-container">
  <h2 class="section-title">Courier & Ride Booking</h2>
  <p>Courier & Ride Booking content here...</p>
</div>

<div id="eventsCatering" class="section-container">
  <h2 class="section-title">Events & Catering</h2>
  <p>Events & Catering content here...</p>
</div>

<!-- Online Grocery & Food Ordering -->
<div id="onlineGrocery" class="section-container">
  <header class="page-header">JKS Online Grocery & Food</header>
  <nav class="grocery-nav">
    <button onclick="showGroceryPage('home')">Home</button>
    <button onclick="showGroceryPage('groceries')">Groceries</button>
    <button onclick="showGroceryPage('food')">Food</button>
    <button onclick="showGroceryPage('pharmacy')">Pharmacy</button>
    <button onclick="showGroceryPage('camera')">Camera</button>
    <button onclick="showGroceryPage('maps')">Google Maps</button>
    <button onclick="showGroceryPage('orders')">Orders</button>
  </nav>
  <main>
    <section id="home" class="page active">
      <h1>Welcome to JKS Online Grocery & Food</h1>
      <p>Explore our categories and place your order via WhatsApp.</p>
      <div class="grid-images">
        <img src="https://source.unsplash.com/150x100/?groceries" alt="Grocery" />
        <img src="https://source.unsplash.com/150x100/?fruits" alt="Fruits" />
        <img src="https://source.unsplash.com/150x100/?vegetables" alt="Vegetables" />
        <img src="https://source.unsplash.com/150x100/?milk" alt="Milk" />
        <img src="https://source.unsplash.com/150x100/?meat" alt="Meat" />
        <img src="https://source.unsplash.com/150x100/?pizza" alt="Pizza" />
        <img src="https://source.unsplash.com/150x100/?ice-cream" alt="Ice Cream" />
        <img src="https://source.unsplash.com/150x100/?tiffin" alt="Tiffin" />
        <img src="https://source.unsplash.com/150x100/?flowers" alt="Flowers" />
        <img src="https://source.unsplash.com/150x100/?medicine" alt="Medicine" />
      </div>
      <div class="folder-section">
        <button onclick="openFolder('groceries')">Groceries</button>
        <button onclick="openFolder('food')">Food</button>
        <button onclick="openFolder('pharmacy')">Pharmacy</button>
      </div>
    </section>
    <section id="groceries" class="page">
      <h2>Groceries</h2>
      <div id="groceries-category-content"></div>
      <button onclick="showGroceryPage('home')">Back to Home</button>
    </section>
    <section id="food" class="page">
      <h2>Food</h2>
      <div id="food-category-content"></div>
      <button onclick="showGroceryPage('home')">Back to Home</button>
    </section>
    <section id="pharmacy" class="page">
      <h2>Pharmacy</h2>
      <div id="pharmacy-content"></div>
      <button onclick="showGroceryPage('home')">Back to Home</button>
    </section>
    <section id="camera" class="page">
      <h2>Camera Page</h2>
      <video id="video" autoplay muted playsinline style="width: 100%; max-width: 400px; border-radius: 6px; background: black;"></video>
      <button onclick="showGroceryPage('home')">Back to Home</button>
    </section>
    <section id="maps" class="page">
      <h2>Google Maps</h2>
      <div id="map" style="width: 100%; height: 400px; border-radius: 6px; margin-top: 15px;"></div>
      <button onclick="showGroceryPage('home')">Back to Home</button>
    </section>
    <section id="orders" class="page">
      <h2>Your Orders</h2>
      <p>No orders yet.</p>
      <button onclick="showGroceryPage('home')">Back to Home</button>
    </section>
  </main>
</div>

<footer class="page-footer">
  Contact us: <a href="tel:+918977143043">+91 89771 43043</a> | WhatsApp: <a href="https://wa.me/918977143043" target="_blank">+91 89771 43043</a>
</footer>

<script>
  function showSection(id) {
    document.querySelectorAll('.section-container').forEach(s => s.classList.remove('active'));
    document.getElementById(id).classList.add('active');
  }

  // Grocery & Food pages functionality
  function showGroceryPage(id) {
    document.querySelectorAll('#onlineGrocery .page').forEach(p => p.classList.remove('active'));
    document.getElementById(id).classList.add('active');
    if(id === 'camera') openCamera();
    if(id === 'maps') initMap();
  }

  function openFolder(folder) {
    showGroceryPage(folder);
    // Simple demo content load
    if(folder === 'groceries') loadGroceriesCategory('milk');
    else if(folder === 'food') loadFoodCategory('biriyani');
    else if(folder === 'pharmacy') loadPharmacy();
  }

  const groceriesData = {
    milk:[
      'https://source.unsplash.com/300x200/?milk,bottle',
      'https://source.unsplash.com/300x200/?milk,carton',
      'https://source.unsplash.com/300x200/?milk,powder'
    ]
  };

  const foodData = {
    biriyani:[
      'https://source.unsplash.com/300x200/?biriyani',
      'https://source.unsplash.com/300x200/?indian,food'
    ]
  };

  const pharmacyData = [
    'https://source.unsplash.com/300x200/?medicine',
    'https://source.unsplash.com/300x200/?pharmacy'
  ];

  function loadGroceriesCategory(category) {
    const container = document.getElementById('groceries-category-content');
    container.innerHTML = '';
    const images = groceriesData[category] || [];
    images.forEach(url => {
      const img = document.createElement('img');
      img.src = url;
      img.style.margin = '5px';
      img.style.width = '150px';
      container.appendChild(img);
    });
  }

  function loadFoodCategory(category) {
    const container = document.getElementById('food-category-content');
    container.innerHTML = '';
    const images = foodData[category] || [];
    images.forEach(url => {
      const img = document.createElement('img');
      img.src = url;
      img.style.margin = '5px';
      img.style.width = '150px';
      container.appendChild(img);
    });
  }

  function loadPharmacy() {
    const container = document.getElementById('pharmacy-content');
    container.innerHTML = '';
    pharmacyData.forEach(url => {
      const img = document.createElement('img');
      img.src = url;
      img.style.margin = '5px';
      img.style.width = '150px';
      container.appendChild(img);
    });
  }

  function openCamera() {
    const video = document.getElementById('video');
    if (navigator.mediaDevices && navigator.mediaDevices.getUserMedia) {
      navigator.mediaDevices.getUserMedia({ video: true })
        .then(stream => {
          video.srcObject = stream;
          video.play();
        })
        .catch(() => alert('Camera access denied or unavailable.'));
    } else {
      alert('Camera not supported.');
    }
  }

  function initMap() {
    if (window.google && google.maps) {
      const mapDiv = document.getElementById('map');
      if (!mapDiv.mapInitialized) {
         const map = new google.maps.Map(mapDiv, {
           center: { lat: 20.5937, lng: 78.9629 },
           zoom: 5
         });
         mapDiv.mapInitialized = true;
      }
    } else {
      const scriptId = 'googleMapsScript';
      if (!document.getElementById(scriptId)) {
        const script = document.createElement('script');
        script.src = 'https://maps.googleapis.com/maps/api/js?key=YOUR_API_KEY&callback=initMap';
        script.id = scriptId;
        script.async = true;
        script.defer = true;
        document.head.appendChild(script);
      }
    }
  }

  // Start with dashboard visible
  showSection('dashboard');
</script>

</body>
</html>
