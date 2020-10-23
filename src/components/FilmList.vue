<template>
  <ul>
     <film-list-item v-for="(film, index) in films"
         :key="index"
         :film="film"
    ></film-list-item> 
  </ul>
</template>

<script>
import FilmListItem from '@/components/FilmListItem';

export default {
    name: "film-list",
    components : {
        FilmListItem,
    },
    props: ["films"],

};
</script>

<style scoped>
ul {
    list-style-type:none;
    padding: 10px;
    height: 50vh;
    overflow-y: auto;
}
</style>