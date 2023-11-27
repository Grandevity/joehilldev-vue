<template>
<div id="landing-page-container">

    <div id="information-card">
        <div>
            <h1>J W HILL</h1>
            <h2 class="welcome-text">Software Engineer</h2>
            <h3 class="welcome-text">BSc Software Engineering</h3>
        </div>

        <div id="btn-container">
            <v-btn icon="mdi-github" id="btn-git" href="https://github.com/Grandevity"></v-btn>
            <v-btn icon="mdi-linkedin" id="btn-linkedin" href="https://www.linkedin.com/in/joseph-hill-9431b9216/"></v-btn>
            <v-btn icon="mdi-email" id="btn-email" @click="openMail"></v-btn>
        </div>
        <div id="down-div">
            <v-btn icon="mdi-chevron-down" size="large" id="btn-down" @click="scrollToDiv"></v-btn>
        </div>
    </div>
</div>

</template>
  
<script>
  export default {
    name: "LandingPage",
    data() {
      return {

      };
    },
    methods: {
        scrollToDiv() {
            this.$emit('scrollToInformationPage')
        },
        openMail() {
          const email = 'joewhillcv@gmail.com';
          const subject = 'Request to Hire';
          const body = 'Hello Joe,\n\nI found your amazing website, lets talk.';

          const mailtoLink = `mailto:${email}?subject=${encodeURIComponent(subject)}&body=${encodeURIComponent(body)}`;

          window.location.href = mailtoLink;
      }
    }
  };
</script>
  
<style scoped>
#btn-container {
  padding: 10px;
  margin: auto;
  text-align: center;
  animation: fadeInAnimation ease 3s forwards;
  opacity: 0;
  animation-delay: 2s;
}

#down-div {
  margin: auto;
  text-align: center;
  position: relative;
  top: 10vh;
}
#btn-git {
  background-color: #302c2c;
  color: #f5f5f5;
  margin: 5px;
  }

#btn-linkedin {
  background-color: #302c2c;
  color: #0072b1 ;
  margin: 5px;
  }

#btn-email {
  background-color: #302c2c;
  color: #3e65cf;
  margin: 5px;
  }

#btn-down {
  background-color: #302c2c;
}

#btn-down:hover {
  color: #3e65cf;
}

#landing-page-container {
  height: 90%;
  width: 95%;
  position: relative;
  top: 5%;
  left: 2.5%;
  z-index: 10;
  overflow: hidden;
  
}

#information-card {
  position: relative;
  top: 30vh;
  opacity: 0;
  animation: fadeInAnimation ease 3s forwards;
  animation-delay: 0.5s;
  align-items: center;
}


#landing-page-downscroll-container {
  height: 100vh;
  background: rgb(22,21,21);
}
.welcome-text {
  color: var(--white-087, rgba(211, 210, 210, 0.87));
  text-align: center;
}

h1 {
  color: #006ae2;
  font-size: 50px;
  text-align: center;
}



@keyframes fadeInAnimation {
    0% {
        opacity: 0;
        top: 40vh;
    }
    100% {
        opacity: 1;
    }
}
</style>