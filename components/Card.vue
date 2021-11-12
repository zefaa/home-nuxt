<template>
  <v-card color="#bbc4c9" light class="d-flex flex-column justify-between mb-7" max-height="220" min-width="270"  max-width="270">
    <v-card-title class="justify-center"> {{item.date}} </v-card-title>

    <v-card-subtitle class="text-h6"
      >{{item.name}}</v-card-subtitle
    >

    <v-card-text class="text-h6">{{item.description}}</v-card-text>
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
