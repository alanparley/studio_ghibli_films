<template>
  <article>
      <h1>{{film.title}}</h1>
      <div>
          
    <dl class="data_table">
        <div> Release Date: {{film.release_date}}</div>
         <div> Directed by: {{film.director}}</div>
         
         <div>Rotten Tomatoes Score: {{film.rt_score}}%</div>
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

h1 {
    text-align: center;
}

article {
 display: block;
  margin-left: auto;
  margin-right: auto;
  width: 60%;

}

.data_table {
  display: block;
  margin-left: auto;
  margin-right: auto;
  border: solid 3px darkgreen;
  border-radius: 10px;
  /* width: 60%; */
  text-align: center;
  background: #efefef;
  padding: 10px;

}

dl {
    margin: 0;
    }
</style>