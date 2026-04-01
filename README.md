<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Casa Vanta</title>
  <link rel="stylesheet" href="style.css"/>
</head>
<body>

<header>
  <h1>Casa Vanta</h1>
  <nav>
    <a href="#">Home</a>
    <a href="#shop">Shop</a>
    <a href="#about">About</a>
    <a href="#contact">Contact</a>
  </nav>
</header>

<section class="hero">
  <h2>Elevate Your Space</h2>
  <p>Modern home accessories curated for comfort & style.</p>
  <button onclick="scrollToShop()">Shop Now</button>
</section>

<section id="shop" class="products">
  <h2>Featured Products</h2>
  <div class="product-grid">

    <div class="product">
      <img src="https://via.placeholder.com/200"/>
      <h3>Minimal Vase</h3>
      <p>$29.99</p>
      <button onclick="addToCart('Minimal Vase')">Add to Cart</button>
    </div>

    <div class="product">
      <img src="https://via.placeholder.com/200"/>
      <h3>Luxury Throw Pillow</h3>
      <p>$39.99</p>
      <button onclick="addToCart('Throw Pillow')">Add to Cart</button>
    </div>

    <div class="product">
      <img src="https://via.placeholder.com/200"/>
      <h3>Ceramic Bowl Set</h3>
      <p>$49.99</p>
      <button onclick="addToCart('Bowl Set')">Add to Cart</button>
    </div>

  </div>
</section>

<section id="about">
  <h2>About Casa Vanta</h2>
  <p>We bring modern, minimal, and elegant home accessories to elevate your living space.</p>
</section>

<section id="contact">
  <h2>Contact</h2>
  <p>Email: your@email.com</p>
</section>

<div id="cart">
  <h3>Cart</h3>
  <ul id="cart-items"></ul>
</div>

<script src="script.js"></script>
</body>
</html>

body {
  margin: 0;
  font-family: Arial, sans-serif;
  background: #f5f5f0;
  color: #111;
}

header {
  display: flex;
  justify-content: space-between;
  padding: 20px;
  background: #000;
  color: #fff;
}

nav a {
  margin: 0 10px;
  color: white;
  text-decoration: none;
}

.hero {
  text-align: center;
  padding: 100px 20px;
  background: #eaeaea;
}

.hero button {
  padding: 10px 20px;
  background: black;
  color: white;
  border: none;
}

.products {
  padding: 50px;
  text-align: center;
}

.product-grid {
  display: flex;
  gap: 20px;
  justify-content: center;
}

.product {
  background: white;
  padding: 20px;
  border-radius: 10px;
}

.product img {
  width: 100%;
}

button {
  cursor: pointer;
}

let cart = [];

function addToCart(item) {
  cart.push(item);
  renderCart();
}

function renderCart() {
  const list = document.getElementById("cart-items");
  list.innerHTML = "";
  cart.forEach(i => {
    const li = document.createElement("li");
    li.textContent = i;
    list.appendChild(li);
  });
}

function scrollToShop() {
  document.getElementById("shop").scrollIntoView({
    behavior: "smooth"
  });
}
