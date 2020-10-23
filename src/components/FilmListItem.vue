<template>
<li @click="handleClick">
    <span>{{film.title}}</span>
</li>
</template>

<script>
import { eventBus } from "@/main.js"

export default {
    name: 'film-list-item',
    props: ["film"],
    methods: {
        handleClick: function(event) {
            eventBus.$emit("film-selected", this.film)
            

        },
    },

};
</script>

<style scoped>
li {
    display: flex;
    align-items: center;
    margin: 10px;
    padding: 10px;
    cursor: pointer;
    border: solid black;
    width: max-content;
}

</style>