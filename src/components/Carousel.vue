<template>
  <div class="carousel-holder">
    <!-- Slot for content slides -->
    <component :is="tag" class="carousel">
      <slot />
    </component>

    <!-- Slot for arrows -->
    <slot name="arrows">
      <button
        type="button"
        class="carousel__arrows carousel__arrows--left"
        @click="changeSlide(-1)"
      >
        ←
      </button>

      <button
        class="carousel__arrows carousel__arrows--right"
        @click="changeSlide(1)"
      >
        →
      </button>
    </slot>
  </div>
</template>

<script lang="ts">
import { Component, Vue } from "vue-property-decorator";

@Component({
  name: "Carousel",
  props: {
    /**
     * Custom tag
     */
    tag: {
      type: String,
      default: "ul"
    }
  },
  methods: {
    changeSlide(direction) {
      console.log("SCROLL TO" + direction);
    }
  }
})
export default class Carousel extends Vue {}
</script>

<style lang="scss">
.carousel-holder {
  position: relative;

  .carousel {
    display: flex;
    overflow-x: scroll;
    overflow-y: hidden;
    scroll-snap-type: x mandatory;
    scroll-behavior: smooth;
    scrollbar-width: none;
    -webkit-overflow-scrolling: touch;
    -ms-overflow-style: none;
    list-style: none;
    margin: 0;
    padding: 0;
  }

  .carousel::-webkit-scrollbar {
    display: none;
  }

  .carousel__arrows:disabled {
    cursor: not-allowed;
  }

  .carousel__arrows {
    position: absolute;
    top: 0;
    bottom: 0;
    margin: auto;
    width: 48px;
    height: 48px;
    padding: 0;
    background: transparent;
    border: 1px solid white;
    color: white;
    cursor: pointer;
    outline: none;

    &:hover {
      background-color: #ffffff38;
    }

    &--left {
      left: 0;
    }
    &--right {
      right: 0;
    }
  }
}
</style>
