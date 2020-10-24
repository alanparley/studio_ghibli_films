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

<style>
ul {
    list-style-type:none;
    display: flex;
    justify-content: center;    
    flex-wrap: wrap;
    margin: 10px;
    overflow-y: auto;
}
</style>