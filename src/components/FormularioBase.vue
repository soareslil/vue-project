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
          v-model="descricao"
        />
      </div>
      <div class="column"><TemporizadorBase @aoTemporizadorFinalizado="finalizarTarefa" /></div>
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
  },
  data(){
    return{
      descricao: ''
    }
  },
  methods: {
    finalizarTarefa(tempoDecorrido: number): void{
      console.log('tempo', tempoDecorrido );
      console.log('tarefa', this.descricao);
      this.descricao = '';
    }
  }
});
</script>

<style scoped></style>
