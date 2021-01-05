<template>
  <div>
    <h2>Auto Scroll</h2>
    <h3>AutoScroll without repeat</h3>
    <em>autoscroll doesn't work with slideshow enabled option set to true</em>
    <vue-horizontal-list-autoscroll :items="items" :options="options">
      <template v-slot:default="{ item }">
        <div class="item">
          <h5>{{ item.title }}</h5>
          <p>{{ item.content }}</p>
        </div>
      </template>
    </vue-horizontal-list-autoscroll>
    <h3>AutoScroll with repeat</h3>
    <em>autoscroll doesn't work with slideshow enabled option set to true</em>
    <vue-horizontal-list-autoscroll :items="items" :options="options2">
      <template v-slot:default="{ item }">
        <div class="item">
          <h5>{{ item.title }}</h5>
          <p>{{ item.content }}</p>
        </div>
      </template>
    </vue-horizontal-list-autoscroll>
  </div>
</template>

<script>
import VueHorizontalListAutoscroll from "@/vue-horizontal-list-autoscroll.vue";

export default {
  name: "autoscroll",
  components: {
    VueHorizontalListAutoscroll,
  },
  data() {
    return {
      options: {
        responsive: [
          { end: 576, size: 1 },
          { start: 576, end: 768, size: 2 },
          { start: 768, end: 992, size: 3 },
          { size: 4 },
        ],
        autoscroll: {
          enabled: true,
          interval: 5000, // in milliseconds
          repeat: false, // used to tell if after reaching the end of the list should the list return to beginning again
        },
        list: {
          // 1200 because @media (min-width: 1200px) and therefore I want to switch to windowed mode
          windowed: 1200,

          // Because: #app {padding: 80px 24px;}
          padding: 24,
        },
      },
      options2: {
        responsive: [
          { end: 576, size: 1 },
          { start: 576, end: 768, size: 2 },
          { start: 768, end: 992, size: 3 },
          { size: 4 },
        ],
        autoscroll: {
          enabled: true,
          interval: 5000, // in milliseconds
          repeat: true, // used to tell if after reaching the end of the list should the list return to beginning again
        },
        list: {
          // 1200 because @media (min-width: 1200px) and therefore I want to switch to windowed mode
          windowed: 1200,

          // Because: #app {padding: 80px 24px;}
          padding: 24,
        },
      },
      items: [0, 1, 2, 3, 4, 5, 6, 7, 8, 9].map((i) => {
        return {
          title: `Auto scroll ${i}`,
          content: `Auto scroll, 5s/5000ms.`,
        };
      }),
    };
  },
};
</script>

<style scoped>
.item {
  padding: 24px;
  border-radius: 3px;
  background: #f5f5f5;
}
</style>
