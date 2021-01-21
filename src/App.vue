<template>
  <div id="app">
    <carousel>
      <slide v-for="fruit in slotsMock" :key="fruit">
        <h1>{{ fruit }}</h1>
      </slide>
    </carousel>
  </div>
</template>

<script lang="ts">
import { Component, Vue } from "vue-property-decorator";
import Carousel from "./components/Carousel.vue";
import Slide from "./components/Slide.vue";

@Component({
  data() {
    return {
      slotsMock: ["Apple", "Orange", "Banana"]
    };
  },
  components: {
    Carousel,
    Slide
  }
})
export default class App extends Vue {}
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
