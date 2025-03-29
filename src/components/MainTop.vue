<template>
  <v-container class="d-flex align-center justify-center fill-height" fluid v-intersect="onIntersect">
    <v-expand-x-transition>
      <v-card
        v-show="isVisible"
        class="elevation-12 text-center py-6"
        width="70%"
        style="background-size: cover; color: white;">
        <v-card-title>
          <v-row class="text-h1 font-weight-bold justify-center">
            Daisuke Hara
          </v-row>
        </v-card-title>
        <v-card-text>
          <v-row class="text-h5 my-4 justify-center">
            Highlighting Your Skills and Innovations
          </v-row>
          <v-row class="justify-center">
            <v-btn icon href="https://github.com/HaraDaisuke/" target="_blank" class="mx-2" color="white">
              <v-icon large>mdi-github</v-icon>
            </v-btn>
            <v-btn icon href="https://www.facebook.com/daisuke.hara.524/" target="_blank" class="mx-2" color="white">
              <v-icon large>mdi-facebook</v-icon>
            </v-btn>
            <v-btn icon href="https://x.com/parsley0402/" target="_blank" class="mx-2" color="white">
              <v-icon large>mdi-twitter</v-icon>
            </v-btn>
          </v-row>
        </v-card-text>
      </v-card>
    </v-expand-x-transition>
  </v-container>
</template>

<script setup>
import { ref } from 'vue';

const isVisible = ref(false);

const onIntersect = (isIntersecting, entries, observer) => {
  if (isIntersecting) {
    console.log("表示領域に達した");
    setTimeout(() => {
      console.log("表示した");
      isVisible.value = true;
    }, 150);
  } else {
    console.log("表示領域から離れた");
    isVisible.value = false;
  }
};
</script>

<style>
html, body, .fill-height {
  height: 100%;
  margin: 0;
}
</style>
