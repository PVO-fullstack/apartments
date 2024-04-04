<template>
  <form @click.prevent="handleSubmit">
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
        "Odesa",
        "Dnipro",
        "Poltava",
        "Kharkiv",
        "Mariupol",
        "Kyiv",
        "Kherson",
        "Lviv",
      ];
    },
  },

  methods: {
    handleSubmit() {
      return this.$emit("submit", { city: this.city, price: this.price });
    },
  },
};
</script>
<style lang="scss"></style>
