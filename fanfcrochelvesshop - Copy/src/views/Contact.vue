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
      <h2 style="text-align: center;">Contact Us</h2>

      <div class="form-box">
        <form @submit.prevent="sendMessage">
          <input
            type="text"
            placeholder="Name"
            v-model="name"
            required
          />

          <textarea
            placeholder="Message"
            rows="5"
            v-model="message"
            required
          ></textarea>

          <button type="submit">Send</button>
        </form>

        <p v-if="successMessage" class="success">
          {{ successMessage }}
        </p>
      </div>
    </main>
  </div>

  <footer>
    <p>©2026 Crochelves | Contact us: crochelveshelp@gmail.com</p>
  </footer>
</template>

<script setup>
import { ref } from 'vue'
import logo from '@/assets/images/logo.png'

// Form state
const name = ref('')
const message = ref('')
const successMessage = ref('')


const sendMessage = () => {

  console.log('Message sent:', {
    name: name.value,
    message: message.value
  })

  successMessage.value = 'Your message has been sent!'


  name.value = ''
  message.value = ''
}
</script>
