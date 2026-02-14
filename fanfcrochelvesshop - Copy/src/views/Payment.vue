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
      <h2>Payment & Delivery</h2>

      <div class="profile-container">
        <p><strong>Select Payment Method:</strong></p>

        <label>
          <input type="radio" value="Cash on Delivery" v-model="paymentMethod" />
          Cash on Delivery
        </label><br />

        <label>
          <input type="radio" value="GCash" v-model="paymentMethod" />
          GCash
        </label><br />

        <label>
          <input type="radio" value="Credit Card" v-model="paymentMethod" />
          Credit Card
        </label>

        <br /><br />

        <p><strong>Select Delivery Option:</strong></p>

        <label>
          <input type="radio" value="Standard Delivery" v-model="deliveryOption" />
          Standard Delivery
        </label><br />

        <label>
          <input type="radio" value="Express Delivery" v-model="deliveryOption" />
          Express Delivery
        </label><br />

        <label>
          <input type="radio" value="Store Pickup" v-model="deliveryOption" />
          Store Pickup
        </label>

        <br /><br />

        <button @click="confirmOrder">
          Confirm Order
        </button>
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

const paymentMethod = ref('')
const deliveryOption = ref('')

const confirmOrder = () => {
  if (!paymentMethod.value || !deliveryOption.value) {
    alert('Please select a payment method and delivery option.')
    return
  }

  localStorage.setItem('paymentMethod', paymentMethod.value)
  localStorage.setItem('deliveryOption', deliveryOption.value)

  router.push('/transaction')
}
</script>
