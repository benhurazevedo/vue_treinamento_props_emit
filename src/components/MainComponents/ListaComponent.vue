<template>
    <table v-if="ehVisivel">
      <thead>
        <tr>
          <th>nome</th>
          <th>idade</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="pessoa in lista" :key="pessoa.codigo">
          <td>{{pessoa.nome}}</td>
          <td>{{pessoa.idade}}</td>
        </tr>
      </tbody> 
    </table>
</template>
<script>
export default 
{
    name: "ListaCompornent",
    props: ["lista"],
    computed:{
      ehVisivel: function(){
        return this.lista.length > 0;
      }
    }
}
</script>
<style scoped>
table, td, th {
    border: 1px solid grey;
}

table {
    border-collapse: collapse;
    font-family: monospace;
    margin-top: 0.5cm;
    margin-bottom: 0.5cm;
}


</style>