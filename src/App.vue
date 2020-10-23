<template>
  <film-list :films="films"></film-list>
</template>

<script>
import FilmList from '@/components/FilmList.vue';
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
  }

}
</script>

<style>

</style>