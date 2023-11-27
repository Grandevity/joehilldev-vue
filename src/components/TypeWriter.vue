<template>
    <div>
        <p class="titles typer">my tech stack #includes <br><span id="textSpan">&lt;{{ currentText }}&gt;</span></p>
    </div>
</template>

<script>
export default {
  data() {
    return {
      texts: [
        "C++",
        "Python",
        "NodeJS",
        "VueJS",
        "SQL",
        "JavaScript",
      ],
      currentTextIndex: 0,
      currentText: "",
      isTyping: false
    };
  },
  mounted() {
    this.typeWriter();
  },
  methods: {
    typeWriter() {
      const speed = 80;
      const text = this.texts[this.currentTextIndex];
      const textLength = text.length;
      const self = this;

      function type(i) {
        if (i < textLength) {
          self.currentText += text.charAt(i);
          i++;
          setTimeout(() => {
            type(i);
          }, speed);
        } else {
          self.isTyping = false;
          setTimeout(() => {
            self.backspace();
          }, 1500);
        }
      }

      type(0);
    },
    backspace() {
      const speed = 30;
      const text = this.texts[this.currentTextIndex];
      const textLength = text.length;
      const self = this;

      function deleteText(i) {
        if (i >= 0) {
          self.currentText = text.substring(0, i);
          i--;
          setTimeout(() => {
            deleteText(i);
          }, speed);
        } else {
          self.isTyping = true;
          self.currentTextIndex =
            (self.currentTextIndex + 1) % self.texts.length;
          setTimeout(() => {
            self.typeWriter();
          }, 1000);
        }
      }

      deleteText(textLength - 1);
    }
  }
};
</script>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Sometype+Mono:ital@1&display=swap');

@import url('https://fonts.googleapis.com/css2?family=Orbitron&family=Sometype+Mono:ital@1&display=swap');

.typer {
    color: #e06e10;
    font-size: 50px;
    font-family: 'Orbitron', sans-serif;
    font-size: 50px;
}

#textSpan {
    color: #1b8acf;
    font-size: 60px;
}

@media (max-width: 479px) {
  .typer {
    font-size: 30px;
  }
  #textSpan {
    font-size: 40px;
  }
}


</style>