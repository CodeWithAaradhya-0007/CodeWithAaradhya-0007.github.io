# CodeWithAaradhya-0007.github.io

<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>CineWave | Movies & Tickets</title>

<style>
:root {
  --bg: #0b1020;
  --panel: #151d30;
  --red: #f04452;
  --text: #ffffff;
  --muted: #aab4c8;
}
* { box-sizing: border-box; }
html { scroll-behavior: smooth; scroll-padding-top: 90px; }
body {
  margin: 0;
  font-family: Arial, sans-serif;
  background: var(--bg);
  color: var(--text);
}
header {
  background: #10182a;
  padding: 16px 6%;
  display: flex;
  align-items: center;
  justify-content: space-between;
  gap: 20px;
  flex-wrap: wrap;
  position: sticky;
  top: 0;
  z-index: 10;
  border-bottom: 1px solid #263149;
}
.logo { font-size: 25px; font-weight: 800; color: var(--red); }
.logo span { color: white; }
nav { display: flex; flex-wrap: wrap; gap: 17px; }
nav a {
  color: #e5eaf3;
  text-decoration: none;
  font-size: 14px;
}
nav a:hover { color: var(--red); }
button, .btn {
  background: var(--red);
  color: white;
  border: none;
  padding: 12px 19px;
  border-radius: 7px;
  font-weight: bold;
  cursor: pointer;
  text-decoration: none;
  display: inline-block;
}
button:hover, .btn:hover { background: #d82e3d; }
section { padding: 55px 6%; }
.hero {
  min-height: 390px;
  display: flex;
  align-items: center;
  background:
    linear-gradient(90deg, #0b1020 10%, rgba(11,16,32,.83) 55%, rgba(11,16,32,.25)),
    url("https://images.unsplash.com/photo-1489599849927-2ee91cede3ba?auto=format&fit=crop&w=1600&q=85")
    center/cover;
}
.hero-content { max-width: 610px; }
.eyebrow {
  color: var(--red);
  text-transform: uppercase;
  letter-spacing: 3px;
  font-size: 12px;
  font-weight: bold;
}
h1 { font-size: clamp(36px, 6vw, 62px); margin: 14px 0; }
h2 { font-size: 29px; margin-top: 0; }
p { line-height: 1.65; color: var(--muted); }
.hero p { max-width: 520px; }
.section-heading {
  display: flex;
  justify-content: space-between;
  align-items: center;
  gap: 12px;
  flex-wrap: wrap;
}
.movie-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(190px, 1fr));
  gap: 22px;
}
.movie-card {
  background: var(--panel);
  border: 1px solid #263149;
  border-radius: 12px;
  overflow: hidden;
  transition: transform .2s;
}
.movie-card:hover { transform: translateY(-5px); }
.movie-card img {
  width: 100%;
  height: 260px;
  object-fit: cover;
  display: block;
  background: #263149;
}
.movie-info { padding: 16px; }
.movie-info h3 { margin: 0 0 8px; }
.movie-info p { margin: 5px 0 14px; font-size: 13px; }
.tag {
  color: #ff9ca4;
  background: #39202d;
  border-radius: 5px;
  padding: 5px 8px;
  font-size: 11px;
}
.panel {
  background: var(--panel);
  padding: 25px;
  border: 1px solid #263149;
  border-radius: 12px;
  margin-top: 20px;
}
.booking-layout {
  display: grid;
  grid-template-columns: minmax(0, 1.3fr) minmax(260px, .7fr);
  gap: 22px;
}
label { display: block; margin: 15px 0 8px; font-size: 14px; }
input, select, textarea {
  width: 100%;
  background: #0b1020;
  color: white;
  border: 1px solid #35425b;
  border-radius: 7px;
  padding: 12px;
  font: inherit;
}
select option { background: #151d30; }
.showtimes { display: flex; flex-wrap: wrap; gap: 9px; }
.showtime {
  background: #202b41;
  border: 1px solid #35425b;
  padding: 10px 14px;
}
.showtime.active { background: var(--red); border-color: var(--red); }
.screen {
  margin: 25px auto;
  width: 85%;
  padding: 9px;
  text-align: center;
  background: #dbeafe;
  color: #172033;
  border-radius: 50% 50% 5px 5px;
  box-shadow: 0 5px 22px #93c5fd55;
  font-size: 12px;
  letter-spacing: 4px;
}
.seat-grid {
  display: grid;
  grid-template-columns: repeat(8, minmax(0, 1fr));
  gap: 8px;
  max-width: 390px;
  margin: auto;
}
.seat {
  padding: 8px 0;
  background: #26364b;
  border: 1px solid #40536c;
  border-radius: 5px;
  font-size: 11px;
}
.seat.selected { background: #22a06b; border-color: #22a06b; }
.seat.occupied { background: #4b5260; color: #a8b0bd; cursor: not-allowed; }
.legend {
  display: flex;
  justify-content: center;
  gap: 15px;
  flex-wrap: wrap;
  margin-top: 20px;
  font-size: 12px;
  color: var(--muted);
}
.dot {
  display: inline-block;
  width: 10px;
  height: 10px;
  border-radius: 3px;
  margin-right: 5px;
  background: #26364b;
}
.dot.green { background: #22a06b; }
.dot.grey { background: #4b5260; }
.summary-line {
  display: flex;
  justify-content: space-between;
  gap: 10px;
  margin: 14px 0;
}
.total {
  border-top: 1px solid #35425b;
  padding-top: 15px;
  font-size: 20px;
  font-weight: bold;
}
.food-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
  gap: 18px;
}
.food-card {
  background: var(--panel);
  border: 1px solid #263149;
  border-radius: 10px;
  padding: 20px;
}
.food-icon { font-size: 42px; }
.food-card h3 { margin-bottom: 5px; }
.food-card .summary-line { margin-bottom: 15px; }
.food-card button { width: 100%; }
.contact-grid {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 25px;
}
footer {
  padding: 30px 6%;
  background: #080c17;
  text-align: center;
  border-top: 1px solid #263149;
}
footer p { font-size: 13px; }
#message {
  padding: 15px;
  background: #123c30;
  border: 1px solid #267b5b;
  border-radius: 8px;
  margin-top: 15px;
  display: none;
  overflow-wrap: anywhere;
}
@media(max-width:700px) {
  header { position: relative; }
  nav { gap: 12px; }
  .booking-layout, .contact-grid { grid-template-columns: 1fr; }
  .hero { min-height: 350px; }
  section { padding: 38px 5%; }
  .movie-card img { height: 230px; }
}
</style>
</head>

<body>

<header>
  <div class="logo">Cine<span>Wave</span> 🎬</div>
  <nav>
    <a href="#home">Home</a>
    <a href="#movies">Movies</a>
    <a href="#booking">Book Tickets</a>
    <a href="#food">Food & Drinks</a>
    <a href="#contact">Contact</a>
  </nav>
</header>

<main>
<section class="hero" id="home">
  <div class="hero-content">
    <div class="eyebrow">Your movie destination</div>
    <h1>Big Screen.<br>Big Feelings.</h1>
    <p>
      Discover your next favourite movie, choose your seats,
      and make every movie night unforgettable with CineWave.
    </p>
    <a class="btn" href="#movies">Explore Movies →</a>
    <a class="btn" href="#booking"
       style="background:transparent;border:1px solid white;margin-left:8px">
       Book Tickets
    </a>
  </div>
</section>

<section id="movies">
  <div class="section-heading">
    <div>
      <div class="eyebrow">Now showing</div>
      <h2>Popular Movies</h2>
    </div>
    <p>Pick a movie for your next outing.</p>
  </div>

  <div class="movie-grid" id="movieGrid"></div>
</section>

<section id="booking">
  <div class="eyebrow">Your movie experience</div>
  <h2>Book Your Tickets</h2>
  <p>Select your movie, showtime and seats to calculate your ticket price.</p>

  <div class="booking-layout">
    <div class="panel">
      <label for="movieSelect">Choose a movie</label>
      <select id="movieSelect"></select>

      <label for="bookingDate">Select date</label>
      <input type="date" id="bookingDate">

      <label>Choose a showtime</label>
      <div class="showtimes" id="showtimes">
        <button class="showtime active" data-time="10:00 AM">10:00 AM</button>
        <button class="showtime" data-time="1:30 PM">1:30 PM</button>
        <button class="showtime" data-time="5:00 PM">5:00 PM</button>
        <button class="showtime" data-time="8:30 PM">8:30 PM</button>
      </div>

      <div class="screen">SCREEN THIS WAY</div>
      <div class="seat-grid" id="seatGrid"></div>

      <div class="legend">
        <span><i class="dot"></i> Available</span>
        <span><i class="dot green"></i> Selected</span>
        <span><i class="dot grey"></i> Occupied</span>
      </div>
      <p style="text-align:center;font-size:12px">
        Select your preferred seats. Each ticket costs ₹180.
      </p>
    </div>

    <div class="panel">
      <h3>Booking Summary</h3>
      <div class="summary-line">
        <span>Movie</span><strong id="summaryMovie">Select a movie</strong>
      </div>
      <div class="summary-line">
        <span>Date</span><strong id="summaryDate">Choose a date</strong>
      </div>
      <div class="summary-line">
        <span>Showtime</span><strong id="summaryTime">10:00 AM</strong>
      </div>
      <div class="summary-line">
        <span>Seats</span><strong id="summarySeats">None</strong>
      </div>
      <div class="summary-line">
        <span>Tickets</span><strong id="summaryCount">0</strong>
      </div>
      <div class="summary-line total">
        <span>Total</span><strong id="summaryTotal">₹0</strong>
      </div>

      <label for="customerName">Your name</label>
      <input id="customerName" type="text" placeholder="Enter your name">

      <label for="customerEmail">Email address</label>
      <input id="customerEmail" type="email" placeholder="Enter your email">

      <button id="confirmBooking" style="width:100%;margin-top:18px">
        Confirm Demo Booking
      </button>

      <div id="message" role="status" aria-live="polite"></div>
      <p style="font-size:12px">
        Demo only. No real tickets are issued and no payment is collected.
      </p>
    </div>
  </div>
</section>

<section id="food">
  <div class="eyebrow">Movie snacks</div>
  <h2>Food & Drinks</h2>
  <p>Make your cinema experience even better with your favourite treats.</p>
  <div class="food-grid" id="foodGrid"></div>

  <div class="panel">
    <div class="summary-line">
      <strong>Your snack order</strong>
      <strong id="foodTotal">₹0</strong>
    </div>
    <div id="foodOrder" style="color:var(--muted)">No snacks selected.</div>
    <button id="clearFood" style="margin-top:15px">Clear Order</button>
  </div>
</section>

<section id="contact">
  <div class="eyebrow">We are here to help</div>
  <h2>Contact Us</h2>
  <div class="contact-grid">
    <div>
      <h3>Let's Connect</h3>
      <p>Have a question or suggestion? Send us a message using the form.</p>
      <p>📧 Email: hello@cinewave.example</p>
      <p>📍 Location: Your City, India</p>
      <p>🎬 CineWave — Your movie, your moment.</p>
    </div>
    <form class="panel" id="contactForm">
      <label for="contactName">Name</label>
      <input id="contactName" required placeholder="Your name">

      <label for="contactEmail">Email</label>
      <input id="contactEmail" type="email" required placeholder="Your email">

      <label for="contactText">Message</label>
      <textarea id="contactText" rows="4" required
        placeholder="Write your message"></textarea>

      <button type="submit" style="margin-top:16px">Send Message</button>
      <p id="contactMessage" role="status"></p>
    </form>
  </div>
</section>
</main>

<footer>
  <div class="logo">Cine<span>Wave</span> 🎬</div>
  <p>Your entertainment, one ticket away.</p>
  <p>© 2026 CineWave | College Project Demonstration</p>
  <p>Independent student demo project. Not affiliated with BookMyShow.</p>
</footer>

<script>
const movies = [
  {
    name: "Interstellar",
    genre: "Sci-Fi • Adventure",
    rating: "9.0/10",
    image: "https://image.tmdb.org/t/p/w500/gEU2QniE6E77NI6lCU6MxlNBvIx.jpg"
  },
  {
    name: "Inception",
    genre: "Sci-Fi • Thriller",
    rating: "8.8/10",
    image: "https://image.tmdb.org/t/p/w500/oYuLEt3zVCKq57qu2F8dT7NIa6f.jpg"
  },
  {
    name: "The Batman",
    genre: "Action • Crime",
    rating: "7.8/10",
    image: "https://image.tmdb.org/t/p/w500/74xTEgt7R36Fpooo50r9T25onhq.jpg"
  },
  {
    name: "Avengers: Endgame",
    genre: "Action • Adventure",
    rating: "8.4/10",
    image: "https://image.tmdb.org/t/p/w500/or06FN3Dka5tukK1e9sl16pB3iy.jpg"
  },
  {
    name: "Dune: Part Two",
    genre: "Sci-Fi • Adventure",
    rating: "8.5/10",
    image: "https://image.tmdb.org/t/p/w500/1pdfLvkbY9ohJlCjQH2CZjjYVvJ.jpg"
  }
];

const foods = [
  { name: "Classic Popcorn", price: 150, icon: "🍿" },
  { name: "Caramel Popcorn", price: 200, icon: "🍿" },
  { name: "Cola", price: 90, icon: "🥤" },
  { name: "Popcorn & Cola Combo", price: 220, icon: "🍿🥤" }
];

const ticketPrice = 180;
const selectedSeats = new Set();
const foodCart = {};
let selectedTime = "10:00 AM";

const movieGrid = document.getElementById("movieGrid");
const movieSelect = document.getElementById("movieSelect");
const seatGrid = document.getElementById("seatGrid");

movies.forEach((movie, index) => {
  movieGrid.insertAdjacentHTML("beforeend", `
    <article class="movie-card">
      <img src="${movie.image}" alt="${movie.name} poster"
           loading="lazy" onerror="this.style.display='none'">
      <div class="movie-info">
        <span class="tag">${movie.rating}</span>
        <h3>${movie.name}</h3>
        <p>${movie.genre}</p>
        <button onclick="bookMovie(${index})">Book Tickets</button>
      </div>
    </article>
  `);

  movieSelect.add(new Option(movie.name, movie.name));
});

function bookMovie(index) {
  movieSelect.value = movies[index].name;
  updateSummary();
  document.getElementById("booking").scrollIntoView({behavior:"smooth"});
}

const today = new Date();
const localDate = [
  today.getFullYear(),
  String(today.getMonth()+1).padStart(2,"0"),
  String(today.getDate()).padStart(2,"0")
].join("-");

const dateInput = document.getElementById("bookingDate");
dateInput.min = localDate;
dateInput.value = localDate;

// Create 40 demo seats.
for (let i = 0; i < 40; i++) {
  const row = String.fromCharCode(65 + Math.floor(i / 8));
  const number = (i % 8) + 1;
  const seatId = row + number;
  const seat = document.createElement("button");

  seat.type = "button";
  seat.className = "seat";
  seat.textContent = seatId;
  seat.setAttribute("aria-label", "Seat " + seatId);

  // Fixed occupied seats for the demonstration.
  if ([3, 12, 21, 30].includes(i)) {
    seat.classList.add("occupied");
    seat.disabled = true;
  }

  seat.addEventListener("click", () => {
    if (selectedSeats.has(seatId)) {
      selectedSeats.delete(seatId);
      seat.classList.remove("selected");
    } else {
      selectedSeats.add(seatId);
      seat.classList.add("selected");
    }
    updateSummary();
  });

  seatGrid.appendChild(seat);
}

document.querySelectorAll(".showtime").forEach(button => {
  button.addEventListener("click", () => {
    document.querySelectorAll(".showtime").forEach(b =>
      b.classList.remove("active")
    );
    button.classList.add("active");
    selectedTime = button.dataset.time;
    updateSummary();
  });
});

movieSelect.addEventListener("change", updateSummary);
dateInput.addEventListener("change", updateSummary);

function updateSummary() {
  document.getElementById("summaryMovie").textContent =
    movieSelect.value;
  document.getElementById("summaryDate").textContent =
    dateInput.value || "Choose a date";
  document.getElementById("summaryTime").textContent = selectedTime;
  document.getElementById("summarySeats").textContent =
    [...selectedSeats].sort().join(", ") || "None";
  document.getElementById("summaryCount").textContent =
    selectedSeats.size;
  document.getElementById("summaryTotal").textContent =
    "₹" + (selectedSeats.size * ticketPrice);

  document.getElementById("message").style.display = "none";
}

document.getElementById("confirmBooking").addEventListener("click", () => {
  const name = document.getElementById("customerName").value.trim();
  const email = document.getElementById("customerEmail").value.trim();
  const message = document.getElementById("message");

  if (!name || !email || !email.includes("@")) {
    alert("Please enter your name and a valid email address.");
    return;
  }

  if (!dateInput.value || dateInput.value < localDate) {
    alert("Please choose today or a future date.");
    return;
  }

  if (selectedSeats.size === 0) {
    alert("Please select at least one seat.");
    return;
  }

  const bookingId = "CW" + Date.now().toString().slice(-8);

  message.innerHTML = `
    <strong>Booking Confirmed! 🎉</strong><br><br>
    Booking ID: ${bookingId}<br>
    Movie: ${movieSelect.value}<br>
    Date: ${dateInput.value}<br>
    Showtime: ${selectedTime}<br>
    Seats: ${[...selectedSeats].sort().join(", ")}<br>
    Total: ₹${selectedSeats.size * ticketPrice}<br><br>
    Thank you, ${escapeHTML(name)}! This is a demo confirmation.
  `;
  message.style.display = "block";
});

function escapeHTML(value) {
  return value.replace(/[&<>"']/g, char => ({
    "&":"&amp;", "<":"&lt;", ">":"&gt;",
    '"':"&quot;", "'":"&#39;"
  })[char]);
}

// Food menu and cart
const foodGrid = document.getElementById("foodGrid");

foods.forEach((food, index) => {
  foodGrid.insertAdjacentHTML("beforeend", `
    <article class="food-card">
      <div class="food-icon">${food.icon}</div>
      <h3>${food.name}</h3>
      <div class="summary-line">
        <span>Price</span><strong>₹${food.price}</strong>
      </div>
      <button onclick="addFood(${index})">Add to Order</button>
    </article>
  `);
});

function addFood(index) {
  const food = foods[index];
  foodCart[index] = (foodCart[index] || 0) + 1;
  updateFood();
}

function updateFood() {
  let total = 0;
  const items = [];

  foods.forEach((food, index) => {
    const quantity = foodCart[index] || 0;
    if (quantity > 0) {
      total += food.price * quantity;
      items.push(`${food.name} × ${quantity}`);
    }
  });

  document.getElementById("foodTotal").textContent = "₹" + total;
  document.getElementById("foodOrder").textContent =
    items.join(" • ") || "No snacks selected.";
}

document.getElementById("clearFood").addEventListener("click", () => {
  Object.keys(foodCart).forEach(key => delete foodCart[key]);
  updateFood();
});

// Demo contact form
document.getElementById("contactForm").addEventListener("submit", event => {
  event.preventDefault();
  document.getElementById("contactMessage").textContent =
    "Thank you! Your demo message has been recorded on this page.";
  document.getElementById("contactForm").reset();
});

updateSummary();
updateFood();
</script>

</body>
</html>
