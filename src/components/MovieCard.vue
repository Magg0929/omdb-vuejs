<template>
  <div class="table-bg">
    <div class="container">
      <table class="table table-bordered border-dark">
        <thead>
          <tr>
            <th scope="col" class="width=100px">#IMDb ID</th>
            <th scope="col">Title</th>
            <th scope="col">Year</th>
            <th scope="col">Type</th>
            <th scope="col">Poster</th>
          </tr>
        </thead>
        <tbody>
          <tr v-for="movie in movies" :key="movie.imdbID">
            <th scope="row">{{ movie.imdbID }}</th>
            <td>{{ movie.Title }}</td>
            <td>{{ movie.Year }}</td>
            <td>{{ movie.Type }}</td>
            <td>
              <img
                :src="
                  movie.Poster !== 'N/A'
                    ? movie.Poster
                    : 'https://st4.depositphotos.com/14953852/22772/v/600/depositphotos_227725020-stock-illustration-image-available-icon-flat-vector.jpg'
                "
                style="max-width: 15em"
                alt="Poster"
              />
            </td>
          </tr>
        </tbody>
      </table>
    </div>
  </div>
</template>

<script>
import axios from "axios";

export default {
  name: "MovieCard",
  props: {
    movieHijo: String,
  },
  data() {
    return {
      movies: [],
    };
  },
  watch: {
    movieHijo: function () {
      this.getMovies();
    },
  },
  methods: {
    getMovies: function () {
      axios
        .get(
          "http://www.omdbapi.com/?s=" +
            this.movieHijo +
            "&type=movie&page=1&apikey=ea1f23ec"
        )
        .then((result) => {
          this.movies = result.data.Search;
        });
    },
  },
  created() {},
};
</script>

<style scoped>
    #MovieCard{
        background: gray;
    }
</style>
