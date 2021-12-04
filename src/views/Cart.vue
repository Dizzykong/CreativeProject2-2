



<template>
<div>
  <div class="px-4 py-5 my-5 text-center">
    <h1 class="display-5 fw-bold">Your Characters</h1>
    <p v-if="cartIsEmpty">You have not selected any characters yet.</p>
  </div>
  <ExpandedDetails :products="cart" />
</div>
</template>

<script>
import ExpandedDetails from "../components/ExpandedDetails.vue"
export default {
  name: 'Cart',
  components: {
    ExpandedDetails
  },
  computed: {
    cartIsEmpty() {
      if(this.$root.$data.cart.length === 0) {
        return true;
      }
      return false;
    },
    cart() {
      return this.$root.$data.cart;
    }
  },
  methods: {
  }
}
</script>