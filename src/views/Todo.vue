<template>
  <div class="">
    <br />
    <v-layout row wrap justify-center class="text-center">
      <v-flex xs6>
        <h1>Homework</h1>
        <br />
        <v-select :items="items" label="All Homework"  outlined></v-select>
        
          <v-text-field
            v-model="message1"
            label="Add Homework"
            clearable
            
          ></v-text-field>
          <v-btn rounded color="primary" @click="saveNickName()"> Add </v-btn>
          
        
        <br /><br />
        <container class="">
      <Homework :list="items" @delete_list="delete_homework"></Homework>
    </container>
      </v-flex>
    </v-layout>
    
    
  </div>
  
</template>

<script>
import Homework from "@/components/HomeWork.vue";

export default {
  components: {
    Homework,
  },
  data: () => ({
    items: ["create Facebook database", "design Google ver.2", "Build system Tesla"],
    
    message1:""
  }),
  methods: {
    saveNickName() {
      this.items.push(this.message1);
    },
    delete_homework(i){
      this.items.splice(i,1)
    }
  },
};
</script>

<style>
.v-select__selection {
  width: 100%;
  justify-content: center;
}
</style>