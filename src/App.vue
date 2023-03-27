<template>
  <v-app>
    <v-main>
      <FormComponent/>
    </v-main>
  </v-app>
</template>

<script lang="ts">
import { defineComponent } from 'vue'
import FormComponent from './components/FormComponent.vue';

export default defineComponent({
  name: 'App',

  components: {
    FormComponent
},

  data () {
    return {
      //
    }
  },
})
</script>
