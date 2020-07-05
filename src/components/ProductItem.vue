<template>
  <p>
    <b>Descrição:</b> {{product.descricao}}
    <br>
    <b>Quantidade:</b> {{product.quantidade}}
    <br>
    <b>Valor:</b> {{product.valor}}
  </p>
</template>

<script>
export default {
    name: 'ProductList',
    props: {
        product: Object
    },
}
</script>

<style>
#app {
}
</style>
