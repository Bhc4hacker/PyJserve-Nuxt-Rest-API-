<template>
  <div>
    <h1>Nomes</h1>
    <ul>
      <li v-for="mountain in mountains" :key="mountain.nome">Nome: {{ mountain.nome }}</li>
    </ul>
    <ul>
      <li v-for="mountain in mountains" :key="mountain.aniversario">Aniversario: {{ mountain.aniversario }}</li>
    </ul>
    <ul>
      <li v-for="mountain in mountains" :key="mountain.idade">Idade: {{ mountain.idade }}</li>
    </ul>
  </div>
</template>
<script>
export default {
  async asyncData ({ $http }) {
    const mountains = await $http.$get('http://localhost:5000/usuario/')
    return { mountains }
  }
}
</script>
<style>
ul li {
  display: inline;
}
li {
  margin: 10px 10px;
}
</style>
