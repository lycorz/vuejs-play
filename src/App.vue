<template>
  <div id="app">
    <h1>{{ msg }}</h1>
    <search-table :apiUrl="url" :rows="rows" :columns="columns"/>
  </div>
</template>

<script>
import searchTable from './components/ui-search-table.vue';

export default {
  name: 'app',
  components: {
    'search-table' : searchTable
  },
  data () {
    return {
      msg: 'Welcome to Your Vue.js App',
      url: 'http://localhost:3000/users/',
      rows: 5,
      columns: [{title: 'Id', name: 'id', width: '20px', searchable: true},
                {title: 'Username', name: 'username', width: '200px', searchable: true},
                {title: 'Name', name: 'name', width: '200px',  searchable: true},
                {title: 'Email', name: 'email', width: '300px',  editable: true, searchable: true}]
    }
  }
}
</script>

<style lang="scss">
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

  &:hover {
    text-decoration: underline !important;
  }
}

* {
  -webkit-transition: all 0.33s ease-in-out;
  transition: all 0.33s ease-in-out;
}
</style>
