<template>
  <div>
    <cabecalho-component></cabecalho-component>
    <botao-consultar :lista=lista @encherLista="funcEncherLista"></botao-consultar>
    <lista-component :lista=lista></lista-component>
    <botao-limpar-lista :lista=lista @limparLista="funcLimparLista"></botao-limpar-lista>
  </div>
  
</template>

<script>
import CabecalhoComponent from './components/MainComponents/CabecalhoComponent.vue';
import BotaoConsultar from './components/MainComponents/BotaoConsultar.vue';
import ListaComponent from './components/MainComponents/ListaComponent.vue';
import BotaoLimparLista from './components/MainComponents/BotaLimparLista.vue';

export default {
  name: 'MainComponent',
  components: {
    CabecalhoComponent,
    BotaoConsultar,
    ListaComponent,
    BotaoLimparLista,
  },
  data: function ()
  {
    return {lista: []}
  },
  methods:{
    funcEncherLista : function (varLista)
    {
      this.lista = varLista;
    },
    funcLimparLista : function()
    {
      this.lista = [];
    }
  }
}
</script>

<style>
</style>
