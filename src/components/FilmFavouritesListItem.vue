<template lang="html">
  <div id="favourite_filmss">
    <h2>Watch List</h2>
    
    <ul>
      <li v-for="favouriteFilm in favouriteFilms">{{favouriteFilm.title}} </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'favourite-films',
  props: ['favouriteFilms']
}
</script>

<style> 

h2 {
    text-align: center;
}

li {
    list-style-type:none;
    display: flex;
    justify-content: center;    
    flex-wrap: wrap;
    padding: 10px;
    margin: 5px;
    overflow-y: auto;
}

</style>