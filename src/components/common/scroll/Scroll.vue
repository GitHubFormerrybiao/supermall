<template>
  <div class="wrapper" ref="wrapper">
    <div class="content">
      <slot></slot>
    </div>
  </div>
</template>

<script>
import BScroll from "better-scroll";
export default {
  name: "Scroll",
  components: {},
  data() {
    return { scroll: null };
  },
  props: {
    probeType: {
      type: Number,
      default: 0,
    },
    pullUpLoad: {
      type: Boolean,
      default: false,
    },
  },
  mounted() {
    this.scroll = new BScroll(this.$refs.wrapper, {
      //   click: true,
      //   probeType: this.probeType,
      //   pullUpLoad: this.pullUpLoad,
    });
  },
};
</script>

<style scoped>
</style>
