<template>
  <header>
    <div class="header-left">
      <img src="@/assets/images/logo.png" alt="Logo" />
      <h1>Crochelves</h1>
    </div>
    <div class="header-right">
      <RouterLink to="/login">Login</RouterLink>
      <RouterLink to="/signup">Sign Up</RouterLink>
    </div>
  </header>

  <div class="container">
    <nav>
      <ul>
        <li><RouterLink to="/profile">Profile</RouterLink></li>
        <li><RouterLink to="/">Home</RouterLink></li>
        <li><RouterLink to="/about">About</RouterLink></li>
        <li><RouterLink to="/contact">Contact</RouterLink></li>
        <li><RouterLink to="/products">Products</RouterLink></li>
        <li><RouterLink to="/cart">Cart</RouterLink></li>
      </ul>
    </nav>

    <main>
      <h2>More of our products!</h2>

   
      <div class="products">
        <div class="product-card">
          <div class="product-box">
            <img src="@/assets/images/item1.jpg" />
          </div>
          <p>Bears</p>
          <p>₱350</p>
        </div>

        <div class="product-card">
          <div class="product-box">
            <img src="@/assets/images/item2.jpg" />
          </div>
          <p>Bags</p>
          <p>₱450</p>
        </div>

        <div class="product-card">
          <div class="product-box">
            <img src="@/assets/images/item3.jpg" />
          </div>
          <p>Sweaters</p>
          <p>₱1000</p>
        </div>

        <div class="product-card">
          <div class="product-box">
            <img src="@/assets/images/item4.jpg" />
          </div>
          <p>Amigurumi</p>
          <p>₱650</p>
        </div>
      </div>

      
      <div class="products">
        <div class="product-card">
          <div class="product-box">
            <img src="@/assets/images/item5.jpg" />
          </div>
          <p>Beanie</p>
          <p>₱350</p>
        </div>

        <div class="product-card">
          <div class="product-box">
            <img src="@/assets/images/item6.jpg" />
          </div>
          <p>Flowers</p>
          <p>₱650</p>
        </div>

        <div class="product-card">
          <div class="product-box">
            <img src="@/assets/images/item7.jpg" />
          </div>
          <p>Wallet</p>
          <p>₱250</p>
        </div>

        <div class="product-card">
          <div class="product-box">
            <img src="@/assets/images/item8.jpg" />
          </div>
          <p>Octopus</p>
          <p>₱650</p>
        </div>
      </div>
    </main>
  </div>

  <footer>
    <p>©2026 Crochelves | Contact us: crochelveshelp@gmail.com</p>
  </footer>
</template>

<script setup>
</script>

