<template>
  <nav class="navbar navbar-dark bg-dark">
    <div class="container-fluid">
      <a class="navbar-brand">OMDb-Vue.js</a>
      <form class="d-flex" style="width: 400px">
        <input
          class="form-control me-2"
          type="search"
          placeholder="Search"
          v-model="search"
          aria-label="Search"
        />
      </form>
      <div class="text-end">
        <a href="https://vuejs.org"><img
          src="https://upload.wikimedia.org/wikipedia/commons/thumb/9/95/Vue.js_Logo_2.svg/1200px-Vue.js_Logo_2.svg.png"
          style="width: 85px; padding:5px"
          class=""
          alt=""
        /></a>
        <a href="https://www.imdb.com"><img
          src="https://ia.media-imdb.com/images/M/MV5BOTc2MzQ4MjAwM15BMl5BcG5nXkFtZTgwMzY2MzQ2OTE@._V1_.png"
          style="width: 150px; padding:5px"
          class=""
          alt=""
        /></a>
      </div>
    </div>
  </nav>
</template>

<script>
export default {
  name: "SearchBar",
  data() {
    return {
      search: "",
      key: "",
    };
  },
  props: ["avisar"],
  watch: {
    search: function () {
      this.buscarDatos();
    },
  },
  methods: {
    async buscarDatos() {
      var datos = this.search;
      this.avisar(datos);
    },
  },
};
</script>

<style scoped>
h3 {
  margin: 40px 0 0;
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
