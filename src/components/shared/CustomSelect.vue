<template>
  <select class="custom-select">
    <option
      v-for="item in items"
      :key="item.value"
      :selected="item.selected"
      :value="item.value"
    >
      {{ item.label }}
    </option>
  </select>
</template>
<script>
export default {
  name: "CustomSelect",
  props: {
    items: {
      type: Array,
      required: true,
    },
  },

  //   setup(props, context) {
  //     const updateValue = (event) => {
  //       context.emit("update:modelValue", event.target.value);
  //     };

  //     return { updateValue };
  //   },
};
</script>
<style lang="scss">
.custom-select {
  height: 40px;
  border: 2px solid orange;
  font-size: 18px;
  outline: none;
  padding: 8px 15px;
  cursor: pointer;
  display: inline-block;
}
</style>
