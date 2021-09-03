<template>
    <div>
      <SearchBar :avisar="onResultados" />
      <MovieCard :movieHijo="movieHijo" />
      <Footer/>
    </div>

</template>

<script>
import Footer from './components/Footer.vue';
import MovieCard from './components/MovieCard.vue';
import SearchBar from './components/SearchBar.vue';

export default {
  
  name: 'App',
  components: {
    MovieCard,
    SearchBar,
    Footer,
    
  },
  data() {
    return {
      movieHijo:"",
    }
  },
  methods: {
    onResultados:function(datos){
        this.movieHijo=datos;
    }
  },
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
</style>
