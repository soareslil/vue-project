<template>
  <main class="columns is-gapless is-multiline modo-escuro">
    <div class="column is-one-quarter">
      <BarraLateral />
    </div>
    <div class="column is-three-quarter conteudo">
      <FormularioBase @aoSalvarTarefa="salvarTarefa" />
      <div class="lista">
        <TarefaBase v-for="(tarefa, index) in tarefas" :key="index" :tarefa="tarefa" />
        <BoxBase v-if="listaEstaVazia">
          Salve suas tarefas para organizar seu dia!
        </BoxBase>
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
import BoxBase from './components/BoxBase.vue';

export default defineComponent({
  name: "App",
  components: {
    BarraLateral,
    FormularioBase,
    TarefaBase,
    BoxBase
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
  computed:{
    listaEstaVazia():boolean{
      return this.tarefas.length === 0;
    }
  }
});
</script>

<style>
.lista {
  padding: 1.24rem;
}
main{
  --bg-primario: #fff;
  --texto-primario: #000;
}

main.modo-escuro{
  --bg-primario: #2b2d42;
  --texto-primario: #ddd;
}

.conteudo{
  background-color: var(--bg-primario);
}
</style>
