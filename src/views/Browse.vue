<template>
<div>
  <div class="px-4 py-5 text-center">
    <h1 class="display-5 fw-bold">Characters by game</h1>
      <p class="pure-menu-item"><a @click="select('Mario')" href="#" class="pure-menu-link">Mario</a></p>
      <p class="pure-menu-item"><a @click="select('Zelda')" href="#" class="pure-menu-link">Zelda</a></p>
      <p class="pure-menu-item"><a @click="select('Earthbound')" href="#" class="pure-menu-link">Earthbound</a></p>
      <p class="pure-menu-item"><a @click="select('Minecraft')" href="#" class="pure-menu-link">Minecraft</a></p>
  </div>
  <ProductList :products="products" />
</div>
</template>

<script>
import ProductList from "../components/ProductList.vue"
export default {
  name: 'Browse',
  components: {
    ProductList
  },
  data() {
    return {
      game: '',
    }
  },
  computed: {
    products() {
      return this.$root.$data.products.filter(product => product.game === this.game);
    }
  },
  methods: {
    select(game) {
      this.game = game;
    }
  }
}
</script>
