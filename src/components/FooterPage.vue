<template>
    <div id="footer-page-container">

      <div id="title-container">
        <h2 id="heading1">like what you see?</h2>
        <h2 id="heading2">what are you waiting for?</h2>
        <h2 id="heading3">get in touch.</h2>
      </div>

      <div id="btn-container" class="d-flex justify-center flex-wrap">
            <v-btn icon="mdi-github" id="btn-git" size="x-large" variant="plain" href="https://github.com/Grandevity"></v-btn>
            <v-btn icon="mdi-linkedin" id="btn-linkedin" size="x-large" variant="plain" href="https://www.linkedin.com/in/joseph-hill-9431b9216/"></v-btn>
            <v-btn icon="mdi-email" id="btn-email" size="x-large" variant="plain" @click="openMail"></v-btn>
      </div>


      <div id="footer-container">
        <div id="company-outter-container">
        <h2 id="software-roles-title">Previous Software Roles</h2>
          <div id="company-container" class="d-flex justify-center flex-wrap">
            <v-img
              :width="100"
              aspect-ratio="16/9"
              max-height="70"
              class="image"
              src="../assets/brands/micronav.png"
            ></v-img>
          </div>

        </div>
          <v-btn variant="plain" @click="downloadCv">
              Download CV
          </v-btn>
          <v-btn variant="plain" @click="scrollToDiv">
              Back to top
          </v-btn>
          <v-btn variant="plain" @click="openMail">
              Contact me
          </v-btn>
      </div>
    </div>
</template>
  
<script>

  export default {
    name: "FooterPage",
    data() {
      return {
      };
      
    },
    components: {
        },
    methods: {
      scrollToDiv() {
            this.$emit('scrollToTop')
        },
      downloadCv() {
         // Define the path to the PDF file
          const pdfPath = '/CV_JWH.pdf';

        // Create an anchor element (hidden) to trigger the download
        const anchor = document.createElement('a');
        anchor.style.display = 'none';
        anchor.href = pdfPath;
        anchor.download = 'CV_JWH.pdf';

        // Append the anchor element to the document body
        document.body.appendChild(anchor);

        // Trigger the download
        anchor.click();

        // Clean up by removing the anchor element
        document.body.removeChild(anchor); 
      },
      openMail() {
        const email = 'joewhillcv@gmail.com';
        const subject = 'Request to Hire';
        const body = 'Hello Joe,\n\nI found your amazing website, lets talk.';

        const mailtoLink = `mailto:${email}?subject=${encodeURIComponent(subject)}&body=${encodeURIComponent(body)}`;

        window.location.href = mailtoLink;
      }
    },
    mounted() {

      const elementToObserve1 = document.querySelector('#heading1');
      const elementToObserve2 = document.querySelector('#heading2');
      const elementToObserve3 = document.querySelector('#heading3');

      const observer = new IntersectionObserver((entries) => {
        entries.forEach(entry => {
          if (entry.isIntersecting) {
          
            elementToObserve1.classList.add('run-animation');
            elementToObserve2.classList.add('run-animation2');
            elementToObserve3.classList.add('run-animation3');
          }
        });
      });

      observer.observe(elementToObserve1);
      observer.observe(elementToObserve2);
      observer.observe(elementToObserve3);
}
  };
</script>
  
<style scoped>
  @import url('https://fonts.googleapis.com/css2?family=Playball&family=Raleway:ital,wght@1,300&family=Space+Grotesk&display=swap');
  @import url('https://fonts.googleapis.com/css2?family=Raleway:ital,wght@1,300&display=swap');
  /* Add your CSS styles here */
.run-animation {
  animation: fadeInAnimation ease 2s forwards;
  animation-delay: 0.25s;
  }

  .run-animation2 {
  animation: fadeInAnimation ease 2s forwards;
  animation-delay: 0.50s;
  }

  .run-animation3 {
  animation: fadeInAnimation ease 2s forwards;
  animation-delay: 1s;
  }

  @keyframes fadeInAnimation {
    0% {
        opacity: 0;
        margin-left: -10%;
    }
    100% {
        opacity: 1;
    }
}

  #footer-page-container {
  height: 100vh;
  /*background: rgb(22,21,21);*/
  background-color: #0c0b0b;
  display: flex;
  flex-direction: column;
}

#title-container {
  position: relative;
  left: 10%;
  top: 10%;
  width: 100vw;
}

#footer-container {
  margin-top: auto;
  margin-bottom: 20px;
  text-align: center;
}

h2 {
  font-family: 'Playball', cursive;
  font-size: 50px;
}

#heading1 {
  color: #3e65cf;
  font-size: 70px;
  opacity: 0;
}

#heading2 {
  color: #4072aa;
  font-size: 40px;
  margin-left: 10%;
  opacity: 0;
}

#heading3 {
  color: #e06e10;
  margin-left: 20%;
  opacity: 0;
  
}

#software-roles-title {
  text-align: center;
  position: relative;
  top: 20%;
  font-family: 'Raleway', sans-serif;
  font-size: 30px;
  color: #b1b1b1;
}
#company-container {
  text-align: center;
  position: relative;
  top: 20%;
}

#company-outter-container {
  padding: 20px;
}
#btn-container {
  padding: 10px;
  animation-delay: 2s;
  margin: auto;
  margin-top: 20vh;
  width: 100%;
}

#btn-git {
  color: #f5f5f5;
  margin: 100px;
  margin-top: 0%;
  font-size: 5vw;
  
  }

#btn-linkedin {
  color: #0072b1 ;
  margin: 100px;
  margin-top: 0%;
  font-size: 5vw;
  }

#btn-email {
  color: #3e65cf;
  margin: 100px;
  margin-top: 0%;
  font-size: 5vw;
  }

@media (max-width: 479px) {
    h2 {
      font-size: 30px;
    }
    #heading1 {
      font-size: 30px;
    } 
    #heading2 {
      font-size: 30px;
      margin-left: 0;
    }
    #heading3 {
      font-size: 30px;
      margin-left: 0;
    }
    #btn-email {
      font-size: 40px;
      margin-bottom: 20px;

    }
    #btn-git {
      font-size: 40px;
      margin-bottom: 20px;
    }
    #btn-linkedin {
      font-size: 40px;
      margin-bottom: 20px;
    }
    #title-container {
      text-align: center;
      margin: 0%;
      left: 0%;
      top: 2%;
    }

    #software-roles-title {
      font-size: 20px;
    }

    #company-container {
      width: 50%;
      margin: 0 auto;
      text-align: center;

    }
  
  }

</style>