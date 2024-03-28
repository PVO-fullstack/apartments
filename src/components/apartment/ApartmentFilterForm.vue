<template>
  <form @submit.prevent="handleSubmit">
    <CustomSelect v-model="city" :items="cities" />
    <CustomInput placeholder="Price, from" v-model="price" />
    <SubmitButton type="submit">Find</SubmitButton>
  </form>
</template>
<script>
import CustomInput from "../shared/CustomInput.vue";
import CustomSelect from "../shared/CustomSelect.vue";
import SubmitButton from "../Button.vue";

export default {
  components: {
    CustomInput,
    CustomSelect,
    SubmitButton,
  },
  data() {
    return {
      price: "",
      city: "",
    };
  },

  computed: {
    cities() {
      return [
        { label: "city", value: "", selected: true },
        { label: "ftut", value: "yufy" },
        { label: "vuyv", value: "ctyt" },
      ];
    },
  },

  methods: {
    handleSubmit() {
      this.$emit("submit", "submitted");
    },
  },
};
</script>
<style lang="scss"></style>
