<template>
    <div>
    <v-card class="v-card-container size">
      <template v-slot:title >
        <slot name="card-title">Default Title</slot>
      </template>
  
      <template v-slot:subtitle>
        <slot name="card-subtitle">Default Subtitle</slot>
      </template>
  
      <template v-slot:text>
        <slot name="card-content">Default Content</slot>
      </template>
    </v-card>
    </div>
  </template>
  
<script>
  export default {
    name: "VueCard",
    data() {
      return {

      };
    },
    methods: {

    }
  };
</script>
  
<style scoped>
  .v-card-container {
    background-color: #111010;
    color: white;
    border-radius: 16px;
    box-shadow: 0 4px 30px rgba(0, 0, 0, 0.2);
  }

  .size {
    width:30vw;
    height:50vh;
  }

  @media (max-width: 479px) {
    .size {
      width:90vw;
      height:20vh;
      margin-top: 10px;
      overflow: auto;
    }

    .v-card-container {
      background-color: #0c0b0b;
      box-shadow: none;
      border-left: 2px solid rgb(190, 184, 184);
    }
}
</style>