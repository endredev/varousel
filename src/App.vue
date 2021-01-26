<template>
  <div id="app">
    <carousel>
      <slide
        class="story-carousel__slide"
        v-for="{ id, content } in mocks"
        :key="id"
      >
        {{ content }}
      </slide>
    </carousel>
  </div>
</template>

<script lang="ts">
import { Component, Vue } from "vue-property-decorator";
import Carousel from "./components/Carousel.vue";
import Slide from "./components/Slide.vue";
import mocks from "./mock";

@Component({
  data() {
    return {
      slotsMock: ["Apple", "Orange", "Banana"],
      mocks
    };
  },
  components: {
    Carousel,
    Slide
  }
})
export default class App extends Vue {}
</script>

<style>
body {
  font-family: "Source Sans Pro", "Helvetica Neue", Arial, sans-serif;
  font-size: 1rem;
}
</style>
