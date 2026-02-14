<template>
  <header>
    <div class="header-left">
      <img :src="logo" alt="Logo" />
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
      <h2>Our Beloved Products!</h2>

      <div class="products">
        <div
          class="product-card"
          v-for="product in products"
          :key="product.name"
        >
          <div class="product-box">
            <img :src="product.image" :alt="product.name" />
          </div>
          <p>{{ product.name }}</p>
          <p>₱{{ product.price }}</p>
        </div>
      </div>
    </main>
  </div>

  <footer>
    <p>©2026 Crochelves | Contact us: crochelveshelp@gmail.com</p>
  </footer>
</template>

<script setup>
import logo from '@/assets/images/logo.png'


import item1 from '@/assets/images/item1.jpg'
import item2 from '@/assets/images/item2.jpg'
import item3 from '@/assets/images/item3.jpg'
import item4 from '@/assets/images/item4.jpg'

const products = [
  { name: 'Bears', price: 350, image: item1 },
  { name: 'Bags', price: 450, image: item2 },
  { name: 'Sweaters', price: 1000, image: item3 },
  { name: 'Amigurumi', price: 650, image: item4 }
]
</script>
