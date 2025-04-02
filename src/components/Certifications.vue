<template>
  <v-container>
    <v-row>
      <v-col cols="12" class="text-center">
        <v-typography variant="h2" class="font-weight-bold">
          Certifications
        </v-typography>
      </v-col>
    </v-row>
    <v-row>
      <v-col v-for="cert in certifications" :key="cert.name" cols="12" sm="6" md="4">
        <v-card class="pa-5" elevation="3">
          <v-row align="center" class="mb-3">
            <v-avatar size="56">
              <v-icon size="48">{{ cert.icon }}</v-icon>
            </v-avatar>
            <v-spacer></v-spacer>
            <v-typography variant="h5" class="font-weight-bold">
              {{ cert.name }}
            </v-typography>
          </v-row>
          <v-card-text>
            {{ cert.description }}
          </v-card-text>
        </v-card>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
export default {
  data() {
    return {
      certifications: [
        { name: "基本情報技術者", icon: "mdi-laptop", description: "ITの基礎知識を問う国家資格" },
        { name: "データベーススペシャリスト", icon: "mdi-database", description: "DB設計・管理の専門資格" },
        { name: "G検定", icon: "mdi-brain", description: "AIの基礎知識と倫理を問う資格" },
        { name: "Azure AZ-900", icon: "mdi-microsoft", description: "Azureの基礎を問う認定資格" },
        { name: "Azure AI-900", icon: "mdi-robot", description: "Azure AIの基礎を問う認定資格" },
        { name: "販売士2級", icon: "mdi-store", description: "流通・小売の知識を問う資格" }
      ]
    };
  }
};
</script>

<style scoped>
.v-card {
  transition: transform 0.2s ease-in-out;
}
.v-card:hover {
  transform: scale(1.05);
}
</style>
