<template>
  <div>  
    <ProductForm :addProduct="addProduct" />
    <br>
    <br>
    <ProductsList :products="products" />
  </div>
</template>

<script>

import ProductForm from './components/ProductForm.vue'
import ProductsList from './components/ProductsList.vue'

export default {
  data() {
    return {
      products: [
        {
          descricao: "Máscara",
          quantidade: 1,
          valor: 500,
        },
        {
          descricao: "Nadadeira",
          quantidade: 1,
          valor: 700,
        }
      ]
    };
  },
  components: {
    ProductsList,
    ProductForm
  }, 
  methods: {
    addProduct(product){
      this.products = this.products.concat({
        descricao: product.descricao,
        quantidade: product.quantidade,
        valor: product.valor
      })
    }
  }  
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
