<template>
<main>
  <film-list :films="films"></film-list>
  <film-detail :film="selectedFilm"></film-detail>
  </main>
</template>

<script>
import FilmList from '@/components/FilmList.vue';
import FilmDetail from '@/components/FilmDetails';
import { eventBus } from '@/main.js';


export default {
  data() {
    return {
      films: [],
      selectedFilm: null,
    };
  },


  mounted() {
     fetch('https://ghibliapi.herokuapp.com/films')
    .then(res => res.json())
    .then(films => this.films = films);

    eventBus.$on("film-selected", (film) => {
      this.selectedFilm = film;
    });

  },
  components: {
    FilmList,
    FilmDetail,
  }

}
</script>

<style>

</style>