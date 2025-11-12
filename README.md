<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>ShineCraft Jewelry</title>
  <style>
    body {
      margin: 0;
      font-family: Arial, sans-serif;
      background: #f9f9f9;
      color: #333;
    }
    .site-header {
      background: #fff;
      box-shadow: 0 2px 4px rgba(0,0,0,0.1);
      padding: 10px 20px;
      display: flex;
      align-items: center;
      justify-content: space-between;
    }
    .logo {
      font-size: 1.5em;
      font-weight: bold;
    }
    .main-nav ul {
      list-style: none;
      padding: 0;
      margin: 0;
      display: flex;
      gap: 15px;
    }
    .main-nav a {
      text-decoration: none;
      color: #333;
    }
    .hero {
      background: url('https://via.placeholder.com/1200x400') center/cover no-repeat;
      color: #fff;
      text-align: center;
      padding: 60px 20px;
    }
    .featured-products .product-list {
      display: flex;
      gap: 20px;
      padding: 20px;
      flex-wrap: wrap;
    }
    .product-item {
      background: #fff;
      padding: 15px;
      text-align: center;
      border: 1px solid #e0e0e0;
      flex: 1 1 calc(33% - 40px);
      box-sizing: border-box;
    }
    .product-item img {
      max-width: 100%;
      height: auto;
    }
    .site-footer {
      text-align: center;
      padding: 15px;
      background: #fff;
      margin-top: 40px;
      font-size: 0.9em;
    }
    .cart-section, .checkout-section {
      padding: 20px;
    }
    .cart-table {
      width: 100%;
      border-collapse: collapse;
      margin-bottom: 20px;
    }
    .cart-table th, .cart-table td {
      border: 1px solid #ddd;
      padding: 10px;
    }
    .cart-total {
      text-align: right;
      margin-top: 20px;
    }
    .checkout-form .form-group {
      margin-bottom: 15px;
    }
    .checkout-form label {
      display: block;
      margin-bottom: 5px;
    }
    .checkout-form input, .checkout-form textarea, .checkout-form select {
      width: 100%;
      padding: 8px;
      border: 1px solid #ccc;
      box-sizing: border-box;
    }
    .checkout-form button {
      padding: 10px 20px;
      background: #007bff;
      color: #fff;
      border: none;
      cursor: pointer;
    }
    .hidden {
      display: none;
    }
  </style>
