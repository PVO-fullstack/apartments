<template>
  <h1>
    {{ text }}
    <slot></slot>
  </h1>
</template>
<script>
export default {
  name: "Title",
  data() {
    return { text: "Число" };
  },
};
</script>
<style lang=""></style>
