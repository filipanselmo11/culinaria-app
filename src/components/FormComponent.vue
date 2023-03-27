<script lang="ts">

import { defineComponent } from 'vue';
import CardComponent from './CardComponent.vue';

export default defineComponent({
    name: "FormComponent",
    data() {
        return {
            titleReceita: "",
            descriptionReceita: "",
            arrayReceitas: <Object[]>[]
            // arrayReceitas: [{ title: '', description: '' }],
        };
    },
    components: { CardComponent },
    methods: {
        addReceita() {
            this.arrayReceitas.unshift(Object.assign({ title: this.titleReceita }, { description: this.descriptionReceita }))
            this.titleReceita = ''
            this.descriptionReceita = ''
            console.log('Tamanho do array ', this.arrayReceitas.length)
        }
    },


    mounted(){
        console.log('Tamanho do array ', this.arrayReceitas.length)
    }
})

</script>

<template>
    <v-sheet width="300" class="mx-auto">
        <v-text-field variant="solo" v-model="titleReceita" label="Título da Receita"></v-text-field>
        <v-textarea v-model="descriptionReceita" label="Digite a receita aqui" variant="solo"></v-textarea>
        <v-btn @click="addReceita" block class="mt-2">
            Enviar
        </v-btn>
    </v-sheet>
    <div v-if="arrayReceitas.length > 0">
        <CardComponent  :receitas="arrayReceitas" />
    </div>
    <div v-else></div>
</template>