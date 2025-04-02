<template>
  <v-app>
    <!-- App Bar -->
    <v-app-bar app>
      <v-toolbar-title>Daisuke Hara</v-toolbar-title>
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
      
    <v-container fluid class="bg-white pt-10" id="about">
      <!-- 見出しを中央に配置 -->
      <v-row justify="center">
        <v-col cols="12" class="text-center">
          <v-typography variant="h2" class="text-h2">
            About
          </v-typography>
        </v-col>
      </v-row>

      <!-- Aboutのコンテンツを中央に配置 -->
      <v-row justify="center">
        <v-col cols="12" md="8">
          <section ref="about" class="bg-white">
            <About></About>
          </section>
        </v-col>
      </v-row>
    </v-container>





    <v-container fluid class="bg-white pt-10" id="skills">
      <!-- 見出しを中央に配置 -->
      <v-row justify="center">
        <v-col cols="12" class="text-center">
          <v-typography variant="h1" class="text-h2">
            Skills
          </v-typography>
        </v-col>
      </v-row>

      <!-- Skillsのコンテンツを中央に配置 -->
      <v-row justify="center">
        <v-col cols="12" md="8">
          <section ref="skills" class="bg-white">
            <SkillTop></SkillTop>
          </section>
        </v-col>
      </v-row>
    </v-container>





    <v-container fluid class="bg-white pt-10" id="certifications">
      <!-- 見出しを中央に配置 -->
      <v-row justify="center">
        <v-col cols="12" class="text-center">
          <v-typography variant="h1" class="text-h2">
            Certifications
          </v-typography>
        </v-col>
      </v-row>

      <!-- Skillsのコンテンツを中央に配置 -->
      <v-row justify="center">
        <v-col cols="12" md="8">
          <section ref="certifications" class="bg-white">
            <Certifications></Certifications>
          </section>
        </v-col>
      </v-row>
    </v-container>






    <v-container fluid class="bg-white pt-10" id="contact">
      <!-- 見出しを中央に配置 -->
      <v-row justify="center">
        <v-col cols="12" class="text-center">
          <v-typography variant="h1" class="text-h2">
            Contact
          </v-typography>
        </v-col>
      </v-row>

      <!-- Skillsのコンテンツを中央に配置 -->
      <v-row justify="center">
        <v-col cols="12" md="8">
          <section ref="contact" class="bg-white">
            <Contact></Contact>
          </section>
        </v-col>
      </v-row>
    </v-container>


    </v-main>
  </v-app>
</template>

<script>
import MainTop from './components/MainTop.vue';
import About from './components/About.vue';
import SkillTop from './components/SkillTop.vue';
import SkillChart from './components/SkillChart.vue';
import Certifications from './components/Certifications.vue';
import Contact from './components/Contact.vue'

export default {
  components: { MainTop, About ,SkillTop,SkillChart,Certifications,Contact},
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
