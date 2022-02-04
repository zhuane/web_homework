<template>
  <v-app>
    <v-app-bar app color="blue-grey" dark>
      <div class="d-flex align-center">
        <h1>MY_web</h1>
      </div>

      <v-spacer></v-spacer>
      
        
      

      <v-btn to="/" text>
        <span class="mr-2">Home</span>
      </v-btn>
      |
      <v-btn to="/about" text>
        <span class="mr-2">About</span>
      </v-btn>
      |
      <v-btn to="/todo" text>
        <span class="mr-2">Todo</span>
      </v-btn>   
           <v-switch v-model="$vuetify.theme.dark" class="position"></v-switch>
    </v-app-bar>

    <v-main>
     
      <router-view />
    </v-main>
  </v-app>
</template>

<script>
export default {
  name: "App",

  data: () => ({
    //
  }),
};
</script>

<style>
.position{
  position: relative;
  top: 10px;
}

</style>
