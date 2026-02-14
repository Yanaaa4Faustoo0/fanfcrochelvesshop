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
      <h2>Transaction Successful</h2>

      <div class="profile-container">
        <p><strong>Date & Time:</strong></p>
        <p>{{ dateTime }}</p>

        <hr />

        <h3>Order Summary</h3>

        <div v-if="cart.length === 0">
          <p>No items found.</p>
        </div>

        <div v-else>
          <div
            v-for="(item, index) in cart"
            :key="index"
            class="profile-item"
          >
            <p>{{ item.name }} x {{ item.qty }}</p>
            <p>₱{{ item.price * item.qty }}</p>
          </div>
        </div>

        <hr />

        <p><strong>Total:</strong> ₱{{ total }}</p>

        <p style="margin-top:20px;">
          Thank you for shopping with Crochelves!
        </p>
      </div>
    </main>
  </div>

  <footer>
    <p>©2026 Crochelves | Contact us: crochelveshelp@gmail.com</p>
  </footer>
</template>

<script setup>
import { ref, computed, onMounted } from 'vue'

const cart = ref([])
const dateTime = ref('')

onMounted(() => {
  const storedCart = JSON.parse(localStorage.getItem('cart'))
  if (storedCart) {
    cart.value = storedCart
  }

  dateTime.value = new Date().toLocaleString()
})

const total = computed(() =>
  cart.value.reduce(
    (sum, item) => sum + item.price * item.qty,
    0
  )
)
</script>
