<template>
    <h1>Hello World, with VUE.js</h1>
    <p>My first Vue project</p>
</template>

<script lang="ts">

import { defineComponent } from "vue";

export default defineComponent({
    name: "OlaMundo",
});
</script>

<style>
h1{
    color: "blue";
},
p{
    color: "pink";
}

</style>