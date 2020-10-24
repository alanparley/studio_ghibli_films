<template>
<div>
    <li v-on:click="handleClick">
    <p>{{film.title}}</p>
    </li>
   
</div>
</template>

<script>
import { eventBus } from "@/main.js";

export default {
    name: 'film-list-item',
    props: ["film"],
    methods: {
        handleClick: function (event) {
            eventBus.$emit("film-selected", this.film);
        },
        addFavourite: function() {
            eventBus.$emit("favourite-added", this.film);
            }
    },
};
</script>

<style>
li {
   font-family: Arial, Helvetica, sans-serif;
    font-size: 10px;
    list-style-type: none;
    text-align: center;
    background-color: lightgreen;
    box-shadow: 10px 10px 5px rgb(158, 158, 158);
    border: 3px solid black;
    border-radius: 20px;
    padding: 10px;
    min-width:10px;
    max-width:120px;
    margin:1px;
    opacity: 0.6;
    cursor: pointer;
    border: solid black;
    /* width: max-content; */
}

li:hover {
     opacity: 1.0;}

</style>