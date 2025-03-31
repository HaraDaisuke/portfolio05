<template>
  <v-card :color="color" class="mr-10 pa-4 rounded-lg d-flex flex-column align-center" elevation="4" style="max-width: 200px;">
    <v-card-text class="d-flex flex-column align-center">
      <div class="icon-container mb-2">
        <slot name="skillIcon"></slot>
      </div>
      <v-card-title class="text-subtitle-1 font-weight-bold text-white text-center">
        <slot name="skillName"></slot>
      </v-card-title>
      <v-rating
        :model-value="level"
        :length="5"
        color="amber"
        size="24"
        density="comfortable"
        readonly
      ></v-rating>
      <div class="mt-1 text-white text-body-2">Level: {{ level }} / 5</div>
    </v-card-text>
  </v-card>
</template>

<script>
export default {
  props: {
    level: {
      type: Number,
      required: true,
    },
    color: {
      type: String,
      default: 'primary',
    },
  },
};
</script>

<style scoped>
.v-card {
  transition: transform 0.3s ease-in-out, box-shadow 0.3s ease-in-out;
  max-width: 200px;
}

.v-card:hover {
  transform: scale(1.05);
  box-shadow: 0px 6px 12px rgba(0, 0, 0, 0.15);
}

.icon-container {
  display: flex;
  justify-content: center;
  align-items: center;
  width: 48px;
  height: 48px;
}
</style>