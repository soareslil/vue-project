<template>
    <div class="box has-text-weight-bold">
        <div class="columns">
            <div class="column is-7">
               {{tarefa.descricao}}
            </div>
            <div class="column">
                <CronometroBase :tempoEmSegundos="tarefa.duracaoEmSegundos" />
            </div>
        </div>
    </div>
</template>

<script lang="ts">
import ITarefa from '@/interface/iTarefa';
import { defineComponent, PropType } from 'vue';
import  CronometroBase from './CronometroBase.vue'
export default defineComponent({
    name: 'TarefaBase',
    components:{
        CronometroBase
    },
    props:{
        tarefa:{
            type: Object as PropType<ITarefa>,
            required: true
        }
    }
});
</script>

<style scoped>
.box{
    background-color: #faf0ca;
}
</style>

