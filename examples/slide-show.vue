<template>
  <div>
    <h2>Slide Show</h2>
    <h3>Slideshow without repeat</h3>
    <em>If slideshow enabled option is set, autoscroll feature is disabled</em>
    <vue-horizontal-list-autoscroll :items="items" :options="options">
      <template v-slot:default="{ item }">
        <div class="item">
          <h5>{{ item.title }}</h5>
          <p>{{ item.content }}</p>
        </div>
      </template>
    </vue-horizontal-list-autoscroll>

    <h3>Slideshow with repeat</h3>
    <em
      >If slideshow enabled option is set, autoscroll feature is disabled,
      notice how auroscroll option doesn't affect this slideshow</em
    >
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
  name: "auto-enabled",
  components: {
    VueHorizontalListAutoscroll,
  },
  data() {
    return {
      items: [0, 1, 2, 3, 4, 5, 6, 7, 8, 9].map((i) => {
        return { title: `Slide show ${i}`, content: `Slide show, 5s/5000ms.` };
      }),
      options: {
        slideshow: {
          enabled: true,
          repeat: false,
          interval: 5000,
        },
      },
      options2: {
        slideshow: {
          enabled: true,
          repeat: true,
          interval: 5000,
        },
        autoscroll: {
          enabled: true,
          interval: 5000,
          repeat: true,
        },
      },
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
