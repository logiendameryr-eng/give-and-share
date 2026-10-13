# give-and-share
A charity website that connects people who want to donate with people who need useful items.

<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Give & Share | Helping Hands</title>

<style>
:root {
  --green: #167d68;
  --dark: #105747;
  --mint: #e8f5ef;
  --cream: #fbf9f2;
  --orange: #f2a65a;
  --text: #25352f;
  --muted: #68766f;
  --white: #ffffff;
}

* { box-sizing: border-box; }

body {
  margin: 0;
  font-family: Arial, sans-serif;
  color: var(--text);
  line-height: 1.7;
  background: var(--white);
}

header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  flex-wrap: wrap;
  gap: 15px;
  padding: 18px 6%;
  background: white;
  box-shadow: 0 2px 12px #0000000b;
  position: sticky;
  top: 0;
  z-index: 10;
}

.logo {
  font-size: 25px;
  font-weight: bold;
  color: var(--dark);
  cursor: pointer;
}

.logo span { color: var(--orange); }

nav {
  display: flex;
  flex-wrap: wrap;
  gap: 5px;
}

nav button {
  background: transparent;
  color: var(--text);
  padding: 9px 12px;
  border-radius: 8px;
  font-weight: bold;
}

nav button:hover,
nav button.active {
  background: var(--mint);
  color: var(--dark);
}

button, input, select, textarea {
  font: inherit;
}

button { cursor: pointer; }

.btn {
  display: inline-block;
  border: 0;
  border-radius: 9px;
  padding: 12px 20px;
  background: var(--green);
  color: white;
  font-weight: bold;
  margin: 5px;
}

.btn:hover { background: var(--dark); }

.btn.light {
  background: white;
  color: var(--dark);
}

.hero {
  display: grid;
  grid-template-columns: 1.1fr 0.9fr;
  gap: 35px;
  align-items: center;
  padding: 65px 7%;
  background: var(--cream);
}

.hero h1 {
  font-size: clamp(36px, 5vw, 57px);
  line-height: 1.15;
  margin: 10px 0;
}

.hero h1 span { color: var(--green); }

.hero p { color: var(--muted); }

.hero img {
  width: 100%;
  height: 350px;
  object-fit: cover;
  border-radius: 22px;
}

.eyebrow {
  color: var(--green);
  font-size: 12px;
  letter-spacing: 2px;
  font-weight: bold;
}

section.content {
  display: none;
  min-height: 65vh;
}

section.content.active { display: block; }

.section {
  padding: 55px 7%;
}

.page-heading {
  text-align: center;
  padding: 45px 7%;
  background: var(--cream);
}

.page-heading h1 {
  font-size: clamp(30px, 4vw, 44px);
  margin: 5px;
}

.page-heading p { color: var(--muted); }

.center { text-align: center; }

.grid {
  display: grid;
  grid-template-columns: repeat(3, minmax(0, 1fr));
  gap: 22px;
}

.card, .item {
  border: 1px solid #e3e9e4;
  border-radius: 15px;
  overflow: hidden;
  background: white;
}

.card { padding: 25px; }

.card .icon { font-size: 35px; }

.card p, .item p { color: var(--muted); }

.item img {
  width: 100%;
  height: 210px;
  object-fit: cover;
  background: var(--mint);
}

.item-info { padding: 18px; }

.tag {
  display: inline-block;
  background: var(--mint);
  color: var(--dark);
  padding: 3px 10px;
  border-radius: 20px;
  font-size: 12px;
  font-weight: bold;
}

input, select, textarea {
  display: block;
  width: 100%;
  padding: 12px;
  margin: 7px 0 17px;
  border: 1px solid #d8e0da;
  border-radius: 8px;
  background: white;
  color: var(--text);
}

label { font-weight: bold; }

form {
  max-width: 650px;
  margin: 25px auto;
  padding: 28px;
  border: 1px solid #e3e9e4;
  border-radius: 15px;
  box-shadow: 0 10px 25px #00000008;
}

form .btn { margin-left: 0; }

.form-message { color: var(--dark); }

.about {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 35px;
  align-items: center;
}

.about img {
  width: 100%;
  border-radius: 18px;
}

