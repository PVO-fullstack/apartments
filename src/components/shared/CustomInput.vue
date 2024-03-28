<template>
  <input :value="modelValue" @input="updateValue" class="custom-input" />
</template>
<script>
export default {
  name: "CustomInput",
  props: {
    modelValue: "",
  },

  setup(props, context) {
    const updateValue = (event) => {
      context.emit("update:modelValue", event.target.value);
    };

    return { updateValue };
  },
};
</script>

<style lang="scss">
.custom-input {
  min-height: 40px;
  border: 2px solid orange;
  font-size: 18px;
  outline: none;
  line-height: inherit;
  padding: 8px 15px;
}
</style>
