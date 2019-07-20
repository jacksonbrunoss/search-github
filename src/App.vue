<template>
  <div id="app">
    <div id="app">
    <Navbar />  
    <div class="container">
      <div class="card card-body">
        <h1>Pesquisar Usuários do Github</h1>
        <p class="lead">Digite um nome para encontrar usuários e repositórios</p>
        <input @keyup="getGithub" type="text" id="search" class="form-control"  required>
      </div>
      <div class="row mt-3" >
        <div class='col-md-4'>
          
        </div>
        <div class="col-md-8">
          
        </div>
      </div>
    </div>
  </div> 
  </div>
</template>

<script>
import Navbar from "@/components/Navbar.vue";
import axios from 'axios'

export default {
  name: 'app',
  data() {
    return {
      github: {
        url: 'https://api.github.com/users',
        client_id: '95d47603732c4da2',
        client_secret: 'e2fdb4c832023f13af1630a55615fe7fff0293e3',
        count: 10,
        sort: 'created: asc'
      },
      user: [],
      repos: []
    }
  },
  components: {
    Navbar
  },
  methods: {
    getGithub(e) {
      const user = e.target.value;
      const { url, client_id, client_secret, count, sort } = this.github
      axios.get(`${url}/${user}?client_id=${client_id}&client_secret=${client_secret}`)
      .then(({data}) => {this.user = data});
    }
  }
}
</script>

<style>
  @import url('https://fonts.googleapis.com/css?family=Ubuntu&display=swap');
  @import url('https://stackpath.bootstrapcdn.com/bootstrap/4.3.1/css/bootstrap.min.css');
  * {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
    font-family: 'Ubuntu', sans-serif;
  }
  
</style>
