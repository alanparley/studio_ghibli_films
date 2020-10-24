<template>
<main>
  
  <film-list :films="films"></film-list>
  <film-detail :film="selectedFilm"></film-detail>
   <button class="displaybutton"
      v-if="!favouriteFilms.includes(selectedFilm)"
      v-on:click="addToFavourites"
    >
      Add Film To Watch-List
    </button>
    <favourite-films
      :favouriteFilms="favouriteFilms"
    ></favourite-films>
   
  </main>
</template>

<script>
import FilmList from '@/components/FilmList.vue';
import FilmDetail from '@/components/FilmDetails';
import { eventBus } from '@/main.js';
import FilmFavouritesListItem from './components/FilmFavouritesListItem.vue';


export default {
  data() {
    return {
      films: [],
      selectedFilm: null,
      favouriteFilms: []
    };
  },
  methods: {
  addToFavourites: function(){
        this.favouriteFilms.push(this.selectedFilm)
      },
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
    'favourite-films': FilmFavouritesListItem
  }

}
</script>

<style>
main {
    font-family: Arial, Helvetica, sans-serif;
    font-size: 14px;
    align-content: center;
    display: block;
    margin-left: auto;
    margin-right: auto
}

.displaybutton {
  display: block;
  margin-left: auto;
  margin-right: auto;
}
</style>