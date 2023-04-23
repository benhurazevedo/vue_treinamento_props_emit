<template>
    <div v-if="exibirBotao">
      <button type="button" @click="preencherLista">Consultar</button>
    </div>
  
</template>
<script>
export default 
{
  name: "BotaoConsultar",
  props: [
    'lista'
  ],
  computed:
  {
    exibirBotao: function()
    {
      return this.lista.length == 0;
    }
  },
  methods: 
  {
    preencherLista: async function ()
    {
      /*var lista = [
        {nome: "benhur", idade: 19, codigo: 1},
        {nome: "alan", idade: 18, codigo: 2},
      ];*/
      var dados = await fetch("http://localhost:3000/lista", {
        method: "GET"
      })
        .then(function(response){
          return response.json();
        })
        .then(function(data){
          return data;
        })
        .catch(function(erro){
          alert(erro);
        });
      this.$emit("encherLista", dados);
    }
  }
}
</script>