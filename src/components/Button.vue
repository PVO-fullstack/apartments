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
  height: 40px;
  background: orange;
  font-size: larger;
  cursor: pointer;
  transition: all 0.5s ease-in-out;

  &:hover {
    background: blue;
  }
}
</style>
