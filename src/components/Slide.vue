<template>
  <div class="slide">
    <slot></slot>
  </div>
</template>

<script lang="ts">
import { Component, Vue } from "vue-property-decorator";

@Component({
  name: "Slide"
})
export default class Slide extends Vue {}
</script>

<style lang="scss">
.slide {
  min-height: 200px;
  min-width: 400px;
  border: 1px solid #c1c1c1;
  display: flex;
  align-items: center;
  justify-content: center;
}
</style>
