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
      <h2>My Cart</h2>

      <div class="profile-container">
        <div v-if="cartItems.length === 0">
          <p>Your cart is empty.</p>
        </div>

        <div
          v-for="(item, index) in cartItems"
          :key="index"
          class="profile-item"
        >
          <p><strong>{{ item.name }}</strong></p>
          <p>Price: ₱{{ item.price }}</p>

          <input
            type="number"
            min="1"
            :value="item.qty"
            @input="updateQty(index, $event.target.value)"
          />

          <p>Subtotal: ₱{{ item.price * item.qty }}</p>

          <button @click="removeItem(index)">Remove</button>
        </div>

        <hr />

        <p><strong>Total:</strong> ₱{{ total }}</p>

        <button
          v-if="cartItems.length > 0"
          @click="goToPayment"
        >
          Proceed to Payment
        </button>
      </div>
    </main>
  </div>

  <footer>
    <p>©2026 Crochelves | Contact us: crochelveshelp@gmail.com</p>
  </footer>
</template>

<script setup>
import { ref, computed, watch } from 'vue'
import { useRouter } from 'vue-router'
import logo from '@/assets/images/logo.png'

const router = useRouter()


const cartItems = ref(
  JSON.parse(localStorage.getItem('cart')) || [
    { name: 'Bears', price: 350, qty: 1 },
    { name: 'Bags', price: 450, qty: 2 }
  ]
)


const total = computed(() =>
  cartItems.value.reduce(
    (sum, item) => sum + item.price * item.qty,
    0
  )
)


const updateQty = (index, value) => {
  cartItems.value[index].qty = Number(value)
}


const removeItem = (index) => {
  cartItems.value.splice(index, 1)
}


watch(
  cartItems,
  (newCart) => {
    localStorage.setItem('cart', JSON.stringify(newCart))
  },
  { deep: true }
)


const goToPayment = () => {
  router.push('/payment')
}
</script>
