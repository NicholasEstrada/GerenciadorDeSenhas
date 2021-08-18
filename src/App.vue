<template>
  <div class="container" id="app">
    <h1>{{ titulo }}</h1>
    <h2>Vai nanar Relen</h2>
    <div class="input-group">
      <input type="text" placeholder="senha" v-model="novaSenha">
      <input type="text" placeholder="user" v-model="novoUser">
      <input type="text" placeholder="url" v-model="novoUrl">
      <span class="input-group-btn">
       <button @click="adcSenha" class="btn btn-success" >Adicionar</button>
      </span>
    </div>

    <div class="conteiner">
      <ul>
        <li v-for="(site, index) in sites" :key="index">
          <label>{{site.user}} </label>
          <label>{{site.senha}} </label>
          <label>{{site.url}} </label>
        </li>
      </ul>
    </div>

    <div class="footer">
      <hr>
      <em>Tipo do seu site</em>
      <input type="text" v-model="titulo">
    </div>
  </div>
</template>

<script>
export default {
  name: 'App',
  data(){
    return{
      titulo: "Minhas Senhas",
      novaSenha: "",
      novoUser: "",
      novoUrl: "",
      sites:[
        {senha: "senha", user: "user", url: "https://google.com"},
      ]
    }
  },
  methods:{
  adcSenha(){
    this.sites.push({
      senha: this.novaSenha,
      user: this.novoUser,
      url: this.novoUrl
    });
    this.novaSenha = "";
    this.novoUser = "";
    this.novoUrl = "";
  }
  }
}
</script>

<style>

</style>
