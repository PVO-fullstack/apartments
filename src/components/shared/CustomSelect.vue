<template>
  <select @input="updateValue" class="custom-select">
    <option
      v-for="item in formatedItems"
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

  setup(props, context) {
    const updateValue = (event) => {
      context.emit("update:modelValue", event.target.value);
    };

    return { updateValue };
  },

  computed: {
    formatedItems() {
      return this.items.map((item) => {
        return typeof item === "object" ? item : { value: item, label: item };
      });
    },
  },
};
</script>
<style lang="scss">
.custom-select {
  min-height: 40px;
  border: 2px solid orange;
  font-size: 18px;
  outline: none;
  padding: 8px 15px;
  cursor: pointer;
  display: inline-block;
}
</style>
