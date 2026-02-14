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
      <div class="form-box" style="width:550px;">
        <h2 style="text-align:center;">Sign Up</h2>

        <form @submit.prevent="submitForm">
          <div class="signup-grid">
            <div class="signup-column">
              <label>First Name</label>
              <input type="text" v-model="form.firstName" placeholder="Yana" />

              <label>Email</label>
              <input type="email" v-model="form.email" placeholder="example@email.com" />

              <label>Confirm Password</label>
              <input type="password" v-model="form.confirmPassword" />

              <label>Mobile Number</label>
              <input type="text" v-model="form.mobile" />
            </div>

            <div class="signup-column">
              <label>Last Name</label>
              <input type="text" v-model="form.lastName" placeholder="Fausto" />

              <label>Password</label>
              <input type="password" v-model="form.password" />

              <label>Home Address</label>
              <textarea rows="4" v-model="form.address"></textarea>
            </div>
          </div>

          <button style="margin-top:20px;">Sign Up</button>
        </form>

        <p style="text-align:center;">
          Already have an account?
          <RouterLink to="/login">Login</RouterLink>
        </p>
      </div>
    </main>
  </div>

  <footer>
    <p>©2026 Crochelves | Contact us: crochelveshelp@gmail.com</p>
  </footer>
</template>

<script setup>
import { reactive } from 'vue'

const form = reactive({
  firstName: '',
  lastName: '',
  email: '',
  password: '',
  confirmPassword: '',
  mobile: '',
  address: ''
})

const submitForm = () => {
  console.log('Signup form data:', form)
  alert('Signup submitted!')
}
</script>
