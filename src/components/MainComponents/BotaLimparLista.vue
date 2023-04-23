<template>
  <div>
    <button v-if="ehVisivel" type="button" @click="limparLista">Limpar</button>
  </div>
  
</template>
<script>
export default 
{
  name: "BotaoLimparLista",
  props: ['lista'],
  computed:{
    ehVisivel: function()
    {
      return this.lista.length > 0;
    }
  },
  methods: {
    limparLista: function()
    {
      this.$emit("limparLista");
    }
  }
}
</script>