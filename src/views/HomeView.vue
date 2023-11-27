<template>
<div id="page-container">
  <LandingPage ref="landingPage" @scrollToInformationPage="scrollToInformationPage"/>
</div>

<div id="landing-page-downscroll-container">
  <InfomationPage ref="infomationPage" @scrollToLanguagePage="scrollToLanguagePage"/>
  <LanguagePage ref="languagePage" @scrollToFooterPage="scrollToFooterPage"></LanguagePage>
  <FooterPage ref="footerPage" @scrollToTop="scrollToTop"></FooterPage>
</div>

</template>

<script>

// Components
import LandingPage from '../components/LandingPage.vue';
import InfomationPage from '../components/InfomationPage.vue';
import LanguagePage from '../components/LanguagePage.vue';
import FooterPage from '../components/FooterPage.vue';

export default {
  name: 'HomeView',

  components: {
    LandingPage,
    InfomationPage,
    LanguagePage,
    FooterPage,
  },
  methods: {
    scrollToInformationPage() {
      this.$refs.infomationPage.$el.scrollIntoView({ behavior: 'smooth' });
      },
      scrollToLanguagePage() {
      this.$refs.languagePage.$el.scrollIntoView({ behavior: 'smooth' });
      },
      scrollToFooterPage() {
      this.$refs.footerPage.$el.scrollIntoView({ behavior: 'smooth' });
      },
      scrollToTop() {
        window.scrollTo(0, 0);
      },
    },
  };
</script>

<style scss scoped>

#page-container {
  width: 100vw;
  height: 100vh;
}

video {
    object-fit: cover;
    width: 100%;
    height: 100%;
    position: absolute;
    top: 0;
    left: 0;
}

</style>

