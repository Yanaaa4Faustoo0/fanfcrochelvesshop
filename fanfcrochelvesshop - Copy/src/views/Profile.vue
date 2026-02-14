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
      <div class="profile-container">
        <div style="text-align:center; margin-bottom:20px;">
          <img
            src="@/assets/images/download.png"
            style="width:120px; border-radius:50%;"
            alt="Profile Picture"
          />
          <h2>Kylie Lopez</h2>
        </div>

        <div class="profile-item">
          <strong>Email</strong><br />
          kyyli3@example.com
        </div>

        <div class="profile-item">
          <strong>Mobile</strong><br />
          091234567890
        </div>

        <div class="profile-item">
          <strong>Address</strong><br />
          Home Address
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