.banner {
  padding: 45px 7%;
  text-align: center;
  background: var(--dark);
  color: white;
}

footer {
  padding: 30px;
  text-align: center;
  background: #f4f7f3;
  color: var(--muted);
}

footer strong { color: var(--dark); }

@media(max-width: 750px) {
  header { justify-content: center; }
  nav { justify-content: center; }
  .hero, .about { grid-template-columns: 1fr; }
  .hero { padding: 40px 6%; }
  .hero img { height: 260px; }
  .grid { grid-template-columns: 1fr; }
  .section { padding: 38px 6%; }
  form { padding: 20px; }
}
</style>
</head>

<body>

<header>
  <div class="logo" onclick="showPage('home')">
    Give <span>&</span> Share
  </div>

  <nav>
    <button class="active" data-page="home" onclick="showPage('home')">Home</button>
    <button data-page="browse" onclick="showPage('browse')">Browse Items</button>
    <button data-page="donate" onclick="showPage('donate')">Donate</button>
    <button data-page="about" onclick="showPage('about')">About Us</button>
    <button data-page="contact" onclick="showPage('contact')">Contact</button>
  </nav>
</header>

<main>

<section id="home" class="content active">
  <div class="hero">
    <div>
      <p class="eyebrow">A LITTLE KINDNESS GOES A LONG WAY</p>
      <h1>Give what you can.<br><span>Share what matters.</span></h1>
      <p>Share the things you no longer need and help someone who needs them. Together, we can make our community kinder.</p>
      <button class="btn" onclick="showPage('browse')">Explore Donations</button>
      <button class="btn light" onclick="showPage('donate')">Donate an Item</button>
    </div>
    <img src="https://images.unsplash.com/photo-1532629345422-7515f3d16bb6?auto=format&fit=crop&w=1000&q=85" alt="People helping their community">
  </div>

  <div class="section">
    <div class="center">
      <p class="eyebrow">HOW IT WORKS</p>
      <h2>Small Actions, Big Differences</h2>
      <p>Helping others can be simple.</p>
    </div>
    <div class="grid">
      <article class="card">
        <div class="icon">🎁</div>
        <h3>Give Items</h3>
        <p>Share books, clothes, school supplies, and useful things.</p>
      </article>
      <article class="card">
        <div class="icon">🔎</div>
        <h3>Find What You Need</h3>
        <p>Browse items that other people are happy to share.</p>
      </article>
      <article class="card">
        <div class="icon">🌱</div>
        <h3>Reduce Waste</h3>
        <p>Give useful things another life instead of throwing them away.</p>
      </article>
    </div>
  </div>

  <div class="banner">
    <h2>Your Unused Items Can Make a Difference</h2>
    <p>One small act of kindness can brighten someone's day.</p>
    <button class="btn light" onclick="showPage('donate')">Share Something Today</button>
  </div>
</section>

<section id="browse" class="content">
  <div class="page-heading">
    <p class="eyebrow">DISCOVER AND SHARE</p>
    <h1>Browse Available Items</h1>
    <p>Find something useful in our community.</p>
  </div>

  <div class="section">
    <input id="search" type="search" placeholder="Search for books, clothes, supplies..." oninput="renderItems()">
    <select id="category" onchange="renderItems()">
      <option value="All">All Categories</option>
      <option value="Books">Books</option>
      <option value="Clothes">Clothes</option>
      <option value="School Supplies">School Supplies</option>
      <option value="Other">Other</option>
    </select>

    <p id="count"></p>
    <div id="items" class="grid"></div>
    <p id="empty" class="center" hidden>No items found. Try another search.</p>
    <div class="center">
      <button class="btn" onclick="showPage('donate')">Add a Donation</button>
    </div>
  </div>
</section>

