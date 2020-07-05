<template>
    <div>
      <div>
        <p v-for="product in products" :key="product.descricao">
          <ProductItem :product="product" /> 
        </p>
      </div>
      <br>
      <b>Total:</b> {{quantidade_total}}        
    </div>  
    
</template>

<script>

import ProductItem from './ProductItem'

export default {
    name: 'ProductList',

    props: {
        products: Array
    },

    components: {
        ProductItem
    },

    computed: {
        quantidade_total(){
            return this.products.length;
        }
    }
}
</script>

<style>
#app {

}
</style>
