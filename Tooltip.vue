<template>
  <div class="tooltip" @mouseover="tip = true" @mouseleave="tip = false">
    <div v-if="tip" class="tooltip__item">{{ text }}</div>
    <slot />
  </div>
</template>

<script>
export default {
  props: {
    text: {
      type: String,
      required: true,
    },
  },
  data() {
    return {
      tip: false,
    }
  },
}
</script>

<style lang="scss" scoped>
.tooltip {
  position: relative;
  .tooltip__item {
    position: absolute;
    z-index: 500;
    bottom: -35px;
    background-color: #2d2d2d;
    padding: 6px 10px;
    color: #fff;
    font-size: 12px;
    font-weight: bold;
  }

  .tooltip__item::after {
    content: '';
    display: block;
    position: absolute;
    top: 0px;
    left: 5px;
    z-index: -1;
    background-color: #2d2d2d;
    height: 20px;
    width: 20px;
    transform: rotate(40deg);
  }
}
</style>
