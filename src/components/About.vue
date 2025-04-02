<template>
  <v-timeline align="start" justify="center" line-color="#bdbdbd" class="mx-5">
    
    <v-timeline-item
      dot-color="red-lighten-2"
      icon="mdi-star"
      fill-dot
    >
        <TimeLineItem>
            <template v-slot:my-card-title>中京大学 情報理工学部入学</template>
            <template v-slot:my-card-text>プログラミングの基礎を学ぶ。<br>研究結果が、IPA主催の情報処理学会にて、第75回、第76回に学生奨励賞を受賞。
            </template>
        </TimeLineItem>
    </v-timeline-item>

        <v-timeline-item
      dot-color="red-lighten-2"
      icon="mdi-star"
      fill-dot
    >
        <TimeLineItem>
            <template v-slot:my-card-title>（株）富士通システムズウエスト 入社</template>
            <template v-slot:my-card-text>流通業界のSEとして従事。上流工程のインフラ保守からシステムスクラッチ開発まで幅広く担当。<br>その後、富士通と合併し、富士通SEとして主に生協の配達システムの構築、保守メンテを担当。</template>
        </TimeLineItem>
    </v-timeline-item>

        <v-timeline-item
      dot-color="red-lighten-2"
      icon="mdi-star"
      fill-dot
    >
        <TimeLineItem>
            <template v-slot:my-card-title>（株）ジェイテクト 入社</template>
            <template v-slot:my-card-text>ラインコントロール関連のシステム構築を担当。デジタル企画関連部署へ移動後、主に生成AIや検索エンジン関連システムの開発を担当。今に至る。</template>
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
