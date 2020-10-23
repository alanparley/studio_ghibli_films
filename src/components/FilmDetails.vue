<template>
  <article>
      <h1>{{film.title}}</h1>
      <h2>{{film.release_date}}</h2>
      <h3>{{film.director}}</h3>
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