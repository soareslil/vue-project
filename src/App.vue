<template>
  <main class="columns is-gapless is-multiline" :class="{ 'modo-escuro': modoEscuroAtivo }">
    <div class="column is-one-quarter">
      <BarraLateral @aoTemaAlterado="trocarTema"/>
    </div>
    <div class="column is-three-quarter conteudo">
      <FormularioBase @aoSalvarTarefa="salvarTarefa"/>
      <div class="lista">
        <TarefaBase v-for="(tarefa, index) in tarefas" :key="index" :tarefa="tarefa"/>
        <BoxBase v-if="listaEstaVazia">
          Adicione suas tarefas aqui.
        </BoxBase>
      </div>
    </div>
  </main>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import BarraLateral from './components/BarraLateral.vue';
import FormularioBase from './components/FormularioBase.vue';
import TarefaBase from './components/TarefaBase.vue';
import BoxBase from './components/BoxBase.vue';
import ITarefa from './interface/iTarefa';
export default defineComponent({
  name: 'App',
  components: {
    BarraLateral,
    FormularioBase,
    TarefaBase,
    BoxBase
  },
  data () {
    return {
      tarefas: [] as ITarefa[],
      modoEscuroAtivo: false
    }
  },
  computed: {
    listaEstaVazia () : boolean {
      return this.tarefas.length === 0
    }
  },
  methods: {
    salvarTarefa (tarefa: ITarefa) {
      this.tarefas.push(tarefa)
    },
    trocarTema (modoEscuroAtivo: boolean) {
      this.modoEscuroAtivo = modoEscuroAtivo
    }
  }
});
</script>

<style>
.lista {
  padding: 1.25rem;
}
main {
  --bg-primario: #fff;
  --texto-primario: #000;
}
main.modo-escuro {
  --bg-primario: #2b2d42;
  --texto-primario: #ddd;
}
.conteudo {
  background-color: var(--bg-primario);
}
</style>