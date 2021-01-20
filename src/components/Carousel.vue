<template>
  <div class="carousel">
    <slot></slot>
  </div>
</template>

<script lang="ts">
import { Component, Vue } from "vue-property-decorator";

@Component({
  name: "Carousel"
})
export default class Carousel extends Vue {}
</script>

<style lang="scss">
.carousel {
  display: flex;
  align-items: center;
  justify-content: center;
}
</style>
