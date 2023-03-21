<template>
  <img alt="Vue logo" src="./assets/logo.png">
  <OlaMundo />
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import OlaMundo from "../src/components/OlaMundo";

export default defineComponent({
  name: 'App',
  components: {
    OlaMundo,
  }
});
</script>
