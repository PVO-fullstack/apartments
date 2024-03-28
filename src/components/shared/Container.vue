<template>
  <div class="container">
    <slot>Default</slot>
  </div>
</template>
<script>
export default {
  name: "Conteiner",
};
</script>
<style lang="scss">
.container {
  max-width: 1110px;
  margin: 0 auto;
}
</style>
