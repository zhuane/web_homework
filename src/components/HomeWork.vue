<template>
  <div>
    <h1>All Homework</h1> 
    <p>Total Homework = {{list.length}}</p>
    <v-list >
      <v-list-item-group v-model="selectedItem" class="solid ">
        <v-list-item v-for="(item, i) in list" :key="i" class="mb-6">
          <v-list-item-content>
            {{ item }}
          </v-list-item-content>
          <v-btn
              rounded
              color="primary"
              class="justify-end"
              @click="delete_homework(i)"
            >
              Delete
            </v-btn>
        </v-list-item>
      </v-list-item-group>
    </v-list>
    
  </div>
</template>

<script>
import colors from 'vuetify/lib/util/colors'
export default {
  props: ["list"],
  
  new_color: colors.indigo,
  data: () => ({
    items: [],
  }),
  methods: {
    list_homeWork() {
      this.$emit("list_homework", this.items);
    },
    delete_homework(i){
        this.$emit("delete_list",i);
    }
   
  },
};
</script>

<style>
.solid {
  border-style: solid;
  padding: 10px;
  }
</style>