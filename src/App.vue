<template>
  <v-app id="website-container">
    <v-main>
      <router-view/>
    </v-main>
  </v-app>
</template>

<script>

export default {
  name: 'App',

  data: () => ({
    toggleA: true
  }),
}
</script>

<style>

@import url('https://fonts.googleapis.com/css2?family=Raleway:ital,wght@1,300&display=swap');

@import url('https://fonts.googleapis.com/css2?family=Orbitron&family=Raleway:ital@1&family=Sometype+Mono:ital@1&display=swap');


#website-container {
  background-color: #0c0b0b;
  color: var(--white-087, rgba(255, 255, 255, 0.87));
  font-family: 'Sometype Mono', monospace;
  overflow: hidden;
}
::-webkit-scrollbar {
    display: none;
}

@media (max-width: 479px) {

   #website-container {
    font-family: 'Sometype Mono', monospace;
   }
}


</style>

