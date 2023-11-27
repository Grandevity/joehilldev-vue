<template>
    <div id="language-page-container">
      <div id="typewriter-container">
        <TypeWriter></TypeWriter>
      </div>
      <div id="brand-container" class=" d-flex align-content-start flex-wrap">
        <v-img
          :width="100"
          aspect-ratio="16/9"
          max-height="200"
          class="image"
          src="../assets/brands/cpp.png"
        ></v-img>
        <v-img
          :width="100"
          aspect-ratio="16/9"
          class="image"
          max-height="200"
          src="../assets/brands/mariadb.png"
        ></v-img>
        <v-img
          width="100"
          aspect-ratio="16/9"
          class="image"
          max-height="200"
          src="../assets/brands/nodejs.png"
        ></v-img>
        <v-img
          width="100"
          aspect-ratio="16/9"
          class="image"
          max-height="200"
          src="../assets/brands/python.png"
        ></v-img>
        <v-img
          width="100"
          aspect-ratio="16/9"
          class="image"
          max-height="200"
          src="../assets/brands/vuejs.png"
        ></v-img>
        <v-img
          width="100"
          aspect-ratio="16/9"
          class="image"
          max-height="200"
          src="../assets/brands/javascript.png"
        ></v-img>
      </div>
      <div id="downDiv">
        <v-btn icon="mdi-chevron-down" size="large" id="btn-down" @click="scrollToDiv"></v-btn>
      </div>
    </div>
</template>
  
<script>
import TypeWriter from '../components/TypeWriter.vue';
  export default {
    name: "LanguagePage",
    data() {
      return {

      };
    },
    components: {
      TypeWriter,
  },
    methods: {
      scrollToDiv() {
            this.$emit('scrollToFooterPage')
        }
    }
  };
</script>
  
<style>
#downDiv {
  margin: auto;
  text-align: center;
  position: relative;
  left: 50%;
  top: 40%;
  transform: translateX(-50%);
}
#btn-down {
  background-color: #302c2c;
}

#btn-down:hover {
  color: #3e65cf;
}

#language-page-container {
  height: 100vh;
  /*background: rgb(22,21,21);*/
  background-color: #0c0b0b;
}

#typewriter-container {
  margin: 0 auto;
  position: relative;
  top: 15%;
  text-align: center;
}

#brand-container {
  position: relative;
  top: 30%;
}

@media (max-width: 479px) {

  #typewriter-container {
    top: 2%;
    margin: 5px;
  }

  #brand-container {
    top: 1%;
  }

  .image {
    height: 20vw;
    margin-top: 5px;
    padding-left: 100%;

  }

  #downDiv {
    top: 5%;
  }

}
</style>