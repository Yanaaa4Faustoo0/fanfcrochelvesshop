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

    <main class="center-content">
      <div class="form-box">
        <h2>Login</h2>

        <form @submit.prevent="login">
          <label>Email</label>
          <input
            type="email"
            placeholder="Enter email"
            v-model="email"
            required
          />

          <label>Password</label>
          <input
            type="password"
            placeholder="Enter password"
            v-model="password"
            required
          />

          <button type="submit">Login</button>
        </form>

        <p style="text-align:center;">
          No account?
          <RouterLink to="/signup">Sign up</RouterLink>
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
import { useRouter } from 'vue-router'

const router = useRouter()

const email = ref('')
const password = ref('')

const login = () => {
  console.log('Email:', email.value)
  console.log('Password:', password.value)


  router.push('/profile')
}
</script>
