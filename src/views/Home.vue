<template>
<div>
  <div class="px-4 py-3 text-center">
    <img class="d-block mx-auto mb-4" src="/images/logo.png" alt="" width="600">
    <h1 class="display-5 fw-bold">Who Will You Choose?</h1>
    <div class="col-lg-6 mx-auto">
      <p class="lead mb-4"><i class="fas fa-search"></i><input v-model="searchText" /></p>
    </div>
  </div>
  <ProductList :products="products" />
</div>
</template>



<script>
import ProductList from "../components/ProductList.vue"
export default {
  name: 'Home',
  components: {
    ProductList
  },
    data() {
    return {
      slide: 0,
      sliding: null,
      searchText: '',
    }
  },
  computed: {
    products() {
      return this.$root.$data.products.filter(product => product.name.toLowerCase().search(this.searchText.toLowerCase()) >= 0);
    }
  },
  methods: {
    }
}
</script>

<style scoped>
</style>


