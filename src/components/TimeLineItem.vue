<template>
  <v-container v-intersect="onIntersect">
    <v-slide-x-transition>
      <v-card v-show="isVisible" class="fixed-card">
        <v-card-title class="text-h6 bg-red-lighten-2 text-left"><slot name="my-card-title"></slot></v-card-title>
        <v-card-text class="bg-white text--primary pt-3 text-left"><p><slot name="my-card-text"></slot></p></v-card-text>      </v-card>
    </v-slide-x-transition>
  </v-container>
</template>

<script setup>
import {ref} from 'vue';
const isVisible = ref(false);

const onIntersect = (isIntersecting, entries, observer)  => {

  if(isIntersecting){
    //console.log("表示領域に達した");
    isVisible.value = true;
  }else{
    //console.log("表示領域から離れた");
    //isVisible.value = false;
  }
};
</script>

<style scoped>
.fixed-card {
  max-width: 1000px; /* 以前より広げる */
  width: 100%;
}
</style>