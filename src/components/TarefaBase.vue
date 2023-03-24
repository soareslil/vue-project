<template>
    <BoxBase>
        <div class="columns">
            <div class="column is-7">
               {{tarefa.descricao || 'Tarefa sem descrição'}}
            </div>
            <div class="column">
                <CronometroBase :tempoEmSegundos="tarefa.duracaoEmSegundos" />
            </div>
        </div>
    </BoxBase>
</template>

<script lang="ts">
import ITarefa from '@/interface/iTarefa';
import { defineComponent, PropType } from 'vue';
import  CronometroBase from './CronometroBase.vue'
import BoxBase from './BoxBase.vue'
export default defineComponent({
    name: 'TarefaBase',
    components:{
        CronometroBase,
        BoxBase
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

</style>