<section id="donate" class="content">
  <div class="page-heading">
    <p class="eyebrow">SHARE SOMETHING GOOD</p>
    <h1>Donate an Item</h1>
    <p>Your unused items might be exactly what someone needs.</p>
  </div>

  <div class="section">
    <form id="donationForm">
      <label for="itemName">Item Name *</label>
      <input id="itemName" required maxlength="80" placeholder="e.g. School Books">

      <label for="itemCategory">Category *</label>
      <select id="itemCategory" required>
        <option value="">Choose a category</option>
        <option>Books</option>
        <option>Clothes</option>
        <option>School Supplies</option>
        <option>Other</option>
      </select>

      <label for="itemDescription">Description *</label>
      <textarea id="itemDescription" rows="4" maxlength="500" required placeholder="Describe your item..."></textarea>

      <label for="itemImage">Photo (optional)</label>
      <input id="itemImage" type="file" accept="image/*">

      <label for="itemContact">Contact Method *</label>
      <input id="itemContact" required maxlength="120" placeholder="A safe way to contact you">
      <p>Do not share your home address or other sensitive personal information.</p>

      <button class="btn" type="submit">Submit Donation</button>
      <p id="donationMessage" class="form-message" role="status"></p>
    </form>
  </div>
</section>

<section id="about" class="content">
  <div class="page-heading">
    <p class="eyebrow">OUR STORY</p>
    <h1>About Give & Share</h1>
    <p>A simple idea with a meaningful purpose.</p>
  </div>

  <div class="section about">
    <div>
      <h2>Sharing Makes a Difference</h2>
      <p>Give & Share is a charitable project designed to connect people who have useful items to give with people who may need them.</p>
      <p>Instead of throwing away books, clothes, and school supplies, people can give these items a new life by sharing them with others.</p>
      <p>Our mission is to encourage kindness, reduce waste, and make helping each other easier.</p>
      <button class="btn" onclick="showPage('donate')">Join Our Mission</button>
    </div>
    <img src="https://images.unsplash.com/photo-1469571486292-0ba58a3f068b?auto=format&fit=crop&w=1000&q=85" alt="Community volunteers">
  </div>

  <div class="section">
    <div class="grid">
      <article class="card">
        <div class="icon">💚</div>
        <h3>Kindness</h3>
        <p>Encouraging people to help one another.</p>
      </article>
      <article class="card">
        <div class="icon">♻️</div>
        <h3>Sustainability</h3>
        <p>Reducing waste by reusing useful items.</p>
      </article>
      <article class="card">
        <div class="icon">🤝</div>
        <h3>Community</h3>
        <p>Building a culture of giving and sharing.</p>
      </article>
    </div>
  </div>
</section>

<section id="contact" class="content">
  <div class="page-heading">
    <p class="eyebrow">LET'S CONNECT</p>
    <h1>Contact Us</h1>
    <p>Questions, suggestions, or ideas? We'd love to hear from you.</p>
  </div>

  <div class="section">
    <form id="contactForm">
      <label for="contactName">Your Name *</label>
      <input id="contactName" required maxlength="80" placeholder="Your name">

      <label for="contactEmail">Your Email *</label>
      <input id="contactEmail" type="email" required maxlength="150" placeholder="you@example.com">

      <label for="contactSubject">Subject *</label>
      <input id="contactSubject" required maxlength="120" placeholder="Message subject">

      <label for="contactMessage">Your Message *</label>
      <textarea id="contactMessage" rows="5" required maxlength="2000" placeholder="Write your message..."></textarea>

      <button class="btn" type="submit">Send Message</button>
      <p id="contactStatus" class="form-message" role="status"></p>
    </form>
    <p class="center">This demonstration form does not send emails yet.</p>
  </div>
</section>

</main>

<footer>
  <strong>Give & Share</strong>
  <p>Give more. Waste less. Help each other.</p>
  <p>© <span id="year"></span> Give & Share</p>
</footer>

<script>
const STORAGE_KEY = "giveShareSingleFileDonations";

const samples = [
  {
    name: "Pre-loved Books",
    category: "Books",
    description: "Books ready for a new reader.",
    image: "https://images.unsplash.com/photo-1544947950-fa07a98d237f?auto=format&fit=crop&w=700&q=80"
  },
  {
    name: "Clothes to Share",
    category: "Clothes",
    description: "Useful clothes looking for a new home.",
    image: "https://images.unsplash.com/photo-1512436991641-6745cdb1723f?auto=format&fit=crop&w=700&q=80"
  },
  {
    name: "Study Supplies",
    category: "School Supplies",
    description: "Stationery another student could use.",
    image: "https://images.unsplash.com/photo-1455390582262-044cdead277a?auto=format&fit=crop&w=700&q=80"
  }
];

