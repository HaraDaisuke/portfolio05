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
      <section id="top" style="height: 100vh; background: #ffffff;">
        <h1>Top</h1>
        <p>Your top page here...</p>
      </section>

      <section id="about" style="height: 100vh; background: #f5f5f5;">
        <h1>About</h1>
        <p>Your information here...</p>
      </section>
      <section id="skills" style="height: 100vh; background: #e3e3e3;">
        <h1>Skills</h1>
        <p>Your skills here...</p>
      </section>
      <section id="certifications" style="height: 100vh; background: #d0d0d0;">
        <h1>Certifications</h1>
        <p>Your certifications here...</p>
      </section>
      <section id="contact" style="height: 100vh; background: #bdbdbd;">
        <h1>Contact</h1>
        <p>Your contact details here...</p>
      </section>
    </v-main>
  </v-app>
</template>

<script>
export default {
  methods: {
    scrollTo(sectionId) {
      const element = document.getElementById(sectionId);
      if (element) {
        element.scrollIntoView({ behavior: 'smooth' });
      }
    },
  },
};
</script>

<style scoped>
section {
  display: flex;
  align-items: center;
  justify-content: center;
  text-align: center;
}
</style>