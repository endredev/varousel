<template>
  <div id="app">
    <carousel
      class="story-carousel story-carousel--colors story-carousel--multiple"
    >
      <slide class="story-carousel__slide">
        <h1>content here</h1>
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
