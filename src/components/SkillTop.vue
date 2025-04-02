<template>
    <div class="d-flex align-center justify-center fill-height">
        <v-container fluid>
            <!-- フロントエンド -->
            <v-row>
                <v-col cols="12">
                    <SkillChart></SkillChart>
                </v-col>
            </v-row>
        </v-container>
    </div>
</template>

<script>
import SkillChart from "./SkillChart.vue"
export default {
  components: {
    SkillChart,
  },
};
</script>

<style scoped>
h2 {
  color: #424242;
  margin-bottom: 8px;
}
</style>
