<template>
  <div class="nav-bar">
    <div class="left">
      <slot name="left"></slot>
    </div>
    <div class="center">
      <slot name="center"></slot>
    </div>
    <div class="right">
      <slot name="right"></slot>
    </div>
  </div>
</template>

<script>
export default {
  name: "NavBar",
  components: {},
  data() {
    return {};
  },
};
</script>


<style>
/* 提供插槽给别的组件使用的组件使用统一的有样式比较合适 */
.nav-bar {
  display: flex;
  height: 44px;
  line-height: 44px;
  text-align: center;
}
.left,
.right {
  /* background-color: brown; */
  width: 60px;
}
.center {
  /* background-color: chartreuse; */
  flex: 1;
}
</style>

