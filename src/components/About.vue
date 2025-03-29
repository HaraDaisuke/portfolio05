<template>
  <v-timeline align="start" justify="center" line-color="#bdbdbd" class="mx-5">
    
    <v-timeline-item
      dot-color="red-lighten-2"
      icon="mdi-star"
      fill-dot
    >
        <TimeLineItem>
            <template v-slot:my-card-title>富山県立大門高等学校に入学</template>
            <template v-slot:my-card-text>富山県立大門高等学校　情報コースでプログラミングに触れる</template>
        </TimeLineItem>
    </v-timeline-item>

        <v-timeline-item
      dot-color="red-lighten-2"
      icon="mdi-star"
      fill-dot
    >
        <TimeLineItem>
            <template v-slot:my-card-title>富山県立大門高等学校に入学</template>
            <template v-slot:my-card-text>富山県立大門高等学校　情報コースでプログラミングに触れる</template>
        </TimeLineItem>
    </v-timeline-item>

        <v-timeline-item
      dot-color="red-lighten-2"
      icon="mdi-star"
      fill-dot
    >
        <TimeLineItem>
            <template v-slot:my-card-title>富山県立大門高等学校に入学</template>
            <template v-slot:my-card-text>富山県立大門高等学校　情報コースでプログラミングに触れる</template>
        </TimeLineItem>
    </v-timeline-item>

        <v-timeline-item
      dot-color="red-lighten-2"
      icon="mdi-star"
      fill-dot
    >
        <TimeLineItem>
            <template v-slot:my-card-title>富山県立大門高等学校に入学</template>
            <template v-slot:my-card-text>富山県立大門高等学校　情報コースでプログラミングに触れる</template>
        </TimeLineItem>
    </v-timeline-item>

        <v-timeline-item
      dot-color="red-lighten-2"
      icon="mdi-star"
      fill-dot
    >
        <TimeLineItem>
            <template v-slot:my-card-title>富山県立大門高等学校に入学</template>
            <template v-slot:my-card-text>富山県立大門高等学校　情報コースでプログラミングに触れる</template>
        </TimeLineItem>
    </v-timeline-item>

        <v-timeline-item
      dot-color="red-lighten-2"
      icon="mdi-star"
      fill-dot
    >
        <TimeLineItem>
            <template v-slot:my-card-title>富山県立大門高等学校に入学</template>
            <template v-slot:my-card-text>富山県立大門高等学校　情報コースでプログラミングに触れる</template>
        </TimeLineItem>
    </v-timeline-item>


  </v-timeline>
</template>


<script>
import TimeLineItem from './TimeLineItem.vue';
export default {
  components: { TimeLineItem },
}
</script>

<script setup>

const items = [
{
    color: 'red-lighten-2',
    icon: 'mdi-star',
},
{
    color: 'purple-lighten-2',
    icon: 'mdi-book-variant',
},
{
    color: 'green-lighten-1',
    icon: 'mdi-airballoon',
},
{
    color: 'indigo-lighten-2',
    icon: 'mdi-layers-triple',
},
]
</script>
