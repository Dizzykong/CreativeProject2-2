

<template>
<div>
  <div class="px-4 py-5 my-5 text-center">
    <h1 class="display-5 fw-bold">All Characters</h1>
  </div>
  <ExpandedDetails :products="products" />
</div>
</template>

<script>
import ExpandedDetails from "../components/ExpandedDetails.vue"
export default {
  name: 'About',
  components: {
    ExpandedDetails
  },
  computed: {
    products() {
      return this.$root.$data.products;
    }
  },
  methods: {
  }
}
</script>