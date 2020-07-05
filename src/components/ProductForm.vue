<template>
  <div>
  
    <form @submit="onFormSubmit">
      <p>
        <label style="padding-right:23px ;"><b>Descrição:</b></label>
        <input type="text" v-model="descricao">
        <br>
        {{descricaoError}}
      </p>
      <p>
        <label style="padding-right:10px ;"><b>Quantidade:</b></label>
        <input type="text" v-model="quantidade">
        <br>
        {{quantidadeError}}
      </p>
      <p>
        <label style="padding-right:54px ;"><b>Valor:</b></label>
        <input type="text" v-model="valor">
      </p>
      <button type="submit">Enviar</button>
    </form>
    
 
  </div>
</template>

<script>

export default {

  data() {
    return {
      descricao: "",
      quantidade: 0,
      valor: 0.00,
      isNameLimitExceeded: false,
      descricaoError: "",
      quantidadeError: ""
    };
  },

  props: {
      addProduct: Function
  },

  watch: {
    descricao() {
      if (this.descricao.length > 15) {
        this.isNameLimitExceeded = true;
        this.descricaoError = "Descrição não pode conter mais que 15 caracteres.";
      } else {
        this.isNameLimitExceeded = false;
        this.descricaoError = "";
      }
    },

    quantidade() {
      if (this.quantidade > 5) {
        this.isNameLimitExceeded = true;
        this.quantidadeError = "A quantidade não pode ser maior que 5.";
      } else {
        this.isNameLimitExceeded = false;
        this.quantidadeError = "";
      }
    }
  },

  methods: {
    onFormSubmit(e) {
      e.preventDefault();

      if (this.isNameLimitExceeded) {
        return;
      }

      this.addProduct({
        descricao: this.descricao,
        quantidade: this.quantidade,
        valor: this.valor
      });
    }
  }
};

</script>

<style>
#app {

}
</style>
