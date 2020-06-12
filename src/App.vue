<template>
  <div id="app" class="container">
    <Header />
    <Search @new-data="Data" @new-err="Error"/>
    <Result :data="data" :showTable="showTable" :error="error" @delete-item="deleteItem"/>
    <Footer />
  </div>
</template>

<script>
import Header from './components/Header.vue';
import Search from './components/Search.vue';
import Result from './components/Result.vue';
import Footer from './components/Footer.vue';


export default {

  name: 'App',
  components: {
    Header, Search, Result, Footer,
  },
  data() {
    return {
      data: [],
      error: {},
      showTable: false
    };
  },
  methods: {
    Data(newData, showTableIstrue) {
      this.data.push(newData);
      this.showTable = showTableIstrue;
    },
    Error(err){
      this.error = err;
    },
    deleteItem(id){
      this.data = this.data.filter(item => item.id !== id);
      if(this.data.length == 0 ){
        this.showTable = false;
      }
    }
  },
};
</script>

<style>
@import url(./assets/style.css);
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
