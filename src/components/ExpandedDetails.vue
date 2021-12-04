<template>
<div class="wrapper">
  <div class="products">
    <div class="product" v-for="product in products" :key="product.id">
      <div class="container col-xxl-8 px-4 py-5">
        <div class="row flex-lg-row-reverse align-items-center g-5 py-5">
          <div class="col-10 col-sm-8 col-lg-6">
            <img :src="'/images/products/'+product.image" class="d-block mx-lg-auto img-fluid" alt="Bootstrap Themes" width="700" height="500" loading="lazy">
          </div>
          <div class="col-lg-6">
            <h1 class="display-5 fw-bold lh-1 mb-3">{{product.name}}</h1>
            <p class="lead">{{product.name}} is a {{product.archetype}} from {{product.game}}. {{product.description}} </p>
            <div class="d-grid gap-2 d-md-flex justify-content-md-start">
              <img :src="'/images/products/'+product.gamelogo" class="d-block mx-lg-auto img-fluid" alt="Bootstrap Themes" width="200" height="500" loading="lazy">
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</div>
</template>

<script>
export default {
  name: 'ProductList',
  props: {
    products: Array
  },
  methods: {
    add(product) {
      this.$root.$data.cart.push(product);
    }
  },
}
</script>