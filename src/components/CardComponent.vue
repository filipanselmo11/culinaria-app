<script lang="ts">

import { defineComponent } from 'vue';

export default defineComponent({
    name: 'CardComponent',
    props: {
        receitas: {
            type: Array,
        },
    },
})
</script>

<template>
    <v-row class="justify-center">
        <v-col v-for="item, index in receitas" :key="index" cols="12">
            <v-card width="400">
                <template v-slot:title>
                    {{ item.title }}
                </template>
                <template v-slot:text>
                    {{ item.description }}
                </template>
            </v-card>
        </v-col>
    </v-row>
</template>