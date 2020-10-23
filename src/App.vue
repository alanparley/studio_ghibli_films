<template>
  <film-list :films="films"></film-list>
</template>

<script>
import FilmList from '@/components/FilmList.vue';


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
  },
  components: {
    FilmList,
  }

}
</script>

<style>

</style>