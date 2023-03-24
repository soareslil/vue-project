<template>
  <main class="columns is-gapless is-multiline">
    <div class="column is-one-quarter">
      <BarraLateral />
    </div>
    <div class="column is-three-quarter">
      <FormularioBase @aoSalvarTarefa="salvarTarefa" />
      <div class="lista">
        <TarefaBase v-for="(tarefa, index) in tarefas" :key="index" :tarefa="tarefa" />
      </div>
    </div>
  </main>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import BarraLateral from "./components/BarraLateral.vue";
import FormularioBase from "./components/FormularioBase.vue";
import TarefaBase from "./components/TarefaBase.vue";

import ITarefa from "./interface/iTarefa";

export default defineComponent({
  name: "App",
  components: {
    BarraLateral,
    FormularioBase,
    TarefaBase,
  },
  data() {
    return {
      tarefas: [] as ITarefa[],
    };
  },
  methods: {
    salvarTarefa(tarefa: ITarefa) {
      this.tarefas.push(tarefa);
    },
  },
});
</script>

<style>
.lista {
  padding: 1.24rem;
}
</style>
