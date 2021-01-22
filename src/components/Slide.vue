<template>
  <component :is="tag" ref="vsSlide" class="slide" tabindex="0">
    <slot />
  </component>
</template>

<script lang="ts">
import { Component, Vue } from "vue-property-decorator";

@Component({
  name: "Slide",
  props: {
    tag: {
      type: String,
      default: "li"
    }
  }
})
export default class Slide extends Vue {}
</script>

<style lang="scss">
.slide {
  flex: 0 0 100%;
  height: 100%;
  scroll-snap-align: start;
  border: 1px solid #cecece;
  display: flex;
  justify-content: center;
  align-items: center;
  outline: none;

  &:nth-child(n + 1) {
    background: #2e5c8a;
  }

  &:nth-child(2n + 1) {
    background: #336699;
  }

  @media (min-width: 500px) {
    flex: 0 0 50%;
  }

  @media (min-width: 768px) {
    flex: 0 0 33.33%;
  }

  @media (min-width: 1024px) {
    flex: 0 0 25%;
  }

  @media (min-width: 1280px) and (max-width: 1440px) {
    flex: 0 0 20%;
  }
}
</style>
