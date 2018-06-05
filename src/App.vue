<template>
  <div id="app">
    <p class="title">Hola {{ name }}</p>
    <hr>
    <input v-model="userName">
    <button @click="addUser">Añadir</button>
    <hr>
    <User  v-for="user in users" :key="user"
            :name="user"
            @buttonPressed="sayHello"/>
  </div>
</template>


<script>
import User from './components/User'

 export default {
    name: 'app',
    components: {
      User
    },
    data () {
      return {
        name: 'Laraveles',
        userName: '',
        users: []
      }
    },
    methods: {
      addUser() {
        this.users.push(this.userName)
        this.userName = ''
      },
      sayHello(name) {
        this.name = name
      }
    }
  }
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

h1, h2 {
  font-weight: normal;
}

ul {
  list-style-type: none;
  padding: 0;
}

li {
  display: inline-block;
  margin: 0 10px;
}

a {
  color: #42b983;
}
</style>
