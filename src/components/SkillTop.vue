<template>
  <v-container>
    <!-- フロントエンド -->
    <v-row>
      <v-col cols="12">
        <h2 class="text-h5 font-weight-bold">Frontend</h2>
        <v-divider class="mb-4"></v-divider>
      </v-col>
      <SkillCard :level="4" color="blue">
        <template v-slot:skillIcon>
          <v-icon size="36">mdi-language-html5</v-icon>
        </template>
        <template v-slot:skillName>HTML</template>
      </SkillCard>
      <SkillCard :level="4" color="green">
        <template v-slot:skillIcon>
          <v-icon size="36">mdi-language-css3</v-icon>
        </template>
        <template v-slot:skillName>CSS</template>
      </SkillCard>
      <SkillCard :level="5" color="orange">
        <template v-slot:skillIcon>
          <v-icon size="36">mdi-language-javascript</v-icon>
        </template>
        <template v-slot:skillName>JavaScript</template>
      </SkillCard>
    </v-row>

    <!-- バックエンド -->
    <v-row>
      <v-col cols="12">
        <h2 class="text-h5 font-weight-bold mt-8">Backend</h2>
        <v-divider class="mb-4"></v-divider>
      </v-col>
      <SkillCard :level="3" color="red">
        <template v-slot:skillIcon>
          <v-icon size="36">mdi-language-python</v-icon>
        </template>
        <template v-slot:skillName>Python</template>
      </SkillCard>
      <SkillCard :level="4" color="purple">
        <template v-slot:skillIcon>
          <v-icon size="36">mdi-language-php</v-icon>
        </template>
        <template v-slot:skillName>PHP</template>
      </SkillCard>
      <SkillCard :level="5" color="amber">
        <template v-slot:skillIcon>
          <v-icon size="36">mdi-database</v-icon>
        </template>
        <template v-slot:skillName>SQL</template>
      </SkillCard>
    </v-row>

    <!-- 言語 -->
    <v-row>
      <v-col cols="12">
        <h2 class="text-h5 font-weight-bold mt-8">Languages</h2>
        <v-divider class="mb-4"></v-divider>
      </v-col>
      <SkillCard :level="4" color="blue">
        <template v-slot:skillIcon>
          <v-icon size="36">mdi-language-java</v-icon>
        </template>
        <template v-slot:skillName>Java</template>
      </SkillCard>
      <SkillCard :level="3" color="light-blue">
        <template v-slot:skillIcon>
          <v-icon size="36">mdi-language-csharp</v-icon>
        </template>
        <template v-slot:skillName>C#</template>
      </SkillCard>
      <SkillCard :level="5" color="green">
        <template v-slot:skillIcon>
          <v-icon size="36">mdi-language-python</v-icon>
        </template>
        <template v-slot:skillName>Python</template>
      </SkillCard>
    </v-row>

    <!-- インフラ -->
    <v-row>
      <v-col cols="12">
        <h2 class="text-h5 font-weight-bold mt-8">Infrastructure</h2>
        <v-divider class="mb-4"></v-divider>
      </v-col>
      <SkillCard :level="4" color="grey">
        <template v-slot:skillIcon>
          <v-icon size="36">mdi-cloud-outline</v-icon>
        </template>
        <template v-slot:skillName>AWS</template>
      </SkillCard>
      <SkillCard :level="3" color="cyan">
        <template v-slot:skillIcon>
          <v-icon size="36">mdi-cloud"></v-icon>
        </template>
        <template v-slot:skillName>Azure</template>
      </SkillCard>
      <SkillCard :level="5" color="orange">
        <template v-slot:skillIcon>
          <v-icon size="36">mdi-docker"></v-icon>
        </template>
        <template v-slot:skillName>Docker</template>
      </SkillCard>
    </v-row>
  </v-container>
</template>

<script>
import SkillCard from "./SkillCard.vue";
export default {
  components: {
    SkillCard,
  },
};
</script>

<style scoped>
h2 {
  color: #424242;
  margin-bottom: 8px;
}
</style>
