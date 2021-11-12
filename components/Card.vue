<template>
  <v-card color="#bbc4c9" light class="d-flex flex-column justify-between mb-7" max-height="220" min-height="220" min-width="220"  max-width="220">
    <v-card-title class="justify-center"> {{item.date}} </v-card-title>

    <v-card-subtitle 
      >{{item.name}}</v-card-subtitle
    >

    <v-card-text >{{item.description}}</v-card-text>
  </v-card>
</template>

<script>
import { defineComponent } from '@vue/composition-api'

export default ({
     props : 
         {
             item: {
                 type : Object, default(){
                     return {}
                 }
             }
         }
     
        
    
})
</script>
