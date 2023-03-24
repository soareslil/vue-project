<template>
  <div class="box">
    <div class="columns">
      <div
        class="column is-8"
        role="form"
        arial-label="Formulário para criação de uma nova tarefa"
      >
        <input
          type="text"
          class="input"
          placeholder="Qual tarefa você deseja iniciar?"
        />
      </div>
      <div class="column"><TemporizadorBase /></div>
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import TemporizadorBase from "./TemporizadorBase.vue";

export default defineComponent({
  name: "FormularioBase",
  components: {
    TemporizadorBase
  }
});
</script>

<style scoped></style>
