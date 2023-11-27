<template>
    <div id="landing-page-downscroll-container">
    
      <div id="hello-container">
        <h2><span id="helloSpan">hello , </span></h2>
        <h2><span id="thisIsSpan">this is an about page</span></h2>
      </div>

      <div>
        <div class="d-flex justify-space-evenly" id="boxDiv">
          <VueCard>
            <template v-slot:card-title>
              <p class="v-card-text-container"><b>My Degree</b></p>
            </template>

            <template v-slot:card-subtitle>
              BSc Software Engineering
            </template>

            <template v-slot:card-content>
              <p class="v-card-text-container">I'm Joe, a Software Engineering graduate from Bournemouth University.
                <br>
                <br>
                Passionate about technology and problem-solving, I bring to the table a strong foundation in software engineering and a commitment to delivering high-quality solutions.
                <br>
                <br>
                Collaboration and continuous learning drive my journey in this ever-evolving tech landscape. Explore my portfolio and let's connect to build the future together, one line of code at a time.

              </p>
            </template>
          </VueCard>
          <VueCard>
            <template v-slot:card-title>
              <p class="v-card-text-container"><b>My tech stack</b></p>
            </template>

            <template v-slot:card-subtitle>
              Fullstack Development
            </template>

            <template v-slot:card-content>
              <p class="v-card-text-container">The thrill of solving complex problems and the endless possibilities technology offers keep me fueled and motivated.
                <br>
                <br>
                I embrace diversity in tech stacks. From full-stack development using web frameworks like Vue.js and Node.js to diving deep into object-oriented high-level languages like C++, I find joy in exploring the unique strengths of each technology.
                <br>
                <br>
                Working with HTTPS RESTful API development is my forte. Building robust, efficient, and secure communication channels between different components of a system excites me. It's all about enabling systems to speak a common language
              </p>
            </template>
          </VueCard>
          <VueCard>
            <template v-slot:card-title>
              <p class="v-card-text-container"><b>The informalities</b></p>
            </template>

            <template v-slot:card-subtitle>
              Saving the best till' last
            </template>

            <template v-slot:card-content>
              <p class="v-card-text-container">
                Well, let's talk about the <i>real</i> me,
                <br>
                <br>
                I like fast cars and beer gardens, lets be honest, who doesn't
                <br>
                <br>
                I take interest in the exploration of space, there's something profoundly captivating about the mysteries of the universe, I follow organizations like NASA and SpaceX, cheering on humanity's quest to the cosmos.
              </p>
            </template>
          </VueCard>
        </div>
        <div id="downDiv">
            <v-btn icon="mdi-chevron-down" size="large" id="btnDown" @click="scrollToDiv"></v-btn>
          </div>
      </div>

    </div>

</template>
  
<script>
import VueCard from '../components/VueCard.vue';

  export default {
    name: "InfomationPage",
    data() {
      return {
        isInViewport: false,
      };
      
    },
    components: {
          VueCard,
        },
    methods: {
      checkVisible () {
        //check if on screen
      },
      scrollToDiv() {
            this.$emit('scrollToLanguagePage')
        }
    },
    mounted() {

      const elementToObserve = document.querySelector('#helloSpan');
      const elementToObserve2 = document.querySelector('#thisIsSpan');
      const elementToObserve3 = document.querySelector('#boxDiv');
      const elementToObserve4 = document.querySelector('#downDiv');

      const observer = new IntersectionObserver((entries) => {
        entries.forEach(entry => {
          if (entry.isIntersecting) {
           
            elementToObserve.classList.add('run-animation');
            elementToObserve2.classList.add('run-animation-2'); 
            elementToObserve3.classList.add('run-animation-3');
            elementToObserve4.classList.add('run-animation-4');  
          }
        });
      });

      observer.observe(elementToObserve);
      observer.observe(elementToObserve2);
      observer.observe(elementToObserve3);
      observer.observe(elementToObserve4);
    }
  };
</script>
  
<style scoped>

@import url('https://fonts.googleapis.com/css2?family=Playball&family=Raleway:ital,wght@1,300&family=Space+Grotesk&display=swap');


  /* Add your CSS styles here */

#downDiv {
  margin: auto;
  text-align: center;
  position: relative;
  margin-top: 10px;
  opacity: 0;
}
#btnDown {
  background-color: #302c2c;
}

#btnDown:hover {
  color: #3e65cf;
}

#landing-page-downscroll-container {
  height: 100vh;
  /*background: rgb(22,21,21);*/
  background-color: #0c0b0b;
}

#hello-container {
  padding-top: 1vh;
}

h2 {
  font-size: 80px;
}

#helloSpan {
  color: #3e65cf;
  opacity: 0;
  font-family: 'Playball', cursive;
}

#thisIsSpan {
  color: #e06e10;
  opacity: 0;
  font-size: 70px;
  font-family: 'Playball', cursive;
}

#boxDiv {
  opacity: 0;
}

.v-card-text-container {
  font-size: 1vw;
  line-height:normal;
  color: #d6d9db;
}
.run-animation {
  animation: fadeInAnimation ease 2s forwards;
  animation-delay: 0.25s;
}

.run-animation-2 {
  animation: fadeInAnimation ease 2s forwards;
  animation-delay: 0.75s;
}
.run-animation-3 {
  animation: fadeInAnimation2 ease 2s forwards;
  animation-delay: 1s;
}

.run-animation-4 {
  animation: fadeInAnimationButtonOnly ease 2s forwards;
  animation-delay: 1s;
}

@keyframes fadeInAnimation {
    0% {
        opacity: 0;
        margin-left: 0%;
    }
    100% {
        opacity: 1;
        margin-left: 10%;
    }
}

@keyframes fadeInAnimation2 {
    0% {
        opacity: 0;
        margin-top: 20%;
    }
    100% {
        opacity: 1;
        margin-top: 1%;
    }
}

@keyframes fadeInAnimationButtonOnly {
    0% {
        opacity: 0;
    }
    100% {
        opacity: 1;
    }
}

/*For phones*/
@media (max-width: 479px) {
    h2 {
      font-size: 15vw;
    }

    #thisIsSpan {
      font-size: 10vw;
      line-height: 0%;
      text-align: center;
      margin: auto;
    }

    .v-card-text-container {
      font-size: 12px;
    }

    #boxDiv {
      flex-direction: column;
      align-items: center;
    }

    
    
  }
</style>