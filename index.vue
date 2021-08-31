<template>
  <div>
    <Navbar />
    <center class="center">
      <table border="1">
        <tr>
          <th>Nome</th>
          <th>Aniversario</th>
          <th>Idade</th>
        </tr>
        <tr v-for="usuario in usuarios" :key="usuario.id">
          <td>{{ usuario.nome }}</td>
          <td> {{ usuario.aniversario }}</td>
          <td> {{ usuario.idade }}</td>
        </tr>
      </table>
    </center>
  </div>
</template>
<script>
export default {
  async asyncData ({ app }) {
    // eslint-disable-next-line no-console
    const usuarios = await app.$axios.$get('http://localhost:5000')
    return {
      usuarios: usuarios.usuario
    }
  },
  data () {
    return {
      usuarios: []
    }
  }
}
</script>
<style>
.botom {border: 2px solid transparent;border-radius: 0px 0px 0px 10px;color: white;background-color: #212529;}
.topo {border: 2px solid transparent;border-radius: 10px 0px 0px 0px;color: white;background-color:#212529;}
.meio {border: 2px solid transparent;border-radius: 0px 0px 0px 0px;color: white;background-color: #212529;}

.top2 {border-left: 1px solid #212529; border-top: 1px solid #212529; text-align: center;}
.botom2 {border-left: 1px solid #212529; border-bottom: 1px solid #212529; text-align: center;}
.meio2 {border-left: 1px solid #212529; text-align: center;}

.botom3 {border: 2px solid transparent;border-radius: 0px 0px 10px 0px;color: white;background-color:#212529;}
.topo3 {border: 2px solid transparent;border-radius: 0px 10px 0px 0px;color: white;background-color:#212529;}
.meio3 {border: 2px solid transparent;border-radius: 0px 0px 0px 0px;color: white;background-color: #212529;}

td {
  padding: 20px;
}

.center {
  margin-top: 10%;
}

</style>
