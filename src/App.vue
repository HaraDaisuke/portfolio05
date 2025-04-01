<template>
  <v-app>
    <!-- App Bar -->
    <v-app-bar app>
      <v-toolbar-title>Daisuke Hara   ~{{ currentSection }}~</v-toolbar-title>
      <v-spacer></v-spacer>
      <!-- Navigation Links -->
      <v-btn text @click="scrollTo('top')">Top</v-btn>
      <v-btn text @click="scrollTo('about')">About</v-btn>
      <v-btn text @click="scrollTo('skills')">Skills</v-btn>
      <v-btn text @click="scrollTo('certifications')">Certifications</v-btn>
      <v-btn text @click="scrollTo('contact')">Contact</v-btn>
    </v-app-bar>

    <!-- Sections -->
    <v-main>
      <section id="top" ref="top" style="height: 100vh; background: #bdbdbd;">
        <MainTop></MainTop>
      </section>
      <section id="about" ref="about" style="background: #ffffff;">
        <About></About>
      </section>
      <section id="skills" ref="skills" style="background: #ffffff;">
        <SkillTop></SkillTop>

      </section>
      <section id="certifications" ref="certifications" style="height: 100vh; background: #ffffff;">
        <h1>Certifications</h1>
        <p>Your certifications here...</p>
      </section>
      <section id="contact" ref="contact" style="height: 100vh; background: #ffffff;">
        <h1>Contact</h1>
        <p>Your contact details here...</p>
      </section>
    </v-main>
  </v-app>
</template>

<script>
import MainTop from './components/MainTop.vue';
import About from './components/About.vue';
import SkillTop from './components/SkillTop.vue';
import SkillChart from './components/SkillChart.vue';

export default {
  components: { MainTop, About ,SkillTop,SkillChart},
  data() {
    return {
      currentSection: "Daisuke Hara", // デフォルトのタイトル
    };
  },
  mounted() {
    const options = {
      root: null, // ビューポート全体を基準
      threshold: 0.5, // セクションが50%以上見えたら発火
    };

    this.observer = new IntersectionObserver(this.handleIntersect, options);

    // 各セクションを監視
    ["top", "about", "skills", "certifications", "contact"].forEach((sectionId) => {
      const section = this.$refs[sectionId];
      if (section) {
        this.observer.observe(section);
      }
    });
  },
  methods: {
    handleIntersect(entries) {
      entries.forEach((entry) => {
        if (entry.isIntersecting) {
          this.currentSection = entry.target.id.charAt(0).toUpperCase() + entry.target.id.slice(1);
        }
      });
    },
    scrollTo(sectionId) {
      const element = document.getElementById(sectionId);
      const appBarHeight = document.querySelector(".v-app-bar").clientHeight; // v-app-barの縦幅
      if (element) {
        const scrollY = element.offsetTop - appBarHeight; // スクロール位置を調整
        window.scrollTo({ top: scrollY, behavior: "smooth" });
      }
    },
  },
  beforeDestroy() {
    if (this.observer) {
      this.observer.disconnect();
    }
  },
};
</script>

<style scoped>
section {
  display: flex;
  align-items: flex-start;
  justify-content: center;
  text-align: center;
}
</style>