function showPage(pageId) {
  document.querySelectorAll("section.content").forEach(section => {
    section.classList.toggle("active", section.id === pageId);
  });

  document.querySelectorAll("nav button").forEach(button => {
    button.classList.toggle("active", button.dataset.page === pageId);
  });

  window.scrollTo({ top: 0, behavior: "smooth" });

  if (pageId === "browse") renderItems();
}

function getDonations() {
  try {
    const result = JSON.parse(localStorage.getItem(STORAGE_KEY) || "[]");
    return Array.isArray(result) ? result : [];
  } catch {
    return [];
  }
}

function renderItems() {
  const container = document.getElementById("items");
  if (!container) return;

  const query = document.getElementById("search").value.trim().toLowerCase();
  const category = document.getElementById("category").value;
  const allItems = [...getDonations(), ...samples];

  const filtered = allItems.filter(item => {
    const matchesCategory = category === "All" || item.category === category;
    const matchesSearch = [item.name, item.description, item.category]
      .some(value => value.toLowerCase().includes(query));

    return matchesCategory && matchesSearch;
  });

  container.replaceChildren();

  filtered.forEach(item => {
    const card = document.createElement("article");
    card.className = "item";

    if (item.image) {
      const img = document.createElement("img");
      img.src = item.image;
      img.alt = item.name;
      img.addEventListener("error", () => img.hidden = true);
      card.appendChild(img);
    }

    const info = document.createElement("div");
    info.className = "item-info";

    const tag = document.createElement("span");
    tag.className = "tag";
    tag.textContent = item.category;

    const title = document.createElement("h3");
    title.textContent = item.name;

    const description = document.createElement("p");
    description.textContent = item.description;

    info.append(tag, title, description);

    if (item.contact) {
      const contact = document.createElement("p");
      contact.textContent = "Contact: " + item.contact;
      info.appendChild(contact);
    } else {
      const sampleLabel = document.createElement("p");
      sampleLabel.textContent = "Sample item";
      info.appendChild(sampleLabel);
    }

    card.appendChild(info);
    container.appendChild(card);
  });

  document.getElementById("count").textContent =
    filtered.length + (filtered.length === 1 ? " item found" : " items found");

  document.getElementById("empty").hidden = filtered.length > 0;
}

document.getElementById("year").textContent = new Date().getFullYear();

document.getElementById("donationForm").addEventListener("submit", event => {
  event.preventDefault();

  const status = document.getElementById("donationMessage");
  const file = document.getElementById("itemImage").files[0];

  if (file && !file.type.startsWith("image/")) {
    status.textContent = "Please choose a valid image.";
    return;
  }

  if (file && file.size > 700 * 1024) {
    status.textContent = "Please choose an image smaller than 700 KB.";
    return;
  }

  function saveDonation(imageData) {
    const donation = {
      name: document.getElementById("itemName").value.trim(),
      category: document.getElementById("itemCategory").value,
      description: document.getElementById("itemDescription").value.trim(),
      contact: document.getElementById("itemContact").value.trim(),
      image: imageData
    };

    try {
      const donations = getDonations();
      donations.unshift(donation);
      localStorage.setItem(STORAGE_KEY, JSON.stringify(donations));

      status.textContent = "Thank you! Your item has been added on this browser.";
      event.target.reset();
    } catch {
      status.textContent = "Could not save this item. Try a smaller photo.";
    }
  }

  if (file) {
    const reader = new FileReader();
    reader.onload = () => saveDonation(reader.result);
    reader.onerror = () => {
      status.textContent = "Could not read the photo. Please try again.";
    };
    reader.readAsDataURL(file);
  } else {
    saveDonation("");
  }
});

document.getElementById("contactForm").addEventListener("submit", event => {
  event.preventDefault();

  document.getElementById("contactStatus").textContent =
    "Thank you for your message! Email sending has not been connected yet.";

  event.target.reset();
});

renderItems();
</script>

</body>
