<template lang="">
  <button class="btn" :type="type">
    <slot> </slot>
  </button>
</template>
<script>
export default {
  name: "Button",
  props: {
    type: {
      type: String,
      default: "button",
    },
  },
};
</script>
<style lang="scss">
.btn {
  width: 95px;
  height: 45px;
  background: rgb(151, 105, 105);
  font-size: larger;

  &:hover {
    background: blue;
  }
}
</style>
