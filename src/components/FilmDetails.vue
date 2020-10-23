<template>
  <article>
      <h1>{{film.title}}</h1>
      <div>
          
    <dl>
        <dt> Release Date:</dt>
        <dd> {{film.release_date}}</dd>
         <dt> Directed by: </dt>
         <dd>{{film.director}}</dd>
         <dt>Rotten Tomatoes Score:</dt>
         <dd>{{film.rt_score}}%</dd>
         </dl>
</div>
    <p>{{film.description}}</p>
    
</article>


</template>

<script>
export default {
    name: 'film-detail',
    props: ['film'],
};
</script>

<style>

</style>