</head>
<body>

  <header class="site-header">
    <div class="logo">ShineCraft Jewelry</div>
    <nav class="main-nav">
      <ul>
        <li><a href="#" data-page="home">Home</a></li>
        <li><a href="#" data-page="shop">Shop</a></li>
        <li><a href="#" data-page="cart">Cart</a></li>
        <li><a href="#" data-page="checkout">Checkout</a></li>
      </ul>
    </nav>
  </header>

  <!-- Home Page -->
  <section class="hero" id="page-home">
    <h1>Handcrafted Jewelry with a Story</h1>
    <p>Unique, artisan-made pieces for you.</p>
  </section>
  <section class="featured-products" id="page-home-featured">
    <h2 style="text-align:center;">Featured Products</h2>
    <div class="product-list">
      <div class="product-item">
        <img src="https://via.placeholder.com/300x300" alt="Silver necklace">
        <h3>Silver Artisan Necklace</h3>
        <p>KSh 3,200</p>
        <button data-add="Silver Artisan Necklace">Add to Cart</button>
      </div>
      <div class="product-item">
        <img src="https://via.placeholder.com/300x300" alt="Leather bracelet">
        <h3>Leather Wrap Bracelet</h3>
        <p>KSh 1,800</p>
        <button data-add="Leather Wrap Bracelet">Add to Cart</button>
      </div>
      <div class="product-item">
        <img src="https://via.placeholder.com/300x300" alt="Beaded earrings">
        <h3>Beaded Earrings</h3>
        <p>KSh 1,200</p>
        <button data-add="Beaded Earrings">Add to Cart</button>
      </div>
    </div>
  </section>

  <!-- Shop Page -->
  <section class="product-listing hidden" id="page-shop">
    <h2 style="text-align:center;">Shop All</h2>
    <div class="product-list">
      <div class="product-item">
        <img src="https://via.placeholder.com/300x300" alt="Minimal silver ring">
        <h3>Minimal Silver Ring</h3>
        <p>KSh 900</p>
        <button data-add="Minimal Silver Ring">Add to Cart</button>
      </div>
      <div class="product-item">
        <img src="https://via.placeholder.com/300x300" alt="Boho pendant necklace">
        <h3>Boho Pendant Necklace</h3>
        <p>KSh 2,500</p>
        <button data-add="Boho Pendant Necklace">Add to Cart</button>
      </div>
      <!-- Add more as needed -->
    </div>
  </section>

  <!-- Cart Page -->
  <section class="cart-section hidden" id="page-cart">
    <h2>Your Cart</h2>
    <table class="cart-table">
      <thead>
        <tr>
          <th>Product</th>
          <th>Qty</th>
          <th>Price</th>
          <th>Total</th>
        </tr>
      </thead>
      <tbody id="cart-tbody">
        <!-- dynamically inserted rows -->
      </tbody>
    </table>
    <div class="cart-total" id="cart-total">Subtotal: KSh 0</div>
    <button id="checkout-btn">Proceed to Checkout</button>
  </section>

  <!-- Checkout Page -->
  <section class="checkout-section hidden" id="page-checkout">
    <h2>Checkout</h2>
    <form class="checkout-form" id="checkout-form">
      <div class="form-group">
        <label for="name">Full Name</label>
        <input type="text" id="name" name="name" required>
      </div>
      <div class="form-group">
        <label for="phone">Phone / Mobile</label>
        <input type="tel" id="phone" name="phone" required>
      </div>
      <div class="form-group">
        <label for="address">Delivery Address</label>
        <textarea id="address" name="address" required></textarea>
      </div>
      <div class="form-group">
        <label for="payment">Payment Method</label>
        <select id="payment" name="payment" required>
          <option value="mpesa">M-Pesa</option>
          <option value="paypal">PayPal</option>
          <option value="card">Credit/Debit Card</option>
        </select>
      </div>
      <button type="submit">Place Order</button>
    </form>
  </section>

  <footer class="site-footer">
    <p>© 2025 ShineCraft Jewelry. All rights reserved.</p>
  </footer>

  <script>
    // Simple page navigation
    const navLinks = document.querySelectorAll('.main-nav a');
    const pages = {
      home: document.getElementById('page-home'),
      shop: document.getElementById('page-shop'),
      cart: document.getElementById('page-cart'),
      checkout: document.getElementById('page-checkout')
    };

    navLinks.forEach(link => {
      link.addEventListener('click', e => {
        e.preventDefault();
        const page = link.getAttribute('data-page');
        for (let p in pages) {
          pages[p].classList.add('hidden');
        }
        pages[page].classList.remove('hidden');
      });
    });

    // Simple cart functionality
    let cart = [];

    document.querySelectorAll('button[data-add]').forEach(btn => {
      btn.addEventListener('click', () => {
        const product = btn.getAttribute('data-add');
        cart.push({ name: product, qty: 1, price: getPrice(product) });
        updateCartUI();
        alert(product + " added to cart!");
      });
    });

    function getPrice(productName) {
      const priceMap = {
        "Silver Artisan Necklace": 3200,
        "Leather Wrap Bracelet": 1800,
        "Beaded Earrings": 1200,
        "Minimal Silver Ring": 900,
        "Boho Pendant Necklace": 2500
      };
      return priceMap[productName] || 0;
    }

    function updateCartUI() {
      const tbody = document.getElementById('cart-tbody');
      tbody.innerHTML = '';
      let subtotal = 0;
      cart.forEach((item, idx) => {
        subtotal += item.price * item.qty;
        const tr = document.createElement('tr');
        tr.innerHTML = `
          <td>${item.name}</td>
          <td><input type="number" value="${item.qty}" min="1" data-idx="${idx}" class="qty-input"></td>
          <td>KSh ${item.price}</td>
          <td>KSh ${item.price * item.qty}</td>
        `;
        tbody.appendChild(tr);
      });
      document.getElementById('cart-total').innerText = 'Subtotal: KSh ' + subtotal;
      document.querySelectorAll('.qty-input').forEach(input => {
        input.addEventListener('change', e => {
          const idx = e.target.getAttribute('data-idx');
          const newQty = parseInt(e.target.value);
          if (newQty >= 1) {
            cart[idx].qty = newQty;
            updateCartUI();
          }
        });
      });
    }

    document.getElementById('checkout-btn').addEventListener('click', () => {
      navLinks.forEach(link => {
        if (link.getAttribute('data-page') === 'checkout') {
          link.click();
        }
      });
    });

    document.getElementById('checkout-form').addEventListener('submit', e => {
      e.preventDefault();
      alert('Order placed! Thank you for shopping with us.');
      // Reset cart
      cart = [];
      updateCartUI();
      // Return to home
      navLinks.forEach(link => {
        if (link.getAttribute('data-page') === 'home') {
          link.click();
        }
      });
    });
  </script>

</body>
</html>
